---
title: Konfigurieren des Video-Inaktivitätsservers in Skype for Business Server
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
description: 'Zusammenfassung: Konfigurieren der Rolle "Video-Inteopserver (VIS)" in Skype for Business Server.'
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820695"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Konfigurieren des Video-Inaktivitätsservers in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Rolle "Video-In-Inop-Server(VIS)" in Skype for Business Server.
  
 Konfigurieren Sie die Einstellungen, die der VIS Video trunks mithilfe von Windows PowerShell. Nach der Installation des VIS-Diensts wird eine Video trunkkonfiguration mit globaler Gültigkeit erstellt. Diese Video trunkkonfiguration wird vom VIS auf alle Trunks angewendet, die keine Video trunkkonfiguration mit einem spezielleren Bereich haben. Beachten Sie, dass es sich bei der Video trunkkonfiguration um eine Auflistung von Einstellungen handelt, die für Video trunks gelten.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Konfigurieren von Video trunk und Wähleinstellungen

Verwenden Sie die folgenden Windows PowerShell, um die Video trunkkonfiguration und den Wählplan anzugeben, die den neu definierten Trunks zugeordnet werden sollen, die im Topologiedokument zwischen dem VIS und allen Videogateways definiert sind. Alle diese Einstellungen können auf der Ebene "Global", "Standort" oder "Dienst (Videogateway) festgelegt werden. 
  
Pro Skype for Business Server-Bereitstellung wird ein Wählplan mit globaler Ebene erstellt. Dieser Wählplan wird vom VIS auf alle Trunks angewendet, die keinen Wählplan mit spezifischem Bereich haben. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Konfigurieren des VIS mithilfe Windows PowerShell

1. Erstellen Sie eine neue Video trunkkonfiguration (eine Auflistung von Einstellungen), die auf dem Trunk zwischen dem VIS und Cisco Unified Communications Manager (CallManager oder CUCM) verwendet werden soll, indem Sie das folgende Windows PowerShell verwenden:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Wenn ein Video trunk vorhanden ist, der geändert werden muss, verwenden Sie das folgende Windows PowerShell Cmdlet:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Verwenden Sie zum Anzeigen der Einstellungen, die einer bestimmten Video trunkkonfiguration zugeordnet sind, das folgende Windows PowerShell Cmdlet:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Verwenden Sie zum Entfernen einer bestimmten Video trunkkonfiguration das folgende Windows PowerShell-Cmdlet (beachten Sie, dass die Konfiguration des Video trunks auf globaler Ebene angewendet wird, wenn für einen bestimmten Trunk keine spezielle Video trunkkonfiguration verfügbar ist):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Richten Sie mithilfe der folgenden cmdlets einen Wählplan ein, der dem Trunk zugeordnet Windows PowerShell wird:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Der **Befehl "Remove-CsVoiceNormalizationRule"** ist erforderlich, um eine Standardregel außer Kraft zu setzen, die die erwartete VIS- und CUCM-Interaktion beeinträchtigt.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) kann verwendet werden, um einen Wählplan zu entfernen.
  
Bei einem Video-SIP-Trunk-Anruf von einem Videogateway, dessen Anforderungs-URI eine Nicht-E.164-Nummer enthält, liest der VIS den Namen der dem zugeordneten Trunk zugeordneten Wählplans und nimmt den Namen des Wählplans in den Telefonkontextteil des Anforderungs-URI in die Einladung auf, die der VIS an das Front-End sendet. Die Übersetzungsanwendung auf dem Front-End extrahiert dann die dem Wählplan zugeordneten Normalisierungsregeln und wendet sie auf den Anforderungs-URI an.
## <a name="trunk-configuration-options"></a>Trunkkonfigurationsoptionen

Die Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015. Die Einstellungen für die Video trunkkonfiguration erfordern eine kurze Erläuterung.
  
 **GatewaySendsRtcpForActiveCalls** Dieser Parameter bestimmt, ob für aktive Anrufe vom VTC an den VIS rtcp-Pakete gesendet werden. Ein aktiver Anruf ist in diesem Kontext ein Anruf, bei dem Mediendaten in mindestens eine Richtung übertragen werden dürfen. Wenn "GatewaySendsRtcpForActiveCalls" auf "True" festgelegt ist, kann der VIS einen Anruf beenden, wenn er für einen Zeitraum von mehr als 30 Sekunden keine RTCP-Pakete erhält. Der Standardwert ist **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Dieser Parameter bestimmt, ob für Anrufe, die in der Warteschleife platziert wurden und keine Medienpakete in beide Richtungen übermittelt werden, weiterhin über den Trunk gesendet werden. Der VIS kann den Anruf beenden, wenn keine RTCP-Pakete vom VTC zum VIS fließen, während sich der Anruf im Halteschleifen befindet. Der Standardwert ist **True**. Wenn das Protokoll "SIPTransport" auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableMediaEncryptionForSipOverTls** Dieser Parameter aktiviert oder deaktiviert SRTP für Medien, wenn das Protokoll SIPTransport auf TLS festgelegt ist. Der Standardwert ist **True**. Wenn das Protokoll "SIPTransport" auf TCP festgelegt ist, wird diese Einstellung ignoriert.
  
 **EnableSessionTimer** Dieser Parameter aktiviert oder deaktiviert Sitzungszeitgeber auf der VIS-Seite für jedes SIP-Dialogfeld, das dem Video-SIP-Trunk zugeordnet ist. Der Standardwert ist **False**.
  
 **ForwardErrorCorrectionType** Dieser Parameter wird verwendet, um zu bestimmen, ob die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) für Videostreams auf dem Abschnitt zwischen dem Video-Inteopserver und einem Videogateway angewendet werden soll. Wenn Sie ForwardErrorCorrectionType auf "None" festlegen, wird FEC zwischen VIS und Videogateway/VTC deaktiviert. Wenn ForwardErrorCorrectionType auf "Cisco" festlegen, ist FEC mit Videogateways von Cisco kompatibel, z. B. Cisco Unified Communications Manager (CUCM). Der Standardwert lautet **Keine**.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server](configure-cucm-for-interoperation.md)
