---
title: Konfigurieren des VoIP-Routings für das direkte Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie das VoIP-Routing mit Microsoft Phone System Direct Routing konfigurieren.
ms.openlocfilehash: 0611684c79d92572ade41f2545096fe1d9bb4dd2
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159012"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="90fe7-103">Konfigurieren des VoIP-Routings für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="90fe7-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="90fe7-104">In diesem Artikel wird beschrieben, wie Sie das VoIP-Routing für das direkte Routing von Telefonsystemen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90fe7-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="90fe7-105">Dies ist Schritt 3 der folgenden Schritte zum Konfigurieren des direkten Routings:</span><span class="sxs-lookup"><span data-stu-id="90fe7-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="90fe7-106">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="90fe7-106">Step 1.</span></span> [<span data-ttu-id="90fe7-107">Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="90fe7-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="90fe7-108">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="90fe7-108">Step 2.</span></span> [<span data-ttu-id="90fe7-109">Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail</span><span class="sxs-lookup"><span data-stu-id="90fe7-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="90fe7-110">**Schritt 3. Konfigurieren des VoIP-Routings** (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="90fe7-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="90fe7-111">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="90fe7-111">Step 4.</span></span> [<span data-ttu-id="90fe7-112">Übersetzen von Zahlen in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="90fe7-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="90fe7-113">Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="90fe7-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="90fe7-114">Übersicht über das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="90fe7-114">Voice routing overview</span></span>

<span data-ttu-id="90fe7-115">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten Session Border Controller (SBC) basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="90fe7-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="90fe7-116">Das so genannte Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="90fe7-116">The called number pattern</span></span> 
- <span data-ttu-id="90fe7-117">Das angerufene Zahlenmuster und der spezifische Benutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="90fe7-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="90fe7-118">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="90fe7-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="90fe7-119">Wenn der als aktiv konfigurierte SBC für eine bestimmte Anrufroute nicht zur Verfügung steht, wird der Anruf an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="90fe7-120">Das VoIP-Routing besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="90fe7-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="90fe7-121">**VoIP-Routing Richtlinie** – ein Container für PSTN-Nutzungen, der einem Benutzer oder mehreren Benutzern zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="90fe7-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="90fe7-122">**PSTN-Verwendungen** – ein Container für VoIP-Routen und PSTN-Nutzungen, der in verschiedenen VoIP-Routing Richtlinien freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="90fe7-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="90fe7-123">**VoIP-Routen** – ein Zahlenmuster und eine Reihe von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="90fe7-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="90fe7-124">**Online-PSTN-Gateway** – ein Zeiger auf einen SBC, der auch die Konfiguration speichert, die angewendet wird, wenn ein Anruf über den SBC durchgeführt wird, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="90fe7-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="90fe7-125">Beispiel 1: VoIP-Routing mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="90fe7-125">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="90fe7-126">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien in einem Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="90fe7-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="90fe7-127">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="90fe7-128">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="90fe7-129">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="90fe7-130">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="90fe7-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="90fe7-131">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="90fe7-133">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="90fe7-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="90fe7-134">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="90fe7-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="90fe7-135">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="90fe7-136">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="90fe7-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="90fe7-137">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="90fe7-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="90fe7-139">Bei allen anderen anrufen:</span><span class="sxs-lookup"><span data-stu-id="90fe7-139">For all other calls:</span></span>

- <span data-ttu-id="90fe7-140">Wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan), wird die automatische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="90fe7-141">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, wird der Anruf über den Microsoft-Anrufplan weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="90fe7-142">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf verworfen, weil keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="90fe7-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="90fe7-143">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da nur eine Route vorhanden ist, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="90fe7-143">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="90fe7-144">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="90fe7-145">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="90fe7-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="90fe7-146">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung, "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="90fe7-146">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="90fe7-147">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="90fe7-147">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="90fe7-148">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="90fe7-148">**PSTN usage**</span></span>|<span data-ttu-id="90fe7-149">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="90fe7-149">**Voice route**</span></span>|<span data-ttu-id="90fe7-150">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="90fe7-150">**Number pattern**</span></span>|<span data-ttu-id="90fe7-151">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="90fe7-151">**Priority**</span></span>|<span data-ttu-id="90fe7-152">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="90fe7-152">**SBC**</span></span>|<span data-ttu-id="90fe7-153">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="90fe7-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90fe7-154">USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-154">US and Canada</span></span>|<span data-ttu-id="90fe7-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="90fe7-155">"Redmond 1"</span></span>|<span data-ttu-id="90fe7-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="90fe7-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="90fe7-157">1</span><span class="sxs-lookup"><span data-stu-id="90fe7-157">1</span></span>|<span data-ttu-id="90fe7-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="90fe7-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="90fe7-160">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="90fe7-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="90fe7-161">USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-161">US and Canada</span></span>|<span data-ttu-id="90fe7-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="90fe7-162">"Redmond 2"</span></span>|<span data-ttu-id="90fe7-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="90fe7-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="90fe7-164">2</span><span class="sxs-lookup"><span data-stu-id="90fe7-164">2</span></span>|<span data-ttu-id="90fe7-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="90fe7-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="90fe7-167">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="90fe7-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="90fe7-168">USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-168">US and Canada</span></span>|<span data-ttu-id="90fe7-169">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="90fe7-169">"Other +1"</span></span>|<span data-ttu-id="90fe7-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="90fe7-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="90fe7-171">3</span><span class="sxs-lookup"><span data-stu-id="90fe7-171">3</span></span>|<span data-ttu-id="90fe7-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="90fe7-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="90fe7-174">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="90fe7-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="90fe7-175">Beispiel 1: Konfigurationsschritte</span><span class="sxs-lookup"><span data-stu-id="90fe7-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="90fe7-176">Im folgenden Beispiel wird gezeigt, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="90fe7-176">The following example shows how to:</span></span>

1. <span data-ttu-id="90fe7-177">Erstellen Sie eine einzelne PSTN-Nutzung.</span><span class="sxs-lookup"><span data-stu-id="90fe7-177">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="90fe7-178">Konfigurieren von drei VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="90fe7-178">Configure three voice routes.</span></span>
3. <span data-ttu-id="90fe7-179">Erstellen einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="90fe7-179">Create a voice routing policy.</span></span>
4. <span data-ttu-id="90fe7-180">Weisen Sie die Richtlinie einem Benutzernamens Spencer Low zu.</span><span class="sxs-lookup"><span data-stu-id="90fe7-180">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="90fe7-181">Sie können das [Microsoft Teams Admin Center](#admincenterexample1) oder [PowerShell](#powershellexample1) verwenden, um diese Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-181">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="90fe7-182">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="90fe7-182">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="90fe7-183">Schritt 1: Erstellen der PSTN-Nutzung in den USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-183">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="90fe7-184">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice** > **Direct Routing**, und wählen Sie dann in der oberen rechten Ecke die Option **PSTN-Verwendungsdaten Sätze verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="90fe7-184">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="90fe7-185">Klicken Sie auf **Hinzufügen**, geben Sie **USA und Kanada**ein, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-185">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="90fe7-186">Schritt 2: Erstellen von drei VoIP-Routen (Redmond 1, Redmond 2 und andere + 1)</span><span class="sxs-lookup"><span data-stu-id="90fe7-186">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="90fe7-187">In den folgenden Schritten wird beschrieben, wie Sie eine VoIP-Route erstellen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-187">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="90fe7-188">Führen Sie die folgenden Schritte aus, um die drei VoIP-Routen mit dem Namen Redmond 1, Redmond 2 und other + 1 für dieses Beispiel zu erstellen, indem Sie die Einstellungen verwenden, die in der vorherigen Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="90fe7-188">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="90fe7-189">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice** > **Direct Routing**, und wählen Sie dann die Registerkarte **VoIP-Routen** aus.</span><span class="sxs-lookup"><span data-stu-id="90fe7-189">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="90fe7-190">Klicken Sie auf **Hinzufügen**, und geben Sie dann einen Namen und eine Beschreibung für die VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="90fe7-190">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="90fe7-191">Legen Sie die Priorität fest, und geben Sie das Muster für die gewählte Nummer an.</span><span class="sxs-lookup"><span data-stu-id="90fe7-191">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="90fe7-192">Wenn Sie einen SBC mit der VoIP-Route registrieren möchten, klicken Sie unter **SBCS registriert (optional)** auf **Add SBCS**, wählen Sie die SBCS aus, die Sie registrieren möchten, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-192">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="90fe7-193">Wenn Sie PSTN-Verwendungsdaten Sätze hinzufügen möchten, klicken Sie unter PSTN-Verwendungs **Datensätze (optional)** auf **PSTN-Verwendung hinzufügen**, wählen Sie die hinzuzufügenden PSTN-Einträge aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-193">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="90fe7-194">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-194">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="90fe7-195">Schritt 3: Erstellen einer VoIP-Routing Richtlinie mit dem Namen "nur US" und Hinzufügen der PSTN-Nutzung "USA und Kanada" zur Richtlinie</span><span class="sxs-lookup"><span data-stu-id="90fe7-195">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="90fe7-196">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Routing Richtlinien**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="90fe7-197">Geben Sie **uns nur** als Namen ein, und fügen Sie eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="90fe7-197">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="90fe7-198">Klicken Sie unter **PSTN-Verwendungsdaten Sätze**auf **PSTN-Verwendung hinzufügen**, wählen Sie den PSTN-Verwendungs Eintrag "USA und Kanada" aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-198">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="90fe7-199">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-199">Click **Save**.</span></span>

<span data-ttu-id="90fe7-200">Weitere Informationen finden Sie unter [Verwalten von VoIP-Routing Richtlinien](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="90fe7-200">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="90fe7-201">Schritt 4: Zuweisen der VoIP-Routing Richtlinie zu einem Benutzer mit dem Namen Spencer Low</span><span class="sxs-lookup"><span data-stu-id="90fe7-201">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="90fe7-202">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="90fe7-202">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="90fe7-203">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-203">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="90fe7-204">Wählen Sie unter **VoIP-Routing Richtlinie**die Richtlinie "nur US" aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-204">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="90fe7-205">Weitere Informationen finden Sie unter [Verwalten von VoIP-Routing Richtlinien](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="90fe7-205">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="90fe7-206">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="90fe7-206">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="90fe7-207">Schritt 1: Erstellen der PSTN-Nutzung in den USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-207">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="90fe7-208">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-208">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="90fe7-209">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="90fe7-209">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="90fe7-210">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="90fe7-210">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="90fe7-211">Das folgende Beispiel zeigt das Ergebnis der Ausführung des `(Get-CSOnlinePSTNUsage).usage` PowerShell-Befehls zum Anzeigen von vollständigen Namen (nicht abgeschnitten):</span><span class="sxs-lookup"><span data-stu-id="90fe7-211">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="90fe7-212">Schritt 2: Erstellen von drei VoIP-Routen (Redmond 1, Redmond 2 und andere + 1)</span><span class="sxs-lookup"><span data-stu-id="90fe7-212">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="90fe7-213">Um die Route "Redmond 1" zu erstellen, geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-213">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="90fe7-214">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="90fe7-214">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="90fe7-215">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-215">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="90fe7-216">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-216">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="90fe7-217">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="90fe7-217">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="90fe7-218">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="90fe7-218">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="90fe7-219">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="90fe7-219">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="90fe7-220">Alle Anrufe an denselben SBC weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="90fe7-220">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="90fe7-221">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der Optionen wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="90fe7-221">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="90fe7-222">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="90fe7-222">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

<span data-ttu-id="90fe7-223">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-223">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="90fe7-224">Schritt 3: Erstellen einer VoIP-Routing Richtlinie mit dem Namen "nur US" und Hinzufügen der PSTN-Nutzung "USA und Kanada" zur Richtlinie</span><span class="sxs-lookup"><span data-stu-id="90fe7-224">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="90fe7-225">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-225">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="90fe7-226">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="90fe7-226">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="90fe7-227">Schritt 4: Zuweisen der VoIP-Routing Richtlinie zu einem Benutzer mit dem Namen Spencer Low</span><span class="sxs-lookup"><span data-stu-id="90fe7-227">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="90fe7-228">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-228">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="90fe7-229">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="90fe7-229">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="90fe7-230">Der Befehl gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="90fe7-230">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="90fe7-231">Beispiel 2: VoIP-Routing mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="90fe7-231">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="90fe7-232">Die in Beispiel 1 erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada – es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-232">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="90fe7-233">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-233">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="90fe7-234">Die Richtlinie verwendet die in Beispiel 1 erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International".</span><span class="sxs-lookup"><span data-stu-id="90fe7-234">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="90fe7-235">Diese Richtlinie leitet alle anderen Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weiter.</span><span class="sxs-lookup"><span data-stu-id="90fe7-235">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="90fe7-236">In den Beispielen, die angezeigt werden, weisen Sie die nur US-Richtlinie Benutzern Spencer Low und die Richtlinie "keine Einschränkungen" für den Benutzer John Woods zu, damit das Routing wie folgt erfolgt:</span><span class="sxs-lookup"><span data-stu-id="90fe7-236">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="90fe7-237">Spencer Low – nur US-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="90fe7-237">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="90fe7-238">Anrufe sind nur für US-und kanadische Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="90fe7-238">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="90fe7-239">Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90fe7-239">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="90fe7-240">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-240">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="90fe7-241">John Woods – internationale Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="90fe7-241">John Woods – International policy.</span></span>  <span data-ttu-id="90fe7-242">Anrufe sind an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="90fe7-242">Calls are allowed to any number.</span></span> <span data-ttu-id="90fe7-243">Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90fe7-243">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="90fe7-244">Nicht-US-Nummern werden mit sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-244">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="90fe7-246">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="90fe7-246">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="90fe7-247">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, wird der Anruf mit dem Microsoft-Anrufplan weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-247">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="90fe7-248">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="90fe7-248">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="90fe7-250">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-250">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="90fe7-251">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="90fe7-251">**PSTN usage**</span></span>|<span data-ttu-id="90fe7-252">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="90fe7-252">**Voice route**</span></span>|<span data-ttu-id="90fe7-253">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="90fe7-253">**Number pattern**</span></span>|<span data-ttu-id="90fe7-254">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="90fe7-254">**Priority**</span></span>|<span data-ttu-id="90fe7-255">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="90fe7-255">**SBC**</span></span>|<span data-ttu-id="90fe7-256">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="90fe7-256">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90fe7-257">USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-257">US and Canada</span></span>|<span data-ttu-id="90fe7-258">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="90fe7-258">"Redmond 1"</span></span>|<span data-ttu-id="90fe7-259">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="90fe7-259">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="90fe7-260">1</span><span class="sxs-lookup"><span data-stu-id="90fe7-260">1</span></span>|<span data-ttu-id="90fe7-261">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-261">sbc1.contoso.biz</span></span><br/><span data-ttu-id="90fe7-262">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-262">sbc2.contoso.biz</span></span>|<span data-ttu-id="90fe7-263">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="90fe7-263">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="90fe7-264">USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-264">US and Canada</span></span>|<span data-ttu-id="90fe7-265">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="90fe7-265">"Redmond 2"</span></span>|<span data-ttu-id="90fe7-266">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="90fe7-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="90fe7-267">2</span><span class="sxs-lookup"><span data-stu-id="90fe7-267">2</span></span>|<span data-ttu-id="90fe7-268">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-268">sbc3.contoso.biz</span></span><br/><span data-ttu-id="90fe7-269">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-269">sbc4.contoso.biz</span></span>|<span data-ttu-id="90fe7-270">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="90fe7-270">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="90fe7-271">USA und Kanada</span><span class="sxs-lookup"><span data-stu-id="90fe7-271">US and Canada</span></span>|<span data-ttu-id="90fe7-272">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="90fe7-272">"Other +1"</span></span>|<span data-ttu-id="90fe7-273">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="90fe7-273">^\\+1(\d{10})$</span></span>|<span data-ttu-id="90fe7-274">3</span><span class="sxs-lookup"><span data-stu-id="90fe7-274">3</span></span>|<span data-ttu-id="90fe7-275">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-275">sbc5.contoso.biz</span></span><br/><span data-ttu-id="90fe7-276">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-276">sbc6.contoso.biz</span></span>|<span data-ttu-id="90fe7-277">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="90fe7-277">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="90fe7-278">International</span><span class="sxs-lookup"><span data-stu-id="90fe7-278">International</span></span>|<span data-ttu-id="90fe7-279">International</span><span class="sxs-lookup"><span data-stu-id="90fe7-279">International</span></span>|<span data-ttu-id="90fe7-280">\d +</span><span class="sxs-lookup"><span data-stu-id="90fe7-280">\d+</span></span>|<span data-ttu-id="90fe7-281">4</span><span class="sxs-lookup"><span data-stu-id="90fe7-281">4</span></span>|<span data-ttu-id="90fe7-282">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-282">sbc2.contoso.biz</span></span><br/><span data-ttu-id="90fe7-283">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="90fe7-283">sbc5.contoso.biz</span></span>|<span data-ttu-id="90fe7-284">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="90fe7-284">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="90fe7-285">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="90fe7-285">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="90fe7-286">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-286">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="90fe7-287">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung in den USA und Kanada erfolgen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-287">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="90fe7-288">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="90fe7-288">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="90fe7-289">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="90fe7-289">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="90fe7-290">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-290">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="90fe7-291">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="90fe7-291">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="90fe7-292">Beispiel 2: Konfigurationsschritte</span><span class="sxs-lookup"><span data-stu-id="90fe7-292">Example 2: Configuration steps</span></span>

<span data-ttu-id="90fe7-293">Im folgenden Beispiel wird gezeigt, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="90fe7-293">The following example shows how to:</span></span>

1. <span data-ttu-id="90fe7-294">Erstellen Sie eine neue PSTN-Nutzung namens "International".</span><span class="sxs-lookup"><span data-stu-id="90fe7-294">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="90fe7-295">Erstellen Sie eine neue VoIP-Route namens "International".</span><span class="sxs-lookup"><span data-stu-id="90fe7-295">Create a new voice route called International.</span></span>
3. <span data-ttu-id="90fe7-296">Erstellen Sie eine VoIP-Routing Richtlinie mit dem Namen keine Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-296">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="90fe7-297">Weisen Sie die Richtlinie dem Benutzer John Woods zu.</span><span class="sxs-lookup"><span data-stu-id="90fe7-297">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="90fe7-298">Sie können das [Microsoft Teams Admin Center](#admincenterexample2) oder [PowerShell](#powershellexample2) verwenden, um diese Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90fe7-298">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="90fe7-299">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="90fe7-299">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="90fe7-300">Schritt 1: Erstellen der PSTN-Nutzung "International"</span><span class="sxs-lookup"><span data-stu-id="90fe7-300">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="90fe7-301">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice** > **Direct Routing**, und wählen Sie dann in der oberen rechten Ecke die Option **PSTN-Verwendungsdaten Sätze verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="90fe7-301">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="90fe7-302">Klicken Sie auf **Hinzufügen**, geben Sie **International**ein, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-302">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="90fe7-303">Schritt 2: Erstellen der VoIP-Route "International"</span><span class="sxs-lookup"><span data-stu-id="90fe7-303">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="90fe7-304">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice** > **Direct Routing**, und wählen Sie dann die Registerkarte **VoIP-Routen** aus.</span><span class="sxs-lookup"><span data-stu-id="90fe7-304">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="90fe7-305">Klicken Sie auf **Hinzufügen**, geben Sie "International" als Namen ein, und fügen Sie dann die Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="90fe7-305">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="90fe7-306">Setzen Sie die Priorität auf 4, und setzen Sie dann das Muster für die gewählte Nummer auf \d +.</span><span class="sxs-lookup"><span data-stu-id="90fe7-306">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="90fe7-307">Klicken Sie unter **SBCS registriert (optional)** auf **Add SBCS**, wählen Sie sbc2.contoso.biz und sbc5.contoso.biz aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-307">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="90fe7-308">Klicken Sie unter **PSTN-Verwendungsdaten Sätze (optional)** auf **PSTN-Verwendung hinzufügen**, wählen Sie den PSTN-Verwendungs Eintrag "International" aus, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-308">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="90fe7-309">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-309">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="90fe7-310">Schritt 3: Erstellen einer VoIP-Routing Richtlinie mit dem Namen "keine Einschränkungen" und Hinzufügen der PSTN-Verwendung "USA und Kanada" und "International" zur Richtlinie</span><span class="sxs-lookup"><span data-stu-id="90fe7-310">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="90fe7-311">Die PSTN-Nutzung "USA und Kanada" wird in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="90fe7-311">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="90fe7-312">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Routing Richtlinien**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-312">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="90fe7-313">Geben Sie **keine Einschränkungen** als Namen ein, und fügen Sie eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="90fe7-313">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="90fe7-314">Klicken Sie unter **PSTN-Verwendungsdaten Sätze**auf **PSTN-Verwendung hinzufügen**, wählen Sie den PSTN-Verwendungs Eintrag "USA und Kanada" aus, und wählen Sie dann den PSTN-Verwendungs Eintrag "International" aus.</span><span class="sxs-lookup"><span data-stu-id="90fe7-314">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="90fe7-315">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-315">Click **Apply**.</span></span>

    <span data-ttu-id="90fe7-316">Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:</span><span class="sxs-lookup"><span data-stu-id="90fe7-316">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="90fe7-317">Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den in diesem Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-317">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="90fe7-318">Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="90fe7-318">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="90fe7-319">Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-319">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="90fe7-320">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-320">Click **Save**.</span></span>

<span data-ttu-id="90fe7-321">Weitere Informationen finden Sie unter [Verwalten von VoIP-Routing Richtlinien](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="90fe7-321">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="90fe7-322">Schritt 4: Zuweisen der VoIP-Routing Richtlinie zu einem Benutzer mit dem Namen John Woods</span><span class="sxs-lookup"><span data-stu-id="90fe7-322">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="90fe7-323">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="90fe7-323">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="90fe7-324">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-324">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="90fe7-325">Wählen Sie unter **VoIP-Routing Richtlinie**die Richtlinie "keine Einschränkungen" aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90fe7-325">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="90fe7-326">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="90fe7-326">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="90fe7-327">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="90fe7-327">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="90fe7-328">Schritt 1: Erstellen der PSTN-Nutzung "International"</span><span class="sxs-lookup"><span data-stu-id="90fe7-328">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="90fe7-329">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-329">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="90fe7-330">Schritt 2: Erstellen einer neuen VoIP-Route mit dem Namen "International"</span><span class="sxs-lookup"><span data-stu-id="90fe7-330">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="90fe7-331">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="90fe7-331">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="90fe7-332">Schritt 3: Erstellen einer VoIP-Routing Richtlinie mit dem Namen "keine Einschränkungen"</span><span class="sxs-lookup"><span data-stu-id="90fe7-332">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="90fe7-333">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="90fe7-333">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="90fe7-334">Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:</span><span class="sxs-lookup"><span data-stu-id="90fe7-334">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="90fe7-335">Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-335">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="90fe7-336">Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="90fe7-336">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="90fe7-337">Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="90fe7-337">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="90fe7-338">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="90fe7-338">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="90fe7-339">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="90fe7-339">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="90fe7-340">Schritt 4: Zuweisen der VoIP-Routing Richtlinie zum Benutzer mit dem Namen John Woods</span><span class="sxs-lookup"><span data-stu-id="90fe7-340">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="90fe7-341">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="90fe7-341">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="90fe7-342">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="90fe7-342">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="90fe7-343">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="90fe7-343">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fe7-344">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90fe7-344">See also</span></span>

[<span data-ttu-id="90fe7-345">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="90fe7-345">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="90fe7-346">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="90fe7-346">Configure Direct Routing</span></span>](direct-routing-configure.md)
