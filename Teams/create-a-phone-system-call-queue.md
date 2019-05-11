---
title: Erstellen einer Anrufwarteschlange
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Hier erfahren Sie, wie eingerichtet Telefonsystem für Cloud Anruf Warteschlangen, Ihnen eine Organisationseinheit Begrüßung Musik in der Warteschleife, und Umleiten von Anrufen Agents in Verteilerlisten und Sicherheitsgruppen aufrufen zu erteilen. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 844ea569da6f59def0ee4df7739456c1f10e7dff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902871"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="721a7-104">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="721a7-104">Create a Cloud call queue</span></span>

<span data-ttu-id="721a7-105">Cloud Anruf Warteschlangen enthalten Ansage, die verwendet werden, wenn jemand anruft eine angegebene Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und die Möglichkeit, suchen Sie für den nächsten verfügbaren Anruf-Agent den Anruf beim Menschen Anruf behandeln Anhören von Musik in der Warteschleife.</span><span class="sxs-lookup"><span data-stu-id="721a7-105">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="721a7-106">Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="721a7-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="721a7-107">Cloud Anruf Warteschlangen bieten:</span><span class="sxs-lookup"><span data-stu-id="721a7-107">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="721a7-108">Eine Begrüßung der Organisation</span><span class="sxs-lookup"><span data-stu-id="721a7-108">An organizational greeting.</span></span>
- <span data-ttu-id="721a7-109">Musik, während die wartenden Anrufer gehalten werden</span><span class="sxs-lookup"><span data-stu-id="721a7-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="721a7-110">Umleiten von Anrufen Agents in e-Mail-aktivierte Verteilerlisten und Sicherheitsgruppen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="721a7-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="721a7-111">Einstellungen für Anruf Warteschlange maximale Größe, Timeout und Optionen für die Behandlung Anruf tätigen.</span><span class="sxs-lookup"><span data-stu-id="721a7-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="721a7-112">Wenn Sie an eine Telefonnummer angerufen werden, das eine Warteschlange Anruf über ein [Benutzerkonto Ressource](manage-resource-accounts.md)zugeordnet ist, hören sie eine Begrüßung erste (sofern eine eingerichtet ist), und anschließend wird in die Warteschlange aufgenommen werden und für den nächsten verfügbaren Anruf Agent warten.</span><span class="sxs-lookup"><span data-stu-id="721a7-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="721a7-113">Die Person einwählen, werden Musik hören, während sie sind in der Warteschleife warten, und die Anrufe, um den Anruf-Agenten auf *First In, First Out* (FIFO) Reihenfolge angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="721a7-114">Alle Anrufe, die in der Warteschlange werden mit einer der folgenden Methoden verteilt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="721a7-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="721a7-115">Mit attendant routing wird der erste Aufruf in der Warteschlange alle Agents gleichzeitig anrufen.</span><span class="sxs-lookup"><span data-stu-id="721a7-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="721a7-116">Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.</span><span class="sxs-lookup"><span data-stu-id="721a7-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="721a7-117">Routing von eingehenden Anrufen ist Round-Robin ausgeglichen, sodass jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="721a7-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="721a7-118">Telefonisten, die **Offline**sind, ihre Anwesenheit auf **Nicht stören** festgelegt haben, oder haben sich von der Warteschleife abgemeldet haben, werden nicht angerufen.</span><span class="sxs-lookup"><span data-stu-id="721a7-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="721a7-119">Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.</span><span class="sxs-lookup"><span data-stu-id="721a7-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="721a7-120">Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.</span><span class="sxs-lookup"><span data-stu-id="721a7-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="721a7-121">Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="721a7-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="721a7-122">Schritt 1: Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="721a7-122">Step 1 - Get started</span></span>

