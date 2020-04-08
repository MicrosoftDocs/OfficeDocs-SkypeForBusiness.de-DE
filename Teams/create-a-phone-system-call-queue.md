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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Hier erfahren Sie, wie Sie das Telefon System für Cloud-Anrufwarteschlangen mit Microsoft Teams einrichten.
ms.openlocfilehash: 2027658c5335f19c00ea1c8e44c6d38e1f16a730
ms.sourcegitcommit: 9a448104a76857e3aa464c53cec577d813f8f414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43184246"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="34218-103">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="34218-103">Create a Cloud call queue</span></span>

<span data-ttu-id="34218-104">Cloud-Anrufwarteschlangen können Folgendes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="34218-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="34218-105">Eine Grußnachricht.</span><span class="sxs-lookup"><span data-stu-id="34218-105">A greeting message.</span></span>
- <span data-ttu-id="34218-106">Musik, während die wartenden Anrufer gehalten werden</span><span class="sxs-lookup"><span data-stu-id="34218-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="34218-107">Umleitung von Anrufen an Telefonisten in die von E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="34218-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="34218-108">Festlegen unterschiedlicher Parameter wie maximale Größe der Warteschlange, Timeout und Anruf Behandlungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="34218-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="34218-109">Voicemail für Anrufer freigegeben, um eine Nachricht für eine Organisation zu hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="34218-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="34218-110">Eine Telefonnummer wird nicht direkt einer Anrufwarteschlange zugeordnet, sondern die Telefonnummer ist mit einem [Ressourcenkonto](manage-resource-accounts.md)verknüpft.</span><span class="sxs-lookup"><span data-stu-id="34218-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="34218-111">Eine Anrufwarteschlange kann direkt gewählt oder über eine Auswahl in einer automatischen Telefonzentrale aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="34218-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="34218-112">Der Anrufer hört Musik, während Sie in Wartestellung sind, und der Anruf stellt eine Verbindung mit den Anruf-Agents in *First in, First Out* (FIFO)-Reihenfolge her.</span><span class="sxs-lookup"><span data-stu-id="34218-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="34218-113">Alle Anrufe in der Warteschlange werden mithilfe einer der folgenden Methoden an Agents gesendet:</span><span class="sxs-lookup"><span data-stu-id="34218-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="34218-114">Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="34218-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="34218-115">Beim seriellen Routing klingelt der erste Anruf in der Warteschlange alle Anruf-Agents einzeln.</span><span class="sxs-lookup"><span data-stu-id="34218-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="34218-116">Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="34218-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

<span data-ttu-id="34218-117">Mit einer der oben genannten Methoden können Sie Optionen für die Anrufbehandlung festlegen, wie beispielsweise die Option zum Deaktivieren des Agents, Anwesenheits basiertes Routing, Wartezeiten für Anrufe und Anruf Timeouts.</span><span class="sxs-lookup"><span data-stu-id="34218-117">You can set call handling options, such as agent opt-in/opt-out, presence-based routing, call wait time, and call time-out options with any of the above methods.</span></span>

<span data-ttu-id="34218-118">Nur eine Benachrichtigung über eingehende Anrufe (für den Anruf am Kopf der Warteschlange) geht zu einem Zeitpunkt an die Anruf Agenten.</span><span class="sxs-lookup"><span data-stu-id="34218-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span> <span data-ttu-id="34218-119">Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.</span><span class="sxs-lookup"><span data-stu-id="34218-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="34218-120">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="34218-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="34218-121">Schritt 1 – erste Schritte</span><span class="sxs-lookup"><span data-stu-id="34218-121">Step 1 — Get started</span></span>

