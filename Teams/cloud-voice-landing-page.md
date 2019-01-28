---
title: Cloud-VoIP in Microsoft-Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Zielseite für die Bereitstellung von Cloud-VoIP in Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f81c9a2c158781303e0d0db67448ae19964cb8d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595401"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="9d5fd-103">Cloud-VoIP in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="9d5fd-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="9d5fd-104">Sie haben den [Einstieg in die](get-started-with-teams-quick-start.md)abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9d5fd-105">Sie haben, Teams mit [Chat, Teams, Kanäle, &-apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9d5fd-106">Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="9d5fd-107">Sie können nun Cloud Voice-Funktionen für Ihre Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="9d5fd-108">Cloud-VoIP bietet Funktionen für (Private Branch Exchange, PBX) und Optionen für die Verbindung zu im Public Switched Telephone Network, (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="9d5fd-109">In diesem Artikel Unterstützung bei der Entscheidung, ob Sie die Cloud VoIP Standardeinstellungen, basierend auf Ihrer Organisation Profil und geschäftlichen Anforderungen, und klicken Sie dann Sie über jede Änderung geführt ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="9d5fd-110">Wir haben die Einstellungen in zwei Gruppen, beginnend mit der Kerngruppe von [Änderungen, die Sie eher Stellen sind](#core-deployment-decisions)aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="9d5fd-111">Die zweite Gruppe enthält die [zusätzliche Einstellungen](#additional-deployment-decisions) , die Sie möglicherweise konfigurieren basierend auf der Anforderungen Ihrer Organisation, möchten.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="9d5fd-112">Es wird empfohlen, dass alle Organisationen über den Core Entscheidungen arbeiten, und Sie, wenn Ihre Organisation zusätzliche Anforderungen umfasst das folgenden Material überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="9d5fd-113">Erfahren Sie mehr über Cloud-VoIP</span><span class="sxs-lookup"><span data-stu-id="9d5fd-113">Learn more about cloud voice</span></span>

<span data-ttu-id="9d5fd-114">Die folgenden Artikel enthalten weitere Informationen zum Bereitstellen und Verwenden von Cloud-VoIP-Funktionen in Teams:</span><span class="sxs-lookup"><span data-stu-id="9d5fd-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="9d5fd-115">Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="9d5fd-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="9d5fd-116">Telefonsystem mit dem Plan aufrufen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-116">Phone System with Calling Plan</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="9d5fd-117">Telefon System direkten Routing</span><span class="sxs-lookup"><span data-stu-id="9d5fd-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="9d5fd-118">Cloud Voice-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9d5fd-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="9d5fd-119">Microsoft-telefonielösungen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="9d5fd-120">Die folgenden Sitzung Weitere Informationen zum Telefonsystem Video: [Einführung in das Telefonsystem in Microsoft-Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="9d5fd-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="9d5fd-121">Zentrale Bereitstellung Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-121">Core deployment decisions</span></span>

<span data-ttu-id="9d5fd-122">Dies sind die Einstellungen, die meisten Organisationen (falls die Standardeinstellungen des Teams für die Organisation nicht funktionieren) ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="9d5fd-123">Telefonsystem (Office 365)</span><span class="sxs-lookup"><span data-stu-id="9d5fd-123">Phone System (Office 365)</span></span>

<span data-ttu-id="9d5fd-124">Telefonsystem ist Microsoft Technologie zum Aktivieren der Remote Call Control und Funktionen in der Office 365-Cloud (Private Branch Exchange, PBX).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="9d5fd-125">Telefonsystem können Sie das bestehende System (Private Branch Exchange, PBX) durch eine Reihe von Features von Office 365 direkt bereitgestellt und eng integriert in das Unternehmen produktivitätserfahrung der Cloud zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="9d5fd-126">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-126">Ask yourself</span></span>|<span data-ttu-id="9d5fd-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9d5fd-128">In welche Standorte oder Büros implementieren ich Telefonsystem?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="9d5fd-129">Weitere Informationen zu Telefonsystem finden Sie unter [Was ist Telefonsystem in Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="9d5fd-130">Verbindung mit der Public Switched Telephone Telefonnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="9d5fd-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="9d5fd-131">Um das Telefonsystem zu im Public Switched Telephone Network, (PSTN) anschließen, damit die Benutzer auf der ganzen Welt Telefonanrufe tätigen können, müssen Sie basierte auf Ihrer geschäftlicher Bedarf Optionen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="9d5fd-132">Stellen Sie sich Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9d5fd-132">Ask yourself the following:</span></span>


|<span data-ttu-id="9d5fd-133">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-133">Ask yourself</span></span>|<span data-ttu-id="9d5fd-134">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9d5fd-135">Führen Sie ich möchte Microsoft aufrufen planen als meines Telefonie verwenden?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="9d5fd-136">Weitere Informationen finden Sie unter [Telefonsystem mit plant aufrufen](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="9d5fd-137">Benötige ich meinen eigenen Telefonie Netzbetreiber verwenden?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="9d5fd-138">Weitere Informationen finden Sie unter [Telefonsystem mit direktem Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="9d5fd-139">Zusätzliche Bereitstellung Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-139">Additional deployment decisions</span></span>

<span data-ttu-id="9d5fd-140">Sie möchten die Einstellungen für den folgenden ändern basierend auf Ihrer Organisation Anforderungen und Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="9d5fd-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="9d5fd-141">Voicemail</span><span class="sxs-lookup"><span data-stu-id="9d5fd-141">Voicemail</span></span>
- <span data-ttu-id="9d5fd-142">Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="9d5fd-142">Calling identity</span></span>
- <span data-ttu-id="9d5fd-143">Telefonnummern von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="9d5fd-144">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="9d5fd-144">Dial plans</span></span>
- <span data-ttu-id="9d5fd-145">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-145">Call queues</span></span>
- <span data-ttu-id="9d5fd-146">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="9d5fd-147">Voicemail</span><span class="sxs-lookup"><span data-stu-id="9d5fd-147">Voicemail</span></span>

<span data-ttu-id="9d5fd-148">Telefon System Voicemail, unterstützt von Azure Voicemail-Dienste unterstützt Voicemail bandbreitenbeschränkungen zu nur Exchange-Postfächern und Drittanbieter-e-Mail-Systemen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-148">Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="9d5fd-149">Voicemail für Telefonsysteme umfasst Voicemailtranskription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-149">Phone System voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="9d5fd-150">Ihre geschäftsanforderungen erfordern möglicherweise, Voicemail Lautschrift für bestimmte Benutzer oder alle Benutzer in der gesamten Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="9d5fd-151">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-151">Ask yourself</span></span>|<span data-ttu-id="9d5fd-152">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d5fd-153">Möchte ich Telefonsystem Voicemail aktivieren?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-153">Do I want to enable Phone System voicemail?</span></span> | <span data-ttu-id="9d5fd-154">Voicemail-Setup-Verfahren finden Sie unter [Einrichten von Voicemail Telefonsystem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-154">For voicemail setup procedures, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="9d5fd-155">Möchte ich Voicemail Lautschrift für einige oder alle Benutzer aktivieren?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="9d5fd-156">Um Voicemail Lautschrift deaktivieren, finden Sie unter [Festlegen von Voicemail Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="9d5fd-157">Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="9d5fd-157">Calling identity</span></span>

<span data-ttu-id="9d5fd-158">Alle ausgehenden Anrufe verwenden standardmäßig die zugewiesene Telefonnummer als aufrufende Identität (Anrufer-ID).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="9d5fd-159">Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="9d5fd-160">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-160">Ask yourself</span></span>|<span data-ttu-id="9d5fd-161">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9d5fd-162">Soll so aktivieren oder Deaktivieren der Anrufer-ID werden?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="9d5fd-163">Ändern oder die Anrufer-ID zu blockieren, finden Sie unter [Legen Sie die Anrufer-ID für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="9d5fd-164">Telefonnummern von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="9d5fd-165">Microsoft verfügt über zwei Arten von Telefonnummern zur Verfügung: *Abonnenten* (Benutzer) Zahlen, die Benutzer in Ihrer Organisation zugewiesen werden können, und *Service* Zahlen als gebührenpflichtige oder gebührenfreie Service Numbers höheren gleichzeitige angerufen werden verfügbar Kapazität als Abonnenten Zahlen und Diensten wie etwa Audiokonferenzen, automatischen Telefonzentralen oder rufen Sie Warteschlangen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="9d5fd-166">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-166">Ask yourself</span></span>|<span data-ttu-id="9d5fd-167">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9d5fd-168">Welche Benutzerstandorte benötigen Sie neue Telefonnummern von Microsoft?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="9d5fd-169">Informationen zum Abrufen von Telefonnummern finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Abrufen von Telefonnummern für Ihre Benutzer](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="9d5fd-170">Der Typ der Telefonnummer (Abonnenten oder Dienst) benötige ich?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="9d5fd-171">Zur einfacheren wählen Sie den Typ der Telefonnummer, die Sie benötigen, finden Sie unter [verschiedenen Arten von Telefonnummern für den Aufruf von plant verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="9d5fd-172">Wie kann ich vorhandene Rufnummern Port zu Office 365?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="9d5fd-173">Weitere Informationen finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="9d5fd-174">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="9d5fd-174">Dial plans</span></span>

<span data-ttu-id="9d5fd-175">Ein Wählplan in das Telefonsystem Feature von Office 365 ist, dass eine Reihe von Normalisierungsregeln, die Übersetzen von Telefonnummern in ein anderes Format (normalerweise e. 164-Format) für Anrufberechtigungen und Anrufrouting gewählt.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="9d5fd-176">Weitere Informationen zu Wählplänen finden Sie unter [Was Wählpläne sind?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9d5fd-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="9d5fd-177">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-177">Ask yourself</span></span>|<span data-ttu-id="9d5fd-178">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d5fd-179">Werden meine Organisation für eine angepasste Wählplan benötigt?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="9d5fd-180">Um zu bestimmen, wenn Sie einen benutzerdefinierten Wählplan benötigen, finden Sie unter [Planen Mandanten Wählpläne](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9d5fd-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="9d5fd-181">Welche Benutzer benötigen einen angepasste Wählplan, und welche Mandanten Wählplan sollte für jeden Benutzer werden zugewiesen?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="9d5fd-182">Zum Hinzufügen von Benutzern zu einem benutzerdefinierten Wählplan in PowerShell finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="9d5fd-183">Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-183">Call queues</span></span>

<span data-ttu-id="9d5fd-184">System-Telefonanruf Warteschlangen enthalten Ansage, die verwendet werden, wenn angerufen eine Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und für den nächsten verfügbaren Anruf-Agent zum Verarbeiten des Anrufs beim Personen die Möglichkeit zum Suchen, die Anruf Musik in der Warteschleife hören sind.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-184">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="9d5fd-185">Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="9d5fd-186">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-186">Ask yourself</span></span>|<span data-ttu-id="9d5fd-187">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d5fd-188">Ruft meiner Organisation Warteschlangen auf müssen?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-188">Does my organization need call queues?</span></span> | <span data-ttu-id="9d5fd-189">Weitere Informationen finden Sie unter [erstellen eine Telefonsystem Anruf Warteschlange](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten von Ihrem Telefonsystem](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-189">For more information, see [Create a Phone System call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="9d5fd-190">Automatische Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="9d5fd-190">Auto attendants</span></span>

<span data-ttu-id="9d5fd-191">Telefonsystem Telefonzentralen verwendet werden können, um ein Menüsystem für Ihre Organisation zu erstellen, externe und interne Anrufer können, über ein Menüsystem platzieren, und durchstellen von Anrufen an Unternehmen Benutzer oder Abteilungen in Ihrer Organisation verschieben.</span><span class="sxs-lookup"><span data-stu-id="9d5fd-191">Phone System auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="9d5fd-192">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="9d5fd-192">Ask yourself</span></span>|<span data-ttu-id="9d5fd-193">Aktion</span><span class="sxs-lookup"><span data-stu-id="9d5fd-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d5fd-194">Werden meine Organisation für automatische Telefonzentralen benötigt?</span><span class="sxs-lookup"><span data-stu-id="9d5fd-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="9d5fd-195">Weitere Informationen finden Sie unter [Was sind Telefonsystem automatischen Telefonzentralen](what-are-phone-system-auto-attendants.md) und [Richten Sie eine automatische Telefonzentrale Telefonsystem](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="9d5fd-195">For more information, see [What are Phone System auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Phone System auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="9d5fd-196">Geräte</span><span class="sxs-lookup"><span data-stu-id="9d5fd-196">Devices</span></span>

<span data-ttu-id="9d5fd-197">Weitere Informationen zu den unterstützten Geräten finden Sie unter den folgenden:</span><span class="sxs-lookup"><span data-stu-id="9d5fd-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="9d5fd-198">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d5fd-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="9d5fd-199">IP-Telefone</span><span class="sxs-lookup"><span data-stu-id="9d5fd-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9d5fd-200">USB-Geräte für audio und video</span><span class="sxs-lookup"><span data-stu-id="9d5fd-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9d5fd-201">Intelligente Communications für Geräte</span><span class="sxs-lookup"><span data-stu-id="9d5fd-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


