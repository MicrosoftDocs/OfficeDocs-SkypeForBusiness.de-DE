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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Hier erfahren Sie, wie Sie das Telefon System für Cloud-Anrufwarteschlangen mit Microsoft Teams einrichten.
ms.openlocfilehash: c33baabdce8366ed9a4027c0b1e030f54eef543b
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41620005"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="05d3e-103">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="05d3e-103">Create a Cloud call queue</span></span>

<span data-ttu-id="05d3e-104">Cloud-Anrufwarteschlangen können Folgendes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="05d3e-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="05d3e-105">Eine Grußnachricht.</span><span class="sxs-lookup"><span data-stu-id="05d3e-105">A greeting message.</span></span>
- <span data-ttu-id="05d3e-106">Musik, während die wartenden Anrufer gehalten werden</span><span class="sxs-lookup"><span data-stu-id="05d3e-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="05d3e-107">Umleitung von Anrufen an Telefonisten in die von E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="05d3e-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="05d3e-108">Festlegen unterschiedlicher Parameter wie maximale Größe der Warteschlange, Timeout und Anruf Behandlungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="05d3e-109">Voicemail für Anrufer freigegeben, um eine Nachricht für eine Organisation zu hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="05d3e-110">Eine Telefonnummer wird nicht direkt einer Anrufwarteschlange zugeordnet, sondern die Telefonnummer ist mit einem [Ressourcenkonto](manage-resource-accounts.md)verknüpft.</span><span class="sxs-lookup"><span data-stu-id="05d3e-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="05d3e-111">Eine Anrufwarteschlange kann direkt gewählt oder über eine Auswahl in einer automatischen Telefonzentrale aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="05d3e-112">Der Anrufer hört Musik, während Sie in Wartestellung sind, und der Anruf stellt eine Verbindung mit den Anruf-Agents in *First in, First Out* (FIFO)-Reihenfolge her.</span><span class="sxs-lookup"><span data-stu-id="05d3e-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="05d3e-113">Alle Anrufe in der Warteschlange werden mithilfe einer der folgenden Methoden an Agents gesendet:</span><span class="sxs-lookup"><span data-stu-id="05d3e-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="05d3e-114">Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="05d3e-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="05d3e-115">Beim seriellen Routing klingelt der erste Anruf in der Warteschlange alle Anruf-Agents einzeln.</span><span class="sxs-lookup"><span data-stu-id="05d3e-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="05d3e-116">Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="05d3e-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05d3e-117">Anruf-Agents, die **Offline**sind, ihre Anwesenheit auf " **nicht stören** " festgelegt haben oder die Anrufwarteschlange deaktiviert haben, werden keine Anrufe empfangen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="05d3e-118">Nur eine Benachrichtigung über eingehende Anrufe (für den Anruf am Kopf der Warteschlange) geht zu einem Zeitpunkt an die Anruf Agenten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="05d3e-119">Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="05d3e-120">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="05d3e-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="05d3e-121">Schritt 1 – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="05d3e-121">Step 1 — Get started</span></span>

