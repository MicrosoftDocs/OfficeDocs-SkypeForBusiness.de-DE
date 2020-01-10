---
title: Konfigurieren des Video-Interop-Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Zusammenfassung: Konfigurieren der Rolle des Video-Interop-Servers (VIS) in Skype for Business Server.'
ms.openlocfilehash: fb9dc36bcf2f1a6f1346705f74dd3cf2844a973c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003055"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="828e8-103">Konfigurieren des Video-Interop-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="828e8-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="828e8-104">**Zusammenfassung:** Konfigurieren Sie die Rolle des Video-Interop-Servers (VIS) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="828e8-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="828e8-105">Konfigurieren Sie die Einstellungen, die das VIS mit Video Stämmen unter Verwendung von Windows PowerShell assoziieren wird.</span><span class="sxs-lookup"><span data-stu-id="828e8-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="828e8-106">Eine Videotrunkkonfiguration auf globaler Ebene wird erstellt, wenn der VIS-Dienst installiert ist.</span><span class="sxs-lookup"><span data-stu-id="828e8-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="828e8-107">Diese Videotrunkkonfiguration wird vom VIS auf alle Trunks angewendet, die keine Videotrunkkonfiguration mit einer spezifischeren Ebene haben.</span><span class="sxs-lookup"><span data-stu-id="828e8-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="828e8-108">Hinweis: Die Videotrunkkonfiguration ist eine Sammlung von Einstellungen, die auf Videotrunks angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="828e8-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="828e8-109">Konfigurieren von Videotrunk und Wählplan</span><span class="sxs-lookup"><span data-stu-id="828e8-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="828e8-110">Verwenden Sie die folgenden Windows PowerShell-Befehle, um die Video trunk-Konfiguration und den Wählplan anzugeben, der den neu definierten Stamm (en) zugeordnet werden soll, die im Topologie-Dokument zwischen dem VIS und allen Video Gateways definiert sind.</span><span class="sxs-lookup"><span data-stu-id="828e8-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="828e8-111">Alle Einstellungen können auf globaler, Standort- oder Dienstebene (Videogateway) eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="828e8-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="828e8-112">Pro Skype for Business Server-Bereitstellung wird ein Wählplan mit globalem Bereich erstellt.</span><span class="sxs-lookup"><span data-stu-id="828e8-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="828e8-113">Dieser Wählplan wird vom VIS auf alle Trunks angewendet, die keinen Wählplan mit einer spezifischeren Ebene haben.</span><span class="sxs-lookup"><span data-stu-id="828e8-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="828e8-114">Konfigurieren des VIS mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="828e8-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="828e8-115">Erstellen Sie mithilfe des folgenden Windows PowerShell-Cmdlets eine neue Video trunk-Konfiguration (eine Sammlung von Einstellungen), die für den trunk zwischen dem VIS und Cisco Unified Communications Manager (CallManager oder CUCM) verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="828e8-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="828e8-116">Wenn ein vorhandener Video trunk vorhanden ist, der geändert werden muss, verwenden Sie das folgende Windows PowerShell-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="828e8-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="828e8-117">Verwenden Sie das folgende Windows PowerShell-Cmdlet, um die Einstellungen anzuzeigen, die einer bestimmten Video trunk-Konfiguration zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="828e8-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="828e8-118">Wenn Sie eine bestimmte Video trunk-Konfiguration entfernen möchten, verwenden Sie das folgende Windows PowerShell-Cmdlet (Beachten Sie, dass die Konfiguration des Global Bereichs-Video Trunks angewendet wird, wenn keine spezifischere Video trunk-Konfiguration für einen bestimmten trunk vorhanden ist):</span><span class="sxs-lookup"><span data-stu-id="828e8-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="828e8-119">Erstellen Sie mithilfe der folgenden Windows PowerShell-Cmdlets einen Wählplan, der dem Stamm zugeordnet werden soll:</span><span class="sxs-lookup"><span data-stu-id="828e8-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="828e8-120">Mit dem Befehl **Remove-CsVoiceNormalizationRule** können Sie eine Standardregel überschreiben, die sich störend auf die erwartete Interaktion zwischen VIS und CUCM auswirkt.</span><span class="sxs-lookup"><span data-stu-id="828e8-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="828e8-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) kann verwendet werden, um einen Wählplan zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="828e8-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="828e8-122">Bei einem Video-SIP-Trunk-Anruf von einem Video-Gateway, dessen Anforderungs-URI eine nicht-E. 164-Nummer enthält, liest VIS den Namen des Wählplans, der dem zugehörigen trunk zugeordnet ist, und enthält den Namen des Wählplans im Kontext Teil des Telefons des Anforderungs-URIs in der Einladung, die VI S wird an das Front-End gesendet.</span><span class="sxs-lookup"><span data-stu-id="828e8-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="828e8-123">Die Übersetzungsanwendung am Front-End-Server extrahiert dann die mit dem Wählplan verbundenen Normalisierungsregeln und wendet sie auf die Anforderungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="828e8-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="828e8-124">Optionen für die Trunkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="828e8-124">Trunk configuration options</span></span>