<span data-ttu-id="721a7-123">Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:</span><span class="sxs-lookup"><span data-stu-id="721a7-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="721a7-124">Eine Warteschlange Anruf ist erforderlich, um ein Ressourcenkonto zugeordneten verfügen.</span><span class="sxs-lookup"><span data-stu-id="721a7-124">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="721a7-125">Details auf Ressourcenkonten finden Sie unter [Manage Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="721a7-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="721a7-126">Wenn Sie eine direkte Routing Number zuweisen möchten, müssen Sie erwerben und weisen Sie die folgenden Lizenzen der Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on\).</span><span class="sxs-lookup"><span data-stu-id="721a7-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="721a7-127">Wenn Sie stattdessen eine Microsoft-Dienst Zahl zuordnen möchten, müssen Sie erwerben und weisen Sie Ihr Ressourcenkonto folgenden Lizenzen \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on und Aufrufen planen\).</span><span class="sxs-lookup"><span data-stu-id="721a7-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="721a7-128">Sie müssen nur die Ressourcenkonten mit einer Telefonnummer, die ihnen zugewiesenen lizenzieren.</span><span class="sxs-lookup"><span data-stu-id="721a7-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="721a7-129">In einer geschachtelten automatische Telefonzentrale oder ein Anruf die Warteschlange müssen Sie nicht den Rest der automatischen Telefonzentralen lizenzieren, oder rufen Sie Warteschlangen aus, wenn keine ihnen zugeordnete Telefonnummern vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="721a7-129">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span> 

> [!NOTE] 
> <span data-ttu-id="721a7-130">Direkte Routing Service Zahlen für die automatische Telefonzentrale und Anruf Warteschlangen werden für Microsoft-Teams, Benutzer und nur Agents unterstützt.</span><span class="sxs-lookup"><span data-stu-id="721a7-130">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="721a7-131">Microsoft arbeitet eine entsprechende Lizenzierungsmodell für Anwendungen wie Cloud automatische Telefonzentrale und den Anruf-Warteschlangen für an jetzt Sie das Benutzerlizenzierung Objektmodell verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="721a7-131">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="721a7-132">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans.</span><span class="sxs-lookup"><span data-stu-id="721a7-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="721a7-133">Finden Sie unter [Skype für Business Lizenzen zuweisen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Lizenzen für Microsoft-Teams zuweisen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="721a7-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="721a7-134">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="721a7-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="721a7-135">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="721a7-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="721a7-136">Weitere Informationen zu Office 365 aufrufen plant, finden Sie unter [Telefonsystem und plant aufrufen](calling-plan-landing-page.md) und [Für Office 365-Pläne aufrufen](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="721a7-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="721a7-137">Sie können nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder aus einem anderen Dienstanbieter in der Cloud Anruf Warteschlangen übertragen.</span><span class="sxs-lookup"><span data-stu-id="721a7-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="721a7-138">Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.</span><span class="sxs-lookup"><span data-stu-id="721a7-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="721a7-139">Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="721a7-140">Wenn Sie eingehende Anrufe aus einer Cloud-Anruf-Warteschlange verteilen, werden diese Clients für Call-Agenten unterstützt:</span><span class="sxs-lookup"><span data-stu-id="721a7-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="721a7-141">Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)</span><span class="sxs-lookup"><span data-stu-id="721a7-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="721a7-142">Desktopclient von Lync 2013 (32- und 64-Bit-Version)</span><span class="sxs-lookup"><span data-stu-id="721a7-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="721a7-143">Alle IP-Telefon-Modelle für die Microsoft-Teams, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="721a7-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="721a7-144">Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="721a7-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="721a7-145">Mac Skype for Business-Client (Version 16.8.196 und höher)</span><span class="sxs-lookup"><span data-stu-id="721a7-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="721a7-146">Android Skype for Business-Client (Version 6.16.0.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="721a7-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="721a7-147">iPhone Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="721a7-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="721a7-148">Mac Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="721a7-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="721a7-149">Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="721a7-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="721a7-150">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="721a7-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="721a7-151">Microsoft-Teams, iPhone-app</span><span class="sxs-lookup"><span data-stu-id="721a7-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="721a7-152">Microsoft-Teams, Android-app</span><span class="sxs-lookup"><span data-stu-id="721a7-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="721a7-153">Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern</span><span class="sxs-lookup"><span data-stu-id="721a7-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="721a7-154">Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie Ihre bestehenden kostenpflichtigen oder gebührenfreien Servicenummern einrichten oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="721a7-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="721a7-155">Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="721a7-156">Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) oder wenn Sie eine vorhandene Servicenummer durchstellen möchten, finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="721a7-156">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="721a7-157">Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="721a7-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="721a7-158">Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="721a7-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="721a7-159">Wenn Sie auch automatische Telefonzentralen festlegen, müssen Sie nur die wichtigsten Telefonzentrale Ressourcenkonto weisen Sie eine Telefonnummer ein, und klicken Sie dann direkte Anrufer an die Warteschlange Anruf.</span><span class="sxs-lookup"><span data-stu-id="721a7-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="721a7-160">Wenn dies der Fall ist, müssen die Anruf-Warteschlange erstellt werden, bevor Sie eine Option in der automatischen Telefonzentrale erstellen können, die die Warteschlange Anruf auswählt.</span><span class="sxs-lookup"><span data-stu-id="721a7-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="721a7-161">Schritt 3: Erstellen einer neuen Warteschleife der Anruf</span><span class="sxs-lookup"><span data-stu-id="721a7-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="721a7-162">Jeder Anruf Warteschlange ist erforderlich, um einer zugeordneten [Ressource-Konto](manage-resource-accounts.md)haben.</span><span class="sxs-lookup"><span data-stu-id="721a7-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="721a7-163">Sie müssen das Ressourcenkonto erstellen und dann können Sie es an die Warteschlange Anruf zuordnen.</span><span class="sxs-lookup"><span data-stu-id="721a7-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="721a7-164">Verwenden das Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="721a7-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="721a7-165">In der **Microsoft-Teams, Administrationscenter**, **VoIP** >  **aufrufen, Warteschlangen**, klicken Sie dann auf **+ Neues hinzufügen**:</span><span class="sxs-lookup"><span data-stu-id="721a7-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="721a7-166">Festlegen des Anruf Warteschlange Display Name und Ressource-Kontos</span><span class="sxs-lookup"><span data-stu-id="721a7-166">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="721a7-168">![Nummer 1](media/sfbcallout1.png)
**Name** Geben Sie einen aussagekräftigen Anzeigenamen für die Warteschlange Anruf.</span><span class="sxs-lookup"><span data-stu-id="721a7-168">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="721a7-169">Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="721a7-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="721a7-170">Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="721a7-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Nummer 2](media/sfbcallout2.png)