<span data-ttu-id="05d3e-122">Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:</span><span class="sxs-lookup"><span data-stu-id="05d3e-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="05d3e-123">Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05d3e-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="05d3e-124">Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="05d3e-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="05d3e-125">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)für das Telefon System verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="05d3e-126">Telefon System ermöglicht Telefonnummern auf Organisationsebene zur Verwendung mit kostengünstigen automatischen Telefonzentralen und Anrufwarteschlangen-Diensten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="05d3e-127">Direct Routing-Dienstnummern für Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="05d3e-128">Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="05d3e-129">Nähers hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="05d3e-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="05d3e-130">Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="05d3e-131">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="05d3e-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="05d3e-132">Weitere Informationen zu Office 365-Anrufplänen finden Sie unter [Telefon System-und Anrufpläne](calling-plan-landing-page.md) sowie [Anrufpläne für Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="05d3e-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="05d3e-133">Sie können nur Cloud-Anrufwarteschlangen gebührenpflichtige und gebührenfreie Service-Telefonnummern zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten haben oder von einem anderen Dienstanbieter übertragen wurden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="05d3e-134">Für gebührenfreie Servicenummern sind Kommunikationsguthaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05d3e-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05d3e-135">Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="05d3e-136">Die folgenden Clients werden für Anruf-Agents unterstützt, die einer Cloud-Anrufwarteschlange zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="05d3e-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="05d3e-137">Skype for Business-Desktop Client 2016 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="05d3e-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="05d3e-138">Lync-Desktop Client 2013 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="05d3e-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="05d3e-139">Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="05d3e-140">Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="05d3e-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="05d3e-141">Mac Skype for Business-Client (Version 16.8.196 und höher)</span><span class="sxs-lookup"><span data-stu-id="05d3e-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="05d3e-142">Android Skype for Business-Client (Version 6.16.0.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="05d3e-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="05d3e-143">iPhone Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="05d3e-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="05d3e-144">Mac Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="05d3e-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="05d3e-145">Microsoft Teams Windows-Client (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="05d3e-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="05d3e-146">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="05d3e-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="05d3e-147">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="05d3e-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="05d3e-148">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="05d3e-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="05d3e-149">Anrufwarteschlangen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, lync-Clients oder Skype for Business-IP-Telefone als Agents.</span><span class="sxs-lookup"><span data-stu-id="05d3e-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="05d3e-150">Schritt 2: Abrufen oder übertragen von gebührenpflichtigen oder gebührenfreien Telefonnummern für Dienstleistungen</span><span class="sxs-lookup"><span data-stu-id="05d3e-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="05d3e-151">Bevor Sie Ihre Anrufwarteschlangen erstellen und einrichten können, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="05d3e-152">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md) oder, wenn Sie eine vorhandene Dienstnummer übertragen möchten, unter [Übertragen von Telefonnummern zu Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="05d3e-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="05d3e-153">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > -**sprach** > **Telefonnummern**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="05d3e-154">Gebührenfreie Nummern werden mit einem **Nummerntyp** für **Dienstleistungen (gebührenfrei**) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="05d3e-155">Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="05d3e-156">Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="05d3e-157">Wenn Sie mehrere automatische Telefonzentralen einrichten, weisen Sie normalerweise dem Ressourcenkonto der primären automatischen Telefonzentrale eine Telefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="05d3e-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="05d3e-158">Ressourcenkonten, die geschachtelten automatischen Telefonzentralen oder Anrufwarteschlangen zugeordnet sind, benötigen häufig keine Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="05d3e-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="05d3e-159">Diese automatische Telefonzentrale kann Anrufer an Ihre Anrufwarteschlangen oder geschachtelte automatische Telefonzentralen weiterleiten, selbst wenn Sie keine Telefonnummer haben.</span><span class="sxs-lookup"><span data-stu-id="05d3e-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="05d3e-160">In diesen Fällen können Sie alle automatischen Telefonzentralen erstellen und Warteschlangen in Ihrem System anrufen, ohne dass Sie die Optionen für die Wähltasten zuweisen, und die Einstellungen später bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="05d3e-161">Es muss eine Anrufwarteschlange oder eine automatische Telefonzentrale vorhanden sein, um Sie als Menüoption zu definieren.</span><span class="sxs-lookup"><span data-stu-id="05d3e-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="05d3e-162">Schritt 3 – Erstellen einer Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="05d3e-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="05d3e-163">Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05d3e-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="05d3e-164">Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="05d3e-165">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="05d3e-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="05d3e-166">Klicken Sie im **Microsoft Teams Admin Center**auf**Warteschlangen**für **sprach** > Anrufe und dann auf **+ Neu hinzufügen**:</span><span class="sxs-lookup"><span data-stu-id="05d3e-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="05d3e-167">Einrichten des Anzeige namens und des Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="05d3e-167">Set the display name and resource account</span></span>

![Screenshot einer neuen Anrufwarteschlange mit nummerierten Beschriftungen](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="05d3e-169">![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)
-**Namen** geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="05d3e-169">![Icon of the number 1, references a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="05d3e-170">Dieser Name ist erforderlich und kann bis zu 64 Zeichen enthalten, einschließlich Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="05d3e-171">Dieser Name wird in der Benachrichtigung für den eingehenden Anruf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png)

<span data-ttu-id="05d3e-173">**Hinzufügen von Konten** Wählen Sie ein Ressourcenkonto aus.</span><span class="sxs-lookup"><span data-stu-id="05d3e-173">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="05d3e-174">Alle Anrufwarteschlangen sind für ein Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05d3e-174">All call queues are required to have a resource account.</span></span> <span data-ttu-id="05d3e-175">Für Ressourcenkonten ist keine Dienst gebührenpflichtige oder gebührenfreie Telefonnummer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05d3e-175">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="05d3e-176">Wenn keine Liste aufgeführt ist, rufen Sie Dienstnummern ab, und weisen Sie Sie einem Ressourcenkonto zu, bevor Sie die Anrufwarteschlange erstellen, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05d3e-176">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="05d3e-177">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="05d3e-177">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="05d3e-178">Einzelheiten zum Zuweisen einer Telefonnummer finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="05d3e-178">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="05d3e-179">Wenn Sie eine **Domäne** zuweisen möchten oder müssen, weisen Sie diese dem Ressourcenkonto für die Anrufwarteschlange zu.</span><span class="sxs-lookup"><span data-stu-id="05d3e-179">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="05d3e-180">Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="05d3e-180">Set the greeting and music played while on hold</span></span>

![Screenshot der Optionen für Begrüßung und Musik mit nummerierten Beschriftungen](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)

<span data-ttu-id="05d3e-183">**Gruß** an die optionale Ansage, die für Personen, die die Anruf Warteschlangennummer anrufen, abgespielt wird.</span><span class="sxs-lookup"><span data-stu-id="05d3e-183">**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="05d3e-184">Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-184">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png)

<span data-ttu-id="05d3e-186">**Musik in Warte** Stellung Sie können die standardmäßige Musik in der Warteschlange verwenden, die mit der Anrufwarteschlange bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="05d3e-186">**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="05d3e-187">Sie können auch eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-187">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="05d3e-188">Wählen Sie die Optionen für die Anrufannahme aus.</span><span class="sxs-lookup"><span data-stu-id="05d3e-188">Select the call answering options</span></span>

![Screenshot der Optionen für die Anrufannahme](media/5d249515-d532-4af2-90da-011404028b89.png) 

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)

<span data-ttu-id="05d3e-191">Wenn Sie einzelne Agents direkt hinzufügen möchten, ohne Sie zu einer Gruppe hinzuzufügen, klicken Sie auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="05d3e-191">To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="05d3e-192">Legen Sie einzelne Agents in der Reihenfolge ab, in der Sie den Anruf empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-192">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="05d3e-193">Sie können bis zu 20 einzelne Agents hinzufügen (um mehr als 20 hinzuzufügen, um Sie in einer Gruppe zu speichern).</span><span class="sxs-lookup"><span data-stu-id="05d3e-193">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="05d3e-194">Anrufe werden zuerst an einzelne Agents und dann an die Agents in Gruppen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="05d3e-194">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="05d3e-195">Sie können bis zu 200-Anruf-Agents auswählen, die zu einer der folgenden Mailinglisten oder-Gruppen gehören:</span><span class="sxs-lookup"><span data-stu-id="05d3e-195">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="05d3e-196">Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="05d3e-196">Office 365 group</span></span>
- <span data-ttu-id="05d3e-197">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="05d3e-197">Security group</span></span>
- <span data-ttu-id="05d3e-198">Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="05d3e-198">Distribution list</span></span>

<span data-ttu-id="05d3e-199">Die ausgewählten Anruf Agenten müssen folgende sein:</span><span class="sxs-lookup"><span data-stu-id="05d3e-199">Call agents selected must be:</span></span> 

- <span data-ttu-id="05d3e-200">Online-Benutzer mit einer Telefon System Lizenz und Enterprise-VoIP aktiviert</span><span class="sxs-lookup"><span data-stu-id="05d3e-200">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="05d3e-201">Online Benutzer mit einem Anrufplan</span><span class="sxs-lookup"><span data-stu-id="05d3e-201">Online users with a Calling Plan</span></span>
- <span data-ttu-id="05d3e-202">Lokale Skype for Business Server-Benutzer</span><span class="sxs-lookup"><span data-stu-id="05d3e-202">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="05d3e-203">Dies gilt auch, wenn Sie Anrufe an Personen in Ihrer Organisation umleiten möchten, die Online sind.</span><span class="sxs-lookup"><span data-stu-id="05d3e-203">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="05d3e-204">Diese Personen müssen über eine **Telefon System** Lizenz und Enterprise-VoIP verfügen **oder** über einen Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-204">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="05d3e-205">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen für Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Zuweisen von Microsoft Teams-Lizenzen](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)oder [der richtige Anrufplan für Sie?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="05d3e-205">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="05d3e-206">Um einen Agenten für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-206">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="05d3e-207">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="05d3e-207">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="05d3e-208">Benutzer mit einer **Telefon System** Lizenz oder einem Anrufplan, die einer Office 365-Gruppe hinzugefügt werden eine e-Mail-aktivierte Verteilerliste oder eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="05d3e-208">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="05d3e-209">Wenn Sie einen Agenten in einer Verteilerliste oder einer Sicherheitsgruppe als Anruf Warteschlangen-Agent hinzufügen, kann es bis zu drei Stunden dauern, bis der erste Anruf eintrifft.</span><span class="sxs-lookup"><span data-stu-id="05d3e-209">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="05d3e-210">Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="05d3e-210">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="05d3e-211">Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05d3e-211">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="05d3e-212">Wenn Ihre Agents die Microsoft Teams-App für Anruf Warteschlangen Anrufe verwenden, müssen Sie sich im TeamsOnly-Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-212">If your agents are using the Microsoft Teams App for call queue calls, they need to be in TeamsOnly mode.</span></span>

![Screenshot des Bereichs "Anruf-Agents hinzufügen"](media/skype-for-business-add-agents-to-call-queue.png)

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png)

<span data-ttu-id="05d3e-215">**Routing Methode** Sie können entweder **Attendant**, **Serial**oder **Round Robin** als Verteilungsmethode auswählen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-215">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="05d3e-216">Standardmäßig sind für alle neuen und vorhandenen Anrufwarteschlangen das Attendant-Routing ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-216">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="05d3e-217">Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="05d3e-217">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="05d3e-218">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-218">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="05d3e-219">Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-219">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="05d3e-220">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-220">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="05d3e-221">**Serielles Routing** eingehende Anrufe Klingeln alle Anruf-Agents eins nach dem anderen vom Anfang der Anruf Agentenliste.</span><span class="sxs-lookup"><span data-stu-id="05d3e-221">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="05d3e-222">Agents können nicht in der Liste der Anruf-Agents bestellt werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-222">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="05d3e-223">Wenn ein Agent einen Anruf abschließt oder nicht annimmt, klingelt der Anruf beim nächsten Agenten und versucht alle Agenten, bis er abgeholt wird oder ein Timeout annimmt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-223">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
  > [!NOTE]
  > <span data-ttu-id="05d3e-224">Bei der seriellen Weiterleitung für Agents, die **Offline** sind oder deren Anwesenheit auf " **nicht stören**" festgelegt wurde, wird der Anruf an diese Benutzer weitergeleitet, und die Verbindung zu nicht verfügbarem Benutzer, dem Routing zum nächsten Agenten in der Agentliste, ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="05d3e-224">With Serial routing, for agents who are **Offline** or have set their presence to **Do not Disturb**, the call will be routed to those users and fail to connect unavailable user, the routing to the next agent in the agent list.</span></span> <span data-ttu-id="05d3e-225">Dies ist nicht der Fall, wenn sich der Agent für das Abrufen von Anrufen aus der Anrufwarteschlange **entschieden** hat.</span><span class="sxs-lookup"><span data-stu-id="05d3e-225">This is not the case if the agent has **opted out** of getting calls from the call queue.</span></span> <span data-ttu-id="05d3e-226">Um das Zeitintervall zu verkürzen, in dem der Anruf an den nächsten Agenten weitergeleitet wird, kann die Benachrichtigungszeit für Agenten verringert werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-226">To reduce the time interval the call routes to next agent in line, Agent Alert time can be decreased.</span></span>
- <span data-ttu-id="05d3e-227">**Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="05d3e-227">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="05d3e-228">Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-228">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="05d3e-229">Auswählen einer Option für den Agenten Ausstieg</span><span class="sxs-lookup"><span data-stu-id="05d3e-229">Select an agent opt-out option</span></span>

![Screenshot der Optionen für das ablehnen von Agents mit nummerierten Beschriftungen](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)

<span data-ttu-id="05d3e-232">**Der Agent kann das Abrufen von Anrufen ablehnen** Sie können festlegen, dass Anruf Warteschlangen-Agents das ablehnen von Anrufen aus einer bestimmten Warteschlange zulassen, indem Sie diese Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="05d3e-232">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="05d3e-233">Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-233">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="05d3e-234">Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).</span><span class="sxs-lookup"><span data-stu-id="05d3e-234">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="05d3e-235">Um auf die Option "ablehnen" zuzugreifen, können Agents:</span><span class="sxs-lookup"><span data-stu-id="05d3e-235">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="05d3e-236">Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.</span><span class="sxs-lookup"><span data-stu-id="05d3e-236">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="05d3e-237">Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="05d3e-237">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="05d3e-238">Klicken Sie auf der Seite Benutzereinstellungen auf **Anrufwarteschlangen**, und deaktivieren Sie dann die Kontrollkästchen, um Warteschlangen abzulehnen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-238">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05d3e-239">Agents, die apps oder Endpunkte außer Skype for Business Desktop verwenden, können auf die Option "ablehnen" im [https://aka.ms/cqsettings](https://aka.ms/cqsettings)Portal "Benutzereinstellungen" zugreifen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-239">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="05d3e-240">Wenn sich die Agents in Microsoft Teams-Desktop Clients befinden, können Sie diese mithilfe der Anrufeinstellungen ablehnen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-240">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png)

<span data-ttu-id="05d3e-242">**Agent-Warnungseinstellung**</span><span class="sxs-lookup"><span data-stu-id="05d3e-242">**Agent Alert setting**</span></span>

<span data-ttu-id="05d3e-243">Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="05d3e-243">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="05d3e-244">Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-244">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="05d3e-245">Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung</span><span class="sxs-lookup"><span data-stu-id="05d3e-245">Set the call overflow and timeout handling options</span></span>

![Screenshot der Überlauf Behandlungsoptionen mit nummerierten Beschriftungen](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)

<span data-ttu-id="05d3e-248">**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-248">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="05d3e-249">Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-249">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="05d3e-250">Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie Sie den Wert für die **Maximale Anzahl von Anrufen** festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="05d3e-250">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png)

