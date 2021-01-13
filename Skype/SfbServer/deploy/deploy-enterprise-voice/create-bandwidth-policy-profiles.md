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
description: Erstellen oder ändern Sie Bandbreitenrichtlinien, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: ac80ebb8b61a763efc0077f267a024a21a359b5d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824845"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Erstellen von Bandbreitenrichtlinienprofilen in Skype for Business Server 
 
Erstellen oder ändern Sie Bandbreitenrichtlinien, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden. 
  
Bandbreitenrichtlinien definieren Einschränkungen bei der Bandbreitennutzung für Audio- und Videomodalitäten in Echtzeit. Bandbreitenrichtlinien werden auf bandbreitenweite Richtlinienprofile angewendet, die zur Anrufsteuerung auf mehrere Netzwerkstandorte angewendet werden können.
  
Richtlinien dazu, welche Bandbreitengrenzwerte Sie in Ihrer Anrufsteuerungsbereitstellung festlegen sollten, finden Sie unter "Planen der Anrufsteuerung [in Skype for Business Server".](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
Die im folgenden Verfahren erstellten Beispielrichtlinien legen Grenzwerte für den gesamten Audiodatenverkehr, einzelne Audiositzungen, den gesamten Videodatenverkehr und einzelne Videositzungen. Beispielsweise werden im 5Mb_Link Bandbreitenrichtlinienprofil die folgenden Grenzwerte gesetzt: 
  
- Audiogrenzwert: 2.000 KBit/s
    
- Grenzwert für Audiositzungen: 200 KBit/s
    
- Videogrenzwert: 1.400 KBit/s
    
- Grenzwert für Videositzungen: 700 KBit/s
    
> [!NOTE]
> Der Mindestgrenzwert für Audiositzungen beträgt 40 KBit/s. Der Mindestwert für videositzungslimit beträgt 100 KBit/s. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie Bandbreitenrichtlinienprofile mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Führen Sie für jedes Bandbreitenrichtlinienprofil, das Sie erstellen möchten, das cmdlet New-CsNetworkBandwidthPolicyProfile aus. Führen Sie beispielsweise den folgenden Befehl aus:
    
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
    
3. Klicken Sie auf **die Navigationsschaltfläche "Richtlinienprofil".**
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie **auf der Seite "Neues** Richtlinienprofil" auf **"Name",** und geben Sie einen Namen für das Bandbreitenrichtlinienprofil ein.
    
6. Klicken **Sie auf "Audiolimit",** und geben Sie dann die maximale Anzahl von KBit/s ein, um alle Audiositzungen zusammen zu ermöglichen.
    
7. Klicken **Sie auf "Audiositzungslimit",** und geben Sie dann die maximale Anzahl von KBit/s ein, die für jede einzelne Audiositzung zulässig ist.
    
8. Klicken **Sie auf "Videolimit",** und geben Sie dann die maximale Anzahl von KBit/s ein, um alle Videositzungen zusammen zu ermöglichen.
    
9. Klicken **Sie auf "Videositzungslimit",** und geben Sie dann die maximale Anzahl von KBit/s ein, die für jede einzelne Videositzung zulässig ist.
    
10. Klicken Sie optional auf **"Beschreibung",** und geben Sie zusätzliche Informationen ein, um dieses Bandbreitenrichtlinienprofil zu beschreiben.
    
11. Klicken Sie auf **Commit ausführen**.
    
12. Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinienprofilen für Ihre Topologie zu beenden.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