<span data-ttu-id="721a7-172">**Hinzufügen von Konten** Wählen Sie eine Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="721a7-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="721a7-173">Das Ressourcenkonto kann oder keiner Service gebührenpflichtige oder gebührenfreie Telefonnummer für die Warteschlange Anruf zugeordnet werden, aber jeder Anruf Warteschlange einer zugeordneten Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="721a7-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="721a7-174">Wenn keine vorhanden sind aufgeführt, Sie müssen Service Zahlen und weisen Sie diesem Kontakt ein Ressourcenkonto vor der Erstellung dieser Warteschlange Anruf wie oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="721a7-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="721a7-175">Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="721a7-175">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> <span data-ttu-id="721a7-176">Sie müssen ein Ressourcenkonto wie unter [Verwalten Ressourcenkonten in Teams](manage-resource-accounts.md) , wenn Sie Ihre Anruf Warteschlange eine jeweilige Rufnummer haben soll erstellen.</span><span class="sxs-lookup"><span data-stu-id="721a7-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="721a7-177">Wenn Sie möchten oder einer **Domäne zuweisen müssen** würden Sie dazu das Ressourcenkonto für die Warteschlange Anruf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="721a7-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="721a7-178">Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="721a7-178">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

<span data-ttu-id="721a7-181">**Begrüßung** ist optional.</span><span class="sxs-lookup"><span data-stu-id="721a7-181">**Greeting** is optional.</span></span> <span data-ttu-id="721a7-182">Dies ist die Ansage, die für Personen, die in Aufrufen an die Warteschlange Anrufnummer wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="721a7-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="721a7-183">Sie können eine Audiodatei (WAV-, MP3 oder WMA-Format) hochladen.</span><span class="sxs-lookup"><span data-stu-id="721a7-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Nummer 2](media/sfbcallout2.png)

<span data-ttu-id="721a7-185">**Musik in der Warteschleife** Sie können entweder übernehmen Sie die Musik in der Warteschleife, die mit der Warteschlange Anruf bereitgestellt, oder Sie können Hochladen einer Audiodatei in WAV, mp3 oder WMA-Formate, die als Ihre benutzerdefinierte Musik in der Warteschleife verwendet.</span><span class="sxs-lookup"><span data-stu-id="721a7-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="721a7-186">Wählen Sie die Optionen für die Anrufbeantwortung</span><span class="sxs-lookup"><span data-stu-id="721a7-186">Select the call answering options</span></span>

