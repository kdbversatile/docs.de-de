---
title: Einsatz von verallgemeinerten additiven Modellen und shape-Funktionen zur Modellerklärung in ML.NET
description: Einsatz von verallgemeinerten additiven Modellen und shape-Funktionen zur Modellerklärung in ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 489aee34d0404293bc080b934636c01bdab92fe9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156628"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="1cc57-103">Einsatz von verallgemeinerten additiven Modellen und shape-Funktionen zur Modellerklärung in ML.NET</span><span class="sxs-lookup"><span data-stu-id="1cc57-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

<span data-ttu-id="1cc57-104">Bei der Erstellung von Machine Learning-Modellen reicht es oft nicht aus, nur Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="1cc57-104">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="1cc57-105">Häufig müssen Machine Learning- Entwickler, Entscheidungsträger und von den Modellen betroffene Personen erst verstehen, wie Machine Learning-Modelle Entscheidungen treffen und welche Features zu ihrer Leistung beitragen.</span><span class="sxs-lookup"><span data-stu-id="1cc57-105">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="1cc57-106">**Verallgemeinerte additive Modelle (Generalized Additive Models, GAMs)** werden intern bei Microsoft zur Modellerklärung verwendet, um Entwickler von Machine Learning-Prozessen bei der Erstellung leistungsstarker Modelle zu unterstützen, die von anderen leicht interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1cc57-106">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="1cc57-107">GAMs sind eine Klasse von **interpretierbaren Modellen**. Dabei handelt es sich um lineare Modelle, bei denen die Benennungen nichtlineare Funktionen sind, die als „shape-Funktionen“ einer einzelnen Variablen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1cc57-107">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="1cc57-108">Als lineare Modelle sind sie leicht zu interpretieren, aber da die Modelle Funktionen von Features anstelle einer einzelnen Gewichtung lernen, können sie komplexere Beziehungen modellieren als ein einfaches lineares Modell.</span><span class="sxs-lookup"><span data-stu-id="1cc57-108">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="1cc57-109">Der resultierende GAM-Vorhersagedienst hat einen Intercept-Term, der die durchschnittliche Vorhersage über den Trainingssatz darstellt, und shape-Funktionen, die die Abweichung von der durchschnittlichen Vorhersage darstellen.</span><span class="sxs-lookup"><span data-stu-id="1cc57-109">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="1cc57-110">Die shape-Funktionen können visuell überprüft werden, um die Reaktion des Modells auf verschiedene Werte eines Features zu analysieren, und wie im folgenden Graph visualisiert werden, der am Ende des Codebeispiels erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1cc57-110">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="1cc57-111">Der GAM-Trainer in ML.NET wird mithilfe einer flachen, verstärkten Verlaufsstruktur (z.B. Strukturstümpfen) implementiert, um nicht parametrische shape-Funktionen zu erlernen, und basiert auf der in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) von Lou, Caruana und Gehrke beschriebenen Methode.</span><span class="sxs-lookup"><span data-stu-id="1cc57-111">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

```csharp
// Train the Generalized Additive Model
var gamTrainer = mlContext.Regression.Trainers.GeneralizedAdditiveModels()
var gamModel = gamTrainer.Fit(data);
 
// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Get the index of a variable from the training data
var myFeatureIndex = featureNames.ToList().FindIndex(str => str.Equals("MyFeature"));
 
// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetFeatureBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetFeatureWeights(myFeatureIndex);
 
// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
  Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
```

![Graph für shape-Funktion eines verallgemeinerten additiven Modelles](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

<span data-ttu-id="1cc57-113">Ein Beispiel zum Trainieren eines GAM-Modells und zur Überprüfung und Interpretation der Ergebnisse finden Sie im [dotnet/machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span><span class="sxs-lookup"><span data-stu-id="1cc57-113">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>