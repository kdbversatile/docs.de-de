---
title: Container als Grundlage für die Zusammenarbeit mit DevOps
description: Verstehen der Schlüsselrolle von Containern bei der Optimierung von DevOps.
ms.date: 02/15/2019
ms.openlocfilehash: 37faf00f270414df363f36894317f31f81a2937e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68672767"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a><span data-ttu-id="7a3e6-103">Container als Grundlage für die Zusammenarbeit mit DevOps</span><span class="sxs-lookup"><span data-stu-id="7a3e6-103">Containers as the foundation for DevOps collaboration</span></span>

<span data-ttu-id="7a3e6-104">Aufgrund der Natur von Containern und der Docker-Technologie können Entwickler ihre Software und Abhängigkeiten komfortabel mit dem IT-Betrieb und Produktionsumgebungen teilen und zugleich die typische Entschuldigung „auf meinem Computer funktioniert es“ hinter sich lassen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-104">By the very nature of the containers and Docker technology, developers can share their software and dependencies easily with IT operations and production environments while eliminating the typical "it works on my machine" excuse.</span></span> <span data-ttu-id="7a3e6-105">Containers lösen Anwendungskonflikte zwischen verschiedenen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-105">Containers solve application conflicts between different environments.</span></span> <span data-ttu-id="7a3e6-106">Indirekt bringen Container und Docker Entwickler und IT-Ops näher zusammen, was ihnen die effektive Zusammenarbeit erleichtert.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-106">Indirectly, containers and Docker bring developers and IT operations closer together, making it easier for them to collaborate effectively.</span></span> <span data-ttu-id="7a3e6-107">Die Einführung der Containerworkflow bietet vielen Kunden die DevOps-Kontinuität, die sie angestrebt haben, aber bisher mit weit komplexeren Konfigurationen für Release- und Buildpipelines implementieren mussten.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-107">Adopting the container workflow provides many customers with the DevOps continuity they've sought but previously had to implement via more complex configuration for release and build pipelines.</span></span> <span data-ttu-id="7a3e6-108">Container vereinfachen die Build-/Test-/Bereitstellungspipelines in DevOps.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-108">Containers simplify the build/test/deploy pipelines in DevOps.</span></span>

![Docker unterstützt das Bauen von Brücken zwischen Entwicklern und Architekten in der Entwicklungs-/Entwurfsworkload und dem IT-Betrieb in der Ausführen-/Überwachen-/Verwaltenworkload](./media/image1.png)

<span data-ttu-id="7a3e6-110">**Abbildung 2-1.**</span><span class="sxs-lookup"><span data-stu-id="7a3e6-110">**Figure 2-1.**</span></span> <span data-ttu-id="7a3e6-111">Hauptworkloads nach „Personas“ im Lebenszyklus von in Containern verpackten Docker-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7a3e6-111">Main workloads per "personas" in the life cycle for containerized Docker applications</span></span>