![Zeigt die Optionen für Anruf-Verteilungsmethoden an](media/5d249515-d532-4af2-90da-011404028b89.png)

![Nummer 1](media/sfbcallout1.png)

<span data-ttu-id="721a7-189">Sie können bis zu 200 Anruf Agents, die angegebene Verteilerlisten oder Gruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="721a7-189">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="721a7-190">Call-Agenten müssen Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="721a7-190">Call agents must be either:</span></span>

- <span data-ttu-id="721a7-191">Ein Online-Benutzer mit einer **Telefonsystem**-Lizenz und Enterprise Voice oder einem Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="721a7-191">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="721a7-192">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen.</span><span class="sxs-lookup"><span data-stu-id="721a7-192">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="721a7-193">Finden Sie unter [Skype für Business Lizenzen zuweisen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Lizenzen für Microsoft-Teams zuweisen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="721a7-193">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="721a7-194">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="721a7-194">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="721a7-195">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="721a7-195">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="721a7-196">Online-Benutzer mit einer **Telefonsystem**-Lizenz und einem Anrufplan, die einer Office 365-Gruppe, einer e-Mail-Verteilerliste oder einer Sicherheitsgruppe hinzugefügt worden sind.</span><span class="sxs-lookup"><span data-stu-id="721a7-196">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="721a7-197">Es kann bis zu 30 Minuten dauern, bis ein neuer Telefonist zu einer Verteilerliste oder Sicherheitsgruppe hinzugefügt wird und Anrufe aus einer Anrufwarteschleife empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="721a7-197">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="721a7-198">Eine neu erstellte Liste oder eine Sicherheitsgruppe Verteilergruppe kann die Verwendung mit dem Anruf Warteschlangen verfügbar bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="721a7-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="721a7-199">Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="721a7-199">Newly created Office 365 Groups are available almost immediately.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Nummer 2](media/sfbcallout2.png)

<span data-ttu-id="721a7-202">**Routingmethode** Sie können entweder **Attendant**, **seriellen**oder **Roundrobin** für Ihre Anruf Warteschlange Verteilungsmethode auswählen.</span><span class="sxs-lookup"><span data-stu-id="721a7-202">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="721a7-203">Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="721a7-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="721a7-204">Wenn attendant routing verwendet wird, wird der erste Aufruf in der Warteschlange alle Agents Anruf gleichzeitig Anrufen aus.</span><span class="sxs-lookup"><span data-stu-id="721a7-204">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="721a7-205">Der erste Aufruf Agent den Anruf übernehmen Ruft den Anruf ab.</span><span class="sxs-lookup"><span data-stu-id="721a7-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="721a7-206">**Attendant routing** bewirkt, dass den ersten Aufruf in der Warteschlange alle Anruf Agents gleichzeitig angeboten werden soll.</span><span class="sxs-lookup"><span data-stu-id="721a7-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="721a7-207">Der erste Aufruf Agent den Anruf übernehmen Ruft den Anruf ab.</span><span class="sxs-lookup"><span data-stu-id="721a7-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="721a7-208">**Serielles routing** bewirkt, dass eingehende Anrufe Call-Agenten jeweils ab dem Anfang der Anrufliste Agent angeboten werden soll.</span><span class="sxs-lookup"><span data-stu-id="721a7-208">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="721a7-209">Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="721a7-209">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="721a7-210">Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**.</span><span class="sxs-lookup"><span data-stu-id="721a7-210">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="721a7-211">**Round-Robin** ausgeglichen routing eingehender Anrufe, sodass jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="721a7-211">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="721a7-212">Dies kann in einer eingehenden sales-Umgebung um die gleiche Chancen zwischen den Call-Agenten sicherzustellen sehr wünschenswert sein.</span><span class="sxs-lookup"><span data-stu-id="721a7-212">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="721a7-213">Wählen Sie eine Option für das Abmelden von Telefonisten</span><span class="sxs-lookup"><span data-stu-id="721a7-213">Select an agent opt out option</span></span>

![Zeigt das Abmeldungs-Kontrollkästchen des Telefonisten](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

<span data-ttu-id="721a7-216">**Option Abmeldung für Telefonisten** Sie können es Telefonisten erlauben, sich von Anrufen von einer bestimmten Anrufwarteschleife abzumelden, indem Sie die **Option Abmeldung für Telefonisten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="721a7-216">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="721a7-217">Durch Aktivieren dieser Option ermöglicht, dass alle Agents in dieser Warteschlange zum Starten oder beenden annehmen von Anrufen aus dieser Warteschlange Anruf am wird.</span><span class="sxs-lookup"><span data-stu-id="721a7-217">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="721a7-218">Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).</span><span class="sxs-lookup"><span data-stu-id="721a7-218">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="721a7-219">Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="721a7-219">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="721a7-220">Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.</span><span class="sxs-lookup"><span data-stu-id="721a7-220">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="721a7-221">Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="721a7-221">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="721a7-222">Klicken Sie auf der Einstellungsseite für Benutzer auf **Anrufwarteschleifen** und deaktivieren Sie die Kontrollkästchen für alle Warteschleifen, von denen sie sich abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="721a7-222">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="721a7-223">Agents mit apps oder Endpunkte außer Skype für Business Desktop kann zugreifen, die lehnen Sie die Option vom Benutzer Einstellungen Portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span><span class="sxs-lookup"><span data-stu-id="721a7-223">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="721a7-224">![Nummer 2](media/sfbcallout2.png)
**Agent Alert Einstellung**</span><span class="sxs-lookup"><span data-stu-id="721a7-224">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="721a7-225">Hierdurch wird die Dauer der Agent eines Aufrufs vor seriell benachrichtigt wird, oder verschieben Sie Roundrobin Routingmethoden zum nächsten Agenten.</span><span class="sxs-lookup"><span data-stu-id="721a7-225">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="721a7-226">Die Standardeinstellung ist 30 Sekunden, aber sie können für bis zu drei Minuten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-226">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="721a7-227">Legen Sie den Anruf Überlauf und Timeout Behandlung-Optionen</span><span class="sxs-lookup"><span data-stu-id="721a7-227">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

<span data-ttu-id="721a7-230">**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt.</span><span class="sxs-lookup"><span data-stu-id="721a7-230">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="721a7-231">Der Standardwert ist 50, aber es kann im Bereich von 0 bis 200.</span><span class="sxs-lookup"><span data-stu-id="721a7-231">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="721a7-232">Wenn dieses Limit erreicht ist, wird der Anruf gemäß Ihrer Angabe für die Einstellung **Wenn die maximale Anzahl der Anrufe erreicht ist** (siehe unten) behandelt.</span><span class="sxs-lookup"><span data-stu-id="721a7-232">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Nummer 2](media/sfbcallout2.png)

