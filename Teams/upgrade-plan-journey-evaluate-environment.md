---
title: Microsoft Teams-Upgrade | Umgebungs Bewertung, Ermittlungs Fragen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Verwenden Sie diese Anleitung, um sich über die Anforderungen für eine ordnungsgemäße Bewertung Ihrer aktuellen Umgebung für ein Upgrade auf Teams zu informieren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158743"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="06bc6-103">Auswerten Ihrer Umgebung vor dem Upgrade auf Teams</span><span class="sxs-lookup"><span data-stu-id="06bc6-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="06bc6-104">![Diagramm Upgrade-Strategie, mit Betonung der Phase „Technische Bereitschaft“](media/upgrade-banner-tech-readiness.png "Etappen der Upgrade-Tour mit Schwerpunkt auf der Phase „Technische Bereitschaft“")</span><span class="sxs-lookup"><span data-stu-id="06bc6-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="06bc6-105">Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="06bc6-106">Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="06bc6-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="06bc6-107">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="06bc6-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="06bc6-108">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="06bc6-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="06bc6-109">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06bc6-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="06bc6-110">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="06bc6-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="06bc6-111">In diesem Artikel finden Sie eine Übersicht über die Anforderungen für die ordnungsgemäße Auswertung Ihrer aktuellen Umgebung für das Funktionieren von Teams.</span><span class="sxs-lookup"><span data-stu-id="06bc6-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="06bc6-112">Durch Auswertung Ihrer Umgebung ermitteln Sie Risiken und Anforderungen, die sich auf die gesamte Bereitstellung auswirken.</span><span class="sxs-lookup"><span data-stu-id="06bc6-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="06bc6-113">Wenn Sie diese Elemente vorher identifizieren, können Sie Ihre Planung anpassen, um den Erfolg zu steigern.</span><span class="sxs-lookup"><span data-stu-id="06bc6-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="06bc6-114">Einführung in den Such Fragebogen</span><span class="sxs-lookup"><span data-stu-id="06bc6-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="06bc6-115">Um Ihre objektiven Hauptergebnisse (OKRs) zu erreichen, haben Sie zuvor wichtige Dienst Entscheidungen getroffen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="06bc6-116">Der nächste Schritt besteht darin, eine Umgebungs Ermittlung durchzuführen, um alle Aspekte in Bezug auf Ihre IT-Infrastruktur, Netzwerke und Vorgänge zu bewerten, um zu bestätigen, dass Ihre Organisation zur Implementierung der Lösung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="06bc6-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="06bc6-117">Die Ermittlung ist einer der ersten wichtigen Schritte, die Sie bei der Planung Ihrer Reise zu Teams Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="06bc6-118">Umgebungs Ermittlung muss eine Netzwerk Readiness-Bewertung umfassen, um sicherzustellen, dass Ihr Netzwerk das Upgrade auf Teams unterstützenkann.</span><span class="sxs-lookup"><span data-stu-id="06bc6-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="06bc6-119">Sie führen eine detaillierte Ermittlung Ihrer Umgebung durch, um den aktuellen Zustand besser zu verstehen und etwaige Schwierigkeiten oder – noch wichtiger – mögliche Blockierungen für die Ausführung Ihres Teams-Rollouts zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="06bc6-120">Sie erkennen technische Risiken als Teil einer Evaluierung der Umweltverträglichkeitsprüfung und Akzeptanz Bereitschaft an und entwickeln einen Minderungsplan für jedes erkannte Risiko.</span><span class="sxs-lookup"><span data-stu-id="06bc6-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="06bc6-121">Sie sollten diese Informationen in das risikoregister aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="06bc6-122">Alle Fragen im Zusammenhang mit Ihrer vorhandenen Infrastruktur für die Zusammenarbeit und der Microsoft 365-oder Office 365-Organisation,-Netzwerke,-Endpunkte,-Vorgänge sowie-Einführung und-Bereitschaft sind Teil des Fragebogens zur Umwelt Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="06bc6-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="06bc6-123">Arbeiten Sie mit Ihrem Projektteam zusammen, um die gewünschten Informationen so detailliert wie möglich zur Verfügung zu stellen, um Ihre Planungsaktivitäten zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="06bc6-124">[Der Fragebogen](upgrade-plan-journey-discovery-questionnaire.md) ist in die folgenden Abschnitte unterteilt, um die Bereitstellung Ihrer Organisation für Ihre Teams in verschiedenen Hauptbereichen zu bestätigen:</span><span class="sxs-lookup"><span data-stu-id="06bc6-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="06bc6-125">Informationen zu Microsoft 365 oder Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="06bc6-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="06bc6-126">Zusammenfassung der vorhandenen Zusammenarbeitsplattform</span><span class="sxs-lookup"><span data-stu-id="06bc6-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="06bc6-127">Bereitstellungsdetails für die Zusammenarbeitsplattform</span><span class="sxs-lookup"><span data-stu-id="06bc6-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="06bc6-128">Netzwerk und Zugriff auf Microsoft 365-oder Office 365-Dienste</span><span class="sxs-lookup"><span data-stu-id="06bc6-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="06bc6-129">Endpunkte</span><span class="sxs-lookup"><span data-stu-id="06bc6-129">Endpoints</span></span>
- <span data-ttu-id="06bc6-130">Vorgänge</span><span class="sxs-lookup"><span data-stu-id="06bc6-130">Operations</span></span>
- <span data-ttu-id="06bc6-131">Annahme und Bereitschaft</span><span class="sxs-lookup"><span data-stu-id="06bc6-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="06bc6-132">Sie können zunächst den Fragebogen in ein Microsoft Word-Dokument kopieren.</span><span class="sxs-lookup"><span data-stu-id="06bc6-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="06bc6-133">Versuchen Sie, alle Fragen zu beantworten und alle Details während des Navigierens zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="06bc6-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="06bc6-134">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="06bc6-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="06bc6-135">Wer ist für das Ausfüllen einer Umgebungs Bewertung verantwortlich?</span><span class="sxs-lookup"><span data-stu-id="06bc6-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="06bc6-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="06bc6-136">Next step</span></span></td><td><ul><li><span data-ttu-id="06bc6-137">Dokumentieren Sie die Ergebnisse der Umgebungs Bewertung.</span><span class="sxs-lookup"><span data-stu-id="06bc6-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="06bc6-138">Projektteam</span><span class="sxs-lookup"><span data-stu-id="06bc6-138">Project team</span></span>

<span data-ttu-id="06bc6-139">Stellen Sie sicher, dass Sie die richtigen Personen für Ihr Projektteam aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="06bc6-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="06bc6-140">Überprüfen Sie die Schritte, die Sie unter eintragen [ihrer Projekt beteiligten](upgrade-enlist-stakeholders.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="06bc6-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="06bc6-141">Nachdem Sie Ihre Umgebung ausgewertet haben, fahren Sie mit dem nächsten Schritt fort: [Vorbereiten des Diensts](upgrade-prepare-environment-prepare-service.md).</span><span class="sxs-lookup"><span data-stu-id="06bc6-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
