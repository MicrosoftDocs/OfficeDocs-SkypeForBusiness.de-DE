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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: Startseite zur Bereitstellung von Cloud Voice in Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92e32950526f12c5da1856ce390ee3e532892681
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483864"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="39bb8-103">Cloud Voice in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39bb8-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="39bb8-104">Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="39bb8-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="39bb8-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39bb8-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="39bb8-106">Sie haben möglicherweise [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39bb8-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="39bb8-107">Jetzt können Sie auch Cloud-Sprachfunktionen für Ihre Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="39bb8-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="39bb8-108">Cloud Voice bietet Funktionen für Nebenstellanlagen (Private Branch Exchange, PBX) und Optionen für die Anbindung an das Telefonfestnetz (Public Switched Telephone Network, PSTN).</span><span class="sxs-lookup"><span data-stu-id="39bb8-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="39bb8-109">Dieser Artikel hilft Ihnen bei der Entscheidung, ob einige der Cloud Voice-Standardeinstellungen geändert werden müssen, berücksichtigt dazu das Profil und die geschäftlichen Anforderungen Ihrer Organisation und führt Sie dann schrittweise durch die einzelnen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="39bb8-109">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="39bb8-110">Wir haben die Einstellungen in zwei Gruppen aufgeteilt und beginnen mit den wichtigsten [Änderungen, die Sie mit größerer Wahrscheinlichkeit vornehmen](#core-deployment-decisions) werden.</span><span class="sxs-lookup"><span data-stu-id="39bb8-110">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="39bb8-111">Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.</span><span class="sxs-lookup"><span data-stu-id="39bb8-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="39bb8-112">Wir empfehlen allen Organisationen, zuerst die grundlegenden Änderungen durchzuführen. Wenn Ihre Organisation zusätzliche Anforderungen hat, sehen Sie sich das folgende Material an.</span><span class="sxs-lookup"><span data-stu-id="39bb8-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="39bb8-113">Weitere Informationen zu Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="39bb8-113">Learn more about cloud voice</span></span>

<span data-ttu-id="39bb8-114">In den folgenden Artikeln finden Sie weitere Informationen zur Bereitstellung und Verwendung der Cloud Voice-Features in Teams:</span><span class="sxs-lookup"><span data-stu-id="39bb8-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="39bb8-115">Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="39bb8-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="39bb8-116">Telefonsystem mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="39bb8-116">Make my service decisions - Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="39bb8-117">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="39bb8-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="39bb8-118">Cloud Voice-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="39bb8-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="39bb8-119">Microsoft-Telefonielösungen</span><span class="sxs-lookup"><span data-stu-id="39bb8-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/de-DE/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="39bb8-120">Schauen Sie sich die folgende Sitzung an, um mehr über das Telefonsystem zu erfahren: [Einführung in das Telefonsystem in Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="39bb8-120">Watch the following session to learn more about Meetings: [Introduction to Meetings in Microsoft Teams for IT Pros](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="39bb8-121">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="39bb8-121">Core deployment decisions</span></span>

<span data-ttu-id="39bb8-122">Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).</span><span class="sxs-lookup"><span data-stu-id="39bb8-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="39bb8-123">Telefonsystem (Office 365)</span><span class="sxs-lookup"><span data-stu-id="39bb8-123">Phone System (Office 365)</span></span>

<span data-ttu-id="39bb8-124">Das Telefonsystem ist die Technologie von Microsoft, die Anrufsteuerung und Funktionen von Nebenstellenanlagen (Private Branch Exchange, PBX) in der Office 365-Cloud bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="39bb8-124">skypeforbusinessCloudPBX is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud with skype16_online.</span></span> <span data-ttu-id="39bb8-125">Mit dem Telefonsystem haben Sie die Möglichkeit, Ihr vorhandenes Nebenstellenanlagensystem (Private Branch Exchange, PBX) durch einen Satz von Funktionen zu ersetzen, die direkt aus Office 365 heraus bereitgestellt werden und eng in die Cloudproduktivitätserfahrungen Ihres Unternehmens integriert sind.</span><span class="sxs-lookup"><span data-stu-id="39bb8-125">skypeforbusinessCloudPBX allows you to replace your existing PBX system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="39bb8-126">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-126">Ask yourself</span></span>|<span data-ttu-id="39bb8-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="39bb8-128">An welchen Benutzerstandorten oder in welchen Büros wird das Telefonsystem implementiert?</span><span class="sxs-lookup"><span data-stu-id="39bb8-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="39bb8-129">Weitere Informationen zum Telefonsystem finden Sie unter [Was ist das Telefonsystem in Office 365?](what-is-phone-system-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="39bb8-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="39bb8-130">Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN)</span><span class="sxs-lookup"><span data-stu-id="39bb8-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="39bb8-131">Wenn Sie das Telefonsystem mit dem Festnetz verbinden möchten, damit Benutzer in die ganze Welt Telefonanrufe tätigen können, haben Sie basierend auf Ihren geschäftlichen Anforderungen verschiedene Optionen.</span><span class="sxs-lookup"><span data-stu-id="39bb8-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="39bb8-132">Stellen Sie sich die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="39bb8-132">Ask yourself the following:</span></span>