<span data-ttu-id="721a7-234">**Wenn die maximale Anzahl von Anrufen erreicht wird** Wenn die Anruf Warteschlange die maximale Größe (unter Verwendung der Einstellung **Maximum von Anrufen in der Warteschlange** festgelegt) erreicht, können Sie auswählen, was passiert, um neue eingehende Anrufe.</span><span class="sxs-lookup"><span data-stu-id="721a7-234">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="721a7-235">**Trennen**: Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="721a7-235">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="721a7-236">**Umleiten an** Wenn Sie diese Option wählen, wählen Sie eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="721a7-236">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="721a7-237">**Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen.</span><span class="sxs-lookup"><span data-stu-id="721a7-237">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="721a7-238">Sie können einrichten, dass Anrufer an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-238">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="721a7-239">Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-239">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="721a7-240">Informationen zur Lizenzierung für Voicemail erforderlich sind, finden Sie unter [Einrichten von Voicemail Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="721a7-240">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="721a7-241">**VoIP-Anwendung** Wählen Sie den Namen des entweder eine Warteschlange Anruf oder automatische um-Telefonzentrale, die bereits erstellt worden ist.</span><span class="sxs-lookup"><span data-stu-id="721a7-241">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Nummer 3](media/sfbcallout3.png)

<span data-ttu-id="721a7-243">**Timeout aufrufen: maximale Wartezeit** Sie können auch bestimmen, wie lange ein Anruf in der Warteschleife in der Warteschlange werden kann bevor es Timeout und umgeleitet oder getrennt werden muss.</span><span class="sxs-lookup"><span data-stu-id="721a7-243">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="721a7-244">Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab.</span><span class="sxs-lookup"><span data-stu-id="721a7-244">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="721a7-245">Sie können eine Dauer von 0 bis 45 Minuten festlegen.</span><span class="sxs-lookup"><span data-stu-id="721a7-245">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="721a7-246">Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-246">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="721a7-247">Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="721a7-247">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="721a7-248">Beispielsweise könnten Sie angeben, dass alle Anrufe, die nicht innerhalb von 30 Sekunden von einem Agent beantwortet werden zu einer Verzeichnissuche Telefonzentrale wechseln.</span><span class="sxs-lookup"><span data-stu-id="721a7-248">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Nummer 4](media/sfbcallout4.png)

