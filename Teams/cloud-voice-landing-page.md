---
title: Cloud Voice in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Erfahren Sie mehr über die Cloud-VoIP-Funktion, und verstehen Sie die erforderlichen Bereitstellungsentscheidungen, denen Sie gegenüberstehen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8106e5ef30b71ec82e9b1ae42f785b7a73b170a5
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158643"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="9ad69-103">VoIP-Telefon System-und PSTN-Verbindungsoptionen</span><span class="sxs-lookup"><span data-stu-id="9ad69-103">Voice - Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="9ad69-104">Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9ad69-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9ad69-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9ad69-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9ad69-106">Vielleichthaben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9ad69-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="9ad69-107">Jetzt sind Sie bereit, Ihren Benutzern Sprachfunktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9ad69-107">Now you're ready to add voice capabilities for your users.</span></span> 

<span data-ttu-id="9ad69-108">Voice bietet Funktionen für Private Branch Exchange (PBX) und Optionen zum Herstellen einer Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9ad69-108">Voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="9ad69-109">Dieser Artikel hilft Ihnen bei der Entscheidung, ob Sie die standardmäßigen Spracheinstellungen basierend auf den Profil-und Geschäftsanforderungen Ihrer Organisation ändern müssen, und führt Sie durch die einzelnen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="9ad69-109">This article helps you decide whether you need to change any of the default voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="9ad69-110">Wir haben die Einstellungen in zwei Gruppen aufgeteilt, beginnend mit dem Haupt Satz von [Änderungen, die Sie wahrscheinlicher vornehmen werden](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="9ad69-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="9ad69-111">Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.</span><span class="sxs-lookup"><span data-stu-id="9ad69-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="9ad69-112">Wir empfehlen, dass alle Organisationen die grundlegenden Entscheidungen treffen, und wenn Ihre Organisation zusätzliche Anforderungen hat, überprüfen Sie das folgende Material.</span><span class="sxs-lookup"><span data-stu-id="9ad69-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-voice"></a><span data-ttu-id="9ad69-113">Weitere Informationen zu Voice</span><span class="sxs-lookup"><span data-stu-id="9ad69-113">Learn more about voice</span></span>

<span data-ttu-id="9ad69-114">In den folgenden Artikeln finden Sie weitere Informationen zum Bereitstellen und Verwenden von Sprachfeatures in Teams:</span><span class="sxs-lookup"><span data-stu-id="9ad69-114">The following articles provide more information about deploying and using voice features in Teams:</span></span>