<span data-ttu-id="7a3e6-112">Mit Docker-Containern sind Entwickler im Besitz des gesamten Containerinhalts (Anwendung und Dienst sowie Abhängigkeiten von Frameworks und Komponenten) und der Weise, wie Container und Dienste sich gemeinsam als aus einer Sammlung von Diensten zusammengesetzte Anwendung verhalten.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-112">With Docker containers, developers own what's within the container (application and service, and dependencies to frameworks and components) and how the containers and services behave together as an application composed by a collection of services.</span></span> <span data-ttu-id="7a3e6-113">Die gegenseitigen Abhängigkeiten der mehreren Container sind in einer `docker-compose.yml`-Datei definiert, die man in diesem Sinne als *Bereitstellungsmanifest* bezeichnen könnte.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-113">The interdependencies of the multiple containers are defined in a `docker-compose.yml` file, or what could be called a *deployment manifest*.</span></span> <span data-ttu-id="7a3e6-114">Inzwischen können sich IT-Betriebsteams (IT-Experten und Management) um die Verwaltung von Produktionsumgebungen, Infrastruktur, Skalierbarkeit, Überwachung und schließlich darum kümmern, dass die Leistung der Anwendungen für die Endbenutzer problemlos verfügbar ist, ohne die Inhalte der verschiedenen Container kennen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-114">Meanwhile, IT operations teams (IT professionals and management) can focus on the management of production environments; infrastructure; scalability; monitoring; and, ultimately, ensuring that the applications are delivering properly for the end users, without having to know the contents of the various containers.</span></span> <span data-ttu-id="7a3e6-115">Daher der Name „Container“, die Analogie zu Frachtcontainern aus der realen Welt ist allzu deutlich.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-115">Hence, the name "container," recalling the analogy to real-world shipping containers.</span></span> <span data-ttu-id="7a3e6-116">Daher brauchen sich die Besitzer der Inhalte eines Containers nicht mit der Frage des Containerversands zu befassen, und das Speditionsunternehmen transportiert einen Container von seinem Ursprungsort an seinen Zielort, ohne die Inhalte des Containers zu kennen oder sich dafür zu interessieren.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-116">Thus, the owners of a container's content need not concern themselves with how the container will be shipped, and the shipping company transports a container from its point of origin to its destination without knowing or caring about the contents.</span></span> <span data-ttu-id="7a3e6-117">In ähnlicher Weise können Entwickler die Inhalte in einem Docker-Container erstellen und besitzen, ohne sich ihrerseits mit den Transportmechanismen zu befassen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-117">In a similar manner, developers can create and own the contents within a Docker container without the need to concern themselves with the "transport" mechanisms.</span></span>

<span data-ttu-id="7a3e6-118">In der linken Säule von Abbildung 2–1 erstellen Entwickler Code lokal in Docker-Containern mithilfe von Docker für Windows oder Mac und führen ihn aus.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-118">In the pillar on the left side of Figure 2-1, developers write and run code locally in Docker containers by using Docker for Windows or Mac.</span></span> <span data-ttu-id="7a3e6-119">Sie definieren die Betriebssystemumgebung für den Code mithilfe eines Dockerfiles, das das auszuführende Basisbetriebssystem sowie die Buildschritte zum Erstellen des Codes in einem Docker-Image angibt.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-119">They define the operating environment for the code by using a Dockerfile that specifies the base operating system to run as well as the build steps for building their code into a Docker image.</span></span> <span data-ttu-id="7a3e6-120">Die Entwickler definieren, wie die Zusammenarbeit eines oder mehrerer Images erfolgt, und verwenden dazu das bereits erwähnte `docker-compose.yml`-Bereitstellungsmanifest.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-120">The developers define how one or more images will interoperate using the aforementioned `docker-compose.yml` file deployment manifest.</span></span> <span data-ttu-id="7a3e6-121">Mit dem Abschluss der lokalen Entwicklung laden sie den Anwendungscode und die Docker-Konfigurationsdateien in das Coderepository ihrer Wahl (d.h. das Git-Repository) hoch.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-121">As they complete their local development, they push their application code plus the Docker configuration files to the code repository of their choice (that is, Git repository).</span></span>

<span data-ttu-id="7a3e6-122">Die DevOps-Säule definiert die Continuous Integration-Erstellungspipelines (CI) unter Verwendung des im Coderepository bereitgestellten Dockerfiles.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-122">The DevOps pillar defines the build–Continuous Integration (CI) pipelines using the Dockerfile provided in the code repository.</span></span> <span data-ttu-id="7a3e6-123">Das CI-System ruft die Container-Basisimages aus der gewählten Docker-Registrierung ab und erstellt die benutzerdefinierten Docker-Images für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-123">The CI system pulls the base container images from the selected Docker registry and builds the custom Docker images for the application.</span></span> <span data-ttu-id="7a3e6-124">Die Images werden anschließend überprüft und in die Docker-Registrierung übertragen, die für die Bereitstellung in mehreren Umgebungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-124">The images then are validated and pushed to the Docker registry used for the deployments to multiple environments.</span></span>

