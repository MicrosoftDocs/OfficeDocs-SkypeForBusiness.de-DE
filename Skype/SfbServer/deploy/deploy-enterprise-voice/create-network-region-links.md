---
title: Erstellen von Netzwerkregionsverbindungen in Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Erstellen oder ändern Sie Netzwerkregionsverbindungen, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822465"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Erstellen von Netzwerkregionsverbindungen in Skype for Business Server
 
Erstellen oder ändern Sie Netzwerkregionsverbindungen, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden. 
  
Regionen in einem Netzwerk sind über eine physische WAN-Verbindung verbunden. Eine Netzwerkregionenverbindung erstellt eine Verbindung zwischen zwei Regionen, die für die Anrufsteuerung konfiguriert sind, und legt die Bandbreiteneinschränkungen für den Audio- und Videodatenverkehr zwischen diesen Regionen fest.
  
Die Beispieltopologie verfügt über eine Verbindung zwischen den Regionen "Nordamerika" und "APAC" sowie über eine Verbindung zwischen den Regionen "EMEA" und "APAC". Jede dieser Regionenverbindungen wird durch die WAN-Bandbreite eingeschränkt, wie in der Tabelle "Informationen zur Bandbreite für Regionenverbindungen" im Beispiel: Erfassen von Anforderungen für die Anrufsteuerung [in Skype for Business Server beschrieben.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie Netzwerkregionsverbindungen mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Führen Sie New-CsNetworkRegionLink cmdlet aus, um die Regionenverbindungen zu erstellen und geeignete Bandbreitenrichtlinienprofile anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie Netzwerkregionsverbindungen mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die **Navigationsschaltfläche "Regionenlink".**
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite **"Neue** Regionenverbindung" auf **"Name",** und geben Sie einen Namen für die Netzwerkregionsverbindung ein.
    
6. Klicken **Sie auf #1**"Netzwerkregion", und klicken Sie dann auf die Netzwerkregion in der Liste, die Sie mit der Netzwerkregion verbinden #2.
    
7. Klicken **Sie auf #2**"Netzwerkregion", und klicken Sie dann auf eine Netzwerkregion in der Liste, die Sie mit der Netzwerkregion verbinden #1.
    
8. Klicken Sie optional auf **"Bandbreitenrichtlinie",** und wählen Sie dann das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionsverbindung anwenden möchten.
    
    > [!NOTE]
    > Wenden Sie eine Bandbreitenrichtlinie nur an, wenn die Netzwerkregionsverbindung bandbreitenbeschränkt ist und Sie die Mediendatenverkehrskontrolle für diese Verbindung mithilfe der Cac steuern möchten. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Regionen, um die Erstellung von Netzwerkregionenverbindungen für Ihre Topologie zu beenden.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
