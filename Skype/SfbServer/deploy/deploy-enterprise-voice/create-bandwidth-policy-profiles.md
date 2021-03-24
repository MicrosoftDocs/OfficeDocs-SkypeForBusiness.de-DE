---
title: Erstellen von Bandbreitenrichtlinienprofilen in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Erstellen oder Ändern von Bandbreitenrichtlinien, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 9458c5576d2c89254c4ee6477ede33c010cb4a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093243"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Erstellen von Bandbreitenrichtlinienprofilen in Skype for Business Server 
 
Erstellen oder Ändern von Bandbreitenrichtlinien, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden. 
  
Bandbreitenrichtlinien definieren Einschränkungen der Bandbreitennutzung für Audio- und Videomodalitäten in Echtzeit. Bandbreitenrichtlinien werden aufbandweite Richtlinienprofile angewendet, die für die Anrufsteuerung auf mehrere Netzwerkstandorte angewendet werden können.
  
Richtlinien dazu, welche Bandbreitengrenzwerte Sie in Ihrer Anrufsteuerungsbereitstellung festlegen sollten, finden Sie unter [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
In den im folgenden Verfahren erstellten Beispielrichtlinien werden Grenzwerte für den gesamten Audiodatenverkehr, einzelne Audiositzungen, den gesamten Videodatenverkehr und einzelne Videositzungen festgelegt. Beispielsweise werden im 5Mb_Link Bandbreitenrichtlinienprofil die folgenden Grenzwerte gesetzt: 
  
- Audiogrenzwert: 2.000 KBit/s
    
- Grenzwert für Audiositzungen: 200 KBit/s
    
- Videolimit: 1.400 KBit/s
    
- Grenzwert für Videositzungen: 700 KBit/s
    
> [!NOTE]
> Der Minimale Grenzwert für Audiositzungen beträgt 40 KBit/s. Der Mindestwert für Videositzungsgrenzwerte beträgt 100 KBit/s. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie Bandbreitenrichtlinienprofile mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Führen Sie für jedes zu erstellende Bandbreitenrichtlinienprofil das cmdlet New-CsNetworkBandwidthPolicyProfile aus. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie Bandbreitenrichtlinienprofile mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf **die Schaltfläche Richtlinienprofilnavigation.**
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite Neues **Richtlinienprofil** auf **Name,** und geben Sie dann einen Namen für das Bandbreitenrichtlinienprofil ein.
    
6. Klicken **Sie auf Audiolimit,** und geben Sie dann die maximale Anzahl von KBit/s ein, die für alle Audiositzungen kombiniert werden soll.
    
7. Klicken Sie auf Audiositzungslimit, und geben Sie dann die maximale Anzahl von KBit/s ein, die für jede einzelne Audiositzung zulässig ist. 
    
8. Klicken **Sie auf Videolimit,** und geben Sie dann die maximale Anzahl von KBit/s ein, um alle Videositzungen kombiniert zu ermöglichen.
    
9. Klicken **Sie auf** Videositzungslimit, und geben Sie dann die maximale Anzahl von KBit/s ein, die für jede einzelne Videositzung zulässig ist.
    
10. Klicken Sie optional auf **Beschreibung,** und geben Sie weitere Informationen ein, um dieses Bandbreitenrichtlinienprofil zu beschreiben.
    
11. Klicken Sie auf **Commit ausführen**.
    
12. Um das Erstellen von Bandbreitenrichtlinienprofilen für Ihre Topologie zu beenden, wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)