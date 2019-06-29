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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Hier erfahren Sie, wie Sie das Telefon System für Cloud-Anrufwarteschlangen mit Microsoft Teams einrichten.
ms.openlocfilehash: b512d674a705c332213456ea639a015e15b51c2d
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394597"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="ab8f8-103">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="ab8f8-103">Create a Cloud call queue</span></span>

<span data-ttu-id="ab8f8-104">Cloud-Anrufwarteschlangen sind ein Dienst, der einen Gruß an Kundenanrufe abspielt, bevor er in einer Warteschlange platziert wird, während er zwischen einem vordefinierten Satz von Agents sucht, um diese Anrufe zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-104">Cloud call queues are a service that play a greeting to customer calls before placing them in a queue while searching among a pre-defined set of agents to answer these calls.</span></span> <span data-ttu-id="ab8f8-105">Sie können eine oder mehrere Anrufwarteschlangen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-105">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="ab8f8-106">Cloud-Anrufwarteschlangen können Folgendes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-106">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="ab8f8-107">Eine Grußnachricht.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-107">A greeting message.</span></span>
- <span data-ttu-id="ab8f8-108">Musik, während die wartenden Anrufer gehalten werden</span><span class="sxs-lookup"><span data-stu-id="ab8f8-108">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="ab8f8-109">Umleiten von Anrufen an Anruf-Agents in e-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-109">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="ab8f8-110">Einstellungen verschiedene Parameter wie maximale Größe der Warteschlange, Timeout und Anruf Behandlungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-110">Settings different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="ab8f8-111">Wenn sich jemand über ein [Ressourcenkonto](manage-resource-accounts.md)an eine Telefonnummer anmeldet, die mit einer Anrufwarteschlange verbunden ist, hören Sie zuerst eine Begrüßung (sofern vorhanden), und Sie werden dann in die Warteschlange gestellt und auf den nächsten verfügbaren Anruf Agenten gewartet.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-111">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="ab8f8-112">Die Einberufungs Person hört Musik, während Sie in Wartestellung sind, und die Anrufe werden den Anruf-Agents in *First in First Out* (FIFO)-Reihenfolge angeboten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-112">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="ab8f8-113">Alle in der Warteschlange wartenden Anrufe werden mithilfe einer der folgenden Methoden verteilt:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-113">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="ab8f8-114">Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-114">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="ab8f8-115">Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-115">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="ab8f8-116">Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-116">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab8f8-117">Anruf-Agents, die **Offline**sind, ihre Anwesenheit auf " **nicht stören** " festgelegt haben oder die Anrufwarteschlange deaktiviert haben, werden keine Anrufe empfangen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>
  
- <span data-ttu-id="ab8f8-118">Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="ab8f8-119">Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="ab8f8-120">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="ab8f8-121">Schritt 1 – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="ab8f8-121">Step 1 - Get started</span></span>

<span data-ttu-id="ab8f8-122">Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="ab8f8-123">Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="ab8f8-124">Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="ab8f8-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="ab8f8-125">Wenn Sie Ihrer Anrufwarteschlange eine Telefonnummer zuweisen möchten, müssen Sie eine der folgenden Lizenzen für Ihre Ressourcenkonten erwerben und zuweisen:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-125">If you plan to assign a phone number to your call queue, you need to acquire and assign one of the following licenses to your resource accounts:</span></span>
    - <span data-ttu-id="ab8f8-126">Office 365 Enterprise E1 oder E3 mit hinzugefügtem Telefon System</span><span class="sxs-lookup"><span data-stu-id="ab8f8-126">Office 365 Enterprise E1 or E3 with Phone System added</span></span>
    - <span data-ttu-id="ab8f8-127">Office 365 Enterprise E5 mit Telefon System</span><span class="sxs-lookup"><span data-stu-id="ab8f8-127">Office 365 Enterprise E5 which includes Phone System</span></span>
- <span data-ttu-id="ab8f8-128">Sie müssen die Ressourcenkonten nur mit einer Telefonnummer lizenzieren, die Ihnen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="ab8f8-129">In einer geschachtelten Anrufwarteschlange müssen Sie die restlichen Anrufwarteschlangen nicht lizenzieren, wenn Ihnen keine Telefonnummern zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-129">In a nested call queue, you do not need to license the rest of the call queues if they do not have phone numbers associated with them.</span></span>

