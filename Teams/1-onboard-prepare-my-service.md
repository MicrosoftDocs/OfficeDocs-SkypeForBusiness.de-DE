---
title: Vorbereiten der Bereitstellung des Microsoft Teams-Cloud Voice-Diensts
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Verwenden Sie Onboarding-Checklisten, um Office 365 für Teams vorzubereiten und die Kernfunktionen von Teams, Netzwerke und Cloud-VoIP-Workloads zu konfigurieren.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: efc7193549fac95a29a574f455576dec5ea35c58
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862825"
---
# <a name="prepare-my-service"></a><span data-ttu-id="657cf-103">Vorbereiten des Diensts</span><span class="sxs-lookup"><span data-stu-id="657cf-103">Prepare my service</span></span>

<span data-ttu-id="657cf-104">Dieser Artikel enthält eine Übersicht über die Anforderungen für das Vorbereiten von Cloud-VoIP-Diensten für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="657cf-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="657cf-105">Wenn Sie ordnungsgemäß vorbereitet sind, können Sie sicherstellen, dass Sie bereit sind, Ihrer Organisation Cloud-Sprachfunktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="657cf-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="657cf-106">Onboarding-Checklisten für Microsoft Teams-sprach Auslastungen</span><span class="sxs-lookup"><span data-stu-id="657cf-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="657cf-107">Die folgenden Checklisten führen Sie durch die Schritte zum Implementieren von Audiokonferenzen, Telefonsystemen mit Anrufplänen ("Anrufpläne") und von Telefonsystem-direkt Routing ("Direct Routing") in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="657cf-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="657cf-108">Vorbereiten von Office 365 für Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="657cf-109">Konfigurieren der Kernfunktionen von Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="657cf-110">Vorbereiten des Netzwerks Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="657cf-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="657cf-111">Konfigurieren von Cloud-sprach Auslastungen in Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="657cf-112">Konfigurieren des direkten Routings in Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="657cf-113">Die Aufgaben und Aktivitäten in diesen Prüflisten sind die Kernaufgaben, die für jede Bereitstellung von Cloud-Sprachfunktionen in Teams gelten.</span><span class="sxs-lookup"><span data-stu-id="657cf-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="657cf-114">Sie können die Checklisten anpassen, um die Aktivitäten und Aufgaben einzubeziehen, die für Ihre eigene Teams-Reise spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="657cf-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="657cf-115">Dieser Leitfaden konzentriert sich ausschließlich auf Anrufpläne, Audiokonferenzen und direktes Routing.</span><span class="sxs-lookup"><span data-stu-id="657cf-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="657cf-116">Wenn Sie neu bei Microsoft Teams sind, überprüfen Sie die [Übersicht über Microsoft Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="657cf-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="657cf-117">Allgemeine Anleitungen zum Planen der Bereitstellung von Teams finden Sie unter [Bereitstellen von Chat, Teams, Kanälen und apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="657cf-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="657cf-118">Verwenden Sie die bereitgestellten Checklisten, um den Status der einzelnen Aktivitäten und Aufgaben zu überwachen und sicherzustellen, dass Sie keine kritischen Schritte übersprungen haben.</span><span class="sxs-lookup"><span data-stu-id="657cf-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="657cf-119">Jede Aktivität umfasst eine detaillierte Beschreibung der erforderlichen Aktionen und Verweise auf zusätzliche Informationen, die Sie zum Ausführen dieser Aktivität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="657cf-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="657cf-120">Obwohl es empfehlenswert ist, die Checklisten in der richtigen Reihenfolge zu befolgen, hängt die genaue Reihenfolge vom Umfang ihrer Bereitstellung und der Konfiguration und Komplexität Ihrer Umgebung ab.</span><span class="sxs-lookup"><span data-stu-id="657cf-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="657cf-121">Sie sind so organisiert, dass Sie eine "Greenfield"-Teams-Bereitstellung (eine ohne vorherige Skype for Business Online-Anwesenheit) oder die Migration von Skype for Business Online zu Teams unterstützen.</span><span class="sxs-lookup"><span data-stu-id="657cf-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="657cf-122">Wenn Sie von Skype for Business Online migrieren, haben Sie möglicherweise bereits einige dieser Aktivitäten abgeschlossen und können diese jetzt ignorieren.</span><span class="sxs-lookup"><span data-stu-id="657cf-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="657cf-123">Wenn Sie Benutzer pro Website an Bord haben, wird dringend empfohlen, dass Sie das Textbuch [für die Website Aktivierung](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) als ergänzende Anleitung für diese Checklisten verwenden.</span><span class="sxs-lookup"><span data-stu-id="657cf-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="657cf-124">Die meisten Konfigurationseinstellungen sind zwischen Teams und Skype for Business Online üblich.</span><span class="sxs-lookup"><span data-stu-id="657cf-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="657cf-125">Sie verwenden das Microsoft 365 Admin Center und das Microsoft Teams Admin Center, um diese Einstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="657cf-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="657cf-126">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="657cf-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="657cf-127">Wer ist für die Überwachung der Fertigstellung der Onboarding-Checklisten zuständig?</span><span class="sxs-lookup"><span data-stu-id="657cf-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="657cf-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="657cf-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="657cf-129">Laden Sie die Checklisten für Onboarding herunter.</span><span class="sxs-lookup"><span data-stu-id="657cf-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="657cf-130">Arbeiten Sie schrittweise über die Elemente der Onboarding-Checkliste in Übereinstimmung mit dem Bereitstellungsplan Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="657cf-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="657cf-131">Onboarding fortsetzen</span><span class="sxs-lookup"><span data-stu-id="657cf-131">Continue onboarding</span></span>

<span data-ttu-id="657cf-132">Nachdem Sie diese Checklisten abgeschlossen haben, haben Sie Ihrer Teams-Bereitstellung erfolgreich Sprachfunktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="657cf-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="657cf-133">Verwenden Sie im nächsten Schritt das Textbuch [für die Website Aktivierung (Textbuch für Sprache)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) , damit Sie Ihre Benutzer auf jeder Website an Bord bringen und sicherstellen können, dass Sie wichtige Website spezifische Aktivitäten planen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="657cf-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="657cf-134">Bereitstellungs Plan für bereite Website nach Website</span><span class="sxs-lookup"><span data-stu-id="657cf-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="657cf-135">Einrichten des Dienst Verwaltungsprozesses</span><span class="sxs-lookup"><span data-stu-id="657cf-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="657cf-136">Testen und Behebung durchführen</span><span class="sxs-lookup"><span data-stu-id="657cf-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="657cf-137">Testen von Cloud-sprach Auslastungen in Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="657cf-138">Nachdem Sie Ihre Teams Cloud Voice Business Success-und Technical implementation-Pläne im Rahmen der enVision-Phase definiert und dokumentiert haben und die gewünschte Konfiguration im Admin Center vorgenommen haben, besteht der nächste Schritt darin, zu überprüfen, ob Ihre Organisation Erwartungen und Anforderungen werden durch Funktion, Funktionalität und Benutzerfreundlichkeit erfüllt.</span><span class="sxs-lookup"><span data-stu-id="657cf-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="657cf-139">Sie sollten diesen Validierungsschritt durchführen, bevor Sie eine Pilot-oder endgültige Bereitstellung in Ihrer Produktionsumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="657cf-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="657cf-140">Sie können den Geschäftserfolgs Plan, den Sie während der enVision-Phase definiert haben, als Grundlage für die Ermittlung der Aktivitäten, Erwartungen, Funktions-/Funktionstest Fälle und des Gesamtumfangs nutzen, der während der Testphase ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="657cf-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="657cf-141">Definieren des testansatzes</span><span class="sxs-lookup"><span data-stu-id="657cf-141">Define your testing approach</span></span>

<span data-ttu-id="657cf-142">In der einfachsten Form basiert Ihr Testansatz auf der Überprüfung der Funktions Funktionen der Audiokonferenzen, der Anrufpläne oder des direkten Routing Diensts sowie der Entwicklung eines Testplans, um zu überprüfen, ob die Funktionsanforderungen für Benutzer im Bereich erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="657cf-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="657cf-143">Im folgenden sehen Sie einen Beispiel Testplan für die Onboard-Phase einer Audiokonferenz-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="657cf-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="657cf-144">Zu prüfendes Audiokonferenz-Feature</span><span class="sxs-lookup"><span data-stu-id="657cf-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="657cf-145">Ergebnis Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="657cf-145">Results summary</span></span> | <span data-ttu-id="657cf-146">Zusätzliche Notizen</span><span class="sxs-lookup"><span data-stu-id="657cf-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="657cf-147">Planen einer Ad-hoc-Teams-Besprechung mit Einwahlinformationen zu Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="657cf-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="657cf-148">Erfolgreich/fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="657cf-148">Pass/Fail</span></span>   | <span data-ttu-id="657cf-149">TBD</span><span class="sxs-lookup"><span data-stu-id="657cf-149">TBD</span></span> |
| <span data-ttu-id="657cf-150">Verwenden Sie ein Telefon für die Audioübertragung, indem Sie sich über das PSTN mit den eingegebenen Informationen in eine Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="657cf-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="657cf-151">Erfolgreich/fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="657cf-151">Pass/Fail</span></span> | <span data-ttu-id="657cf-152">TBD</span><span class="sxs-lookup"><span data-stu-id="657cf-152">TBD</span></span> |
| <span data-ttu-id="657cf-153">Teilnehmen an einer vorhandenen Besprechung durch Anrufen über das PSTN</span><span class="sxs-lookup"><span data-stu-id="657cf-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="657cf-154">Erfolgreich/fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="657cf-154">Pass/Fail</span></span> | <span data-ttu-id="657cf-155">TBD</span><span class="sxs-lookup"><span data-stu-id="657cf-155">TBD</span></span> |



| <span data-ttu-id="657cf-156">Anrufpläne oder direktes Routing-Feature zum Testen</span><span class="sxs-lookup"><span data-stu-id="657cf-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="657cf-157">Ergebnis Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="657cf-157">Results summary</span></span> | <span data-ttu-id="657cf-158">Zusätzliche Notizen</span><span class="sxs-lookup"><span data-stu-id="657cf-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="657cf-159">Tätigen eines PSTN-Anrufs durch Wählen einer PSTN-Nummer</span><span class="sxs-lookup"><span data-stu-id="657cf-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="657cf-160">Erfolgreich/fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="657cf-160">Pass/Fail</span></span>       | <span data-ttu-id="657cf-161">TBD</span><span class="sxs-lookup"><span data-stu-id="657cf-161">TBD</span></span> |
| <span data-ttu-id="657cf-162">Empfangen eines PSTN-Anrufs, indem Sie Ihre PSTN-Nummer von einer externen Leitung anrufen (Mobil, Festnetztelefon)</span><span class="sxs-lookup"><span data-stu-id="657cf-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="657cf-163">Erfolgreich/fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="657cf-163">Pass/Fail</span></span> | <span data-ttu-id="657cf-164">TBD</span><span class="sxs-lookup"><span data-stu-id="657cf-164">TBD</span></span>|
| <span data-ttu-id="657cf-165">Übertragen eines PSTN-Anrufs von einem Teams-Benutzer zu einem anderen</span><span class="sxs-lookup"><span data-stu-id="657cf-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="657cf-166">Erfolgreich/fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="657cf-166">Pass/Fail</span></span> | <span data-ttu-id="657cf-167">TBD</span><span class="sxs-lookup"><span data-stu-id="657cf-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="657cf-168">Wenn Sie die Erstellung von Testfällen als Ausgangspunkt unterstützen möchten, lesen Sie die Liste der Benutzerleitfäden, die in den [Teams-Besprechungen und-anrufen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="657cf-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="657cf-169">Einrichten von Cloud-sprach Auslastungen für Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="657cf-170">Nachdem Sie Ihren Testansatz definiert haben, besteht der nächste Schritt darin, ihre Dienstumgebung und die Benutzer im Bereich für die Cloud-Sprachfeatures von Teams zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="657cf-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="657cf-171">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="657cf-171">For additional information, see:</span></span>

- [<span data-ttu-id="657cf-172">Technische Planung für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="657cf-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="657cf-173">Einrichten von Audiokonferenzen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="657cf-174">Technische Planung für Telefonsysteme mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="657cf-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="657cf-175">Einrichten von Anrufplänen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="657cf-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="657cf-176">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="657cf-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="657cf-177">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="657cf-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="657cf-178">Ausführen des Testplans</span><span class="sxs-lookup"><span data-stu-id="657cf-178">Execute the test plan</span></span>

[//]: # (Bearbeiten OK? "Nutzer" schien mir etwas zweideutig zu sein.)
<span data-ttu-id="657cf-180">Nach der Konfiguration der Benutzerumgebung und des Diensts umfasst der letzte Test Schritt die Ausführung des Test Plans mit dem Fokus auf Feature-und Funktionsüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="657cf-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="657cf-181">**Testen der Audiokonferenz-Voraussetzungen und Annahmen für Benutzer und Websites im Bereich:**</span><span class="sxs-lookup"><span data-stu-id="657cf-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="657cf-182">Die Business Use Case-Definition für den Audiokonferenzdienst wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="657cf-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="657cf-183">Die für Audiokonferenzen erforderliche Lizenzierung steht zur Verfügung und wurde zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="657cf-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="657cf-184">Die Liste der Organisations Websites und Benutzergruppen wurde identifiziert.</span><span class="sxs-lookup"><span data-stu-id="657cf-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="657cf-185">Die Liste der dedizierten und freigegebenen Audiokonferenz-Einwahlnummern mit Spracheinstellungen wurden identifiziert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="657cf-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="657cf-186">Für Ihre Organisation wurden [Kommunikationsguthaben](what-are-communications-credits.md) (falls erforderlich) eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="657cf-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="657cf-187">Die Einstellungen für Audiokonferenz-Konferenz Brücken wurden identifiziert und konfiguriert (PIN-Länge, Benachrichtigungen für ein-und Ausstiege, Aktivierung der Benachrichtigungseinstellung).</span><span class="sxs-lookup"><span data-stu-id="657cf-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="657cf-188">Mandanten Konferenzrichtlinien und Einstellungen für den Wählplan, die Wähl Szenarien für die Audiokonferenz unterstützen, wurden identifiziert, konfiguriert und angewendet.</span><span class="sxs-lookup"><span data-stu-id="657cf-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="657cf-189">Compliance-Anforderungen an die Audiokonferenz wurden identifiziert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="657cf-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="657cf-190">**Anrufpläne Testen von Voraussetzungen und Annahmen für Benutzer und Websites im Bereich:**</span><span class="sxs-lookup"><span data-stu-id="657cf-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="657cf-191">Die Business Use Case-Definition für den Service für Anrufpläne wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="657cf-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="657cf-192">Die für Anrufpläne erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="657cf-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="657cf-193">Die Liste der Organisations Websites und Benutzergruppen wurde identifiziert.</span><span class="sxs-lookup"><span data-stu-id="657cf-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="657cf-194">Telefonnummern, die Benutzern zugewiesen werden sollen, wurden erworben oder an Microsoft portiert und stehen im mandantenportal zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="657cf-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="657cf-195">Für Ihre Organisation wurden [Kommunikationsguthaben](what-are-communications-credits.md) (falls erforderlich) eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="657cf-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="657cf-196">Mandanten Benutzerrichtlinien und Einstellungen für den Wählplan, die Szenarien für Anrufpläne unterstützen, wurden identifiziert, konfiguriert und angewendet.</span><span class="sxs-lookup"><span data-stu-id="657cf-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="657cf-197">Die Compliance-Anforderungen für Anrufpläne wurden identifiziert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="657cf-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="657cf-198">**Direktes Routing Testen von Voraussetzungen und Annahmen für Benutzer und Websites im Bereich:**</span><span class="sxs-lookup"><span data-stu-id="657cf-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="657cf-199">Die Geschäfts Anwendungsfall Definition für den Direct Routing-Dienst wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="657cf-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="657cf-200">Die für das direkte Routing erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="657cf-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="657cf-201">Die Liste der Organisations Websites und Benutzergruppen wurde identifiziert.</span><span class="sxs-lookup"><span data-stu-id="657cf-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="657cf-202">Ein [Certified Session Border Controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) wurde bereitgestellt, konfiguriert und mit dem Telefon System gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="657cf-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="657cf-203">Enterprise-VoIP wurde aktiviert, und die Telefonnummern wurden zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="657cf-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="657cf-204">VoIP-Routing Richtlinien wurden identifiziert, konfiguriert und zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="657cf-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="657cf-205">Microsoft Teams wurde als bevorzugter Anruf Client für die Benutzer im Bereich eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="657cf-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="657cf-206">Die Compliance-Anforderungen für Direct Routing wurden identifiziert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="657cf-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="657cf-207">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="657cf-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="657cf-208">Entscheiden Sie, welche Funktionen für Audiokonferenz Features bereitgestellt werden (Dienst Entscheidung).</span><span class="sxs-lookup"><span data-stu-id="657cf-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="657cf-209">Ermitteln Sie die Anforderungen der Benutzerfunktionalität für Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="657cf-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="657cf-210">Ermitteln der Dienst Konfigurationsanforderungen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="657cf-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="657cf-211">Entscheiden Sie, ob direkte Routing-oder Anrufpläne bereitgestellt und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="657cf-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="657cf-212">Entscheiden Sie, welche Funktionen für das Telefon System bereitgestellt werden (Dienst Entscheidung).</span><span class="sxs-lookup"><span data-stu-id="657cf-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="657cf-213">Ermitteln der Benutzer Funktionalitätsanforderungen für Anrufpläne oder direktes Routing</span><span class="sxs-lookup"><span data-stu-id="657cf-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="657cf-214">Ermitteln der Dienst Konfigurationsanforderung für Anrufpläne oder direktes Routing</span><span class="sxs-lookup"><span data-stu-id="657cf-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="657cf-215">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="657cf-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="657cf-216">Entwickeln und dokumentieren Sie Ihren Testplan-Ansatz.</span><span class="sxs-lookup"><span data-stu-id="657cf-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="657cf-217">Bereiten Sie Ihre Dienstumgebung und die Benutzer im Bereich für Audiokonferenzfunktionen vor.</span><span class="sxs-lookup"><span data-stu-id="657cf-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="657cf-218">Bereiten Sie Ihre Dienstumgebung und die Benutzer im Bereich für Anrufpläne oder direkte Routing Features vor.</span><span class="sxs-lookup"><span data-stu-id="657cf-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="657cf-219">Führen Sie die Testüberprüfung für die Audio-Konferenzfeatures aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="657cf-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="657cf-220">Führen Sie die Testüberprüfung für die Anrufpläne oder direkt Routing Features aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="657cf-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="657cf-221">Überprüfen Sie bei Test Fehlern, ob Ihre Konfiguration richtig ist, lesen Sie Community-Artikel, und führen Sie bei Bedarf einen Supportfall aus.</span><span class="sxs-lookup"><span data-stu-id="657cf-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="657cf-222">Weitere detaillierte Anleitungen zum Durchführen von Tests für Audiokonferenzen in Teams finden Sie im [ausführlichen Testhandbuch für Audiokonferenzen](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="657cf-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="657cf-223">Weitere detaillierte Anleitungen zum Durchführen von Tests für Anrufpläne in Teams finden Sie im [ausführlichen Testhandbuch für das Telefon System](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="657cf-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