|<span data-ttu-id="39bb8-133">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-133">Ask yourself</span></span>|<span data-ttu-id="39bb8-134">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="39bb8-135">Möchte ich den Microsoft-Anrufplan als meinen Netzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="39bb8-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="39bb8-136">Weitere Informationen hierzu finden Sie unter [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="39bb8-137">Muss ich meinen bestehenden Netzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="39bb8-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="39bb8-138">Weitere Informationen hierzu finden Sie unter [Telefonsystem mit direktem Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="39bb8-139">Zusätzliche Bereitstellungsentscheidungen</span><span class="sxs-lookup"><span data-stu-id="39bb8-139">Additional deployment decisions</span></span>

<span data-ttu-id="39bb8-140">Je nach den Anforderungen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, folgende Einstellungen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="39bb8-140">You may want to change these settings, based on your organization's needs and configuration.</span></span>

- <span data-ttu-id="39bb8-141">Voicemail</span><span class="sxs-lookup"><span data-stu-id="39bb8-141">Voicemail</span></span>
- <span data-ttu-id="39bb8-142">Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="39bb8-142">Optional: Calling identity</span></span>
- <span data-ttu-id="39bb8-143">Telefonnummern von Microsoft</span><span class="sxs-lookup"><span data-stu-id="39bb8-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="39bb8-144">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="39bb8-144">Dial plans</span></span>
- <span data-ttu-id="39bb8-145">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="39bb8-145">Call queues</span></span>
- <span data-ttu-id="39bb8-146">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="39bb8-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="39bb8-147">Voicemail</span><span class="sxs-lookup"><span data-stu-id="39bb8-147">Voicemail</span></span>

<span data-ttu-id="39bb8-148">Cloud-Voicemail, unterstützt von Azure Voicemail-Diensten, unterstützt die Ablage von Voicemails nur in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39bb8-148">Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailbox only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="39bb8-149">Cloud-Voicemail umfasst die Voicemailaufzeichnung. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="39bb8-149">Phone System voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="39bb8-150">Möglicherweise muss Ihr Unternehmen die Voicemailaufzeichnung für bestimmte Benutzer oder für alle in der gesamten Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="39bb8-150">Your business might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="39bb8-151">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-151">Ask yourself</span></span>|<span data-ttu-id="39bb8-152">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="39bb8-153">Möchte ich die Cloud-Voicemail aktivieren?</span><span class="sxs-lookup"><span data-stu-id="39bb8-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="39bb8-154">Das Vorgehen für die Einrichtung von Voicemail finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="39bb8-155">Möchte ich die Voicemailaufzeichnung für einige oder alle meiner Benutzer aktivieren?</span><span class="sxs-lookup"><span data-stu-id="39bb8-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="39bb8-156">Wenn Sie die Aufzeichnung von Voicemails deaktivieren möchten, lesen Sie [Einrichten von Voicemailrichtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="39bb8-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="39bb8-157">Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="39bb8-157">Optional: Calling identity</span></span>

<span data-ttu-id="39bb8-158">Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet.</span><span class="sxs-lookup"><span data-stu-id="39bb8-158">By default, all outbound calls use the assigned phone number for the calling identity (Caller ID).</span></span> <span data-ttu-id="39bb8-159">Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.</span><span class="sxs-lookup"><span data-stu-id="39bb8-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="39bb8-160">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-160">Ask yourself</span></span>|<span data-ttu-id="39bb8-161">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="39bb8-162">Möchte ich die Anrufer-ID maskieren oder deaktivieren?</span><span class="sxs-lookup"><span data-stu-id="39bb8-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="39bb8-163">Informationen zum Ändern oder Blockieren der Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-163">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="39bb8-164">Telefonnummern von Microsoft</span><span class="sxs-lookup"><span data-stu-id="39bb8-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="39bb8-165">Microsoft verfügt über zwei Arten von Telefonnummern: Nummern für *Abonnenten* (Benutzer), die Benutzern in Ihrer Organisation zugewiesen werden können, sowie *Dienstnummern*, die gebührenpflichtig und gebührenfrei verfügbar sind. Letztere bieten eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="39bb8-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="39bb8-166">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-166">Ask yourself</span></span>|<span data-ttu-id="39bb8-167">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="39bb8-168">Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft?</span><span class="sxs-lookup"><span data-stu-id="39bb8-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="39bb8-169">Informationen zum Abrufen neuer Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Reservieren von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="39bb8-170">Welche Art von Telefonnummer (Abonnenten oder Dienst) benötige ich?</span><span class="sxs-lookup"><span data-stu-id="39bb8-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="39bb8-171">Informationen, wie Sie die Art der Telefonnummer auswählen, die Sie benötigen, finden Sie unter [Unterschiedliche Arten von Telefonnummern für Anrufpläne](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="39bb8-172">Wie kann ich vorhandene Telefonnummern nach Office 365 übertragen?</span><span class="sxs-lookup"><span data-stu-id="39bb8-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="39bb8-173">Weitere Informationen finden Sie unter [Übertragen von Telefonnummern nach Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="39bb8-174">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="39bb8-174">Dial plans</span></span>

<span data-ttu-id="39bb8-175">Bei einem Wählplan in der Telefonsystemfunktion von Office 365 handelt es sich um eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format E.164) übersetzt, um Anrufe zu autorisieren und weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="39bb8-175">A Dial Plan, in the Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="39bb8-176">Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).</span><span class="sxs-lookup"><span data-stu-id="39bb8-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="39bb8-177">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-177">Ask yourself</span></span>|<span data-ttu-id="39bb8-178">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="39bb8-179">Benötigt meine Organisation einen angepassten Wählplan?</span><span class="sxs-lookup"><span data-stu-id="39bb8-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="39bb8-180">Um zu ermitteln, ob Sie einen angepassten Wählplan benötigen, sehen Sie sich den Abschnitt [Planen eines Mandantenwählplans](what-are-dial-plans.md#planning-for-tenant-dial-plans) an.</span><span class="sxs-lookup"><span data-stu-id="39bb8-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans).</span></span>|
<span data-ttu-id="39bb8-181">Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden?</span><span class="sxs-lookup"><span data-stu-id="39bb8-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="39bb8-182">Wenn Sie Benutzer mithilfe von PowerShell zu einem benutzerdefinierten Wählplan hinzufügen möchten, lesen Sie den Abschnitt [Erstellen und Verwalten von Wahlplänen](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-182">To add users to a customized dial plan using PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="39bb8-183">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="39bb8-183">Call queues</span></span>