<span data-ttu-id="7a3e6-125">In der rechten Säule verwalten Betriebsteams Anwendungen und Infrastruktur in der Produktion, während sie Umgebung und Anwendungen überwachen, sodass sie dem Entwicklungsteam Feedback und Erkenntnisse über mögliche Verbesserungen der Anwendung geben können.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-125">In the pillar on the right, operations teams manage deployed applications and infrastructure in production while monitoring the environment and applications so that they can provide feedback and insights to the development team about how the application might be improved.</span></span> <span data-ttu-id="7a3e6-126">Container-Apps werden normalerweise in der Produktion mithilfe von Containerorchestratoren ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-126">Container apps are typically run in production using container orchestrators.</span></span>

<span data-ttu-id="7a3e6-127">Die beiden Teams arbeiten mithilfe einer Grundplattform (Docker-Container) zusammen, die eine Separation of Concerns als Vertrag zur Verfügung stellt, während sie die Zusammenarbeit der beiden Teams im Anwendungslebenszyklus erheblich verbessert.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-127">The two teams are collaborating through a foundational platform (Docker containers) that provides a separation of concerns as a contract, while greatly improving the two teams' collaboration in the application life cycle.</span></span> <span data-ttu-id="7a3e6-128">Die Entwickler besitzen die Inhalte der Container, ihre Betriebsumgebung und die Abhängigkeiten zwischen Containern, während die Betriebsteams die erstellten Inhalte zusammen mit dem Manifest an sich nehmen und sie in ihrem Orchestrierungssystem ausführen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-128">The developers own the container contents, its operating environment, and the container interdependencies, whereas the operations teams take the built images along with the manifest and runs them in their orchestration system.</span></span>

## <a name="challenges-in-application-life-cycle-when-using-docker"></a><span data-ttu-id="7a3e6-129">Herausforderungen im Lebenszyklus von Anwendungen beim Einsatz von Docker.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-129">Challenges in application life cycle when using Docker.</span></span>

<span data-ttu-id="7a3e6-130">Es gibt viele Gründe, warum die Anzahl der containerisierten Anwendungen in den kommenden Jahren steigen wird, und einer dieser Gründe ist die Erstellung von Anwendungen, die auf Microservices basieren.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-130">There are many reasons that will increase the number of containerized applications in the upcoming years, and one of these reasons is the creation of applications based on microservices.</span></span>

<span data-ttu-id="7a3e6-131">Während der letzten 15 Jahre war die Nutzung von Webdiensten die Grundlage von Tausenden von Anwendungen, und wahrscheinlich werden wir in einigen Jahren die gleiche Situation im Hinblick auf Microservice-basierten Anwendungen vorfinden, die in Docker-Containern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-131">During the last 15 years, the use of web services has been the base of thousands of applications, and probably, after a few years, we'll find the same situation with microservice-based applications running on Docker containers.</span></span>

<span data-ttu-id="7a3e6-132">Es ist darüber hinaus erwähnenswert, dass Sie Docker-Container auch für monolithische Anwendungen verwenden und trotzdem den größten Teil der Vorteile von Docker nutzen können.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-132">It is also worth to mention that you can also use Docker containers for monolithic applications and you still get most of the benefits of Docker.</span></span> <span data-ttu-id="7a3e6-133">Container richten sich nicht nur auf Microservices.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-133">Containers are not targeting only microservices.</span></span>

<span data-ttu-id="7a3e6-134">Die Verwendung von Containerisierung mit Docker und Microservices hat zu neuen Herausforderungen im Entwicklungsprozess Ihrer Organisationen geführt und daher benötigen Sie eine solide Strategie zum Verwalten vieler Container und Microservices, die auf Produktionssystemen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-134">The use of Docker containerization and microservices causes new challenges in the development process of your organizations and therefore, you need a solid strategy to maintain many containers and microservices running on production systems.</span></span> <span data-ttu-id="7a3e6-135">Schließlich können beim Unternehmenseinsatz Hunderte oder Tausende von Containern/Instanzen in der Produktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-135">Eventually, enterprise applications will have hundreds or thousands of containers/instances running in production.</span></span>

<span data-ttu-id="7a3e6-136">Durch diese Herausforderungen entstehen neue Anforderungen für den Einsatz von DevOps-Tools, sodass Sie in Ihren DevOps-Aktivitäten neue Prozesse definieren und Antworten auf diese Art von Fragen finden müssen:</span><span class="sxs-lookup"><span data-stu-id="7a3e6-136">These challenges create new demands when using DevOps tools, so you'll have to define new processes in your DevOps activities, and find answers for this type of questions:</span></span>

