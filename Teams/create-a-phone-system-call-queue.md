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
ms.openlocfilehash: 845a9ca61b7d9b4cfe325d03027241634cbdb37e
ms.sourcegitcommit: a0df7479662b3bea488c19722ad588981f58a5e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447952"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="c982a-103">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="c982a-103">Create a Cloud call queue</span></span>

<span data-ttu-id="c982a-104">Cloud-Anrufwarteschlangen können Folgendes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="c982a-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="c982a-105">Eine Grußnachricht.</span><span class="sxs-lookup"><span data-stu-id="c982a-105">A greeting message.</span></span>
- <span data-ttu-id="c982a-106">Musik, während die wartenden Anrufer gehalten werden</span><span class="sxs-lookup"><span data-stu-id="c982a-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="c982a-107">Umleitung von Anrufen an Telefonisten in die von E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="c982a-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="c982a-108">Festlegen unterschiedlicher Parameter wie maximale Größe der Warteschlange, Timeout und Anruf Behandlungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="c982a-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="c982a-109">Sie würden einer Anrufwarteschlange mithilfe eines [Ressourcenkontos](manage-resource-accounts.md)eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c982a-109">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c982a-110">Eine Anrufwarteschlange kann direkt gewählt oder über eine Auswahl in einer automatischen Telefonzentrale aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-110">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="c982a-111">Der Anrufer hört Musik, während Sie in Wartestellung sind, und der Anruf stellt eine Verbindung mit den Anruf-Agents in *First in, First Out* (FIFO)-Reihenfolge her.</span><span class="sxs-lookup"><span data-stu-id="c982a-111">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="c982a-112">Alle Anrufe in der Warteschlange werden mithilfe einer der folgenden Methoden an Agents gesendet:</span><span class="sxs-lookup"><span data-stu-id="c982a-112">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="c982a-113">Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="c982a-113">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="c982a-114">Beim seriellen Routing klingelt der erste Anruf in der Warteschlange alle Anruf-Agents einzeln.</span><span class="sxs-lookup"><span data-stu-id="c982a-114">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="c982a-115">Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="c982a-115">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c982a-116">Anruf-Agents, die **Offline**sind, ihre Anwesenheit auf " **nicht stören** " festgelegt haben oder die Anrufwarteschlange deaktiviert haben, werden keine Anrufe empfangen.</span><span class="sxs-lookup"><span data-stu-id="c982a-116">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="c982a-117">Nur eine Benachrichtigung über eingehende Anrufe (für den Anruf am Kopf der Warteschlange) geht zu einem Zeitpunkt an die Anruf Agenten.</span><span class="sxs-lookup"><span data-stu-id="c982a-117">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="c982a-118">Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.</span><span class="sxs-lookup"><span data-stu-id="c982a-118">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="c982a-119">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="c982a-119">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="c982a-120">Schritt 1 – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="c982a-120">Step 1 — Get started</span></span>