<span data-ttu-id="05d3e-252">**Wenn die maximale Anzahl von Anrufen erreicht ist** Wenn die Anrufwarteschlange die maximale Größe erreicht (festgelegt mit den **maximalen anrufen in der Warteschlangen** Einstellung), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.</span><span class="sxs-lookup"><span data-stu-id="05d3e-252">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="05d3e-253">**Verbindung trennen** Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-253">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="05d3e-254">**Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="05d3e-254">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="05d3e-255">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat.</span><span class="sxs-lookup"><span data-stu-id="05d3e-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="05d3e-256">Sie können es so einrichten, dass der Anrufer an Voicemail gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="05d3e-256">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="05d3e-257">Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="05d3e-258">Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="05d3e-258">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="05d3e-259">**Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="05d3e-259">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Symbol der Zahl 3, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout3.png)

<span data-ttu-id="05d3e-261">**Anruf Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und er muss umgeleitet oder getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-261">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="05d3e-262">Die Stelle, an der Sie umgeleitet wird, basiert auf der Festlegung des Timeouts für **einen Anruf** .</span><span class="sxs-lookup"><span data-stu-id="05d3e-262">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="05d3e-263">Sie können eine Dauer von 0 bis 45 Minuten festlegen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-263">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="05d3e-264">Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-264">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="05d3e-265">Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-265">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="05d3e-266">So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.</span><span class="sxs-lookup"><span data-stu-id="05d3e-266">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Symbol der Zahl 4, verweist auf eine Legende im vorherigen Screenshot](media/sfbcallout4.png)