<span data-ttu-id="39bb8-184">Cloudanrufwarteschleifen beinhalten die telefonischen Begrüßungen Ihrer Organisation sowie die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Ansprechpartner zu suchen, während für den Anrufer Musik abgespielt wird.</span><span class="sxs-lookup"><span data-stu-id="39bb8-184">Skype for Business Online Cloud PBX Call Queues include greetings that are used when someone calls into a phone number for your organization, the ability to automatically put the calls on hold and search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="39bb8-185">Sie können eine oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="39bb8-185">You can create a single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="39bb8-186">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-186">Ask yourself</span></span>|<span data-ttu-id="39bb8-187">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="39bb8-188">Benötigt meine Organisation Anrufwarteschleifen?</span><span class="sxs-lookup"><span data-stu-id="39bb8-188">Does my organization need call queues?</span></span> | <span data-ttu-id="39bb8-189">Weitere Informationen hierzu finden Sie unter [Erstellen einer Cloudanrufwarteschleife](https://docs.microsoft.com/de-DE/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten des Telefonsystems](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="39bb8-190">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="39bb8-190">Auto attendants</span></span>

<span data-ttu-id="39bb8-191">Sie können automatische Telefonzentralen verwenden, um ein Menüsystem für Ihre Organisation zu erstellen. Dann können externe und interne Anrufer durch das Menüsystem navigieren, um Benutzer in der Firma oder Abteilungen in der Organisation zu finden und sie anzurufen oder Anrufe an sie durchzustellen.</span><span class="sxs-lookup"><span data-stu-id="39bb8-191">Skype for Business Cloud PBX auto attendants can be used to create a menu system for your organization that lets external and internal callers move through menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="39bb8-192">Frage</span><span class="sxs-lookup"><span data-stu-id="39bb8-192">Ask yourself</span></span>|<span data-ttu-id="39bb8-193">Aktion</span><span class="sxs-lookup"><span data-stu-id="39bb8-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="39bb8-194">Benötigt meine Organisation automatische Telefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="39bb8-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="39bb8-195">Weitere Informationen finden Sie unter [Was sind automatische Cloudtelefonzentralen](what-are-phone-system-auto-attendants.md) und [Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="39bb8-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="39bb8-196">Geräte</span><span class="sxs-lookup"><span data-stu-id="39bb8-196">Devices</span></span>

<span data-ttu-id="39bb8-197">Weitere Informationen zu unterstützten Geräten finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="39bb8-197">For more information about archiving, see the following topics:</span></span>

- [<span data-ttu-id="39bb8-198">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39bb8-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="39bb8-199">IP-Telefone</span><span class="sxs-lookup"><span data-stu-id="39bb8-199">IP phones</span></span>](https://docs.microsoft.com/de-DE/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="39bb8-200">USB-Audio- und -Videogeräte</span><span class="sxs-lookup"><span data-stu-id="39bb8-200">USB audio and video devices</span></span>](https://docs.microsoft.com/de-DE/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="39bb8-201">Intelligente Kommunikation für Geräte</span><span class="sxs-lookup"><span data-stu-id="39bb8-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


