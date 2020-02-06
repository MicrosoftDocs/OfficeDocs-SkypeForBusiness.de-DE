---
title: Konfigurieren des Video-Interop-Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Zusammenfassung: Konfigurieren der Rolle des Video-Interop-Servers (VIS) in Skype for Business Server.'
ms.openlocfilehash: 2618a7829fde79bd63eb2c3c91dbe921530e3b04
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798062"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Konfigurieren des Video-Interop-Servers in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Rolle des Video-Interop-Servers (VIS) in Skype for Business Server.
  
 Konfigurieren Sie die Einstellungen, die das VIS mit Video Stämmen unter Verwendung von Windows PowerShell assoziieren wird. Eine Videotrunkkonfiguration auf globaler Ebene wird erstellt, wenn der VIS-Dienst installiert ist. Diese Videotrunkkonfiguration wird vom VIS auf alle Trunks angewendet, die keine Videotrunkkonfiguration mit einer spezifischeren Ebene haben. Hinweis: Die Videotrunkkonfiguration ist eine Sammlung von Einstellungen, die auf Videotrunks angewendet wird.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Konfigurieren von Videotrunk und Wählplan

Verwenden Sie die folgenden Windows PowerShell-Befehle, um die Video trunk-Konfiguration und den Wählplan anzugeben, der den neu definierten Stamm (en) zugeordnet werden soll, die im Topologie-Dokument zwischen dem VIS und allen Video Gateways definiert sind. Alle Einstellungen können auf globaler, Standort- oder Dienstebene (Videogateway) eingerichtet werden. 
  
Pro Skype for Business Server-Bereitstellung wird ein Wählplan mit globalem Bereich erstellt. Dieser Wählplan wird vom VIS auf alle Trunks angewendet, die keinen Wählplan mit einer spezifischeren Ebene haben. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Konfigurieren des VIS mithilfe von Windows PowerShell

1. Erstellen Sie mithilfe des folgenden Windows PowerShell-Cmdlets eine neue Video trunk-Konfiguration (eine Sammlung von Einstellungen), die für den trunk zwischen dem VIS und Cisco Unified Communications Manager (CallManager oder CUCM) verwendet werden soll:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Wenn ein vorhandener Video trunk vorhanden ist, der geändert werden muss, verwenden Sie das folgende Windows PowerShell-Cmdlet:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Verwenden Sie das folgende Windows PowerShell-Cmdlet, um die Einstellungen anzuzeigen, die einer bestimmten Video trunk-Konfiguration zugeordnet sind:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Wenn Sie eine bestimmte Video trunk-Konfiguration entfernen möchten, verwenden Sie das folgende Windows PowerShell-Cmdlet (Beachten Sie, dass die Konfiguration des Global Bereichs-Video Trunks angewendet wird, wenn keine spezifischere Video trunk-Konfiguration für einen bestimmten trunk vorhanden ist):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Erstellen Sie mithilfe der folgenden Windows PowerShell-Cmdlets einen Wählplan, der dem Stamm zugeordnet werden soll:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Mit dem Befehl **Remove-CsVoiceNormalizationRule** können Sie eine Standardregel überschreiben, die sich störend auf die erwartete Interaktion zwischen VIS und CUCM auswirkt.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) kann verwendet werden, um einen Wählplan zu entfernen.
  
Bei einem Video-SIP-Trunk-Anruf von einem Video-Gateway, dessen Anforderungs-URI eine nicht-E. 164-Nummer enthält, liest VIS den Namen des Wählplans, der dem zugehörigen trunk zugeordnet ist, und enthält den Namen des Wählplans im Kontext Teil des Telefons des Anforderungs-URIs in der Einladung, die VI S wird an das Front-End gesendet. Die Übersetzungsanwendung am Front-End-Server extrahiert dann die mit dem Wählplan verbundenen Normalisierungsregeln und wendet sie auf die Anforderungs-URI an.
## <a name="trunk-configuration-options"></a>Optionen für die Trunkkonfiguration

Die zuvor erwähnten Windows PowerShell-Cmdlets für die Video trunk-Konfiguration waren neu bei Skype for Business Server 2015. Es folgt eine kurze Erläuterung der Einstellungen für die Videotrunkkonfiguration.
  
 **GatewaySendsRtcpForActiveCalls** Dieser Parameter bestimmt, ob RTCP-Pakete für aktive Anrufe vom VTC an das VIS gesendet werden. Ein aktiver Anruf ist in diesem Kontext ein Anruf, bei dem Mediendaten in mindestens eine Richtung übertragen werden dürfen. Wenn „GatewaySendsRtcpForActiveCalls“ auf „True“ festgelegt ist, kann der VIS einen Anruf beenden, wenn für mehr als 30 Sekunden keine RTCP-Pakete empfangen werden. Der Standardwert ist **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Dieser Parameter bestimmt, ob RTCP-Pakete weiterhin über den trunk für Anrufe gesendet werden, die in Wartestellung gesetzt wurden, und es wird davon ausgegangen, dass keine Medienpakete in beide Richtungen fließen. Der VIS kann den Anruf beenden, wenn bei einem Anruf in der Warteschleife keine RTCP-Pakete vom VTC zum VIS übertragen werden. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableMediaEncryptionForSipOverTls** Dieser Parameter aktiviert oder deaktiviert SRTP für Medien, wenn das SIPTransport-Protokoll auf TLS eingestellt ist. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableSessionTimer** Dieser Parameter aktiviert oder deaktiviert Sitzungs Timer auf der VIS-Seite für jedes SIP-Dialogfeld, das dem Video SIP-Trunk zugeordnet ist. Der Standardwert ist **False**.
  
 **ForwardErrorCorrectionType** Dieser Parameter wird verwendet, um zu ermitteln, ob die Forward-Fehlerkorrektur (FEC) für Videodatenströme auf dem Bein zwischen dem Video-Interop-Server und einem Video-Gateway angewendet werden soll. Wenn ForwardErrorCorrectionType auf "None" festgelegt wird, wird FEC zwischen VIS und Video Gateway/VTC deaktiviert. Das Festlegen von ForwardErrorCorrectionType auf "Cisco" ermöglicht FEC, das mit Video Gateways von Cisco kompatibel ist, beispielsweise Cisco Unified Communications Manager (CUCM). Der Standardwert ist **None**.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server](configure-cucm-for-interoperation.md)
