---
title: Richtlinien für das Entwerfen von Containern
description: Lernen Sie ein grundlegendes Prinzip guten Containerdesigns kennen – nämlich dass ein Container nur einen Prozess beherbergen sollte.
ms.date: 02/15/2019
ms.openlocfilehash: 69f3ff6c9303f0c4082695d861a8c90031295b6a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68672497"
---
# <a name="common-container-design-principles"></a><span data-ttu-id="59e44-103">Richtlinien für das Entwerfen von Containern</span><span class="sxs-lookup"><span data-stu-id="59e44-103">Common container design principles</span></span>

<span data-ttu-id="59e44-104">Vor dem Einstieg in den Entwicklungsprozess sind ein paar grundlegende Konzepte erwähnenswert, die die Art betreffen, wie Sie Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="59e44-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="59e44-105">Ein Container entspricht einem Prozess</span><span class="sxs-lookup"><span data-stu-id="59e44-105">Container equals a process</span></span>

<span data-ttu-id="59e44-106">Im Containermodell stellt ein Container einen einzelnen Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="59e44-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="59e44-107">Durch Definieren eines Containers als Prozessgrenze beginnen Sie, die Primitive zu erstellen, die zum Skalieren von Prozessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59e44-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="59e44-108">Wenn Sie einen Docker-Container ausführen, sehen Sie eine [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint)-Definition.</span><span class="sxs-lookup"><span data-stu-id="59e44-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="59e44-109">Diese definiert den Prozess und die Lebensdauer des Containers.</span><span class="sxs-lookup"><span data-stu-id="59e44-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="59e44-110">Wenn der Prozess abgeschlossen ist, endet der Lebenszyklus des Containers.</span><span class="sxs-lookup"><span data-stu-id="59e44-110">When the process completes, the container life-cycle ends.</span></span> <span data-ttu-id="59e44-111">Es gibt Prozesse mit langer Ausführungsdauer, wie etwa Webserver, und kurzlebige Prozesse, wie etwa Batchaufträge, die beispielsweise als Microsoft Azure-[WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/) implementiert worden sein können.</span><span class="sxs-lookup"><span data-stu-id="59e44-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="59e44-112">Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz.</span><span class="sxs-lookup"><span data-stu-id="59e44-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="59e44-113">Wenn der Orchestrator dazu angewiesen wurde, fünf Instanzen auszuführen und eine davon fehlschlägt, erstellt der Orchestrator einen weiteren Container, um den fehlgeschlagenen Prozess zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="59e44-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="59e44-114">In einem Batchauftrag wird der Prozess mit Parametern gestartet.</span><span class="sxs-lookup"><span data-stu-id="59e44-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="59e44-115">Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="59e44-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="59e44-116">Es gibt Szenarien, in denen mehrere Prozesse in einem einzigen Container ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="59e44-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="59e44-117">In einem Architekturdokument gibt es kein „niemals“, und ebenso wenig bedeutet „immer“ wirklich immer.</span><span class="sxs-lookup"><span data-stu-id="59e44-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="59e44-118">Für Szenarien, die mehrere Prozesse erfordern, besteht ein gängiger Ansatz im Einsatz eines [Supervisors](http://supervisord.org/).</span><span class="sxs-lookup"><span data-stu-id="59e44-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="59e44-119">[Zurück](design-docker-applications.md)
>[Weiter](monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="59e44-119">[Previous](design-docker-applications.md)
[Next](monolithic-applications.md)</span></span>