<span data-ttu-id="828e8-125">Die zuvor erwähnten Windows PowerShell-Cmdlets für die Video trunk-Konfiguration waren neu bei Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="828e8-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="828e8-126">Es folgt eine kurze Erläuterung der Einstellungen für die Videotrunkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="828e8-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="828e8-127">**GatewaySendsRtcpForActiveCalls** Dieser Parameter bestimmt, ob RTCP-Pakete für aktive Anrufe vom VTC an das VIS gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="828e8-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="828e8-128">Ein aktiver Anruf ist in diesem Kontext ein Anruf, bei dem Mediendaten in mindestens eine Richtung übertragen werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="828e8-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="828e8-129">Wenn „GatewaySendsRtcpForActiveCalls“ auf „True“ festgelegt ist, kann der VIS einen Anruf beenden, wenn für mehr als 30 Sekunden keine RTCP-Pakete empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="828e8-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="828e8-130">Der Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="828e8-130">The default is **True**.</span></span>
  
 <span data-ttu-id="828e8-131">**GatewaySendsRtcpForCallsOnHold** Dieser Parameter bestimmt, ob RTCP-Pakete weiterhin über den trunk für Anrufe gesendet werden, die in Wartestellung gesetzt wurden, und es wird davon ausgegangen, dass keine Medienpakete in beide Richtungen fließen.</span><span class="sxs-lookup"><span data-stu-id="828e8-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="828e8-132">Der VIS kann den Anruf beenden, wenn bei einem Anruf in der Warteschleife keine RTCP-Pakete vom VTC zum VIS übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="828e8-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="828e8-133">Der Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="828e8-133">The default is **True**.</span></span> <span data-ttu-id="828e8-134">Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="828e8-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="828e8-135">**EnableMediaEncryptionForSipOverTls** Dieser Parameter aktiviert oder deaktiviert SRTP für Medien, wenn das SIPTransport-Protokoll auf TLS eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="828e8-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="828e8-136">Der Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="828e8-136">The default is **True**.</span></span> <span data-ttu-id="828e8-137">Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="828e8-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="828e8-138">**EnableSessionTimer** Dieser Parameter aktiviert oder deaktiviert Sitzungs Timer auf der VIS-Seite für jedes SIP-Dialogfeld, das dem Video SIP-Trunk zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="828e8-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="828e8-139">Der Standardwert ist **False**.</span><span class="sxs-lookup"><span data-stu-id="828e8-139">The default is **False**.</span></span>
  
 <span data-ttu-id="828e8-140">**ForwardErrorCorrectionType** Dieser Parameter wird verwendet, um zu ermitteln, ob die Forward-Fehlerkorrektur (FEC) für Videodatenströme auf dem Bein zwischen dem Video-Interop-Server und einem Video-Gateway angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="828e8-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="828e8-141">Wenn ForwardErrorCorrectionType auf "None" festgelegt wird, wird FEC zwischen VIS und Video Gateway/VTC deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="828e8-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="828e8-142">Das Festlegen von ForwardErrorCorrectionType auf "Cisco" ermöglicht FEC, das mit Video Gateways von Cisco kompatibel ist, beispielsweise Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="828e8-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="828e8-143">Der Standardwert ist **None**.</span><span class="sxs-lookup"><span data-stu-id="828e8-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="828e8-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="828e8-144">See also</span></span>

[<span data-ttu-id="828e8-145">Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="828e8-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