- <span data-ttu-id="7a3e6-137">Welche Tools kann ich für die Entwicklung, für CI/CD, Management und Betrieb verwenden?</span><span class="sxs-lookup"><span data-stu-id="7a3e6-137">Which tools can I use for development, for CI/CD, management and operations?</span></span>

- <span data-ttu-id="7a3e6-138">Wie kann mein Unternehmen mit Fehlern in Containern umgehen, die in der Produktion eingesetzt werden?</span><span class="sxs-lookup"><span data-stu-id="7a3e6-138">How can my company manage errors in containers when running in production?</span></span>

- <span data-ttu-id="7a3e6-139">Wie können wir Teile unserer Software in der Produktion mit minimalen Ausfallzeiten ändern?</span><span class="sxs-lookup"><span data-stu-id="7a3e6-139">How can we change pieces of our software in production with minimum downtime?</span></span>

- <span data-ttu-id="7a3e6-140">Wie können wir skalieren, und wie können wir unser Produktionssystem überwachen?</span><span class="sxs-lookup"><span data-stu-id="7a3e6-140">How can we scale and how can we monitor our production system?</span></span>

- <span data-ttu-id="7a3e6-141">Wie können wir Test und Bereitstellung von Containern in unsere Releasepipeline einbeziehen?</span><span class="sxs-lookup"><span data-stu-id="7a3e6-141">How can we include testing and deployment of containers in our release pipeline?</span></span>

- <span data-ttu-id="7a3e6-142">Wie können wir Open Source-Tools/-Plattformen für Container in Microsoft Azure verwenden?</span><span class="sxs-lookup"><span data-stu-id="7a3e6-142">How can we use Open Source tools/platforms for containers in Microsoft Azure?</span></span>

<span data-ttu-id="7a3e6-143">Wenn Sie alle diese Fragen beantworten, sind Sie besser darauf vorbereitet, Ihre Anwendungen (vorhandene oder neue) in Docker-Container zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-143">If you can answer all those questions, you'll be better prepared to move your applications (existing or new apps) to Docker containers.</span></span> 

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a><span data-ttu-id="7a3e6-144">Einführung in eine allgemeine Anwendungslebenszyklus-Workflow mit Docker</span><span class="sxs-lookup"><span data-stu-id="7a3e6-144">Introduction to a generic end-to-end Docker application life cycle workflow</span></span>

<span data-ttu-id="7a3e6-145">Abbildung 2–2 stellt einen detaillierteren Workflow für einen Docker-Anwendungslebenszyklus dar, in dieser Instanz mit dem Schwerpunkt auf bestimmten DevOps-Aktivitäten und -Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-145">Figure 2-2 presents a more detailed workflow for a Docker application life cycle, focusing in this instance on specific DevOps activities and assets.</span></span>

![Dieses Diagramm zeigt die „äußere Schleife“ von DevOps.](./media/image2.png)

<span data-ttu-id="7a3e6-149">**Abbildung 2–2.**</span><span class="sxs-lookup"><span data-stu-id="7a3e6-149">**Figure 2-2.**</span></span> <span data-ttu-id="7a3e6-150">Allgemeiner Workflow für den Lebenszyklus von in Containern verpackten Docker-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7a3e6-150">High-level workflow for the Docker containerized application life cycle</span></span>

<span data-ttu-id="7a3e6-151">Alles beginnt mit dem Entwickler, der in der Workflow der inneren Schleife mit dem Schreiben von Code beginnt.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-151">Everything begins with the developer, who starts writing code in the inner-loop workflow.</span></span> <span data-ttu-id="7a3e6-152">In der Phase der inneren Schleife definieren Entwickler alles, was geschieht, bevor sie den Code in das Coderepository übertragen (beispielsweise ein Quellcodeverwaltungssystem wie Git).</span><span class="sxs-lookup"><span data-stu-id="7a3e6-152">The inner-loop stage is where developers define everything that happens before pushing code into the code repository (for example, a source control system such as Git).</span></span> <span data-ttu-id="7a3e6-153">Nach dem Commit löst das Repository Continuous Integration (CI) und den Rest der Workflow aus.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-153">After it's committed, the repository triggers Continuous Integration (CI) and the rest of the workflow.</span></span>