<span data-ttu-id="721a7-250">**Wenn ein Anruf Timeout** Wenn der Aufruf den Grenzwert, den Sie für die Einstellung für **wie lange ein Anruf in der Warteschlange warten kann** festlegen erreicht, können Sie auswählen, was geschieht, um dieses Anrufs:</span><span class="sxs-lookup"><span data-stu-id="721a7-250">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="721a7-251">**Trennen**: Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="721a7-251">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="721a7-252">**Dieser Aufruf umleiten** Wenn Sie diese Option wählen, müssen Sie diese Optionen:</span><span class="sxs-lookup"><span data-stu-id="721a7-252">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="721a7-253">**Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder plant aufrufen.</span><span class="sxs-lookup"><span data-stu-id="721a7-253">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="721a7-254">Sie können einrichten, dass Anrufer an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-254">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="721a7-255">Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="721a7-255">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="721a7-256">Informationen zur Lizenzierung für Voicemail erforderlich sind, finden Sie unter [Einrichten von Voicemail Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="721a7-256">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="721a7-257">**VoIP-Anwendung** Wählen Sie den Namen des entweder eine Warteschlange Anruf oder automatische um-Telefonzentrale, die bereits erstellt worden ist.</span><span class="sxs-lookup"><span data-stu-id="721a7-257">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="721a7-258">Ändern eines Benutzers Anrufer-ID für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="721a7-258">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="721a7-259">Sie können die Identität eines Benutzers mit ändern ihre Anrufer-ID für ausgehende Anrufe an eine Warteschlange Anruf, automatische Telefonzentrale oder eine beliebige Anzahl Service stattdessen durch Erstellen einer Richtlinie mit dem Cmdlet **New-CsCallingLineIdentity** schützen.</span><span class="sxs-lookup"><span data-stu-id="721a7-259">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="721a7-260">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="721a7-260">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="721a7-261">Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an.</span><span class="sxs-lookup"><span data-stu-id="721a7-261">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="721a7-262">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="721a7-262">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="721a7-263">Sie erhalten weitere Informationen zum Anrufer-ID-Einstellungen in Ihrer Organisation im Artikel [wie kann Anrufer-ID verwendet werden in Ihrer Organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization)zu ändern.</span><span class="sxs-lookup"><span data-stu-id="721a7-263">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="721a7-264">Möchten Sie mehr wissen?</span><span class="sxs-lookup"><span data-stu-id="721a7-264">Want to know more?</span></span>

<span data-ttu-id="721a7-265">Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="721a7-265">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="721a7-266">Cmdlets für Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="721a7-266">Call queue cmdlets</span></span>

<span data-ttu-id="721a7-267">Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="721a7-267">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="721a7-268">Neue CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="721a7-268">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="721a7-269">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="721a7-269">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="721a7-270">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="721a7-270">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="721a7-271">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="721a7-271">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="721a7-272">Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="721a7-272">More about Windows PowerShell</span></span>

- <span data-ttu-id="721a7-273">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="721a7-273">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="721a7-274">Mit Windows PowerShell können Sie Office 365 und eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Microsoft-Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="721a7-274">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="721a7-275">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="721a7-275">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="721a7-276">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="721a7-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="721a7-277">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="721a7-277">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="721a7-278">Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur mithilfe der Verwaltungskonsole Microsoft-Teams, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen.</span><span class="sxs-lookup"><span data-stu-id="721a7-278">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="721a7-279">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="721a7-279">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="721a7-280">Verwalten von Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="721a7-280">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="721a7-281">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="721a7-281">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="721a7-282">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="721a7-282">Related topics</span></span>

[<span data-ttu-id="721a7-283">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="721a7-283">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="721a7-284">Abrufen von Diensttelefonnummern</span><span class="sxs-lookup"><span data-stu-id="721a7-284">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="721a7-285">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="721a7-285">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="721a7-286">Neue CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="721a7-286">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
