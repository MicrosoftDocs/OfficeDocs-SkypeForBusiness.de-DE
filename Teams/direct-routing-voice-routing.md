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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157967"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="aeca0-103">Konfigurieren des VoIP-Routings für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="aeca0-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="aeca0-104">In diesem Artikel wird beschrieben, wie Sie das VoIP-Routing für das direkte Routing von Telefonsystemen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="aeca0-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="aeca0-105">Dies ist Schritt 3 der folgenden Schritte zum Konfigurieren des direkten Routings:</span><span class="sxs-lookup"><span data-stu-id="aeca0-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="aeca0-106">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="aeca0-106">Step 1.</span></span> [<span data-ttu-id="aeca0-107">Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="aeca0-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="aeca0-108">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="aeca0-108">Step 2.</span></span> [<span data-ttu-id="aeca0-109">Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail</span><span class="sxs-lookup"><span data-stu-id="aeca0-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="aeca0-110">**Schritt 3. Konfigurieren des VoIP-Routings** (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="aeca0-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="aeca0-111">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="aeca0-111">Step 4.</span></span> [<span data-ttu-id="aeca0-112">Übersetzen von Zahlen in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="aeca0-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="aeca0-113">Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="aeca0-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="aeca0-114">Übersicht über das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="aeca0-114">Voice routing overview</span></span>

<span data-ttu-id="aeca0-115">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten Session Border Controller (SBC) basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="aeca0-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="aeca0-116">Das so genannte Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="aeca0-116">The called number pattern</span></span> 
- <span data-ttu-id="aeca0-117">Das angerufene Zahlenmuster und der spezifische Benutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="aeca0-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="aeca0-118">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="aeca0-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="aeca0-119">Wenn der als aktiv konfigurierte SBC für eine bestimmte Anrufroute nicht zur Verfügung steht, wird der Anruf an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="aeca0-120">Das VoIP-Routing besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="aeca0-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="aeca0-121">**VoIP-Routing Richtlinie** – ein Container für PSTN-Nutzungen, der einem Benutzer oder mehreren Benutzern zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="aeca0-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="aeca0-122">**PSTN-Verwendungen** – ein Container für VoIP-Routen und PSTN-Nutzungen, der in verschiedenen VoIP-Routing Richtlinien freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="aeca0-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="aeca0-123">**VoIP-Routen** – ein Zahlenmuster und eine Reihe von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="aeca0-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="aeca0-124">**Online-PSTN-Gateway** – ein Zeiger auf einen SBC, der auch die Konfiguration speichert, die angewendet wird, wenn ein Anruf über den SBC durchgeführt wird, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aeca0-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="aeca0-125">Beispiel 1: VoIP-Routing mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="aeca0-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="aeca0-126">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien in einem Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="aeca0-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="aeca0-127">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="aeca0-128">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="aeca0-129">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="aeca0-130">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="aeca0-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="aeca0-131">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="aeca0-133">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="aeca0-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="aeca0-134">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="aeca0-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="aeca0-135">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="aeca0-136">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="aeca0-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="aeca0-137">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="aeca0-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="aeca0-139">Bei allen anderen anrufen:</span><span class="sxs-lookup"><span data-stu-id="aeca0-139">For all other calls:</span></span>

- <span data-ttu-id="aeca0-140">Wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan), wird die automatische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="aeca0-141">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, wird der Anruf über den Microsoft-Anrufplan weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="aeca0-142">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf verworfen, weil keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="aeca0-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="aeca0-143">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da nur eine Route vorhanden ist, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="aeca0-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="aeca0-144">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="aeca0-145">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="aeca0-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="aeca0-146">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="aeca0-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="aeca0-147">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="aeca0-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="aeca0-148">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="aeca0-148">**PSTN usage**</span></span>|<span data-ttu-id="aeca0-149">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="aeca0-149">**Voice route**</span></span>|<span data-ttu-id="aeca0-150">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="aeca0-150">**Number pattern**</span></span>|<span data-ttu-id="aeca0-151">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="aeca0-151">**Priority**</span></span>|<span data-ttu-id="aeca0-152">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="aeca0-152">**SBC**</span></span>|<span data-ttu-id="aeca0-153">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aeca0-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aeca0-154">Nur USA</span><span class="sxs-lookup"><span data-stu-id="aeca0-154">US only</span></span>|<span data-ttu-id="aeca0-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="aeca0-155">"Redmond 1"</span></span>|<span data-ttu-id="aeca0-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="aeca0-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aeca0-157">1</span><span class="sxs-lookup"><span data-stu-id="aeca0-157">1</span></span>|<span data-ttu-id="aeca0-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="aeca0-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="aeca0-160">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aeca0-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aeca0-161">Nur USA</span><span class="sxs-lookup"><span data-stu-id="aeca0-161">US only</span></span>|<span data-ttu-id="aeca0-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="aeca0-162">"Redmond 2"</span></span>|<span data-ttu-id="aeca0-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="aeca0-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aeca0-164">2</span><span class="sxs-lookup"><span data-stu-id="aeca0-164">2</span></span>|<span data-ttu-id="aeca0-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="aeca0-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="aeca0-167">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aeca0-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aeca0-168">Nur USA</span><span class="sxs-lookup"><span data-stu-id="aeca0-168">US only</span></span>|<span data-ttu-id="aeca0-169">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="aeca0-169">"Other +1"</span></span>|<span data-ttu-id="aeca0-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="aeca0-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="aeca0-171">3</span><span class="sxs-lookup"><span data-stu-id="aeca0-171">3</span></span>|<span data-ttu-id="aeca0-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="aeca0-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="aeca0-174">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="aeca0-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="aeca0-175">Beispiel 1: Konfigurationsschritte</span><span class="sxs-lookup"><span data-stu-id="aeca0-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="aeca0-176">Im folgenden Beispiel wird gezeigt, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="aeca0-176">The following example shows how to:</span></span>

- <span data-ttu-id="aeca0-177">Erstellen einer einzelnen PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="aeca0-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="aeca0-178">Konfigurieren von drei VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="aeca0-178">Configure three voice routes</span></span>
- <span data-ttu-id="aeca0-179">Erstellen einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="aeca0-179">Create a voice routing policy</span></span>
- <span data-ttu-id="aeca0-180">Zuweisen der Richtlinie zum Benutzer Spencer Low</span><span class="sxs-lookup"><span data-stu-id="aeca0-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="aeca0-181">**Schritt 1:** Erstellen der PSTN-Nutzung "USA und Kanada"</span><span class="sxs-lookup"><span data-stu-id="aeca0-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="aeca0-182">Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="aeca0-183">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="aeca0-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="aeca0-184">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="aeca0-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="aeca0-185">Das folgende Beispiel zeigt das Ergebnis der Ausführung des PowerShell- `(Get-CSOnlinePSTNUsage).usage` Befehls zum Anzeigen von vollständigen Namen (nicht abgeschnitten):</span><span class="sxs-lookup"><span data-stu-id="aeca0-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="aeca0-186">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle gezeigt</span><span class="sxs-lookup"><span data-stu-id="aeca0-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="aeca0-187">Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="aeca0-188">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="aeca0-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="aeca0-189">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="aeca0-190">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="aeca0-191">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="aeca0-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="aeca0-192">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="aeca0-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="aeca0-193">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="aeca0-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="aeca0-194">Alle Anrufe an denselben SBC weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="aeca0-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="aeca0-195">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="aeca0-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="aeca0-196">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="aeca0-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="aeca0-197">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="aeca0-198">**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.</span><span class="sxs-lookup"><span data-stu-id="aeca0-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="aeca0-199">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="aeca0-200">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="aeca0-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="aeca0-201">**Schritt 4:** Erteilen Sie die VoIP-Routing Richtlinie mithilfe von PowerShell dem Benutzer Spencer Low:</span><span class="sxs-lookup"><span data-stu-id="aeca0-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="aeca0-202">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="aeca0-203">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="aeca0-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="aeca0-204">Der Befehl gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="aeca0-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="aeca0-205">Beispiel 2: VoIP-Routing mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="aeca0-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="aeca0-206">Die in Beispiel 1 erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada – es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="aeca0-207">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="aeca0-208">Die Richtlinie verwendet die in Beispiel 1 erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.</span><span class="sxs-lookup"><span data-stu-id="aeca0-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="aeca0-209">Diese Richtlinie leitet alle anderen Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weiter.</span><span class="sxs-lookup"><span data-stu-id="aeca0-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="aeca0-210">In den Beispielen, die angezeigt werden, weisen Sie die nur US-Richtlinie Benutzern Spencer Low und die Richtlinie "keine Einschränkungen" für den Benutzer John Woods zu, damit das Routing wie folgt erfolgt:</span><span class="sxs-lookup"><span data-stu-id="aeca0-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="aeca0-211">Spencer Low – nur US-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="aeca0-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="aeca0-212">Anrufe sind nur für US-und kanadische Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="aeca0-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="aeca0-213">Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aeca0-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="aeca0-214">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="aeca0-215">John Woods – internationale Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="aeca0-215">John Woods – International policy.</span></span>  <span data-ttu-id="aeca0-216">Anrufe sind an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="aeca0-216">Calls are allowed to any number.</span></span> <span data-ttu-id="aeca0-217">Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aeca0-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="aeca0-218">Nicht-US-Nummern werden mit sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="aeca0-220">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="aeca0-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="aeca0-221">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, wird der Anruf mit dem Microsoft-Anrufplan weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="aeca0-222">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="aeca0-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="aeca0-224">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="aeca0-225">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="aeca0-225">**PSTN usage**</span></span>|<span data-ttu-id="aeca0-226">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="aeca0-226">**Voice route**</span></span>|<span data-ttu-id="aeca0-227">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="aeca0-227">**Number pattern**</span></span>|<span data-ttu-id="aeca0-228">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="aeca0-228">**Priority**</span></span>|<span data-ttu-id="aeca0-229">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="aeca0-229">**SBC**</span></span>|<span data-ttu-id="aeca0-230">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aeca0-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aeca0-231">Nur USA</span><span class="sxs-lookup"><span data-stu-id="aeca0-231">US Only</span></span>|<span data-ttu-id="aeca0-232">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="aeca0-232">"Redmond 1"</span></span>|<span data-ttu-id="aeca0-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="aeca0-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aeca0-234">1</span><span class="sxs-lookup"><span data-stu-id="aeca0-234">1</span></span>|<span data-ttu-id="aeca0-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="aeca0-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="aeca0-237">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aeca0-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aeca0-238">Nur USA</span><span class="sxs-lookup"><span data-stu-id="aeca0-238">US Only</span></span>|<span data-ttu-id="aeca0-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="aeca0-239">"Redmond 2"</span></span>|<span data-ttu-id="aeca0-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="aeca0-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="aeca0-241">2</span><span class="sxs-lookup"><span data-stu-id="aeca0-241">2</span></span>|<span data-ttu-id="aeca0-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="aeca0-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="aeca0-244">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="aeca0-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="aeca0-245">Nur USA</span><span class="sxs-lookup"><span data-stu-id="aeca0-245">US Only</span></span>|<span data-ttu-id="aeca0-246">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="aeca0-246">"Other +1"</span></span>|<span data-ttu-id="aeca0-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="aeca0-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="aeca0-248">3</span><span class="sxs-lookup"><span data-stu-id="aeca0-248">3</span></span>|<span data-ttu-id="aeca0-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="aeca0-250">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="aeca0-251">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="aeca0-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="aeca0-252">International</span><span class="sxs-lookup"><span data-stu-id="aeca0-252">International</span></span>|<span data-ttu-id="aeca0-253">International</span><span class="sxs-lookup"><span data-stu-id="aeca0-253">International</span></span>|<span data-ttu-id="aeca0-254">\d +</span><span class="sxs-lookup"><span data-stu-id="aeca0-254">\d+</span></span>|<span data-ttu-id="aeca0-255">4</span><span class="sxs-lookup"><span data-stu-id="aeca0-255">4</span></span>|<span data-ttu-id="aeca0-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="aeca0-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="aeca0-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="aeca0-258">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="aeca0-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="aeca0-259">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="aeca0-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="aeca0-260">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="aeca0-261">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="aeca0-262">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aeca0-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="aeca0-263">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="aeca0-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="aeca0-264">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aeca0-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="aeca0-265">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="aeca0-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="aeca0-266">Beispiel 2: Konfigurationsschritte</span><span class="sxs-lookup"><span data-stu-id="aeca0-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="aeca0-267">Im folgenden Beispiel wird gezeigt, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="aeca0-267">The following example shows how to:</span></span>

- <span data-ttu-id="aeca0-268">Erstellen einer neuen PSTN-Nutzung namens "International"</span><span class="sxs-lookup"><span data-stu-id="aeca0-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="aeca0-269">Erstellen einer neuen VoIP-Route mit dem Namen "International"</span><span class="sxs-lookup"><span data-stu-id="aeca0-269">Create a new voice route called International</span></span>
- <span data-ttu-id="aeca0-270">Erstellen einer VoIP-Routing Richtlinie mit dem Namen "keine Einschränkungen"</span><span class="sxs-lookup"><span data-stu-id="aeca0-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="aeca0-271">Zuweisen der Richtlinie zum Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="aeca0-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="aeca0-272">**Schritt 1**: Erstellen der PSTN-Nutzung "International"</span><span class="sxs-lookup"><span data-stu-id="aeca0-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="aeca0-273">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="aeca0-274">**Schritt 2**: Erstellen der neuen VoIP-Route "International"</span><span class="sxs-lookup"><span data-stu-id="aeca0-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="aeca0-275">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="aeca0-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="aeca0-276">**Schritt 3**: Erstellen einer VoIP-Routing Richtlinie "keine Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="aeca0-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="aeca0-277">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="aeca0-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="aeca0-278">Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:</span><span class="sxs-lookup"><span data-stu-id="aeca0-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="aeca0-279">a.</span><span class="sxs-lookup"><span data-stu-id="aeca0-279">a.</span></span> <span data-ttu-id="aeca0-280">Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="aeca0-281">Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="aeca0-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="aeca0-282">b.</span><span class="sxs-lookup"><span data-stu-id="aeca0-282">b.</span></span> <span data-ttu-id="aeca0-283">Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="aeca0-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="aeca0-284">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="aeca0-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="aeca0-285">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="aeca0-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="aeca0-286">**Schritt 4**: weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="aeca0-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="aeca0-287">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="aeca0-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="aeca0-288">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="aeca0-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="aeca0-289">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="aeca0-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="aeca0-290">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aeca0-290">See also</span></span>

[<span data-ttu-id="aeca0-291">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="aeca0-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="aeca0-292">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="aeca0-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