<span data-ttu-id="7a3e6-154">Die innere Schleife besteht im Grunde genommen aus typischen Schritten wie „Codeerstellung“, „Ausführen“, „Testen“ und Debuggen, zuzüglich der zusätzlichen Schritte, die vor der lokalen Ausführung der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-154">The inner loop basically consists of typical steps like "code," "run," "test," and "debug," plus the additional steps needed right before running the app locally.</span></span> <span data-ttu-id="7a3e6-155">Dies ist der Prozess des Entwicklers zum Ausführen und Testen der App als Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-155">This is the developer's process to run and test the app as a Docker container.</span></span> <span data-ttu-id="7a3e6-156">Die Workflow der inneren Schleife wird in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-156">The inner-loop workflow will be explained in the sections that follow.</span></span>

<span data-ttu-id="7a3e6-157">Wenn wir einen Schritt zurücktreten, um die Workflow im Ganzen zu betrachten, erweist sich die DevOps-Workflow als mehr als eine Technologie oder ein Toolset: Es ist eine Geisteshaltung, für die eine kulturelle Weiterentwicklung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-157">Taking a step back to look at the end-to end workflow, the DevOps workflow is more than a technology or a tool set: it's a mindset that requires cultural evolution.</span></span> <span data-ttu-id="7a3e6-158">Es geht um Personen, Prozesse und die geeigneten Tools, um Ihren Anwendungslebenszyklus schneller und besser vorhersagbar zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-158">It's people, processes, and the appropriate tools to make your application life cycle faster and more predictable.</span></span> <span data-ttu-id="7a3e6-159">Unternehmen, die einen Workflow mit Containern einführen, führen normalerweise eine Umstrukturierung ihrer Organisationen durch, um Personen und Prozesse an die Workflow mit Containern anzupassen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-159">Enterprises that adopt a containerized workflow typically restructure their organizations to represent people and processes that match the containerized workflow.</span></span>

<span data-ttu-id="7a3e6-160">Das Praktizieren von DevOps kann Teams helfen, gemeinsam schneller auf Wettbewerbsdruck zu reagieren, indem sie fehleranfällige manuelle Prozesse durch Automatisierung ersetzen, wodurch sich verbesserte Nachverfolgbarkeit und wiederholbare Workflows ergeben.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-160">Practicing DevOps can help teams respond faster together to competitive pressures by replacing error-prone manual processes with automation, which results in improved traceability and repeatable workflows.</span></span> <span data-ttu-id="7a3e6-161">Organisationen können darüber hinaus mit einer Kombination aus lokalen und Cloudressourcen sowie eng integrierten Tools Umgebungen effizienter verwalten und Kosteneinsparungen realisieren.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-161">Organizations also can manage environments more efficiently and realize cost savings with a combination of on-premises and cloud resources as well as tightly integrated tooling.</span></span>

<span data-ttu-id="7a3e6-162">Beim Implementieren Ihrer DevOps-Workflow für Docker-Anwendungen werden Sie feststellen, dass Docker-Technologien in nahezu jeder Phase der Workflow präsent sind, beginnend mit Ihrer Entwicklungsbox bei der Arbeit in der inneren Schleife (Codeerstellung, Ausführen, Debuggen), der Build-Test-CI-Phase und schließlich der Bereitstellung der Container in den Staging- und Produktionsumgebungen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-162">When implementing your DevOps workflow for Docker applications, you'll see that Docker technologies are present in almost every stage of the workflow, from your development box while working in the inner loop (code, run, debug), the build-test-CI phase, and, finally, the deployment of those containers to the staging and production environments.</span></span>

