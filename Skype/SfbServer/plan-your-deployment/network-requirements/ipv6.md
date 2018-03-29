---
title: Plan für IPv6 in Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Zusammenfassung: Implementieren IPv6 vor der Installation von Skype für Business Server 2015.'
ms.openlocfilehash: e91b0a3afabf8088d6fed2f21124fb17a4f7e94f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="c9229-103">Plan für IPv6 in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c9229-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="c9229-104">**Zusammenfassung:** Implementieren Sie vor der Installation von Skype für Business Server 2015 IPv6.</span><span class="sxs-lookup"><span data-stu-id="c9229-104">**Summary:** Implement IPv6 before you install Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c9229-105">Skype für Business Server bietet Unterstützung für IP Version 6 (IPv6) Adressen Adressen zusammen mit Fortgesetzte Unterstützung für IP Version 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="c9229-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="c9229-106">Bei IPv4-Adressen handelt es sich um 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c9229-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="c9229-107">Aufgrund der steigenden Anzahl von Geräten weltweit haben die verfügbaren IPv4-Adressen zur Neige. Aus diesem Grund werden viele neue Geräte verschoben, Verwendung von IPv6-Adressen.</span><span class="sxs-lookup"><span data-stu-id="c9229-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="c9229-108">IPv6-Adressen haben die gleiche Funktion wie IPv4-Adressen (und bieten einige zusätzliche Features), anstelle von lediglich 32 Bit werden von IPv6-Adressen jedoch 128 Bit verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9229-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="c9229-109">Dadurch steht nicht nur ein neuer Satz, sondern auch eine größere Anzahl an Adressen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c9229-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="c9229-110">Eine typische IPv4-Adresse sieht in etwa wie folgt: 192.0.2.235, während eine IPv6-Adresse wie folgt aussieht: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span><span class="sxs-lookup"><span data-stu-id="c9229-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="c9229-111">Die Änderung der Formatierung und Funktionen für Geräte, die IPv6-Adressen verwenden erfordert verschiedene Aspekte der Bereitstellung und Konfiguration Ihrer Skype für Business Server-Installation.</span><span class="sxs-lookup"><span data-stu-id="c9229-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="c9229-112">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="c9229-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="c9229-113">Overview of IP address types</span><span class="sxs-lookup"><span data-stu-id="c9229-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="c9229-114">Technical requirements for IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="c9229-115">Migration and coexistence considerations for IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="c9229-116">Wenn Sie, dass Sie IPv6-Adressen verwenden werden feststellen, finden Sie im Artikel [Konfigurieren der IP-Adresstypen in Skype für Unternehmen](ip-address-types.md) .</span><span class="sxs-lookup"><span data-stu-id="c9229-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="c9229-117">Übersicht über IP-Adresstypen</span><span class="sxs-lookup"><span data-stu-id="c9229-117">Overview of IP address types</span></span>
<span data-ttu-id="c9229-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-118"></span></span>