<span data-ttu-id="c982a-121">Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:</span><span class="sxs-lookup"><span data-stu-id="c982a-121">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="c982a-122">Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c982a-122">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="c982a-123">Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="c982a-123">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="c982a-124">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)für das Telefon System verwenden.</span><span class="sxs-lookup"><span data-stu-id="c982a-124">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="c982a-125">Telefon System ermöglicht Telefonnummern auf Organisationsebene zur Verwendung mit kostengünstigen automatischen Telefonzentralen und Anrufwarteschlangen-Diensten.</span><span class="sxs-lookup"><span data-stu-id="c982a-125">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="c982a-126">Direct Routing-Dienstnummern für Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c982a-126">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="c982a-127">Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen.</span><span class="sxs-lookup"><span data-stu-id="c982a-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c982a-128">Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c982a-128">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c982a-129">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="c982a-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c982a-130">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c982a-130">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c982a-131">Weitere Informationen zu Office 365-Anrufplänen finden Sie unter [Telefon System-und Anrufpläne](calling-plan-landing-page.md) sowie [Anrufpläne für Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c982a-131">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="c982a-132">Sie können nur Cloud-Anrufwarteschlangen gebührenpflichtige und gebührenfreie Service-Telefonnummern zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten haben oder von einem anderen Dienstanbieter übertragen wurden.</span><span class="sxs-lookup"><span data-stu-id="c982a-132">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="c982a-133">Für gebührenfreie Servicenummern sind Kommunikationsguthaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c982a-133">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c982a-134">Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="c982a-135">Die folgenden Clients werden für Anruf-Agents unterstützt, die einer Cloud-Anrufwarteschlange zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="c982a-135">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="c982a-136">Skype for Business-Desktop Client 2016 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="c982a-136">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c982a-137">Lync-Desktop Client 2013 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="c982a-137">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c982a-138">Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-138">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c982a-139">Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c982a-139">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="c982a-140">Mac Skype for Business-Client (Version 16.8.196 und höher)</span><span class="sxs-lookup"><span data-stu-id="c982a-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="c982a-141">Android Skype for Business-Client (Version 6.16.0.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="c982a-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="c982a-142">iPhone Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="c982a-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c982a-143">Mac Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="c982a-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c982a-144">Microsoft Teams Windows-Client (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="c982a-144">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c982a-145">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="c982a-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="c982a-146">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="c982a-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="c982a-147">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="c982a-147">Microsoft Teams Android app</span></span>

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="c982a-148">Schritt 2: Abrufen oder übertragen von gebührenpflichtigen oder gebührenfreien Telefonnummern für Dienstleistungen</span><span class="sxs-lookup"><span data-stu-id="c982a-148">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="c982a-149">Bevor Sie Ihre Anrufwarteschlangen erstellen und einrichten können, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="c982a-149">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c982a-150">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service\*\*\*\* > -Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **-Legacy-Portal** > -**Telefonnummern**angezeigt, und der **Nummerntyp** wird als **Service – gebührenfrei**.</span><span class="sxs-lookup"><span data-stu-id="c982a-150">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="c982a-151">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](getting-service-phone-numbers.md) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c982a-151">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c982a-152">Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c982a-152">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c982a-153">Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.</span><span class="sxs-lookup"><span data-stu-id="c982a-153">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="c982a-154">Wenn Sie mehrere automatische Telefonzentralen einrichten, können Sie dem Hauptkonto der automatischen Telefonzentrale nur eine Telefonnummer zuweisen, mit der Anrufer an Ihre Anrufwarteschlangen oder geschachtelte automatische Telefonzentralen weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="c982a-154">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="c982a-155">In diesen Situationen erstellen Sie alle automatischen Telefonzentralen und Anrufwarteschlangen in Ihrem System, ohne dass Sie die Optionen für die Wähltasten zuweisen, und bearbeiten die Einstellungen später.</span><span class="sxs-lookup"><span data-stu-id="c982a-155">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="c982a-156">Dies ist erforderlich, da Sie keine Option erstellen können, die mit einer Anrufwarteschlange oder einer automatischen Telefonzentrale verknüpft ist, die noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c982a-156">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="c982a-157">Schritt 3: Erstellen einer neuen Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="c982a-157">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="c982a-158">Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c982a-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c982a-159">Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c982a-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c982a-160">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="c982a-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c982a-161">Klicken Sie im **Microsoft Teams Admin Center**auf Warteschlangen für **sprach** > **Anrufe**und dann auf **+ Neu hinzufügen**:</span><span class="sxs-lookup"><span data-stu-id="c982a-161">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="c982a-162">Einrichten des Anzeige namens und des Ressourcenkontos für die Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="c982a-162">Set the call queue display name and resource account</span></span>

![Screenshot einer neuen Anrufwarteschlange mit nummerierten Beschriftungen](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="c982a-164">![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)
-**Namen** verweist, geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="c982a-164">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="c982a-165">Dieser Name ist erforderlich und kann bis zu 64 Zeichen enthalten, einschließlich Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="c982a-165">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="c982a-166">Dieser Name wird in der Benachrichtigung für den eingehenden Anruf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c982a-166">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="c982a-168">**Hinzufügen von Konten** Wählen Sie ein Ressourcenkonto aus.</span><span class="sxs-lookup"><span data-stu-id="c982a-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="c982a-169">Das Ressourcenkonto ist möglicherweise mit einer Dienst gebührenpflichtigen oder gebührenfreien Telefonnummer für die Anrufwarteschlange verknüpft, aber für jede Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c982a-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="c982a-170">Wenn keine Liste aufgeführt ist, müssen Sie Dienstnummern abrufen und Sie einem Ressourcenkonto zuweisen, bevor Sie diese Anrufwarteschlange wie zuvor beschrieben erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c982a-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="c982a-171">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c982a-171">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="c982a-172">Sie erstellen ein Ressourcenkonto, wie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) beschrieben, wenn Sie möchten, dass Ihre Anrufwarteschlange über eine zugeordnete Telefonnummer verfügt.</span><span class="sxs-lookup"><span data-stu-id="c982a-172">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="c982a-173">Wenn Sie eine **Domäne** zuweisen möchten, sollten Sie dies tun, indem Sie Sie dem Ressourcenkonto für die Anrufwarteschlange zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c982a-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="c982a-174">Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="c982a-174">Set the greeting and music played while on hold</span></span>

![Screenshot der Optionen für Begrüßung und Musik mit nummerierten Beschriftungen](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="c982a-177">**Begrüßung** ist optional.</span><span class="sxs-lookup"><span data-stu-id="c982a-177">**Greeting** is optional.</span></span> <span data-ttu-id="c982a-178">Hierbei handelt es sich um die Ansage, die für Personen abgespielt wird, die die Anruf Warteschlangennummer anrufen.</span><span class="sxs-lookup"><span data-stu-id="c982a-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="c982a-179">Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.</span><span class="sxs-lookup"><span data-stu-id="c982a-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="c982a-181">**Musik in Warte** Stellung Sie können entweder die standardmäßige Musik in der Warteschlange für die Anrufwarteschlange verwenden, oder Sie können eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c982a-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="c982a-182">Wählen Sie die Optionen für die Anrufannahme aus.</span><span class="sxs-lookup"><span data-stu-id="c982a-182">Select the call answering options</span></span>

![Screenshot der Optionen für die Anrufannahme mit nummerierten Beschriftungen](media/5d249515-d532-4af2-90da-011404028b89.png)

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="c982a-185">Sie können bis zu 200-Anruf-Agents auswählen, die zu einer der folgenden Mailinglisten oder-Gruppen gehören:</span><span class="sxs-lookup"><span data-stu-id="c982a-185">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="c982a-186">Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="c982a-186">Office 365 group</span></span>
- <span data-ttu-id="c982a-187">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="c982a-187">Security group</span></span>
- <span data-ttu-id="c982a-188">Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="c982a-188">Distribution list</span></span>

<span data-ttu-id="c982a-189">Ausgewählte Anruf-Agents müssen **entweder** Online-Benutzer mit einer **Telefon System** Lizenz und Enterprise-VoIP sein **oder** über einen Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="c982a-189">Call agents selected must **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c982a-190">Dies gilt auch, wenn Sie Anrufe an Personen in Ihrer Organisation umleiten möchten, die Online sind.</span><span class="sxs-lookup"><span data-stu-id="c982a-190">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="c982a-191">Diese Personen müssen über eine **Telefon System** Lizenz und Enterprise-VoIP verfügen **oder** über einen Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="c982a-191">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="c982a-192">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen für Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Zuweisen von Microsoft Teams-Lizenzen](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)oder [der richtige Anrufplan für Sie?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c982a-192">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="c982a-193">Um einen Agenten für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="c982a-193">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c982a-194">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c982a-194">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c982a-195">Benutzer mit einer **Telefon System** Lizenz oder einem Anrufplan, die einer Office 365-Gruppe hinzugefügt werden eine e-Mail-aktivierte Verteilerliste oder eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="c982a-195">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="c982a-196">Es kann bis zu drei Stunden dauern, bis ein neu hinzugefügter Agent in einer Verteilerliste oder einer Sicherheitsgruppe Anrufe von einer Anrufwarteschlange empfängt.</span><span class="sxs-lookup"><span data-stu-id="c982a-196">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="c982a-197">Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c982a-197">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="c982a-198">Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c982a-198">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="c982a-199">Wenn Ihre Agents die Microsoft Teams-App zum Annehmen von Anruf Warteschlangen anrufen verwenden, müssen Sie sich im TeamsOnly-Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="c982a-199">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![Screenshot des Bereichs "Anruf-Agents hinzufügen"](media/skype-for-business-add-agents-to-call-queue.png)

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="c982a-202">**Routing Methode** Sie können für Ihre Verteilungsmethode für die Anrufwarteschlange entweder **Attendant**, **seriell**oder **Round Robin** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c982a-202">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="c982a-203">Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="c982a-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="c982a-204">Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="c982a-204">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="c982a-205">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="c982a-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c982a-206">Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt.</span><span class="sxs-lookup"><span data-stu-id="c982a-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="c982a-207">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="c982a-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="c982a-208">**Serielles Routing** eingehende Anrufe Klingeln die Anruf-Agents einzeln, beginnend mit dem Anfang der Anruf Agentenliste.</span><span class="sxs-lookup"><span data-stu-id="c982a-208">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="c982a-209">Agents können nicht in der Liste der Anruf-Agents bestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-209">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="c982a-210">Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="c982a-210">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c982a-211">Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**.</span><span class="sxs-lookup"><span data-stu-id="c982a-211">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="c982a-212">**Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="c982a-212">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c982a-213">Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="c982a-213">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="c982a-214">Auswählen einer Option für den Agenten Ausstieg</span><span class="sxs-lookup"><span data-stu-id="c982a-214">Select an agent opt-out option</span></span>

![Screenshot der Optionen für das ablehnen von Agents mit nummerierten Beschriftungen](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="c982a-217">**Der Agent kann das Abrufen von Anrufen ablehnen** Sie können festlegen, dass Anruf Warteschlangen-Agents das ablehnen von Anrufen aus einer bestimmten Warteschlange zulassen, indem Sie diese Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c982a-217">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="c982a-218">Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden.</span><span class="sxs-lookup"><span data-stu-id="c982a-218">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="c982a-219">Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).</span><span class="sxs-lookup"><span data-stu-id="c982a-219">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="c982a-220">Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="c982a-220">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="c982a-221">Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.</span><span class="sxs-lookup"><span data-stu-id="c982a-221">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="c982a-222">Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c982a-222">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="c982a-223">Klicken Sie auf der Seite Benutzereinstellungen auf **Anrufwarteschlangen**, und deaktivieren Sie dann die Kontrollkästchen für alle Warteschlangen, für die Sie sich abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="c982a-223">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c982a-224">Agents, die apps oder Endpunkte außer Skype for Business Desktop verwenden, können auf die Option "ablehnen" im [https://aka.ms/cqsettings](https://aka.ms/cqsettings)Portal "Benutzereinstellungen" zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c982a-224">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="c982a-225">![Symbol der Zahl 2, die auf eine Legende in der vorherigen](media/sfbcallout2.png)
**Benachrichtigungseinstellung** des Screenshot-Agents verweist</span><span class="sxs-lookup"><span data-stu-id="c982a-225">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="c982a-226">Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="c982a-226">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="c982a-227">Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-227">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="c982a-228">Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung</span><span class="sxs-lookup"><span data-stu-id="c982a-228">Set the call overflow and timeout handling options</span></span>

![Screenshot der Überlauf Behandlungsoptionen mit nummerierten Beschriftungen](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="c982a-231">**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt.</span><span class="sxs-lookup"><span data-stu-id="c982a-231">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="c982a-232">Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen.</span><span class="sxs-lookup"><span data-stu-id="c982a-232">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c982a-233">Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie Sie den Wert für die **Maximale Anzahl von Anrufen** festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="c982a-233">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<span data-ttu-id="c982a-235">**Wenn die maximale Anzahl von Anrufen erreicht ist** Wenn die Anrufwarteschlange die maximale Größe erreicht (festgelegt mit den **maximalen anrufen in der Warteschlangen** Einstellung), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.</span><span class="sxs-lookup"><span data-stu-id="c982a-235">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="c982a-236">**Verbindung trennen** Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="c982a-236">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="c982a-237">**Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c982a-237">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="c982a-238">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat.</span><span class="sxs-lookup"><span data-stu-id="c982a-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c982a-239">Sie können es so einrichten, dass der Anrufer an Voicemail gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c982a-239">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="c982a-240">Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c982a-241">Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c982a-241">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c982a-242">**Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c982a-242">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout3.png)

<span data-ttu-id="c982a-244">**Anruf Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und er muss umgeleitet oder getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-244">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="c982a-245">Die Stelle, an der Sie umgeleitet wird, basiert auf der Festlegung des Timeouts für **einen Anruf** .</span><span class="sxs-lookup"><span data-stu-id="c982a-245">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="c982a-246">Sie können eine Dauer von 0 bis 45 Minuten festlegen.</span><span class="sxs-lookup"><span data-stu-id="c982a-246">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="c982a-247">Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-247">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="c982a-248">Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c982a-248">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="c982a-249">So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.</span><span class="sxs-lookup"><span data-stu-id="c982a-249">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout4.png)

<span data-ttu-id="c982a-251">**Beim Timeout** des Anrufs Wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit diesem Anruf geschieht:</span><span class="sxs-lookup"><span data-stu-id="c982a-251">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="c982a-252">**Verbindung trennen** Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="c982a-252">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="c982a-253">**Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c982a-253">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="c982a-254">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat.</span><span class="sxs-lookup"><span data-stu-id="c982a-254">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="c982a-255">Sie können einrichten, dass Anrufer an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-255">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c982a-256">Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c982a-256">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c982a-257">Informationen zur Lizenzierung, die für Voicemail erforderlich ist, finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c982a-257">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c982a-258">**Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c982a-258">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="c982a-259">Ändern der Rufnummernanzeige eines Benutzers für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="c982a-259">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="c982a-260">Sie können die Identität eines Benutzers schützen, indem Sie die Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer anstelle des Cmdlets **New-CsCallingLineIdentity** ändern.</span><span class="sxs-lookup"><span data-stu-id="c982a-260">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="c982a-261">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c982a-261">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="c982a-262">Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an.</span><span class="sxs-lookup"><span data-stu-id="c982a-262">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="c982a-263">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c982a-263">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="c982a-264">Weitere Informationen zum Festlegen von Einstellungen für die Rufnummernanzeige in Ihrer Organisation finden Sie im Artikel [wie kann die Rufnummernanzeige in Ihrer Organisation verwendet werden](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c982a-264">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c982a-265">Cmdlets für Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="c982a-265">Call queue cmdlets</span></span>

<span data-ttu-id="c982a-266">Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c982a-266">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c982a-267">Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.</span><span class="sxs-lookup"><span data-stu-id="c982a-267">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="c982a-268">Neu – CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c982a-268">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c982a-269">Satz-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c982a-269">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c982a-270">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c982a-270">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c982a-271">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c982a-271">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="c982a-272">Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c982a-272">More about Windows PowerShell</span></span>

- <span data-ttu-id="c982a-273">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c982a-273">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c982a-274">Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c982a-274">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c982a-275">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c982a-275">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c982a-276">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c982a-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="c982a-277">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="c982a-277">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="c982a-278">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität über das Microsoft Teams Admin Center, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c982a-278">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c982a-279">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c982a-279">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c982a-280">Verwalten von Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c982a-280">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="c982a-281">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c982a-281">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="c982a-282">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c982a-282">Related topics</span></span>

[<span data-ttu-id="c982a-283">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="c982a-283">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c982a-284">Abrufen von Diensttelefonnummern</span><span class="sxs-lookup"><span data-stu-id="c982a-284">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c982a-285">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="c982a-285">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c982a-286">Neu – CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c982a-286">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
