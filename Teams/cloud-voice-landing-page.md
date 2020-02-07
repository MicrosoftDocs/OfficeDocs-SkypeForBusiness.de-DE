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
search.appverid: MET150
description: Startseite zum Bereitstellen von Cloud-VoIP in Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8498d8d4f6336bf54f6ae7f9c96540783b54dd1
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825053"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="bcbb4-103">Cloud Voice in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcbb4-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="bcbb4-104">Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="bcbb4-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="bcbb4-106">Vielleichthaben Sie [Besprechungen #a0 Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="bcbb4-107">Nun können Sie Ihren Benutzern Cloud-Sprachfunktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="bcbb4-108">Cloud Voice bietet Funktionen für Private Branch Exchange (PBX) und Optionen zum Herstellen einer Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="bcbb4-109">Dieser Artikel hilft Ihnen bei der Entscheidung, ob Sie die Standardeinstellungen für die Cloud-VoIP basierend auf den Profil-und Geschäftsanforderungen Ihrer Organisation ändern müssen, und führt Sie durch die einzelnen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="bcbb4-110">Wir haben die Einstellungen in zwei Gruppen aufgeteilt, beginnend mit dem Haupt Satz von [Änderungen, die Sie wahrscheinlicher vornehmen werden](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="bcbb4-111">Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="bcbb4-112">Wir empfehlen, dass alle Organisationen die grundlegenden Entscheidungen treffen, und wenn Ihre Organisation zusätzliche Anforderungen hat, überprüfen Sie das folgende Material.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="bcbb4-113">Weitere Informationen zu Cloud-VoIP</span><span class="sxs-lookup"><span data-stu-id="bcbb4-113">Learn more about cloud voice</span></span>

<span data-ttu-id="bcbb4-114">In den folgenden Artikeln finden Sie weitere Informationen zur Bereitstellung und Verwendung von Cloud-Sprachfeatures in Teams:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="bcbb4-115">Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="bcbb4-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="bcbb4-116">Telefonsystem mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="bcbb4-117">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="bcbb4-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="bcbb4-118">Cloud Voice-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="bcbb4-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="bcbb4-119">Microsoft-Telefonielösungen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="bcbb4-120">Schauen Sie sich die folgende Sitzung an, um mehr über das Telefonsystem zu erfahren: [Einführung in das Telefonsystem in Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="bcbb4-121">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="bcbb4-121">Core deployment decisions</span></span>

<span data-ttu-id="bcbb4-122">Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="bcbb4-123">Telefon System (Office 365)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-123">Phone System (Office 365)</span></span>

<span data-ttu-id="bcbb4-124">Telefon System ist die Microsoft-Technologie für die Aktivierung der Anrufsteuerung und der Funktionen für Private Branch Exchange (PBX) in der Office 365-Cloud.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="bcbb4-125">Mit dem Telefonsystem können Sie Ihr vorhandenes Private Branch Exchange (PBX)-System durch eine Reihe von Features ersetzen, die direkt von Office 365 bereitgestellt werden und eng in die Cloud-Produktivitäts Erfahrung des Unternehmens integriert sind.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="bcbb4-126">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-126">Ask yourself</span></span>|<span data-ttu-id="bcbb4-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bcbb4-128">An welchen Speicherorten oder Büros wird das Telefon System implementiert?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="bcbb4-129">Weitere Informationen zum Telefonsystem finden Sie unter [Was ist Telefonsystem in Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="bcbb4-130">Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="bcbb4-131">Wenn Sie das Telefon System mit dem öffentlichen Telefonnetz (PSTN) verbinden möchten, damit Benutzer überall in der Welt Telefonanrufe tätigen können, haben Sie Optionen, die auf Ihren geschäftlichen Anforderungen basieren.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="bcbb4-132">Stellen Sie sich folgende Fragen:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-132">Ask yourself the following:</span></span>


|<span data-ttu-id="bcbb4-133">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-133">Ask yourself</span></span>|<span data-ttu-id="bcbb4-134">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="bcbb4-135">Möchte ich den Microsoft-Anrufplan als meinen Telefonnetzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="bcbb4-136">Weitere Informationen finden Sie unter [Telefon System mit Anrufplänen](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="bcbb4-137">Muss ich meinen eigenen Telefonnetzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="bcbb4-138">Weitere Informationen finden Sie unter [Telefon System mit direktem Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="bcbb4-139">Zusätzliche Bereitstellungsentscheidungen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-139">Additional deployment decisions</span></span>

<span data-ttu-id="bcbb4-140">Basierend auf den Anforderungen und der Konfiguration Ihrer Organisation können Sie die Einstellungen für Folgendes ändern:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="bcbb4-141">Voicemail</span><span class="sxs-lookup"><span data-stu-id="bcbb4-141">Voicemail</span></span>
- <span data-ttu-id="bcbb4-142">Identität des Anrufs</span><span class="sxs-lookup"><span data-stu-id="bcbb4-142">Calling identity</span></span>
- <span data-ttu-id="bcbb4-143">Telefonnummern von Microsoft</span><span class="sxs-lookup"><span data-stu-id="bcbb4-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="bcbb4-144">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="bcbb4-144">Dial plans</span></span>
- <span data-ttu-id="bcbb4-145">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-145">Call queues</span></span>
- <span data-ttu-id="bcbb4-146">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="bcbb4-147">Voicemail</span><span class="sxs-lookup"><span data-stu-id="bcbb4-147">Voicemail</span></span>

<span data-ttu-id="bcbb4-148">Cloud Voicemail, powered by Azure Voicemail Services, unterstützt Voicemail-Einzahlungen nur für Exchange-Postfächer und unterstützt keine e-Mail-Systeme von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="bcbb4-149">Cloud Voicemail umfasst Voicemail-Transkription, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="bcbb4-150">Für Ihre geschäftlichen Anforderungen müssen Sie möglicherweise die Voicemail-Transkription für bestimmte Benutzer oder alle in der Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="bcbb4-151">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-151">Ask yourself</span></span>|<span data-ttu-id="bcbb4-152">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bcbb4-153">Möchte ich Cloud Voicemail aktivieren?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="bcbb4-154">Anweisungen zum Einrichten von Voicemail finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="bcbb4-155">Soll die Sprachübertragung für einige oder alle meine Benutzer aktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="bcbb4-156">Informationen zum Deaktivieren der Voicemail-Transkription finden Sie unter [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="bcbb4-157">Identität des Anrufs</span><span class="sxs-lookup"><span data-stu-id="bcbb4-157">Calling identity</span></span>

<span data-ttu-id="bcbb4-158">Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="bcbb4-159">Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="bcbb4-160">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-160">Ask yourself</span></span>|<span data-ttu-id="bcbb4-161">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bcbb4-162">Soll die Rufnummernanzeige maskiert oder deaktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="bcbb4-163">Informationen zum Ändern oder Blockieren der Rufnummernanzeige finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="bcbb4-164">Telefonnummern von Microsoft</span><span class="sxs-lookup"><span data-stu-id="bcbb4-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="bcbb4-165">Microsoft hat zwei Arten von Telefonnummern zur Verfügung: *Teilnehmer* (Benutzer) Nummern, die Benutzern in Ihrer Organisation zugewiesen werden können, und *Dienst* Nummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen, die eine höhere gleichzeitige Anrufkapazität als Teilnehmer Nummern aufweisen und Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="bcbb4-166">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-166">Ask yourself</span></span>|<span data-ttu-id="bcbb4-167">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="bcbb4-168">Welche Benutzer Standorte benötigen neue Telefonnummern von Microsoft?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="bcbb4-169">Informationen zum Abrufen von Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="bcbb4-170">Welche Art von Telefonnummer (Abonnent oder Dienst) benötige ich?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="bcbb4-171">Wenn Sie die Art der benötigten Telefonnummer ermitteln möchten, finden Sie unter [verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)werden.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="bcbb4-172">Wie kann ich vorhandene Telefonnummern an Teams portieren?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-172">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="bcbb4-173">Weitere Informationen finden Sie unter [übertragen von Telefonnummern an Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-173">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="bcbb4-174">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="bcbb4-174">Dial plans</span></span>

<span data-ttu-id="bcbb4-175">Ein Wählplan in der Telefon System Funktion von Office 365 ist eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="bcbb4-176">Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="bcbb4-177">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-177">Ask yourself</span></span>|<span data-ttu-id="bcbb4-178">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bcbb4-179">Benötigt meine Organisation einen angepassten Wählplan?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="bcbb4-180">Informationen zum ermitteln, ob Sie einen benutzerdefinierten Wählplan benötigen, finden Sie unter [Planen von Mandanten Wählplänen](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="bcbb4-181">Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="bcbb4-182">Informationen zum Hinzufügen von Benutzern zu einem benutzerdefinierten Wählplan in PowerShell finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="bcbb4-183">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-183">Call queues</span></span>

<span data-ttu-id="bcbb4-p107">Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-p107">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="bcbb4-186">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-186">Ask yourself</span></span>|<span data-ttu-id="bcbb4-187">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bcbb4-188">Benötigt meine Organisation Anrufwarteschlangen?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-188">Does my organization need call queues?</span></span> | <span data-ttu-id="bcbb4-189">Weitere Informationen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten Ihres Telefonsystems](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="bcbb4-190">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="bcbb4-190">Auto attendants</span></span>

<span data-ttu-id="bcbb4-191">Sie können automatische Telefonzentralenverwenden, um ein Menüsystem für Ihre Organisation zu erstellen. Dann können externe und interne Anrufer durch das Menüsystem navigieren, um Benutzer in der Firma oder Abteilungen in der Organisation zu finden und sie anzurufen oder Anrufe an sie durchzustellen.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="bcbb4-192">Frage</span><span class="sxs-lookup"><span data-stu-id="bcbb4-192">Ask yourself</span></span>|<span data-ttu-id="bcbb4-193">Aktion</span><span class="sxs-lookup"><span data-stu-id="bcbb4-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bcbb4-194">Benötigt meine Organisation automatische Telefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="bcbb4-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="bcbb4-195">Weitere Informationen finden Sie unter [Was sind automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md) und [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="bcbb4-196">Geräte</span><span class="sxs-lookup"><span data-stu-id="bcbb4-196">Devices</span></span>

<span data-ttu-id="bcbb4-197">Weitere Informationen zu unterstützten Geräten finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="bcbb4-198">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcbb4-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="bcbb4-199">IP-Telefone</span><span class="sxs-lookup"><span data-stu-id="bcbb4-199">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="bcbb4-200">USB-Audio- und -Videogeräte</span><span class="sxs-lookup"><span data-stu-id="bcbb4-200">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="bcbb4-201">Intelligente Kommunikation für Geräte</span><span class="sxs-lookup"><span data-stu-id="bcbb4-201">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


