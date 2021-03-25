---
title: Konfigurieren des Videointeopservers in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Zusammenfassung: Konfigurieren sie die Rolle Video Interop Server (VIS) in Skype for Business Server.'
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120304"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Konfigurieren des Videointeopservers in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Rolle Video Interop Server (VIS) in Skype for Business Server.
  
 Konfigurieren Sie die Einstellungen, die das VIS Video trunks mithilfe von Windows PowerShell. Nach der Installation des VIS-Diensts wird eine Video trunkkonfiguration mit globaler Gültigkeit erstellt. Diese Video trunkkonfiguration wird vom VIS auf alle Trunks angewendet, die keine Video trunkkonfiguration mit einem spezielleren Bereich haben. Beachten Sie, dass die Konfiguration des Video trunks eine Sammlung von Einstellungen ist, die für Video trunks gelten.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Konfigurieren von Video trunk und Wähleinstellungen

Verwenden Sie die folgenden Windows PowerShell-Befehle, um die Video trunkkonfiguration und den Wählplan anzugeben, die den neu definierten Trunks zugeordnet werden sollen, die im Topologiedokument zwischen dem VIS und allen Videogateways definiert sind. Alle diese Einstellungen können auf den Ebenen Global, Site oder Service (Video Gateway) festgelegt werden. 
  
Pro Skype for Business Server-Bereitstellung wird ein Wählplan mit globaler Reichweite erstellt. Dieser Wählplan wird von VIS auf alle Trunks angewendet, die keinen Wählplan mit einem spezielleren Bereich haben. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Konfigurieren des VIS mithilfe Windows PowerShell

1. Erstellen Sie eine neue Video trunkkonfiguration (eine Auflistung von Einstellungen), die im Trunk zwischen vis und Cisco Unified Communications Manager (CallManager oder CUCM) verwendet werden soll, indem Sie das folgende cmdlet Windows PowerShell verwenden:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Wenn ein vorhandener Video trunk vorhanden ist, der geändert werden muss, verwenden Sie das folgende Windows PowerShell Cmdlet:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Verwenden Sie zum Anzeigen der Einstellungen, die einer bestimmten Video trunkkonfiguration zugeordnet sind, das folgende Windows PowerShell Cmdlet:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Um eine bestimmte Video trunkkonfiguration zu entfernen, verwenden Sie das folgende Windows PowerShell-Cmdlet (beachten Sie, dass die Konfiguration des global begrenzten Video trunks angewendet wird, wenn für einen bestimmten Trunk keine speziell bereichsspezifisch verteilte Video trunkkonfiguration besteht):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Richten Sie einen Wählplan ein, der dem Trunk zugeordnet werden soll, indem Sie die folgenden Windows PowerShell verwenden:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Der **Befehl Remove-CsVoiceNormalizationRule** ist erforderlich, um eine Standardregel außer Kraft zu setzen, die die erwartete VIS- und CUCM-Interaktion beeinträchtigt.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) kann zum Entfernen eines Wählplans verwendet werden.
  
Bei einem Video-SIP-Trunk-Anruf von einem Videogateway, dessen Anforderungs-URI eine Nicht-E.164-Nummer enthält, liest VIS den Namen des Wählplans, der dem zugeordneten Trunk zugeordnet ist, und enthält den Namen des Wählplans im Telefonkontextteil des Anforderungs-URI in die Einladung, die VIS an das Front-End sendet. Die Übersetzungsanwendung im Front-End extrahiert dann die dem Wählplan zugeordneten Normalisierungsregeln und wendet sie auf den Anforderungs-URI an.
## <a name="trunk-configuration-options"></a>Trunkkonfigurationsoptionen

Die Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015. Die Einstellungen, die der Konfiguration des Video trunk zugeordnet sind, erfordern eine kurze Erläuterung.
  
 **GatewaySendsRtcpForActiveCalls** Dieser Parameter bestimmt, ob RTCP-Pakete für aktive Anrufe vom VTC an das VIS gesendet werden. Ein aktiver Anruf ist in diesem Kontext ein Anruf, bei dem Mediendaten in mindestens eine Richtung übertragen werden dürfen. Wenn GatewaySendsRtcpForActiveCalls auf True festgelegt ist, kann VIS einen Anruf beenden, wenn es für einen Zeitraum von mehr als 30 Sekunden keine RTCP-Pakete erhält. Der Standardwert ist **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Dieser Parameter bestimmt, ob RTCP-Pakete weiterhin über den Trunk für Anrufe gesendet werden, die in der Warteschleife platziert wurden, und es wird erwartet, dass keine Medienpakete in beide Richtungen fließen. VIS kann den Anruf beenden, wenn keine RTCP-Pakete vom VTC in VIS fließen, während sich der Anruf im Halteschleifen befindet. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableMediaEncryptionForSipOverTls** Dieser Parameter aktiviert oder deaktiviert SRTP für Medien, wenn das SIPTransport-Protokoll auf TLS festgelegt ist. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableSessionTimer** Dieser Parameter aktiviert oder deaktiviert Sitzungszeitgeber auf der VIS-Seite für jedes SIP-Dialogfeld, das dem Video-SIP-Trunk zugeordnet ist. Der Standardwert ist **False**.
  
 **ForwardErrorCorrectionType** Dieser Parameter wird verwendet, um zu bestimmen, ob die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) für Videostreams auf das Bein zwischen dem Video interop Server und einem Videogateway angewendet werden soll. Durch Festlegen von ForwardErrorCorrectionType auf "None" wird FEC zwischen VIS und Video Gateway/VTC deaktiviert. Durch festlegen von ForwardErrorCorrectionType auf "Cisco" ist FEC mit Videogateways von Cisco kompatibel, z. B. Cisco Unified Communications Manager (CUCM). Der Standardwert lautet **Keine**.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server](configure-cucm-for-interoperation.md)