<span data-ttu-id="34218-122">Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:</span><span class="sxs-lookup"><span data-stu-id="34218-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="34218-123">Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34218-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="34218-124">Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="34218-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="34218-125">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)für das Telefon System verwenden.</span><span class="sxs-lookup"><span data-stu-id="34218-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="34218-126">Telefon System ermöglicht Telefonnummern auf Organisationsebene zur Verwendung mit kostengünstigen automatischen Telefonzentralen und Anrufwarteschlangen-Diensten.</span><span class="sxs-lookup"><span data-stu-id="34218-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="34218-127">Direct Routing-Dienstnummern für Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34218-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="34218-128">Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen.</span><span class="sxs-lookup"><span data-stu-id="34218-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="34218-129">Nähers hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="34218-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="34218-130">Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="34218-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="34218-131">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="34218-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="34218-132">Weitere Informationen zu Office 365-Anrufplänen finden Sie unter [Telefon System-und Anrufpläne](calling-plan-landing-page.md) sowie [Anrufpläne für Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="34218-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="34218-133">Sie können nur Cloud-Anrufwarteschlangen gebührenpflichtige und gebührenfreie Service-Telefonnummern zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten haben oder von einem anderen Dienstanbieter übertragen wurden.</span><span class="sxs-lookup"><span data-stu-id="34218-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="34218-134">Für gebührenfreie Servicenummern sind Kommunikationsguthaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34218-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="34218-135">Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34218-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="34218-136">Die folgenden Clients werden für Anruf-Agents unterstützt, die einer Cloud-Anrufwarteschlange zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="34218-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="34218-137">Skype for Business-Desktop Client 2016 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="34218-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="34218-138">Lync-Desktop Client 2013 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="34218-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="34218-139">Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="34218-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="34218-140">Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="34218-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="34218-141">Mac Skype for Business-Client (Version 16.8.196 und höher)</span><span class="sxs-lookup"><span data-stu-id="34218-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="34218-142">Android Skype for Business-Client (Version 6.16.0.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="34218-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="34218-143">iPhone Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="34218-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="34218-144">Mac Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="34218-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="34218-145">Microsoft Teams Windows-Client (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="34218-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="34218-146">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="34218-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="34218-147">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="34218-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="34218-148">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="34218-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="34218-149">Anrufwarteschlangen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, lync-Clients oder Skype for Business-IP-Telefone als Agents.</span><span class="sxs-lookup"><span data-stu-id="34218-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="34218-150">Schritt 2: Abrufen oder übertragen von gebührenpflichtigen oder gebührenfreien Telefonnummern für Dienstleistungen</span><span class="sxs-lookup"><span data-stu-id="34218-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="34218-151">Bevor Sie Ihre Anrufwarteschlangen erstellen und einrichten können, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="34218-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="34218-152">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md) oder, wenn Sie eine vorhandene Dienstnummer übertragen möchten, unter [Übertragen von Telefonnummern zu Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="34218-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="34218-153">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > -**sprach** > **Telefonnummern**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34218-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="34218-154">Gebührenfreie Nummern werden mit einem **Nummerntyp** für **Dienstleistungen (gebührenfrei**) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="34218-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="34218-155">Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="34218-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="34218-156">Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.</span><span class="sxs-lookup"><span data-stu-id="34218-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="34218-157">Wenn Sie mehrere automatische Telefonzentralen einrichten, weisen Sie normalerweise dem Ressourcenkonto der primären automatischen Telefonzentrale eine Telefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="34218-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="34218-158">Ressourcenkonten, die geschachtelten automatischen Telefonzentralen oder Anrufwarteschlangen zugeordnet sind, benötigen häufig keine Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="34218-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="34218-159">Diese automatische Telefonzentrale kann Anrufer an Ihre Anrufwarteschlangen oder geschachtelte automatische Telefonzentralen weiterleiten, selbst wenn Sie keine Telefonnummer haben.</span><span class="sxs-lookup"><span data-stu-id="34218-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="34218-160">In diesen Fällen können Sie alle automatischen Telefonzentralen erstellen und Warteschlangen in Ihrem System anrufen, ohne dass Sie die Optionen für die Wähltasten zuweisen, und die Einstellungen später bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="34218-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="34218-161">Es muss eine Anrufwarteschlange oder eine automatische Telefonzentrale vorhanden sein, um Sie als Menüoption zu definieren.</span><span class="sxs-lookup"><span data-stu-id="34218-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="34218-162">Schritt 3 – Erstellen einer Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="34218-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="34218-163">Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34218-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="34218-164">Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.</span><span class="sxs-lookup"><span data-stu-id="34218-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="34218-165">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="34218-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="34218-166">Klicken Sie im **Microsoft Teams Admin Center**auf**Warteschlangen**für **sprach** > Anrufe und dann auf **+ Neu hinzufügen**:</span><span class="sxs-lookup"><span data-stu-id="34218-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="34218-167">Einrichten des Anzeige namens und des Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="34218-167">Set the display name and resource account</span></span>

![Screenshot einer neuen Anrufwarteschlange mit nummerierten Beschriftungen](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="34218-169">![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/teamscallout1.png)
-**Namen** geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="34218-169">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="34218-170">Dieser Name ist erforderlich und kann bis zu 64 Zeichen enthalten, einschließlich Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="34218-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="34218-171">Dieser Name wird in der Benachrichtigung für den eingehenden Anruf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34218-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="34218-172">![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/teamscallout2.png)
**Hinzufügen von Konten** wählen Sie ein Ressourcenkonto aus.</span><span class="sxs-lookup"><span data-stu-id="34218-172">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="34218-173">Alle Anrufwarteschlangen sind für ein Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34218-173">All call queues are required to have a resource account.</span></span> <span data-ttu-id="34218-174">Für Ressourcenkonten ist keine Dienst gebührenpflichtige oder gebührenfreie Telefonnummer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34218-174">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="34218-175">Wenn keine Liste aufgeführt ist, rufen Sie Dienstnummern ab, und weisen Sie Sie einem Ressourcenkonto zu, bevor Sie die Anrufwarteschlange erstellen, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34218-175">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="34218-176">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="34218-176">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="34218-177">Einzelheiten zum Zuweisen einer Telefonnummer finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="34218-177">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="34218-178">Wenn Sie eine **Domäne** zuweisen möchten oder müssen, weisen Sie diese dem Ressourcenkonto für die Anrufwarteschlange zu.</span><span class="sxs-lookup"><span data-stu-id="34218-178">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="34218-179">Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="34218-179">Set the greeting and music played while on hold</span></span>

![Screenshot der Optionen für Begrüßung und Musik mit nummerierten Beschriftungen](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="34218-181">![Symbol der Zahl 1, verweist auf eine Legende im](media/teamscallout1.png)
**vorherigen Screenshot,** in der die optionale Ansage für Personen, die die Anruf Warteschlangennummer anrufen, abgespielt wird.</span><span class="sxs-lookup"><span data-stu-id="34218-181">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="34218-182">Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.</span><span class="sxs-lookup"><span data-stu-id="34218-182">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="34218-183">![Symbol der Zahl 2, verweist auf eine Legende in der vorherigen Screenshot](media/teamscallout2.png)
-**Musik** in der Warteschleife können Sie die standardmäßige Musik in der Warteschlange verwenden.</span><span class="sxs-lookup"><span data-stu-id="34218-183">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="34218-184">Sie können auch eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="34218-184">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="34218-185">Wählen Sie die Optionen für die Anrufannahme aus.</span><span class="sxs-lookup"><span data-stu-id="34218-185">Select the call answering options</span></span>

![Screenshot der Optionen für die Anrufannahme](media/teams-cq-call-answering-options.png)

<span data-ttu-id="34218-187">![Symbol der Zahl 1, verweist auf eine Legende in den vorherigen Screenshot](media/teamscallout1.png)
-**Anruf-Agents und-Gruppen** , um einzelne Agents direkt hinzuzufügen, ohne Sie zu einer Gruppe hinzuzufügen, klicken Sie auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34218-187">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="34218-188">Legen Sie einzelne Agents in der Reihenfolge ab, in der Sie den Anruf empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="34218-188">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="34218-189">Sie können bis zu 20 einzelne Agents hinzufügen (um mehr als 20 hinzuzufügen, um Sie in einer Gruppe zu speichern).</span><span class="sxs-lookup"><span data-stu-id="34218-189">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="34218-190">Anrufe werden zuerst an einzelne Agents und dann an die Agents in Gruppen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="34218-190">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="34218-191">Sie können bis zu 200-Anruf-Agents auswählen, die zu einer der folgenden Mailinglisten oder-Gruppen gehören:</span><span class="sxs-lookup"><span data-stu-id="34218-191">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="34218-192">Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="34218-192">Office 365 group</span></span>
- <span data-ttu-id="34218-193">Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="34218-193">Security group</span></span>
- <span data-ttu-id="34218-194">Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="34218-194">Distribution list</span></span>

<span data-ttu-id="34218-195">Ausgewählte Anruf-Agents müssen eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="34218-195">Call agents selected must be one of the following:</span></span>

- <span data-ttu-id="34218-196">Online-Benutzer mit einer Telefon System Lizenz und Enterprise-VoIP aktiviert</span><span class="sxs-lookup"><span data-stu-id="34218-196">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="34218-197">Online Benutzer mit einem Anrufplan</span><span class="sxs-lookup"><span data-stu-id="34218-197">Online users with a Calling Plan</span></span>
- <span data-ttu-id="34218-198">Lokale Skype for Business Server-Benutzer</span><span class="sxs-lookup"><span data-stu-id="34218-198">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="34218-199">Dies gilt auch, wenn Sie Anrufe an Personen in Ihrer Organisation umleiten möchten, die Online sind.</span><span class="sxs-lookup"><span data-stu-id="34218-199">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="34218-200">Diese Personen müssen über eine **Telefon System** Lizenz und Enterprise-VoIP verfügen *oder* über einen Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="34218-200">These individuals must have a **Phone System** license and Enterprise Voice enabled *or* have a Calling Plan.</span></span> <span data-ttu-id="34218-201">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen für Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Zuweisen von Microsoft Teams-Lizenzen](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)oder [der richtige Anrufplan für Sie?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="34218-201">For more information, see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="34218-202">Um einen Agenten für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="34218-202">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="34218-203">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="34218-203">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="34218-204">Benutzer mit einer **Telefon System** Lizenz oder einem Anrufplan, die einer Office 365-Gruppe hinzugefügt werden eine e-Mail-aktivierte Verteilerliste oder eine Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="34218-204">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="34218-205">Wenn Sie einen Agenten in einer Verteilerliste oder einer Sicherheitsgruppe als Anruf Warteschlangen-Agent hinzufügen, kann es bis zu drei Stunden dauern, bis der erste Anruf eintrifft.</span><span class="sxs-lookup"><span data-stu-id="34218-205">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="34218-206">Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="34218-206">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="34218-207">Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34218-207">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="34218-208">Wenn Ihre Agents die Microsoft Teams-App für Anruf Warteschlangen Anrufe verwenden, müssen Sie sich im TeamsOnly-Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="34218-208">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="34218-209">![Symbol der Zahl 2, verweist auf eine Legende in der vorherigen Screenshot](media/teamscallout2.png)
 **-Routing Methode** Sie können entweder **Attendant**, **Serial**oder **Round Robin** als Verteilungsmethode auswählen.</span><span class="sxs-lookup"><span data-stu-id="34218-209">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="34218-210">Standardmäßig sind für alle neuen und vorhandenen Anrufwarteschlangen das Attendant-Routing ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="34218-210">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="34218-211">Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="34218-211">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="34218-212">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="34218-212">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="34218-213">Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt.</span><span class="sxs-lookup"><span data-stu-id="34218-213">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="34218-214">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="34218-214">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="34218-215">**Serielles Routing** eingehende Anrufe Klingeln alle Anruf-Agents eins nach dem anderen vom Anfang der Anruf Agentenliste.</span><span class="sxs-lookup"><span data-stu-id="34218-215">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="34218-216">Agents können nicht in der Liste der Anruf-Agents bestellt werden.</span><span class="sxs-lookup"><span data-stu-id="34218-216">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="34218-217">Wenn ein Agent einen Anruf abschließt oder nicht annimmt, klingelt der Anruf beim nächsten Agenten und versucht alle Agenten, bis er abgeholt wird oder ein Timeout annimmt.</span><span class="sxs-lookup"><span data-stu-id="34218-217">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
- <span data-ttu-id="34218-218">**Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="34218-218">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="34218-219">Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="34218-219">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

<span data-ttu-id="34218-220">![Symbol der Zahl 3, verweist auf eine Legende im vorherigen Screenshot](media/teamscallout3.png)
**Anwesenheits** basiertes Routing-Anwesenheits basiertes Routing verwendet den Verfügbarkeitsstatus von Anruf-Agents, um zu ermitteln, ob ein Agent in die Anruf Weiterleitungsliste für die ausgewählte Routingmethode aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="34218-220">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Presence-based routing** Presence-based routing uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="34218-221">Anruf-Agents, deren Verfügbarkeitsstatus auf **verfügbar** festgesetzt ist, sind in der Anruf Weiterleitungsliste enthalten und können Anrufe empfangen.</span><span class="sxs-lookup"><span data-stu-id="34218-221">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="34218-222">Agents, deren Verfügbarkeitsstatus auf einen beliebigen anderen Status festgesetzt ist, werden aus der Anruf Weiterleitungsliste ausgeschlossen und empfangen keine Anrufe, bis sich der Verfügbarkeitsstatus wieder in **verfügbar**ändert.</span><span class="sxs-lookup"><span data-stu-id="34218-222">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span>

<span data-ttu-id="34218-223">Sie können das anwesenheitsbasierte Anrufrouting mit einer der Routingmethoden aktivieren.</span><span class="sxs-lookup"><span data-stu-id="34218-223">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="34218-224">Wenn sich ein Agent für das Abrufen von Anrufen entscheidet, wird er nicht in die Anruf Weiterleitungsliste aufgenommen, unabhängig davon, auf welchen Verfügbarkeitsstatus er festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="34218-224">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span>

> [!CAUTION]
> <span data-ttu-id="34218-225">Agents, die den Skype for Business-Client verwenden, sind nicht in der Anruf Weiterleitungsliste enthalten, wenn das anwesenheitsbasierte Routing unabhängig von deren Verfügbarkeitsstatus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="34218-225">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled, regardless of their availability status.</span></span> <span data-ttu-id="34218-226">Agenten, die nicht in der Anruf Weiterleitungsliste sind, erhalten keine Anrufe.</span><span class="sxs-lookup"><span data-stu-id="34218-226">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="34218-227">Wenn Sie über Agenten verfügen, die Skype for Business verwenden, aktivieren Sie das anwesenheitsbasierte Anrufrouting nicht.</span><span class="sxs-lookup"><span data-stu-id="34218-227">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="34218-228">Auswählen einer Option für den Agenten Ausstieg</span><span class="sxs-lookup"><span data-stu-id="34218-228">Select an agent opt-out option</span></span>

![Screenshot der Optionen für das ablehnen von Agents mit nummerierten Beschriftungen](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="34218-230">![Symbol der Zahl 1, bezieht sich auf eine Legende im vorherigen](media/teamscallout1.png)
Screenshot-**Agent kann das Abrufen von Anrufen ablehnen** Sie können festlegen, dass Anruf Warteschlangen-Agents das ablehnen von Anrufen aus einer bestimmten Warteschlange zulassen, indem Sie diese Option aktivieren.</span><span class="sxs-lookup"><span data-stu-id="34218-230">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="34218-231">Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden.</span><span class="sxs-lookup"><span data-stu-id="34218-231">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="34218-232">Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).</span><span class="sxs-lookup"><span data-stu-id="34218-232">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="34218-233">Um auf die Option "ablehnen" zuzugreifen, können Agents:</span><span class="sxs-lookup"><span data-stu-id="34218-233">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="34218-234">Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.</span><span class="sxs-lookup"><span data-stu-id="34218-234">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="34218-235">Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="34218-235">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="34218-236">Klicken Sie auf der Seite Benutzereinstellungen auf **Anrufwarteschlangen**, und deaktivieren Sie dann die Kontrollkästchen, um Warteschlangen abzulehnen.</span><span class="sxs-lookup"><span data-stu-id="34218-236">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="34218-237">Agents, die apps oder Endpunkte außer Skype for Business Desktop verwenden, können auf die Option "ablehnen" im [https://aka.ms/cqsettings](https://aka.ms/cqsettings)Portal "Benutzereinstellungen" zugreifen.</span><span class="sxs-lookup"><span data-stu-id="34218-237">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="34218-238">Wenn sich die Agents in Microsoft Teams-Desktop Clients befinden, können Sie diese mithilfe der Anrufeinstellungen ablehnen.</span><span class="sxs-lookup"><span data-stu-id="34218-238">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="34218-239">![Symbol der Zahl 2, bezieht sich auf einen Callout in der](media/teamscallout2.png)
**Benachrichtigungseinstellung** vorheriger Screenshot-Agent</span><span class="sxs-lookup"><span data-stu-id="34218-239">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="34218-240">Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.</span><span class="sxs-lookup"><span data-stu-id="34218-240">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="34218-241">Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="34218-241">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="34218-242">Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung</span><span class="sxs-lookup"><span data-stu-id="34218-242">Set the call overflow and timeout handling options</span></span>

![Screenshot der Überlauf Behandlungsoptionen mit nummerierten Beschriftungen](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="34218-244">![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot](media/teamscallout1.png)
**Maximale Anrufe in der Warteschlange** verwenden Sie diese Einstellung, um die maximale Anzahl von Anrufen festzulegen, die gleichzeitig in der Warteschlange warten können.</span><span class="sxs-lookup"><span data-stu-id="34218-244">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="34218-245">Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen.</span><span class="sxs-lookup"><span data-stu-id="34218-245">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="34218-246">Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie Sie den Wert für die **Maximale Anzahl von Anrufen** festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="34218-246">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="34218-247">![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot](media/teamscallout2.png)
,**Wenn die maximale Anzahl von Anrufen erreicht wird** , wenn die Anrufwarteschlange die maximale Größe erreicht (mit der Einstellung Maximale Anzahl von **anrufen in der Warteschlange** festlegen), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.</span><span class="sxs-lookup"><span data-stu-id="34218-247">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="34218-248">**Verbindung trennen** Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="34218-248">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="34218-249">**Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="34218-249">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="34218-250">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat.</span><span class="sxs-lookup"><span data-stu-id="34218-250">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="34218-251">Sie können es so einrichten, dass der Anrufer an Voicemail gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="34218-251">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="34218-252">Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="34218-252">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="34218-253">Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="34218-253">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="34218-254">**Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="34218-254">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

<span data-ttu-id="34218-255">![Symbol der Zahl 3, bezieht sich auf eine Legende im vorherigen](media/teamscallout3.png)
Screenshot-**Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und muss umgeleitet oder getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="34218-255">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="34218-256">Die Stelle, an der Sie umgeleitet wird, basiert auf der Festlegung des Timeouts für **einen Anruf** .</span><span class="sxs-lookup"><span data-stu-id="34218-256">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="34218-257">Sie können eine Dauer von 0 bis 45 Minuten festlegen.</span><span class="sxs-lookup"><span data-stu-id="34218-257">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="34218-258">Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="34218-258">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="34218-259">Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="34218-259">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="34218-260">So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.</span><span class="sxs-lookup"><span data-stu-id="34218-260">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="34218-261">![Symbol der Zahl 4, bezieht sich auf eine Legende im vorherigen](media/teamscallout4.png)
Screenshot, wenn der Anruf**ausfällt** , wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit dem Anruf geschieht:</span><span class="sxs-lookup"><span data-stu-id="34218-261">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="34218-262">**Verbindung trennen** Der Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="34218-262">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="34218-263">**Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="34218-263">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="34218-264">**Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat.</span><span class="sxs-lookup"><span data-stu-id="34218-264">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="34218-265">Wenn Sie die Person so einrichten möchten, dass Sie an Voicemail gesendet werden kann, wählen Sie eine **Person in Ihrem Unternehmen** aus, und legen Sie diese Person so fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="34218-265">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="34218-266">Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="34218-266">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="34218-267">**Sprach-App** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die Sie bereits erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="34218-267">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="34218-268">Ändern der Rufnummernanzeige für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="34218-268">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="34218-269">Um die Identität eines Anruf Agenten zu schützen, ändern Sie die Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer mit dem Cmdlet **New-CsCallingLineIdentity** wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="34218-269">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="34218-270">Wenden Sie dann die Richtlinie für den Benutzer mit dem **Grant-CallingLineIdentity-** Cmdlet wie im folgenden Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="34218-270">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="34218-271">Weitere Informationen finden Sie unter [wie kann die Anrufer-ID in Ihrer Organisation verwendet werden](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="34218-271">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="34218-272">Cmdlets für Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="34218-272">Call queue cmdlets</span></span>

<span data-ttu-id="34218-273">Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="34218-273">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="34218-274">Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.</span><span class="sxs-lookup"><span data-stu-id="34218-274">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="34218-275">Neu – CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="34218-275">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="34218-276">Satz-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="34218-276">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="34218-277">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="34218-277">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="34218-278">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="34218-278">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="34218-279">Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34218-279">More about Windows PowerShell</span></span>

- <span data-ttu-id="34218-280">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="34218-280">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="34218-281">Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten.</span><span class="sxs-lookup"><span data-stu-id="34218-281">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="34218-282">Sie können Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="34218-282">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="34218-283">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="34218-283">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="34218-284">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="34218-284">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="34218-285">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="34218-285">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="34218-286">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität über das Microsoft Teams Admin Center, wenn Sie Änderungen für viele Benutzer gleichzeitig vornehmen.</span><span class="sxs-lookup"><span data-stu-id="34218-286">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="34218-287">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="34218-287">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="34218-288">Verwalten von Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34218-288">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="34218-289">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34218-289">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="34218-290">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="34218-290">Related topics</span></span>

[<span data-ttu-id="34218-291">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="34218-291">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="34218-292">Abrufen von Diensttelefonnummern</span><span class="sxs-lookup"><span data-stu-id="34218-292">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="34218-293">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="34218-293">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="34218-294">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="34218-294">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