> [!NOTE]
> <span data-ttu-id="ab8f8-130">Direct Routing-Dienstnummern für Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-130">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="ab8f8-131">Microsoft arbeitet an einem kostenlosen Lizenzierungsmodell für Anwendungen wie automatische Cloud-Telefonzentralen und Anrufwarteschlangen, denn jetzt müssen Sie das Benutzer Lizenzierungsmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-131">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="ab8f8-132">Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="ab8f8-133">Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="ab8f8-134">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="ab8f8-135">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="ab8f8-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="ab8f8-136">Weitere Informationen zu Office 365-Anrufplänen finden Sie unter [Telefon System-und Anrufpläne](calling-plan-landing-page.md) sowie [Anrufpläne für Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="ab8f8-137">Sie können nur gebührenpflichtige und gebührenfreie Telefonnummern für Dienstleistungen zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten oder von einem anderen Dienstanbieter zu Cloud-Anrufwarteschlangen übertragen haben.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="ab8f8-138">Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab8f8-139">Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="ab8f8-140">Wenn Sie die eingehenden Anrufe aus einer Cloud-Anrufwarteschlange verteilen, werden diese Clients für Anruf-Agents unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="ab8f8-141">Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="ab8f8-142">Desktopclient von Lync 2013 (32- und 64-Bit-Version)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="ab8f8-143">Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="ab8f8-144">Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="ab8f8-145">Mac Skype for Business-Client (Version 16.8.196 und höher)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="ab8f8-146">Android Skype for Business-Client (Version 6.16.0.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="ab8f8-147">iPhone Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="ab8f8-148">Mac Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="ab8f8-149">Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="ab8f8-150">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="ab8f8-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="ab8f8-151">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="ab8f8-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="ab8f8-152">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="ab8f8-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="ab8f8-153">Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern</span><span class="sxs-lookup"><span data-stu-id="ab8f8-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="ab8f8-154">Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie Ihre bestehenden kostenpflichtigen oder gebührenfreien Servicenummern einrichten oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="ab8f8-155">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service\*\*\*\* > -Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **-Legacy-Portal** > -**Telefonnummern**angezeigt, und der **Nummerntyp** wird angezeigt. als **Service-gebührenfrei**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="ab8f8-156">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](getting-service-phone-numbers.md) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-156">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab8f8-157">Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="ab8f8-158">Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="ab8f8-159">Wenn Sie auch automatische Telefonzentralen einrichten, müssen Sie möglicherweise nur dem Ressourcenkonto der primären automatischen Telefonzentrale eine Telefonnummer zuweisen und dann Anrufer an Ihre Anrufwarteschlange weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="ab8f8-160">Wenn dies der Fall ist, muss die Anrufwarteschlange erstellt werden, bevor Sie eine Option in der automatischen Telefonzentrale erstellen können, mit der die Anrufwarteschlange ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="ab8f8-161">Schritt 3 – Erstellen einer neuen Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="ab8f8-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="ab8f8-162">Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="ab8f8-163">Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ab8f8-164">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="ab8f8-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="ab8f8-165">Klicken Sie im **Microsoft Teams Admin Center**auf Warteschlangen für **sprach** >  **Anrufe**und dann auf **+ Neu hinzufügen**:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="ab8f8-166">Einrichten des Anzeige namens und des Ressourcenkontos für die Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="ab8f8-166">Set the call queue display name and resource account</span></span>

![Screenshot einer neuen Anrufwarteschlange mit nummerierten Beschriftungen](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="ab8f8-168">![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)
-**Namen** verweist, geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-168">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="ab8f8-169">Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="ab8f8-170">Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="ab8f8-172">**Hinzufügen von Konten** Wählen Sie ein Ressourcenkonto aus.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="ab8f8-173">Das Ressourcenkonto ist möglicherweise mit einer Dienst gebührenpflichtigen oder gebührenfreien Telefonnummer für die Anrufwarteschlange verknüpft, aber für jede Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="ab8f8-174">Wenn keine Liste aufgeführt ist, müssen Sie Dienstnummern abrufen und Sie einem Ressourcenkonto zuweisen, bevor Sie diese Anrufwarteschlange wie zuvor beschrieben erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="ab8f8-175">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-175">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="ab8f8-176">Sie müssen ein Ressourcenkonto erstellen, wie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) beschrieben, wenn Sie möchten, dass Ihre Anrufwarteschlange über eine zugeordnete Telefonnummer verfügt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="ab8f8-177">Wenn Sie eine **Domäne** zuweisen möchten, sollten Sie dies tun, indem Sie Sie dem Ressourcenkonto für die Anrufwarteschlange zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="ab8f8-178">Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="ab8f8-178">Set the greeting and music played while on hold</span></span>

