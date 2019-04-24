---
title: Konfigurieren der Interop-Videoserver in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Zusammenfassung: Konfigurieren der Rolle Video Interop Server (gegenüber) in Skype für Business Server.'
ms.openlocfilehash: 1cdc03fea116b5c41eaca13b4349ffc340dbc061
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219607"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Konfigurieren der Interop-Videoserver in Skype für Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Rolle Video Interop Server (gegenüber) in Skype für Business Server.
  
 Konfigurieren Sie die Einstellungen, die die gegenüber mithilfe von Windows PowerShell-video Trunks zuordnen möchten. Eine Videotrunkkonfiguration auf globaler Ebene wird erstellt, wenn der VIS-Dienst installiert ist. Diese Videotrunkkonfiguration wird vom VIS auf alle Trunks angewendet, die keine Videotrunkkonfiguration mit einer spezifischeren Ebene haben. Hinweis: Die Videotrunkkonfiguration ist eine Sammlung von Einstellungen, die auf Videotrunks angewendet wird.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Konfigurieren von Videotrunk und Wählplan

Verwenden Sie die folgenden Windows PowerShell-Befehle an den video trunkkonfiguration, und wählen Planen der neu definierten Trunk(s) definiert im Topologiedokument zwischen den gegenüber und alle Video Gateways zugeordnet werden soll. Alle Einstellungen können auf globaler, Standort- oder Dienstebene (Videogateway) eingerichtet werden. 
  
Ein Wählplan mit globaler Ebene wird pro Skype für Business Server-Bereitstellung erstellt. Dieser Wählplan wird vom VIS auf alle Trunks angewendet, die keinen Wählplan mit einer spezifischeren Ebene haben. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Konfigurieren der gegenüber mithilfe von Windows PowerShell

1. Erstellen einer neuen video trunkkonfiguration (eine Auflistung von Einstellungen) auf den Trunk zwischen der gegenüber und Cisco Unified Communications-Manager (CallManager oder CUCM) verwenden, um mithilfe des folgenden Windows PowerShell-Cmdlets:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Ist ein vorhandener video Trunk, der geändert werden soll, verwenden Sie das folgende Windows PowerShell-Cmdlet:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Um die Einstellungen, die einer bestimmten video trunkkonfiguration zugeordneten anzuzeigen, verwenden Sie das folgende Windows PowerShell-Cmdlet:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Um einen bestimmten video trunkkonfiguration zu entfernen, verwenden Sie die folgenden Windows PowerShell-Cmdlets (Beachten Sie, dass die trunkkonfiguration global gültiger video angewendet wird, wenn genauer gesagt bereichsbezogenen video trunkkonfiguration für einen bestimmten Trunk nicht vorhanden ist):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Richten Sie einen Wählplan den Trunk mit den folgenden Windows PowerShell-Cmdlets zugeordnet:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Mit dem Befehl **Remove-CsVoiceNormalizationRule** können Sie eine Standardregel überschreiben, die sich störend auf die erwartete Interaktion zwischen VIS und CUCM auswirkt.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) kann verwendet werden, um einen Wählplan zu entfernen.
  
Für einen SIP-Trunk Videoanruf von einem Video Gateway, deren Anforderungs-URI einer nicht e. 164-Nummer enthält, gegenüber liest den Namen des Wählplans, der dem zugeordneten Trunk zugeordnet und der Wählplanname im Kontext Telefon Teil des Anforderungs-URI einladen, VI umfasst S sendet an den Front-End. Die Übersetzungsanwendung am Front-End-Server extrahiert dann die mit dem Wählplan verbundenen Normalisierungsregeln und wendet sie auf die Anforderungs-URI an.
## <a name="trunk-configuration-options"></a>Optionen für die Trunkkonfiguration

Windows PowerShell-Cmdlets für video trunkkonfiguration weiter oben erwähnten wurden neu in Skype für Business Server 2015. Es folgt eine kurze Erläuterung der Einstellungen für die Videotrunkkonfiguration.
  
 **GatewaySendsRtcpForActiveCalls** Dieser Parameter bestimmt, ob RTCP-Pakete, die gegenüber für aktive Anrufe aus den VTC gesendet werden. Ein aktiver Anruf ist in diesem Kontext ein Anruf, bei dem Mediendaten in mindestens eine Richtung übertragen werden dürfen. Wenn „GatewaySendsRtcpForActiveCalls“ auf „True“ festgelegt ist, kann der VIS einen Anruf beenden, wenn für mehr als 30 Sekunden keine RTCP-Pakete empfangen werden. Der Standardwert ist **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Dieser Parameter bestimmt, ob weiterhin RTCP-Pakete über den Trunk für Anrufe gesendet werden, die in der Warteschleife abgelegt wurden und keine Pakete Medien erwartet werden, dass flow in beide Richtungen. Der VIS kann den Anruf beenden, wenn bei einem Anruf in der Warteschleife keine RTCP-Pakete vom VTC zum VIS übertragen werden. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableMediaEncryptionForSipOverTls** Dieser Parameter aktiviert oder deaktiviert die SRTP für Medien, wenn das Protokoll SIPTransport TLS festgelegt ist. Der Standardwert ist **True**. Wenn das SIPTransport-Protokoll auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableSessionTimer** Dieser Parameter aktiviert oder deaktiviert Sitzung Timer auf der Seite gegenüber für jede SIP-Dialogfeld video SIP-Trunk zugeordnet. Der Standardwert ist **False**.
  
 **ForwardErrorCorrectionType** Dieser Parameter wird verwendet, um festzustellen, ob Forward Error Correction (Correction, FEC) für Videostreams wird vom Abschnitt zwischen dem Video Interop-Server und ein Video Gateway angewendet werden sollen. Einstellung ForwardErrorCorrectionType auf "None" deaktiviert FEC zwischen gegenüber und Video Gateway/VTC. Durch Festlegen auf "Cisco" ForwardErrorCorrectionType können FEC kompatibel mit Video Gateways von Cisco, wie beispielsweise Cisco Unified Communications Manager (CUCM). Der Standardwert ist **None**.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von CUCM für die Interoperation mit Skype für Business Server](configure-cucm-for-interoperation.md)