- [<span data-ttu-id="9ad69-115">Telefon System in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="9ad69-115">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="9ad69-116">Telefonsystem mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="9ad69-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="9ad69-117">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="9ad69-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="9ad69-118">Microsoft-Telefonielösungen</span><span class="sxs-lookup"><span data-stu-id="9ad69-118">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="9ad69-119">Schauen Sie sich die folgende Sitzung an, um mehr über das Telefonsystem zu erfahren: [Einführung in das Telefonsystem in Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="9ad69-119">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="9ad69-120">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9ad69-120">Core deployment decisions</span></span>

<span data-ttu-id="9ad69-121">Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).</span><span class="sxs-lookup"><span data-stu-id="9ad69-121">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="9ad69-122">Telefon System (Office 365)</span><span class="sxs-lookup"><span data-stu-id="9ad69-122">Phone System (Office 365)</span></span>

<span data-ttu-id="9ad69-123">Telefon System ist die Microsoft-Technologie für die Aktivierung der Anrufsteuerung und der Funktionen für Private Branch Exchange (PBX) in der Microsoft 365-oder Office 365-Cloud.</span><span class="sxs-lookup"><span data-stu-id="9ad69-123">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud.</span></span> <span data-ttu-id="9ad69-124">Mit dem Telefonsystem können Sie Ihr vorhandenes Private Branch Exchange (PBX)-System durch eine Reihe von Features ersetzen, die direkt von Microsoft 365 oder Office 365 bereitgestellt und eng in die Cloud-Produktivitäts Erfahrung des Unternehmens integriert sind.</span><span class="sxs-lookup"><span data-stu-id="9ad69-124">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Microsoft 365 or Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="9ad69-125">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-125">Ask yourself</span></span>|<span data-ttu-id="9ad69-126">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-126">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9ad69-127">An welchen Speicherorten oder Büros wird das Telefon System implementiert?</span><span class="sxs-lookup"><span data-stu-id="9ad69-127">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="9ad69-128">Weitere Informationen zum Telefonsystem finden Sie unter [Was ist Telefonsystem in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-128">For more information about Phone System, see [What is Phone System in Microsoft 365 or Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="9ad69-129">Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="9ad69-129">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="9ad69-130">Wenn Sie das Telefon System mit dem öffentlichen Telefonnetz (PSTN) verbinden möchten, damit Benutzer überall in der Welt Telefonanrufe tätigen können, haben Sie Optionen, die auf Ihren geschäftlichen Anforderungen basieren.</span><span class="sxs-lookup"><span data-stu-id="9ad69-130">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="9ad69-131">Stellen Sie sich folgende Fragen:</span><span class="sxs-lookup"><span data-stu-id="9ad69-131">Ask yourself the following:</span></span>


|<span data-ttu-id="9ad69-132">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-132">Ask yourself</span></span>|<span data-ttu-id="9ad69-133">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-133">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9ad69-134">Möchte ich den Microsoft-Anrufplan als meinen Telefonnetzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="9ad69-134">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="9ad69-135">Weitere Informationen finden Sie unter [Telefon System mit Anrufplänen](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-135">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="9ad69-136">Muss ich meinen eigenen Telefonnetzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="9ad69-136">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="9ad69-137">Weitere Informationen finden Sie unter [Telefon System mit direktem Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-137">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="9ad69-138">Zusätzliche Bereitstellungsentscheidungen</span><span class="sxs-lookup"><span data-stu-id="9ad69-138">Additional deployment decisions</span></span>

<span data-ttu-id="9ad69-139">Basierend auf den Anforderungen und der Konfiguration Ihrer Organisation können Sie die Einstellungen für Folgendes ändern:</span><span class="sxs-lookup"><span data-stu-id="9ad69-139">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="9ad69-140">Voicemail</span><span class="sxs-lookup"><span data-stu-id="9ad69-140">Voicemail</span></span>
- <span data-ttu-id="9ad69-141">Identität des Anrufs</span><span class="sxs-lookup"><span data-stu-id="9ad69-141">Calling identity</span></span>
- <span data-ttu-id="9ad69-142">Telefonnummern von Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ad69-142">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="9ad69-143">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="9ad69-143">Dial plans</span></span>
- <span data-ttu-id="9ad69-144">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="9ad69-144">Call queues</span></span>
- <span data-ttu-id="9ad69-145">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="9ad69-145">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="9ad69-146">Voicemail</span><span class="sxs-lookup"><span data-stu-id="9ad69-146">Voicemail</span></span>

<span data-ttu-id="9ad69-147">Cloud Voicemail, powered by Azure Voicemail Services, unterstützt Voicemail-Einzahlungen nur für Exchange-Postfächer und unterstützt keine e-Mail-Systeme von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="9ad69-147">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="9ad69-148">Cloud Voicemail umfasst Voicemail-Transkription, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9ad69-148">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="9ad69-149">Für Ihre geschäftlichen Anforderungen müssen Sie möglicherweise die Voicemail-Transkription für bestimmte Benutzer oder alle in der Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9ad69-149">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="9ad69-150">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-150">Ask yourself</span></span>|<span data-ttu-id="9ad69-151">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-151">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9ad69-152">Möchte ich Cloud Voicemail aktivieren?</span><span class="sxs-lookup"><span data-stu-id="9ad69-152">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="9ad69-153">Anweisungen zum Einrichten von Voicemail finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-153">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="9ad69-154">Soll die Sprachübertragung für einige oder alle meine Benutzer aktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="9ad69-154">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="9ad69-155">Informationen zum Deaktivieren der Voicemail-Transkription finden Sie unter [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9ad69-155">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="9ad69-156">Identität des Anrufs</span><span class="sxs-lookup"><span data-stu-id="9ad69-156">Calling identity</span></span>

<span data-ttu-id="9ad69-157">Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige).</span><span class="sxs-lookup"><span data-stu-id="9ad69-157">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="9ad69-158">Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.</span><span class="sxs-lookup"><span data-stu-id="9ad69-158">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="9ad69-159">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-159">Ask yourself</span></span>|<span data-ttu-id="9ad69-160">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-160">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9ad69-161">Soll die Rufnummernanzeige maskiert oder deaktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="9ad69-161">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="9ad69-162">Informationen zum Ändern oder Blockieren der Rufnummernanzeige finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-162">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="9ad69-163">Telefonnummern von Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ad69-163">Phone numbers from Microsoft</span></span>

<span data-ttu-id="9ad69-164">Microsoft hat zwei Arten von Telefonnummern zur Verfügung: *Teilnehmer* (Benutzer) Nummern, die Benutzern in Ihrer Organisation zugewiesen werden können, und *Dienst* Nummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen, die eine höhere gleichzeitige Anrufkapazität als Teilnehmer Nummern aufweisen und Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="9ad69-164">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="9ad69-165">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-165">Ask yourself</span></span>|<span data-ttu-id="9ad69-166">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-166">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9ad69-167">Welche Benutzer Standorte benötigen neue Telefonnummern von Microsoft?</span><span class="sxs-lookup"><span data-stu-id="9ad69-167">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="9ad69-168">Informationen zum Abrufen von Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-168">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="9ad69-169">Welche Art von Telefonnummer (Abonnent oder Dienst) benötige ich?</span><span class="sxs-lookup"><span data-stu-id="9ad69-169">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="9ad69-170">Wenn Sie die Art der benötigten Telefonnummer ermitteln möchten, finden Sie unter [verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)werden.</span><span class="sxs-lookup"><span data-stu-id="9ad69-170">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="9ad69-171">Wie kann ich vorhandene Telefonnummern an Teams portieren?</span><span class="sxs-lookup"><span data-stu-id="9ad69-171">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="9ad69-172">Weitere Informationen finden Sie unter [übertragen von Telefonnummern an Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-172">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="9ad69-173">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="9ad69-173">Dial plans</span></span>

<span data-ttu-id="9ad69-174">Ein Wählplan in der Telefon System Funktion von Microsoft 365 oder Office 365 ist eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen.</span><span class="sxs-lookup"><span data-stu-id="9ad69-174">A dial plan in the Phone System feature of Microsoft 365 or Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="9ad69-175">Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).</span><span class="sxs-lookup"><span data-stu-id="9ad69-175">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="9ad69-176">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-176">Ask yourself</span></span>|<span data-ttu-id="9ad69-177">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-177">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9ad69-178">Benötigt meine Organisation einen angepassten Wählplan?</span><span class="sxs-lookup"><span data-stu-id="9ad69-178">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="9ad69-179">Informationen zum ermitteln, ob Sie einen benutzerdefinierten Wählplan benötigen, finden Sie unter [Planen von Mandanten Wählplänen](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9ad69-179">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="9ad69-180">Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden?</span><span class="sxs-lookup"><span data-stu-id="9ad69-180">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="9ad69-181">Informationen zum Hinzufügen von Benutzern zu einem benutzerdefinierten Wählplan in PowerShell finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-181">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="9ad69-182">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="9ad69-182">Call queues</span></span>

<span data-ttu-id="9ad69-p107">Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ad69-p107">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="9ad69-185">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-185">Ask yourself</span></span>|<span data-ttu-id="9ad69-186">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-186">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9ad69-187">Benötigt meine Organisation Anrufwarteschlangen?</span><span class="sxs-lookup"><span data-stu-id="9ad69-187">Does my organization need call queues?</span></span> | <span data-ttu-id="9ad69-188">Weitere Informationen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten Ihres Telefonsystems](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-188">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="9ad69-189">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="9ad69-189">Auto attendants</span></span>

<span data-ttu-id="9ad69-190">Sie können automatische Telefonzentralenverwenden, um ein Menüsystem für Ihre Organisation zu erstellen. Dann können externe und interne Anrufer durch das Menüsystem navigieren, um Benutzer in der Firma oder Abteilungen in der Organisation zu finden und sie anzurufen oder Anrufe an sie durchzustellen.</span><span class="sxs-lookup"><span data-stu-id="9ad69-190">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="9ad69-191">Frage</span><span class="sxs-lookup"><span data-stu-id="9ad69-191">Ask yourself</span></span>|<span data-ttu-id="9ad69-192">Aktion</span><span class="sxs-lookup"><span data-stu-id="9ad69-192">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9ad69-193">Benötigt meine Organisation automatische Telefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="9ad69-193">Does my organization need auto attendants?</span></span> | <span data-ttu-id="9ad69-194">Weitere Informationen finden Sie unter [Was sind automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md) und [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="9ad69-194">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="9ad69-195">Geräte</span><span class="sxs-lookup"><span data-stu-id="9ad69-195">Devices</span></span>

<span data-ttu-id="9ad69-196">Weitere Informationen zu unterstützten Geräten finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="9ad69-196">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="9ad69-197">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ad69-197">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="9ad69-198">IP-Telefone</span><span class="sxs-lookup"><span data-stu-id="9ad69-198">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9ad69-199">USB-Audio- und -Videogeräte</span><span class="sxs-lookup"><span data-stu-id="9ad69-199">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9ad69-200">Intelligente Kommunikation für Geräte</span><span class="sxs-lookup"><span data-stu-id="9ad69-200">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