![Screenshot der Optionen für Begrüßung und Musik mit nummerierten Beschriftungen](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="ab8f8-181">**Begrüßung** ist optional.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-181">**Greeting** is optional.</span></span> <span data-ttu-id="ab8f8-182">Hierbei handelt es sich um die Ansage, die für Personen abgespielt wird, die die Anruf Warteschlangennummer anrufen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="ab8f8-183">Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="ab8f8-185">**Musik in Warte** Stellung Sie können entweder die standardmäßige Musik in der Warteschlange für die Anrufwarteschlange verwenden, oder Sie können eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="ab8f8-186">Wählen Sie die Optionen für die Anrufannahme aus.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-186">Select the call answering options</span></span>

![Screenshot der Optionen für die Anrufannahme mit nummerierten Beschriftungen](media/5d249515-d532-4af2-90da-011404028b89.png)

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="ab8f8-189">Sie können bis zu 200-Anruf-Agents auswählen, die zu einer der folgenden Mailinglisten oder-Gruppen gehören:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-189">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="ab8f8-190">Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ab8f8-190">Office 365 group</span></span>
- <span data-ttu-id="ab8f8-191">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="ab8f8-191">Security group</span></span>
- <span data-ttu-id="ab8f8-192">Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="ab8f8-192">Distribution list</span></span>

<span data-ttu-id="ab8f8-193">Ausgewählte Anruf-Agents müssen **entweder** Online-Benutzer mit einer **Telefon System** Lizenz und Enterprise-VoIP sein **oder** über einen Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-193">Call agents selected must  **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ab8f8-194">Dies gilt auch, wenn Sie Anrufe an Personen in Ihrer Organisation umleiten möchten, die Online sind.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-194">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="ab8f8-195">Diese Personen müssen über eine **Telefon System** Lizenz und Enterprise-VoIP verfügen **oder** über einen Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-195">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="ab8f8-196">Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), Zuweisen von [Microsoft Teams-Lizenzen](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)oder [der richtige Anrufplan für Sie?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-196">For more information see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="ab8f8-197">Um einen Agenten für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-197">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="ab8f8-198">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="ab8f8-198">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="ab8f8-199">Online Benutzer mit einer **Telefon System** Lizenz oder einem Anrufplan, die einer Office 365-Gruppe hinzugefügt werden eine e-Mail-aktivierte Verteilerliste oder eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-199">Online users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="ab8f8-200">Es kann bis zu drei Stunden dauern, bis ein neu hinzugefügter Agent in einer Verteilerliste oder einer Sicherheitsgruppe Anrufe von einer Anrufwarteschlange empfängt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-200">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="ab8f8-201">Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-201">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="ab8f8-202">Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-202">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="ab8f8-203">Wenn Ihre Agents die Microsoft Teams-App verwenden, um Anruf Warteschlangen Anrufe zu empfangen, müssen Sie sich im TeamsOnly-Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-203">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

![Screenshot des Bereichs "Anruf-Agents hinzufügen"](media/skype-for-business-add-agents-to-call-queue.png)

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="ab8f8-206">**Routing Methode** Sie können für Ihre Verteilungsmethode für die Anrufwarteschlange entweder **Attendant**, **seriell**oder **Round Robin** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-206">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="ab8f8-207">Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-207">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="ab8f8-208">Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-208">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="ab8f8-209">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-209">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="ab8f8-210">Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-210">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="ab8f8-211">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-211">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="ab8f8-212">Bei der seriellen weiter **Leitung** von eingehenden Anrufen werden die Anruf-Agents einzeln und ab dem Anfang der Anruf Agentenliste angerufen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-212">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="ab8f8-213">Agents können nicht in der Liste der Anruf-Agents bestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-213">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="ab8f8-214">Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-214">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="ab8f8-215">Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-215">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="ab8f8-216">**Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-216">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="ab8f8-217">Dies kann in einer eingehenden Vertriebsumgebung sehr wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-217">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="ab8f8-218">Wählen Sie eine Option für das Abmelden von Telefonisten</span><span class="sxs-lookup"><span data-stu-id="ab8f8-218">Select an agent opt out option</span></span>

![Screenshot der Optionen für das Deaktivieren von Agenten mit nummerierten Beschriftungen](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="ab8f8-221">**Option Abmeldung für Telefonisten** Sie können es Telefonisten erlauben, sich von Anrufen von einer bestimmten Anrufwarteschleife abzumelden, indem Sie die **Option Abmeldung für Telefonisten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-221">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="ab8f8-222">Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-222">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="ab8f8-223">Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-223">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="ab8f8-224">Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-224">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="ab8f8-225">Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-225">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="ab8f8-226">Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-226">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="ab8f8-227">Klicken Sie auf der Einstellungsseite für Benutzer auf **Anrufwarteschleifen** und deaktivieren Sie die Kontrollkästchen für alle Warteschleifen, von denen sie sich abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-227">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab8f8-228">Agents, die apps oder Endpunkte mit Ausnahme von Skype for Business Desktop verwenden, können über das Benutzer Einstellungs [https://aka.ms/cqsettings](https://aka.ms/cqsettings)Portal auf die Option "ablehnen" zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-228">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="ab8f8-229">![Symbol der Zahl 2, die auf eine Legende in der vorherigen](media/sfbcallout2.png)
**Benachrichtigungseinstellung** des Screenshot-Agents verweist</span><span class="sxs-lookup"><span data-stu-id="ab8f8-229">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="ab8f8-230">Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-230">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="ab8f8-231">Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-231">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="ab8f8-232">Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung</span><span class="sxs-lookup"><span data-stu-id="ab8f8-232">Set the call overflow and timeout handling options</span></span>

![Screenshot der Überlauf Behandlungsoptionen mit nummerierten Beschriftungen](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="ab8f8-235">**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-235">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="ab8f8-236">Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-236">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="ab8f8-237">Wenn dieses Limit erreicht ist, wird der Anruf gemäß Ihrer Angabe für die Einstellung **Wenn die maximale Anzahl der Anrufe erreicht ist** (siehe unten) behandelt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-237">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="ab8f8-239">**Wenn die maximale Anzahl von Anrufen erreicht ist** Wenn die Anrufwarteschlange die maximale Größe erreicht (festgelegt mit den **maximalen anrufen in der Warteschlangen** Einstellung), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-239">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="ab8f8-240">**Trennen**: Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-240">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="ab8f8-241">**Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-241">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="ab8f8-242">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-242">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="ab8f8-243">Sie können einrichten, dass Anrufer an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-243">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="ab8f8-244">Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-244">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="ab8f8-245">Informationen zur Lizenzierung, die für Voicemail erforderlich ist, finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-245">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="ab8f8-246">**Sprachanwendung** Wählen Sie den Namen einer Anrufwarteschlange oder einer automatischen Telefonzentrale aus, die bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-246">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout3.png)

<span data-ttu-id="ab8f8-248">**Anruf Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und er muss umgeleitet oder getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-248">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="ab8f8-249">Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-249">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="ab8f8-250">Sie können eine Dauer von 0 bis 45 Minuten festlegen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-250">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="ab8f8-251">Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-251">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="ab8f8-252">Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-252">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="ab8f8-253">So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-253">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout4.png)

<span data-ttu-id="ab8f8-255">**Beim Timeout** des Anrufs Wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit diesem Anruf geschieht:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-255">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="ab8f8-256">**Trennen**: Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-256">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="ab8f8-257">**Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Optionen:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-257">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="ab8f8-258">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-258">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="ab8f8-259">Sie können einrichten, dass Anrufer an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-259">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="ab8f8-260">Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-260">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="ab8f8-261">Informationen zur Lizenzierung, die für Voicemail erforderlich ist, finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-261">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="ab8f8-262">**Sprachanwendung** Wählen Sie den Namen einer Anrufwarteschlange oder einer automatischen Telefonzentrale aus, die bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-262">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="ab8f8-263">Ändern der Rufnummernanzeige eines Benutzers für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="ab8f8-263">Changing a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="ab8f8-264">Sie können die Identität eines Benutzers schützen, indem Sie dessen Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer ändern, indem Sie stattdessen eine Richtlinie mit dem Cmdlet **New-CsCallingLineIdentity** erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-264">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="ab8f8-265">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-265">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="ab8f8-266">Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-266">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="ab8f8-267">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-267">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="ab8f8-268">Weitere Informationen zum vornehmen von Änderungen an den Einstellungen für die Rufnummernanzeige in Ihrer Organisation finden Sie im Artikel [wie kann die Rufnummernanzeige in Ihrer Organisation verwendet werden](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="ab8f8-268">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="ab8f8-269">Cmdlets für Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="ab8f8-269">Call queue cmdlets</span></span>

<span data-ttu-id="ab8f8-270">Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-270">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="ab8f8-271">Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-271">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="ab8f8-272">Neu – CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ab8f8-272">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="ab8f8-273">Satz-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ab8f8-273">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="ab8f8-274">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ab8f8-274">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="ab8f8-275">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ab8f8-275">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="ab8f8-276">Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab8f8-276">More about Windows PowerShell</span></span>

- <span data-ttu-id="ab8f8-277">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-277">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ab8f8-278">Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-278">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ab8f8-279">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-279">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ab8f8-280">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ab8f8-280">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="ab8f8-281">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="ab8f8-281">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="ab8f8-282">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft Teams Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ab8f8-282">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ab8f8-283">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ab8f8-283">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="ab8f8-284">Verwalten von Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab8f8-284">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="ab8f8-285">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab8f8-285">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="ab8f8-286">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ab8f8-286">Related topics</span></span>

[<span data-ttu-id="ab8f8-287">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="ab8f8-287">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ab8f8-288">Abrufen von Diensttelefonnummern</span><span class="sxs-lookup"><span data-stu-id="ab8f8-288">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="ab8f8-289">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="ab8f8-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="ab8f8-290">Neu – CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="ab8f8-290">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
