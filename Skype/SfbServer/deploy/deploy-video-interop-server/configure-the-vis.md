---
title: Konfigurieren des Video-Interoperabilitätsservers in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Zusammenfassung: Konfigurieren der Rolle des Video-Interoperabilität-Servers (VIS) in Skype for Business Server.'
ms.openlocfilehash: c6122e27f3b462a69a365259827a394b9b379012
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389617"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Konfigurieren des Video-Interoperabilitätsservers in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Rolle des Video-Interoperabilität-Servers (VIS) in Skype for Business Server.
  
 Konfigurieren Sie die Einstellungen, die der VIS videotrunks mithilfe von Windows PowerShell zuordnen wird. Nach der Installation des VIS-Diensts wird eine Videotrunkkonfiguration mit globaler Reichweite erstellt. Diese Videotrunkkonfiguration wird vom VIS auf alle Trunks angewendet, die keine Videotrunkkonfiguration mit einem spezifischeren Bereich haben. Beachten Sie, dass die Videotrunkkonfiguration eine Sammlung von Einstellungen ist, die für Videotrunks gelten.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Konfigurieren von Videotrunk und Wählplan

Verwenden Sie die folgenden Windows PowerShell Befehle, um die Konfiguration des Videotrunks und den Wählplan anzugeben, die den neu definierten Trunks zugeordnet werden sollen, die im Topologiedokument zwischen dem VIS und allen Videogateways definiert sind. Alle diese Einstellungen können auf globaler, Standort- oder Dienstebene (Videogateway) festgelegt werden. 
  
Pro Skype for Business Server Bereitstellung wird ein Wählplan mit globaler Gültigkeitsbereich erstellt. Dieser Wählplan wird vom VIS auf alle Trunks angewendet, die keinen Wählplan mit einem spezifischeren Bereich haben. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Konfigurieren des VIS mithilfe von Windows PowerShell

1. Erstellen Sie eine neue Videotrunkkonfiguration (eine Sammlung von Einstellungen), die auf dem Trunk zwischen dem VIS und Cisco Unified Communications Manager (CallManager oder CUCM) verwendet werden soll, mithilfe des folgenden Windows PowerShell Cmdlets:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Wenn ein videotrunk vorhanden ist, der geändert werden muss, verwenden Sie das folgende cmdlet Windows PowerShell:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Um die Einstellungen anzuzeigen, die einer bestimmten Videotrunkkonfiguration zugeordnet sind, verwenden Sie das folgende cmdlet Windows PowerShell:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Verwenden Sie zum Entfernen einer bestimmten Videotrunkkonfiguration das folgende cmdlet Windows PowerShell (beachten Sie, dass die Videotrunkkonfiguration mit globaler Bereichsdefinition angewendet wird, wenn für einen bestimmten Trunk keine spezifischere Videotrunkkonfiguration vorhanden ist):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Richten Sie mithilfe der folgenden Windows PowerShell Cmdlets einen Wählplan ein, der dem Trunk zugeordnet werden soll:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Der Befehl **"Remove-CsVoiceNormalizationRule** " ist erforderlich, um eine Standardregel außer Kraft zu setzen, die die erwartete VIS- und CUCM-Interaktion beeinträchtigt.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) kann zum Entfernen eines Wählplans verwendet werden.
  
Bei einem Video-SIP-Trunkanruf von einem Videogateway, dessen Anforderungs-URI eine Nicht-E.164-Nummer enthält, liest der VIS den Namen des Wählplans, der dem zugeordneten Trunk zugeordnet ist, und schließt den Namen des Wählplans in den Telefonkontextteil des Anforderungs-URI in die Einladung ein, die der VIS an das Front-End sendet. Die Übersetzungsanwendung im Front-End extrahiert dann die Normalisierungsregeln, die dem Wählplan zugeordnet sind, und wendet sie auf den Anforderungs-URI an.
## <a name="trunk-configuration-options"></a>Trunkkonfigurationsoptionen

Die zuvor erwähnten Windows PowerShell Cmdlets für die Videotrunkkonfiguration waren neu in Skype for Business Server 2015. Die mit der Videotrunkkonfiguration verbundenen Einstellungen erfordern eine kurze Erläuterung.
  
 **GatewaySendsRtcpForActiveCalls** Dieser Parameter bestimmt, ob RTCP-Pakete für aktive Anrufe vom VTC an den VIS gesendet werden. Ein aktiver Anruf ist in diesem Kontext ein Anruf, bei dem Mediendaten in mindestens eine Richtung übertragen werden dürfen. Wenn GatewaySendsRtcpForActiveCalls auf "True" festgelegt ist, kann der VIS einen Anruf beenden, wenn er für einen Zeitraum von mehr als 30 Sekunden keine RTCP-Pakete empfängt. Der Standardwert ist **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Dieser Parameter bestimmt, ob RTCP-Pakete für Anrufe, die gehalten wurden, weiterhin über den Trunk gesendet werden, und es wird erwartet, dass keine Medienpakete in beide Richtungen fließen. Der VIS kann den Anruf beenden, wenn während des Anhaltens des Anrufs keine RTCP-Pakete vom VTC zum VIS fließen. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableMediaEncryptionForSipOverTls** Dieser Parameter aktiviert oder deaktiviert SRTP für Medien, wenn das SIPTransport-Protokoll auf TLS festgelegt ist. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableSessionTimer** Dieser Parameter aktiviert oder deaktiviert Sitzungszeitgeber auf der VIS-Seite für jedes SIP-Dialogfeld, das dem Video-SIP-Trunk zugeordnet ist. Der Standardwert ist **False**.
  
 **ForwardErrorCorrectionType** Dieser Parameter wird verwendet, um zu bestimmen, ob die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) für Videodatenströme auf den Abschnitt zwischen dem Video-Interoperabilitätsserver und einem Videogateway angewendet werden soll. Wenn ForwardErrorCorrectionType auf "None" festgelegt wird, wird FEC zwischen VIS und Videogateway/VTC deaktiviert. Wenn ForwardErrorCorrectionType auf "Cisco" festgelegt wird, ist FEC kompatibel mit Videogateways von Cisco, z. B. Cisco Unified Communications Manager (CUCM). Der Standardwert lautet **Keine**.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server](configure-cucm-for-interoperation.md)