<span data-ttu-id="05d3e-268">**Beim Timeout des Anrufs** Wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit dem Anruf geschieht:</span><span class="sxs-lookup"><span data-stu-id="05d3e-268">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="05d3e-269">**Verbindung trennen** Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="05d3e-269">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="05d3e-270">**Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="05d3e-270">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="05d3e-271">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat.</span><span class="sxs-lookup"><span data-stu-id="05d3e-271">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="05d3e-272">Wenn Sie die Person so einrichten möchten, dass Sie an Voicemail gesendet werden kann, wählen Sie eine **Person in Ihrem Unternehmen** aus, und legen Sie diese Person so fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="05d3e-272">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="05d3e-273">Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="05d3e-273">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="05d3e-274">**Sprach-App** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die Sie bereits erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="05d3e-274">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="05d3e-275">Ändern der Rufnummernanzeige für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="05d3e-275">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="05d3e-276">Um die Identität eines Anruf Agenten zu schützen, ändern Sie die Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer mit dem Cmdlet **New-CsCallingLineIdentity** wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="05d3e-276">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="05d3e-277">Wenden Sie dann die Richtlinie für den Benutzer mit dem **Grant-CallingLineIdentity-** Cmdlet wie im folgenden Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="05d3e-277">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="05d3e-278">Weitere Informationen finden Sie unter [wie kann die Anrufer-ID in Ihrer Organisation verwendet werden](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="05d3e-278">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="05d3e-279">Cmdlets für Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="05d3e-279">Call queue cmdlets</span></span>

<span data-ttu-id="05d3e-280">Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-280">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="05d3e-281">Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-281">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="05d3e-282">Neu – CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="05d3e-282">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="05d3e-283">Satz-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="05d3e-283">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="05d3e-284">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="05d3e-284">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="05d3e-285">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="05d3e-285">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="05d3e-286">Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05d3e-286">More about Windows PowerShell</span></span>

- <span data-ttu-id="05d3e-287">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="05d3e-287">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="05d3e-288">Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten.</span><span class="sxs-lookup"><span data-stu-id="05d3e-288">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="05d3e-289">Sie können Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-289">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="05d3e-290">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05d3e-290">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="05d3e-291">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="05d3e-291">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="05d3e-292">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="05d3e-292">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="05d3e-293">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität über das Microsoft Teams Admin Center, wenn Sie Änderungen für viele Benutzer gleichzeitig vornehmen.</span><span class="sxs-lookup"><span data-stu-id="05d3e-293">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="05d3e-294">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="05d3e-294">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="05d3e-295">Verwalten von Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05d3e-295">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="05d3e-296">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05d3e-296">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="05d3e-297">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="05d3e-297">Related topics</span></span>

[<span data-ttu-id="05d3e-298">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="05d3e-298">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="05d3e-299">Abrufen von Diensttelefonnummern</span><span class="sxs-lookup"><span data-stu-id="05d3e-299">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="05d3e-300">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="05d3e-300">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="05d3e-301">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="05d3e-301">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
