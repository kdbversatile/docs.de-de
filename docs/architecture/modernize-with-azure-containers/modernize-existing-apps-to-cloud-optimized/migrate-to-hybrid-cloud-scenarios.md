---
title: Migrieren zu Hybridcloudszenarios
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migration zu Hybrid Cloud Szenarios
ms.date: 04/30/2018
ms.openlocfilehash: 04c618681c61f5584e641e0a4735e1261ab34fa3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578213"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="80c54-103">Migrieren zu Hybridcloudszenarios</span><span class="sxs-lookup"><span data-stu-id="80c54-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="80c54-104">Einige Organisationen und Unternehmen können einige Ihrer Anwendungen aufgrund von Bestimmungen oder ihrer eigenen Richtlinien nicht in öffentliche Clouds wie Microsoft Azure oder andere Public Cloud migrieren.</span><span class="sxs-lookup"><span data-stu-id="80c54-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="80c54-105">Es ist jedoch wahrscheinlich, dass alle Organisationen davon profitieren können, dass einige Ihrer Anwendungen in der Public Cloud und anderen Anwendungen lokal vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="80c54-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="80c54-106">Eine gemischte Umgebung kann jedoch aufgrund verschiedener Plattformen und Technologien, die in öffentlichen Clouds und lokalen Umgebungen verwendet werden, zu einer übermäßigen Komplexität in Umgebungen führen.</span><span class="sxs-lookup"><span data-stu-id="80c54-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="80c54-107">Microsoft bietet die beste Hybrid Cloud Lösung, bei der Sie Ihre vorhandenen Ressourcen lokal und im Public Cloud optimieren können, während Sie die Konsistenz in einem Azure-Hybrid Cloud gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="80c54-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="80c54-108">Dank Azure Stack (lokal) und Azure (Public Cloud) können Sie vorhandene Fähigkeiten maximieren und einen flexiblen, einheitlichen Ansatz zum Entwickeln von Apps nutzen, die in der Cloud oder lokal ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="80c54-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="80c54-109">Wenn es um die Sicherheit geht, können Sie die Verwaltung und Sicherheit über ihre Hybrid Cloud hinweg zentralisieren.</span><span class="sxs-lookup"><span data-stu-id="80c54-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="80c54-110">Durch Bereitstellen von einmaligem Anmelden für lokale und Cloud-Apps können Sie die Kontrolle über alle Assets von Ihrem Rechenzentrum in die Cloud erhalten.</span><span class="sxs-lookup"><span data-stu-id="80c54-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="80c54-111">Dies erreichen Sie, indem Sie Active Directory auf eine Hybrid Cloud erweitern und die Identitätsverwaltung verwenden.</span><span class="sxs-lookup"><span data-stu-id="80c54-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="80c54-112">Schließlich können Sie Daten nahtlos verteilen und analysieren, die gleichen Abfrage Sprachen für Cloud-und lokale Ressourcen verwenden und Analysen und Deep Learning in Azure anwenden, um Ihre Daten unabhängig von ihrer Quelle zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="80c54-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="80c54-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="80c54-113">Azure Stack</span></span>

<span data-ttu-id="80c54-114">Azure Stack ist eine Hybrid Cloud Plattform, mit der Sie Azure-Dienste aus dem Rechenzentrum Ihrer Organisation bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="80c54-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="80c54-115">Azure Stack ist für die Unterstützung neuer Optionen für ihre modernen Anwendungen in wichtigen Szenarien konzipiert, z. b. bei Edge-und nicht verbundenen Umgebungen oder bei der Erfüllung spezifischer Sicherheits-und Konformitätsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="80c54-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="80c54-116">Abbildung 4-13 zeigt eine Übersicht über die echte Hybrid Cloud Plattform, die Microsoft bietet.</span><span class="sxs-lookup"><span data-stu-id="80c54-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure](./media/image13.jpg)

> <span data-ttu-id="80c54-118">**Abbildung 4-13.**</span><span class="sxs-lookup"><span data-stu-id="80c54-118">**Figure 4-13.**</span></span> <span data-ttu-id="80c54-119">Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure</span><span class="sxs-lookup"><span data-stu-id="80c54-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="80c54-120">Azure Stack wird in zwei Bereitstellungs Optionen angeboten, die Ihren Anforderungen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="80c54-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="80c54-121">Azure Stack integrierter Systeme</span><span class="sxs-lookup"><span data-stu-id="80c54-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="80c54-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="80c54-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="80c54-123">Azure Stack integrierter Systeme</span><span class="sxs-lookup"><span data-stu-id="80c54-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="80c54-124">Azure Stack integrierte Systeme werden über eine Partnerschaft von Microsoft und Hardwarepartnern angeboten.</span><span class="sxs-lookup"><span data-stu-id="80c54-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="80c54-125">Mit der Partnerschaft wird eine Lösung erstellt, die Innovationen in der Cloud bietet, die mit der Einfachheit der Verwaltung ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="80c54-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="80c54-126">Da Azure Stack als integriertes System von Hardware und Software angeboten wird, erhalten Sie die richtige Flexibilität und Kontrolle, während Sie trotzdem Innovationen aus der Cloud einführen.</span><span class="sxs-lookup"><span data-stu-id="80c54-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="80c54-127">Azure Stack integrierte Systeme reichen von 4 bis 12 Knoten und werden vom Hardwarepartner und von Microsoft gemeinsam unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80c54-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="80c54-128">Verwenden Sie Azure Stack integrierte Systeme, um neue Szenarien für Ihre produktionsworkloads zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="80c54-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="80c54-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="80c54-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="80c54-130">Microsoft Azure Stack Development Kit ist eine Bereitstellung von Azure Stack mit einem einzelnen Knoten, die Sie zum Auswerten und Kennenlernen von Azure Stack verwenden können.</span><span class="sxs-lookup"><span data-stu-id="80c54-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="80c54-131">Sie können auch Azure Stack Development Kit als Entwicklerumgebung verwenden, in der Sie mithilfe von APIs und Tools entwickeln können, die mit Azure konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="80c54-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="80c54-132">Azure Stack Development Kit ist nicht für die Verwendung als Produktionsumgebung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="80c54-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="80c54-133">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="80c54-133">Additional resources</span></span>

- <span data-ttu-id="80c54-134">**Azure-Hybrid Cloud**</span><span class="sxs-lookup"><span data-stu-id="80c54-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="80c54-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="80c54-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="80c54-136">**Active Directory-Dienst Konten für Windows-Container**</span><span class="sxs-lookup"><span data-stu-id="80c54-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="80c54-137">**Erstellen eines Containers mit Active Directory-Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="80c54-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="80c54-138">**Azure-Hybridvorteil Lizenzierung**</span><span class="sxs-lookup"><span data-stu-id="80c54-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="80c54-139">[Zurück](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="80c54-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>