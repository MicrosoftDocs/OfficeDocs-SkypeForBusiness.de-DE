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
description: Erstellen oder Ändern von Netzwerkregionsverbindungen, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 5fd9657b3919e80552a82912550e7314297182cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093103"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Erstellen von Netzwerkregionsverbindungen in Skype for Business Server
 
Erstellen oder Ändern von Netzwerkregionsverbindungen, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden. 
  
Regionen in einem Netzwerk sind über eine physische WAN-Verbindung verbunden. Eine Netzwerkregionenverbindung erstellt eine Verbindung zwischen zwei Regionen, die für die Anrufsteuerung konfiguriert sind, und legt die Bandbreiteneinschränkungen für den Audio- und Videodatenverkehr zwischen diesen Regionen fest.
  
Die Beispieltopologie hat eine Verbindung zwischen den Regionen Nordamerika und APAC sowie eine Verbindung zwischen den Regionen EMEA und APAC. Jede dieser Regionenverbindungen ist durch die WAN-Bandbreite eingeschränkt, wie in der Tabelle "Bandbreiteninformationen zu Regionenverbindungen" in Beispiel: Sammeln von Anforderungen für die Anrufsteuerung [in Skype for Business Server beschrieben.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie Netzwerkregionsverbindungen mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
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
    
3. Klicken Sie auf **die Navigationsschaltfläche** Region Link.
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite Neue **Regionenverknüpfung** auf **Name,** und geben Sie dann einen Namen für den Netzwerkbereichslink ein.
    
6. Klicken **Sie auf Netzwerkregion #1**, und klicken Sie dann auf die Netzwerkregion in der Liste, die Sie mit der Netzwerkregion verbinden #2.
    
7. Klicken **Sie auf Netzwerkregion #2**, und klicken Sie dann in der Liste auf eine Netzwerkregion, die Sie mit der Netzwerkregion #1.
    
8. Klicken Sie optional auf **Bandbreitenrichtlinie,** und wählen Sie dann das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionsverbindung anwenden möchten.
    
    > [!NOTE]
    > Wenden Sie eine Bandbreitenrichtlinie nur an, wenn die Netzwerkregionsverbindung bandbreitenbeschränkt ist und Sie die Mediendatenverkehrskontrolle für diese Verbindung verwenden möchten. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Regionen, um das Erstellen von Netzwerkregionenverbindungen für Ihre Topologie zu beenden.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)