<span data-ttu-id="c9229-119">Ihnen stehen drei Optionen beim Konfigurieren von IP-Adressen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9229-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="c9229-120">Sie können Skype für Business Server unterstützen nur IP Version 4 (IPv4), nur IP Version 6 (IPv6), konfigurieren oder eine Kombination aus beidem (als eine mit doppeltem Stack bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="c9229-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="c9229-121">Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="c9229-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="c9229-122">**Nur IPv4** IPv6 erstellt wurde, da die ganzen Welt nicht mehr genug IPv4-Adressen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c9229-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="c9229-123">IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen möglicherweise kommunizieren muss, unterstützen derzeit noch nicht IPv6 und möglicherweise bleibt das auch noch eine ganze Weile so.</span><span class="sxs-lookup"><span data-stu-id="c9229-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="c9229-124">Eine reine IPv4-Konfiguration hilft Ihnen, um sicherzustellen, dass Ihre Skype für Business Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="c9229-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="c9229-125">**Nur IPv6** Dagegen wird eine reine IPv6-Implementierung die Kommunikation mit vielen vorhandenen Geräten ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c9229-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="c9229-126">**Dualer Stapel** Mit doppeltem Stack ist ein Netzwerk, in denen sowohl IPv4 als auch IPv6-Adressen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c9229-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="c9229-127">Diese Konfiguration wird in Skype für Business Server unterstützt, da in den meisten Fällen der Übergang vom vollständig IPv4 in voller IPv6 mehrere Jahre dauern wird.</span><span class="sxs-lookup"><span data-stu-id="c9229-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="c9229-128">In den folgenden Abschnitten werden die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene Skype für Business Server-Features.</span><span class="sxs-lookup"><span data-stu-id="c9229-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9229-p106">Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der serienmäßigen Bereitstellung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9229-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="c9229-131">Clientregistrierung</span><span class="sxs-lookup"><span data-stu-id="c9229-131">Client Registration</span></span>
<span data-ttu-id="c9229-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-132"></span></span>

|<span data-ttu-id="c9229-133">**Clientendpunkt-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="c9229-133">**Client endpoint network**</span></span>|<span data-ttu-id="c9229-134">**Server-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="c9229-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9229-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-135">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-137">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-138">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-139">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-139">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-141">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-141">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-142">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-143">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-143">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="c9229-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-145">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-146">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-147">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="c9229-149">Peer-to-Peer-Client</span><span class="sxs-lookup"><span data-stu-id="c9229-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="c9229-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-150"></span></span>

<span data-ttu-id="c9229-p107">Peer-to-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9229-p107">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="c9229-153">**Clientendpunkt 1**</span><span class="sxs-lookup"><span data-stu-id="c9229-153">**Client endpoint 1**</span></span>|<span data-ttu-id="c9229-154">**Clientendpunkt 2**</span><span class="sxs-lookup"><span data-stu-id="c9229-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9229-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-155">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-157">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-158">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-159">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-159">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-160">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-161">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-162">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-163">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="c9229-165">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="c9229-165">Conferencing</span></span>
<span data-ttu-id="c9229-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-166"></span></span>

<span data-ttu-id="c9229-167">Konferenzfunktionen beinhalten Audio/Video, Anwendungsfreigabe und Datenzusammenarbeitsanwendungen wie Whiteboards und Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="c9229-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="c9229-168">**Clientendpunkt-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="c9229-168">**Client endpoint network**</span></span>|<span data-ttu-id="c9229-169">**Server-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="c9229-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9229-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-170">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-172">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-173">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-174">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-174">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-176">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-176">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-177">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-178">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-178">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="c9229-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-180">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-181">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-182">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="c9229-184">Vermittlungsserver/PSTN</span><span class="sxs-lookup"><span data-stu-id="c9229-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="c9229-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-185"></span></span>

<span data-ttu-id="c9229-186">Skype für Business Server unterstützt keine medienumgehung für public switched Telephone Network (Telefonfestnetz PSTN) anrufen, wenn der Datenverkehr über eine IPv6-Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="c9229-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="c9229-187">Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9229-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="c9229-188">**Primäre Schnittstelle 1**</span><span class="sxs-lookup"><span data-stu-id="c9229-188">**Primary interface 1**</span></span>|<span data-ttu-id="c9229-189">**PSTN-Schnittstelle (Vermittlungsserver)**</span><span class="sxs-lookup"><span data-stu-id="c9229-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="c9229-190">**PSTN-Gateway-Einstellung**</span><span class="sxs-lookup"><span data-stu-id="c9229-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9229-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-191">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-192">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-192">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-194">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-194">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-195">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-195">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-197">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-197">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-198">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-198">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="c9229-200">Die primäre Schnittstelle ist die Schnittstelle, mit die die Skype für Business Server-Komponenten kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="c9229-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="c9229-201">Peer-to-Peer-Kommunikation mit Remotebenutzern</span><span class="sxs-lookup"><span data-stu-id="c9229-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="c9229-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-202"></span></span>

<span data-ttu-id="c9229-203">Peer-to-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="c9229-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="c9229-204">**Des Remotebenutzers**</span><span class="sxs-lookup"><span data-stu-id="c9229-204">**Remote user network**</span></span>|<span data-ttu-id="c9229-205">**Edgeserver (externer Edge)**</span><span class="sxs-lookup"><span data-stu-id="c9229-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9229-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-206">IPv4</span></span>  <br/> |<span data-ttu-id="c9229-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-208">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-208">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="c9229-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="c9229-210">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-210">Dual stack</span></span>  <br/> |<span data-ttu-id="c9229-211">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-212">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-213">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="c9229-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c9229-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-214">IPv6</span></span>  <br/> |<span data-ttu-id="c9229-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="c9229-216">Konfiguration mit Front-End-Pool und Edgepool</span><span class="sxs-lookup"><span data-stu-id="c9229-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="c9229-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-217"></span></span>

<span data-ttu-id="c9229-218">Die folgende Tabelle zeigt die Matrix der unterstützten zwischen den Front-End-Server-Pool und der internen Edge-Server-Pool.</span><span class="sxs-lookup"><span data-stu-id="c9229-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="c9229-219">**Front-End-Pool und Matrix der Edge-Pool (interner Edge)**</span><span class="sxs-lookup"><span data-stu-id="c9229-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="c9229-220">**Edgepool: IPv4**</span><span class="sxs-lookup"><span data-stu-id="c9229-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="c9229-221">**Edgepool: Dualer Stapel**</span><span class="sxs-lookup"><span data-stu-id="c9229-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="c9229-222">**Edgepool: IPv6**</span><span class="sxs-lookup"><span data-stu-id="c9229-222">**Edge Pool: IPv6**</span></span> <br/> |
|<span data-ttu-id="c9229-223">**Front-End-Pool: IPv4**</span><span class="sxs-lookup"><span data-stu-id="c9229-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="c9229-224">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-224">Yes</span></span>  <br/> |<span data-ttu-id="c9229-225">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-225">Yes</span></span>  <br/> |<span data-ttu-id="c9229-226">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-226">No</span></span>  <br/> |
|<span data-ttu-id="c9229-227">**Front-End-Pool: Dualer Stapel**</span><span class="sxs-lookup"><span data-stu-id="c9229-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="c9229-228">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-228">Yes</span></span>  <br/> |<span data-ttu-id="c9229-229">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-229">Yes</span></span>  <br/> |<span data-ttu-id="c9229-230">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-230">No</span></span>  <br/> |
|<span data-ttu-id="c9229-231">**Front-End-Pool: IPv6**</span><span class="sxs-lookup"><span data-stu-id="c9229-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="c9229-232">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-232">No</span></span>  <br/> |<span data-ttu-id="c9229-233">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-233">No</span></span>  <br/> |<span data-ttu-id="c9229-234">"Ja"\*</span><span class="sxs-lookup"><span data-stu-id="c9229-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="c9229-235">\*Verwenden Sie diese Kombination nur in einer laborumgebung.</span><span class="sxs-lookup"><span data-stu-id="c9229-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="c9229-236">Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c9229-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="c9229-237">**Edgepool (interner Edge) und Edge-pool-Matrix (externer Edge)**</span><span class="sxs-lookup"><span data-stu-id="c9229-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="c9229-238">**Edgepool (Externer Edge): IPv4**</span><span class="sxs-lookup"><span data-stu-id="c9229-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="c9229-239">**Edgepool (Externer Edge): Dualer Stapel**</span><span class="sxs-lookup"><span data-stu-id="c9229-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="c9229-240">**Edgepool (Externer Edge): IPv6**</span><span class="sxs-lookup"><span data-stu-id="c9229-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|<span data-ttu-id="c9229-241">**Edgepool (Interner Edge): IPv4**</span><span class="sxs-lookup"><span data-stu-id="c9229-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="c9229-242">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-242">Yes</span></span>  <br/> |<span data-ttu-id="c9229-243">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-243">Yes</span></span>  <br/> |<span data-ttu-id="c9229-244">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-244">No</span></span>  <br/> |
|<span data-ttu-id="c9229-245">**Edgepool (Interner Edge): Dualer Stapel**</span><span class="sxs-lookup"><span data-stu-id="c9229-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="c9229-246">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-246">No</span></span>  <br/> |<span data-ttu-id="c9229-247">Ja</span><span class="sxs-lookup"><span data-stu-id="c9229-247">Yes</span></span>  <br/> |<span data-ttu-id="c9229-248">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-248">No</span></span>  <br/> |
|<span data-ttu-id="c9229-249">**Edgepool (Interner Edge): IPv6**</span><span class="sxs-lookup"><span data-stu-id="c9229-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="c9229-250">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-250">No</span></span>  <br/> |<span data-ttu-id="c9229-251">Nein</span><span class="sxs-lookup"><span data-stu-id="c9229-251">No</span></span>  <br/> |<span data-ttu-id="c9229-252">"Ja"\*</span><span class="sxs-lookup"><span data-stu-id="c9229-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="c9229-253">\*Verwenden Sie diese Kombination nur in einer laborumgebung.</span><span class="sxs-lookup"><span data-stu-id="c9229-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="c9229-254">Erweiterte Unterstützung für Enterprise-VoIP für IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="c9229-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-255"></span></span>

<span data-ttu-id="c9229-p109">Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E911-Notrufdienste oder Medienumgehung beinhalten, können nur mit IPv4 oder als Implementierung mit dualem Stapel konfiguriert werden. Endpunkte, die nur IPv6 verwenden, haben diese Funktionen nicht.</span><span class="sxs-lookup"><span data-stu-id="c9229-p109">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation. Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9229-258">In einer Bereitstellung dualer-Stapel stellen Skype für Business Server, auch wenn eine Skype für Business Server-Client an einen Skype für Business Server stellt eine Verbindung über IPv6 bemüht, eine geeignete IPv4-Adresse zur Unterstützung der E9-1-1 zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c9229-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="c9229-259">Standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9229-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="c9229-p110">Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9229-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="c9229-263">Andere Skype für Business Serverunterstützung für IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="c9229-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-264"></span></span>

<span data-ttu-id="c9229-265">Zusätzlich zu den Features und Komponenten, die weiter oben erwähnten unterstützt Skype für Business Server IPv6 für die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="c9229-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="c9229-266">**Beständiger Chat**</span><span class="sxs-lookup"><span data-stu-id="c9229-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="c9229-267">Sie Konfigurieren von IPv6 für beständigen Chat mithilfe des Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c9229-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="c9229-268">Ausführliche Informationen zum Konfigurieren von Persistent Chat finden Sie unter Deploying Persistent Chat Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c9229-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="c9229-269">**QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen (KDS)**</span><span class="sxs-lookup"><span data-stu-id="c9229-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="c9229-270">In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.</span><span class="sxs-lookup"><span data-stu-id="c9229-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="c9229-271">Technische Anforderungen für IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="c9229-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-272"></span></span>

<span data-ttu-id="c9229-273">Wenn Sie Skype für Business Server für IPv6 konfigurieren möchten, sollten beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c9229-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="c9229-274">Um IPv6-Adressen mit Skype für Business Server verwenden, müssen Sie Domain Name System (DNS) Einträge für Datensätze erstellen, der ermittelt und in eine IPv6-Adresse aufgelöst werden muss.</span><span class="sxs-lookup"><span data-stu-id="c9229-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="c9229-275">IPv6-DNS verwendet Host-AAAA-Einträge (vier „A“).</span><span class="sxs-lookup"><span data-stu-id="c9229-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="c9229-276">Falls Sie sowohl IPv4 als auch IPv6 in Ihrer Bereitstellung verwenden, empfiehlt es sich, sowohl Host-A-Einträge für IPv4 als auch Host-AAAA-Einträge für IPv6 zu konfigurieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c9229-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="c9229-277">Selbst wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die noch IPv4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9229-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="c9229-p113">Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen. Falls der Client oder Server IPv6 nicht verwendet, wird nicht auf den Eintrag verwiesen. Umstellungstechnologien bestimmen anhand von Konfiguration und Richtlinien, welcher Eintrag verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9229-p113">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="c9229-281">Jede IPv6-Adresse hat einen Adressbereich.</span><span class="sxs-lookup"><span data-stu-id="c9229-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="c9229-282">Die drei Bereiche, die Sie für IPv6-Adressen verwenden können sind globalen IPv6-Adressen (analog zu öffentliche IPv4-Adressen), IPv6 eindeutige lokalen Adressen (ähnlich wie die private Adressbereiche IPv4) und IPv6-Link-Local-Adressen (analog zu automatische private IP-Adressen in WindowsServer für IPv4).</span><span class="sxs-lookup"><span data-stu-id="c9229-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="c9229-283">Alle Server innerhalb eines Pools sollten IPv6-Adressen mit dem gleichen Adressbereich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c9229-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="c9229-284">IPv6 ist ein komplexes Thema und erfordert sorgfältige Planung mit Teammitgliedern Netzwerke und Ihren Internetanbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server-Ebene und auf die Skype für Business Server Ebene zuweisen wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c9229-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="c9229-285">Zusätzliche Informationen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c9229-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="c9229-286">Überlegungen zu Migration und Koexistenz für IPv6</span><span class="sxs-lookup"><span data-stu-id="c9229-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="c9229-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-287"></span></span>

<span data-ttu-id="c9229-288">IP Version 6 (IPv6) wird auf Lync Server 2010 oder Office Communications Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9229-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="c9229-289">Aus Gründen der Pilotphase können Sie Lync Server 2010 und Skype Business Server dualen Koexistenz testen.</span><span class="sxs-lookup"><span data-stu-id="c9229-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="c9229-290">Es wird empfohlen, alle Pools für einen bestimmten zentralen Standort auf wurden Skype für Business Server aktualisiert vor dem Aktivieren von IPv6 (Dual-Stack Network) für alle Pools.</span><span class="sxs-lookup"><span data-stu-id="c9229-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="c9229-291">Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Nur-IPv6-Pool in Ihrer Testumgebung zum Testen einrichten.</span><span class="sxs-lookup"><span data-stu-id="c9229-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="c9229-292">Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c9229-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="c9229-293">Skype für Business Server, Lync Server 2013 und Lync Server 2010-Pools im IPv4-Modus, gemeinsame Verwendung mit Skype für Business Server im dualen Modus.</span><span class="sxs-lookup"><span data-stu-id="c9229-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="c9229-294">Skype für Business Server-Pool im nur-IPv6-Modus, wenn der reine IPv6-Pool in Silos zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="c9229-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c9229-295">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c9229-295">See also</span></span>
<span data-ttu-id="c9229-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="c9229-296"></span></span>

#### 

[<span data-ttu-id="c9229-297">Konfigurieren von IP-Adresstypen in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="c9229-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)
#### 

[<span data-ttu-id="c9229-298">Reagieren auf IP Version 6-Architektur</span><span class="sxs-lookup"><span data-stu-id="c9229-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="c9229-299">Format der IPv6-globale Unicast-Adresse</span><span class="sxs-lookup"><span data-stu-id="c9229-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="c9229-300">Eindeutige lokale IPv6-Unicast-Adressen</span><span class="sxs-lookup"><span data-stu-id="c9229-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)