<span data-ttu-id="7a3e6-163">Die Verbesserung der Qualitätspraktiken hilft, Fehler frühzeitig im Entwicklungszyklus zu erkennen, wodurch sich die Kosten zu ihrer Behebung verringern.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-163">Improvement of quality practices helps to identify defects early in the development cycle, which reduces the cost of fixing them.</span></span> <span data-ttu-id="7a3e6-164">Durch Einschließen von Umgebung und Abhängigkeiten in das Image und die Einführung einer Philosophie, das gleiche Image übergreifend in mehreren Umgebungen einzusetzen, fördern Sie einen Habitus, die umgebungsspezifischen Konfigurationen zu extrahieren, wodurch Bereitstellungen an Zuverlässigkeit gewinnen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-164">By including the environment and dependencies in the image and adopting a philosophy of deploying the same image across multiple environments, you promote a discipline of extracting the environment-specific configurations making deployments more reliable.</span></span>

<span data-ttu-id="7a3e6-165">Aussagekräftige Daten, die durch effektive Instrumentierung (Überwachung und Diagnose) erhalten werden, bieten Einsicht in Leistungsprobleme und Benutzerverhalten, um die Richtung zukünftiger Prioritäten und Investitionen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-165">Rich data obtained through effective instrumentation (monitoring and diagnostics) provides insight into performance issues and user behavior to guide future priorities and investments.</span></span>

<span data-ttu-id="7a3e6-166">DevOps sollte als ein Weg angesehen werden, nicht als ein Zielort.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-166">DevOps should be considered a journey, not a destination.</span></span> <span data-ttu-id="7a3e6-167">Es sollte inkrementell durch Projekte mit passendem Umfang implementiert werden, die Ihnen Erfolge, Erkenntnisse und Weiterentwicklung erbringen.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-167">It should be implemented incrementally through appropriately scoped projects from which you can demonstrate success, learn, and evolve.</span></span>

## <a name="benefits-of-devops-for-containerized-applications"></a><span data-ttu-id="7a3e6-168">Vorteile von DevOps für Anwendungen in Containern</span><span class="sxs-lookup"><span data-stu-id="7a3e6-168">Benefits of DevOps for containerized applications</span></span>

<span data-ttu-id="7a3e6-169">Dies sind einige der wichtigsten Vorteile, die sich durch eine solide DevOps-Workflow ergeben:</span><span class="sxs-lookup"><span data-stu-id="7a3e6-169">Here are some of the most important benefits provided by a solid DevOps workflow:</span></span>

- <span data-ttu-id="7a3e6-170">Schnelleres Ausliefern besserer Software mit besserer Compliance</span><span class="sxs-lookup"><span data-stu-id="7a3e6-170">Deliver better-quality software, faster and with better compliance.</span></span>

- <span data-ttu-id="7a3e6-171">Frühzeitige und ökonomisch sinnvollere Förderung von fortlaufenden Verbesserungen und Anpassungen</span><span class="sxs-lookup"><span data-stu-id="7a3e6-171">Drive continuous improvement and adjustments earlier and more economically.</span></span>

- <span data-ttu-id="7a3e6-172">Bessere Transparenz und Zusammenarbeit von Projektbeteiligten, die an Herstellung und Betrieb von Software beteiligt sind</span><span class="sxs-lookup"><span data-stu-id="7a3e6-172">Increase transparency and collaboration among stakeholders involved in delivering and operating software.</span></span>

- <span data-ttu-id="7a3e6-173">Kostenkontrolle und effektiverer Einsatz der bereitgestellten Ressourcen bei gleichzeitiger Minimierung von Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-173">Control costs and utilize provisioned resources more effectively while minimizing security risks.</span></span>

- <span data-ttu-id="7a3e6-174">Plug-and-Play-Bereitschaft mit vielen Ihrer bereits getätigten DevOps-Investitionen, einschließlich Investitionen in Open-Source.</span><span class="sxs-lookup"><span data-stu-id="7a3e6-174">Plug and play well with many of your existing DevOps investments, including investments in open-source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7a3e6-175">[Zurück](index.md)
>[Weiter](../Microsoft-platform-tools-containerized-apps/index.md)</span><span class="sxs-lookup"><span data-stu-id="7a3e6-175">[Previous](index.md)
[Next](../Microsoft-platform-tools-containerized-apps/index.md)</span></span>