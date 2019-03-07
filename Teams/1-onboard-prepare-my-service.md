---
title: Vorbereiten der Bereitstellung des Microsoft Teams-Cloud Voice-Diensts
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Verwenden Sie Onboarding Prüflisten zum Vorbereiten von Office 365 für Teams und Konfigurieren von Teams Kernfunktionen, Netzwerk, und cloud-VoIP-Arbeitslasten.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 203a819eb3732d37aa65f92372eb21ffd59aea08
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462068"
---
# <a name="prepare-my-service"></a><span data-ttu-id="d39e0-103">Meine Service vorbereiten</span><span class="sxs-lookup"><span data-stu-id="d39e0-103">Prepare my service</span></span>

<span data-ttu-id="d39e0-104">Dieser Artikel bietet eine Übersicht über die Anforderungen bei der Vorbereitung von Cloud-VoIP-Dienste für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="d39e0-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="d39e0-105">Vorbereiten der ordnungsgemäß, können Sie sein sicher, dass Sie Cloud Voice-Funktionen in Ihrer Organisation bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d39e0-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="d39e0-106">Onboarding Checklisten für die Microsoft-Teams, VoIP-Arbeitslasten</span><span class="sxs-lookup"><span data-stu-id="d39e0-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="d39e0-107">Die folgenden Prüflisten führen Sie durch die Schritte für die Implementierung von Audiokonferenzen, Telefonsystem mit Aufrufen plant ("aufrufen plant") und Funktionen Phone System direkten Routing ("Direktes Routing") im Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="d39e0-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="d39e0-108">Vorbereiten der Office 365 für Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="d39e0-109">Konfigurieren von Teams Kernfunktionen</span><span class="sxs-lookup"><span data-stu-id="d39e0-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="d39e0-110">Netzwerk konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d39e0-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="d39e0-111">Konfigurieren von VoIP-Arbeitslasten Cloud in Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="d39e0-112">Konfigurieren der direkten Weiterleitung von Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="d39e0-113">Die Aufgaben und Aktivitäten in dieser Prüflisten sind die Core "Aufgabe" Elemente, die in jeder Bereitstellung von Cloud-Sprachfunktionen mit Teams liegen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="d39e0-114">Sie können die Prüflisten zum Einschließen von Aktivitäten und Aufgaben, die speziell für Ihre eigenen Teams Reise anpassen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="d39e0-115">Diese Anleitung konzentriert sich ausschließlich auf aufrufen plant, Audiokonferenzen und direkte Routing.</span><span class="sxs-lookup"><span data-stu-id="d39e0-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="d39e0-116">Wenn Sie neue Teams sind, überprüfen Sie die [Übersicht der Microsoft-Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d39e0-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="d39e0-117">Starten Sie als allgemeinen Leitfaden zum Planen der Bereitstellung von Teams mit [Chat bereitstellen, Teams, Kanäle und apps im Microsoft-Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="d39e0-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="d39e0-118">Verwenden Sie die bereitgestellten Prüflisten zum Nachverfolgen des Status der jede einzelne Aktivität und jede Aufgabe, und um sicherzustellen, dass Sie alle wichtigen Schritte übersprungen noch nicht.</span><span class="sxs-lookup"><span data-stu-id="d39e0-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="d39e0-119">Jede Aktivität enthält eine ausführliche Beschreibung der erforderlichen Aktionen und Verweise auf zusätzliche Informationen, die Sie verwenden können, um diese Aktivität abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="d39e0-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="d39e0-120">Obwohl es wird empfohlen, dass Sie die Prüflisten in Reihenfolge ausführen, wird der Umfang der Bereitstellung und Konfiguration und Komplexität der Umgebung die genauen Reihenfolge abhängen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="d39e0-121">Sie sind so angeordnet, dass entweder ein "ohne bestehende Infrastruktur" unterstützt Teams Bereitstellung (eine mit keine vorherigen Skype für Business Onlineanwesenheit) oder die Migration von Skype für Business Online zu Teams.</span><span class="sxs-lookup"><span data-stu-id="d39e0-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="d39e0-122">Wenn Sie von Skype für Business Online migrieren, möglicherweise haben bereits abgeschlossen einige dieser Aktivitäten und jetzt ignorieren können.</span><span class="sxs-lookup"><span data-stu-id="d39e0-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="d39e0-123">Wenn Sie Onboarding-Benutzer auf eine Websitebasis sind, empfehlen wir nachdrücklich für die Verwendung der [Website Aktivierung Playbook für VoIP (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) als zusätzliche Anleitung zu dieser Prüflisten.</span><span class="sxs-lookup"><span data-stu-id="d39e0-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="d39e0-124">Die meisten Konfigurationseinstellungen gelten sowohl für Teams und Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="d39e0-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="d39e0-125">Sie verwenden die Verwaltungskonsole von Office 365 Admin Center und Microsoft-Teams, um diese Einstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d39e0-125">You use the Office 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="d39e0-126">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="d39e0-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="d39e0-127">Wer wird für die Aufsicht über den Abschluss der Onboarding Prüflisten zuständig sein?</span><span class="sxs-lookup"><span data-stu-id="d39e0-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="d39e0-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d39e0-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="d39e0-129">Laden Sie die Prüflisten Onboarding.</span><span class="sxs-lookup"><span data-stu-id="d39e0-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="d39e0-130">Durch die Onboarding Prüfliste Elemente schrittweise nach Plan für die Bereitstellung Ihrer Organisation arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d39e0-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="d39e0-131">Onboarding fortsetzen</span><span class="sxs-lookup"><span data-stu-id="d39e0-131">Continue onboarding</span></span>

<span data-ttu-id="d39e0-132">Nach Abschluss dieser Prüflisten benötigen Sie erfolgreich Voice-Funktionen für Ihre Bereitstellung Teams hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d39e0-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="d39e0-133">Als Nächstes verwenden Sie die [Website Aktivierung Playbook für VoIP (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Einstieg erleichtern die Benutzer auf jeder Website durch, und dazu beitragen Sie, dass Sie beim Planen und Ausführen von wichtigen standortspezifische Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="d39e0-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="d39e0-134">Plan für die Einführung der bereit von Standorten</span><span class="sxs-lookup"><span data-stu-id="d39e0-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="d39e0-135">Service-Management Prozess herstellen</span><span class="sxs-lookup"><span data-stu-id="d39e0-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="d39e0-136">Ausführen von Tests und-Wartung</span><span class="sxs-lookup"><span data-stu-id="d39e0-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="d39e0-137">Test Cloud VoIP Arbeitslasten in Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="d39e0-138">Nachdem Sie definiert und die Teams Cloud VoIP geschäftlichen Erfolg und technische Pläne als Teil der Phase Ermitteln übergeordneter Faktoren dokumentiert und in der Verwaltungskonsole gewünschte Konfiguration vorgenommen, wird im nächste Schritt zu überprüfen, die Ihre Organisation die Erwartungen und Anforderungen erfüllt sind über Features, Funktionen und Verwendbarkeit.</span><span class="sxs-lookup"><span data-stu-id="d39e0-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="d39e0-139">Sie sollten diese Validierungsschritt führen Sie vor der Bereitstellung einer pilot oder final-bereitstellungs in Ihrer produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="d39e0-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="d39e0-140">Sie können Business Erfolg planen nutzen, die Sie während der Phase der Ermitteln übergeordneter Faktoren dienen als Grundlage für die Bestimmung der Aktivitäten, erwartet, die Funktionalität der Testfälle und allgemeine Bereich während der Testphase ausgewertet werden definiert haben.</span><span class="sxs-lookup"><span data-stu-id="d39e0-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="d39e0-141">Definieren Sie Ihren testing Ansatz</span><span class="sxs-lookup"><span data-stu-id="d39e0-141">Define your testing approach</span></span>

<span data-ttu-id="d39e0-142">In der einfachsten Form Ihre testing Ansatz basiert auf Ihre Funktion Funktionen von Audiokonferenzen, aufrufen plant, überprüfen oder direkte Routingdienst und Entwickeln von einen Test planen, um sicherzustellen, dass Ihre Funktionalität für Benutzer im Gültigkeitsbereich erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="d39e0-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="d39e0-143">Es folgt ein Beispiel Testplan für die integrierte Phase einer Audiokonferenz Implementierung.</span><span class="sxs-lookup"><span data-stu-id="d39e0-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="d39e0-144">So testen Sie Audio Feature für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="d39e0-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="d39e0-145">Zusammenfassung der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="d39e0-145">Results summary</span></span> | <span data-ttu-id="d39e0-146">Zusätzliche Hinweise</span><span class="sxs-lookup"><span data-stu-id="d39e0-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="d39e0-147">Planen Sie eine Ad-hoc-Teams Besprechung, die Einwahlinformationen Audiokonferenzen enthält</span><span class="sxs-lookup"><span data-stu-id="d39e0-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="d39e0-148">Bestanden wurden oder</span><span class="sxs-lookup"><span data-stu-id="d39e0-148">Pass/Fail</span></span>   | <span data-ttu-id="d39e0-149">TBD</span><span class="sxs-lookup"><span data-stu-id="d39e0-149">TBD</span></span> |
| <span data-ttu-id="d39e0-150">Verwenden Sie ein Telefon zur Erfüllung von Audio in einer Besprechung über das Telefonfestnetz erreichen, indem er mit den bereitgestellten Informationen Zugriffsnummer für Einwahl</span><span class="sxs-lookup"><span data-stu-id="d39e0-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="d39e0-151">Bestanden wurden oder</span><span class="sxs-lookup"><span data-stu-id="d39e0-151">Pass/Fail</span></span> | <span data-ttu-id="d39e0-152">TBD</span><span class="sxs-lookup"><span data-stu-id="d39e0-152">TBD</span></span> |
| <span data-ttu-id="d39e0-153">Teilnehmen an andere Personen zu einer vorhandenen Besprechung durch Telefonverbindung über das Telefonfestnetz</span><span class="sxs-lookup"><span data-stu-id="d39e0-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="d39e0-154">Bestanden wurden oder</span><span class="sxs-lookup"><span data-stu-id="d39e0-154">Pass/Fail</span></span> | <span data-ttu-id="d39e0-155">TBD</span><span class="sxs-lookup"><span data-stu-id="d39e0-155">TBD</span></span> |



| <span data-ttu-id="d39e0-156">Aufrufen von Plänen oder direkten Routing feature zum Testen</span><span class="sxs-lookup"><span data-stu-id="d39e0-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="d39e0-157">Zusammenfassung der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="d39e0-157">Results summary</span></span> | <span data-ttu-id="d39e0-158">Zusätzliche Hinweise</span><span class="sxs-lookup"><span data-stu-id="d39e0-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="d39e0-159">Stellen Sie einen PSTN-Anruf durch wählen eine PSTN-Nummer</span><span class="sxs-lookup"><span data-stu-id="d39e0-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="d39e0-160">Bestanden wurden oder</span><span class="sxs-lookup"><span data-stu-id="d39e0-160">Pass/Fail</span></span>       | <span data-ttu-id="d39e0-161">TBD</span><span class="sxs-lookup"><span data-stu-id="d39e0-161">TBD</span></span> |
| <span data-ttu-id="d39e0-162">Erhalten Sie einen PSTN-Anruf durch Wählen der PSTN-Nummer aus einer externen Zeile (mobile, Festnetz)</span><span class="sxs-lookup"><span data-stu-id="d39e0-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="d39e0-163">Bestanden wurden oder</span><span class="sxs-lookup"><span data-stu-id="d39e0-163">Pass/Fail</span></span> | <span data-ttu-id="d39e0-164">TBD</span><span class="sxs-lookup"><span data-stu-id="d39e0-164">TBD</span></span>|
| <span data-ttu-id="d39e0-165">Übertragen Sie einen PSTN-Anruf von einem Benutzer von Teams auf einen anderen</span><span class="sxs-lookup"><span data-stu-id="d39e0-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="d39e0-166">Bestanden wurden oder</span><span class="sxs-lookup"><span data-stu-id="d39e0-166">Pass/Fail</span></span> | <span data-ttu-id="d39e0-167">TBD</span><span class="sxs-lookup"><span data-stu-id="d39e0-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="d39e0-168">Zur Erleichterung der Testfall Erstellung als Ausgangspunkt finden Sie in der Liste der Benutzer Anleitungen verfügbar unter [Teams Besprechungen und Telefonkonferenzen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="d39e0-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="d39e0-169">Einrichten von Cloud-VoIP-Arbeitslasten für Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="d39e0-170">Nun, da Sie Ihren testing Ansatz definiert haben, wird im nächste Schritt der Service-Umgebung und den Benutzer im Gültigkeitsbereich für Teams Cloud VoIP-Funktionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d39e0-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="d39e0-171">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="d39e0-171">For additional information, see:</span></span>

- [<span data-ttu-id="d39e0-172">Technische Planung für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="d39e0-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="d39e0-173">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-173">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [<span data-ttu-id="d39e0-174">Technische Telefonsystem mit dem Aufrufen der Pläne planen</span><span class="sxs-lookup"><span data-stu-id="d39e0-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="d39e0-175">Einrichten von Aufrufen Pläne für Skype für Unternehmen und die Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="d39e0-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="d39e0-176">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="d39e0-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="d39e0-177">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="d39e0-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="d39e0-178">Führen Sie den Testplan</span><span class="sxs-lookup"><span data-stu-id="d39e0-178">Execute the test plan</span></span>

[//]: # (Okay bearbeiten? "User" erschien mir etwas nicht eindeutig.)
<span data-ttu-id="d39e0-180">Nachdem die Umgebung des Benutzers und der Dienst konfiguriert haben, enthält der letzte Schritt testen Test Plan Ausführung mit Fokus auf Features und Funktionen Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="d39e0-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="d39e0-181">**Audiokonferenzen Voraussetzungen und Annahmen für Benutzer und Standorte im Bereich testen:**</span><span class="sxs-lookup"><span data-stu-id="d39e0-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="d39e0-182">Business verwenden Sie Groß-/Kleinschreibung Definition für die Audiokonferenz Service abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d39e0-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="d39e0-183">Lizenzierung für Audiokonferenzen erforderlich ist verfügbar und zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d39e0-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="d39e0-184">Die Liste der Organisationseinheit Standorte und Benutzergruppen ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="d39e0-185">Die Liste der dedizierten und freigegebene Audiokonferenz einwählen und Nummern mit bevorzugte Sprache identifiziert und konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="d39e0-186">[Communications haben](what-are-communications-credits.md) (falls erforderlich) Ihrer Organisation eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="d39e0-187">Live Meeting-Konferenz Bridge audioeinstellungen wurden identifiziert und konfiguriert (PIN-Mindestlänge, Eintrag/Exit Benachrichtigungen, Aktivierung Benachrichtigung Option Sie bevorzugen).</span><span class="sxs-lookup"><span data-stu-id="d39e0-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="d39e0-188">Mandanten Sie konferenzrichtlinien, und wählen Sie planen von Einstellungen, die Audiokonferenz unterstützen Dial-Out-Szenarien identifiziert, angewendet und konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="d39e0-189">Audio Conferencing Compliance-Bestimmungen haben identifiziert und konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="d39e0-190">**Aufrufen von Pläne Voraussetzungen und Annahmen für Benutzer und Standorte im Bereich testen:**</span><span class="sxs-lookup"><span data-stu-id="d39e0-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="d39e0-191">Business verwenden Sie Groß-/Kleinschreibung Definition für den Aufruf von plant Service abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d39e0-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="d39e0-192">Lizenzierung für aufrufen Pläne erforderlich ist verfügbar und zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d39e0-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="d39e0-193">Die Liste der Organisationseinheit Standorte und Benutzergruppen ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="d39e0-194">Rufnummern, die Benutzern zugewiesen werden wurden erworben oder Microsoft und sind in den Mandanten Portal übertragen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="d39e0-195">[Communications haben](what-are-communications-credits.md) (falls erforderlich) Ihrer Organisation eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="d39e0-196">Mandanten Benutzerrichtlinien und Wähleinstellungen, die Pläne aufrufen Szenarios unterstützen haben identifiziert, angewendet und konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="d39e0-197">Aufrufen von Plänen Compliance-Bestimmungen identifiziert und konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="d39e0-198">**Direkte Routing Voraussetzungen und Annahmen für Benutzer und Standorte im Bereich testen:**</span><span class="sxs-lookup"><span data-stu-id="d39e0-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="d39e0-199">Business verwenden Sie Groß-/Kleinschreibung Definition für das direkte Routing Service abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d39e0-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="d39e0-200">Lizenzierung für das direkte Routing erforderlich ist verfügbar und zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d39e0-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="d39e0-201">Die Liste der Organisationseinheit Standorte und Benutzergruppen ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="d39e0-202">Eine [zertifizierte Session Border Controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) wurde bereitgestellt, konfiguriert und gepaart mit einer Telefonsystem.</span><span class="sxs-lookup"><span data-stu-id="d39e0-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="d39e0-203">Enterprise-VoIP aktiviert wurde, und die Rufnummern zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="d39e0-204">VoIP-Routingrichtlinien zurückgegeben haben identifiziert, konfiguriert und zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="d39e0-205">Microsoft-Teams wurde als bevorzugter Client aufrufende für die Benutzer im Bereich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d39e0-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="d39e0-206">Direktes Routing Compliance Anforderungen identifiziert und konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39e0-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="d39e0-207">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="d39e0-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="d39e0-208">Entscheiden, welche Funktionen der Audiokonferenz Feature bereitgestellt werden soll (service Entscheidung).</span><span class="sxs-lookup"><span data-stu-id="d39e0-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="d39e0-209">Identifizieren der Anforderungen an den Funktionen für Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="d39e0-210">Identifizieren Sie die Konfiguration der dienstanforderungen für Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="d39e0-211">Entscheiden Sie, ob direkten Routing oder aufrufen plant bereitgestellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="d39e0-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="d39e0-212">Entscheiden, welche Telefonsystem Feature Funktionen bereitgestellt werden soll (service Entscheidung).</span><span class="sxs-lookup"><span data-stu-id="d39e0-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="d39e0-213">Identifizieren der Anforderungen für Benutzer-Funktionalität für direkte Routing oder plant aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="d39e0-214">Identifizieren Sie Service Konfigurationsaufwand für direkte Routing oder plant aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d39e0-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="d39e0-215">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d39e0-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="d39e0-216">Entwickeln Sie und Dokumentieren Sie Ihren Test Plan Ansatz.</span><span class="sxs-lookup"><span data-stu-id="d39e0-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="d39e0-217">Vorbereiten der Service-Umgebung und Benutzer für Audiokonferenzen Features im Bereich.</span><span class="sxs-lookup"><span data-stu-id="d39e0-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="d39e0-218">Vorbereiten der Service-Umgebung und Benutzer für den Aufruf von Plänen oder direkten Routing Features im Bereich.</span><span class="sxs-lookup"><span data-stu-id="d39e0-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="d39e0-219">Führen Sie Test-Überprüfung für die Audiokonferenz-Features, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d39e0-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="d39e0-220">Führen Sie Test-Überprüfung für die direkte Routing oder plant aufrufen Features, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d39e0-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="d39e0-221">Testen Sie für alle Fehler, bestätigen Sie, dass Ihre Konfiguration korrekt ist, Community-Artikel zu lesen und – falls erforderlich – auslösen eine Supportanfrage.</span><span class="sxs-lookup"><span data-stu-id="d39e0-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="d39e0-222">Weitere ausführliche Anleitungen zur Durchführung von Tests für Audiokonferenzen in Teams finden Sie unter der- [ausführliche Anleitung für Audiokonferenzen testen](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="d39e0-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="d39e0-223">Weitere ausführliche Anleitungen zur Durchführung von Tests für Aufrufen in Teams plant finden Sie unter der- [ausführliche Anleitung für Telefonsystem testen](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="d39e0-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
