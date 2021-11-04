---
title: Erstellen von Netzwerkregionenverbindungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Erstellen oder Ändern von Netzwerkregionenverbindungen, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: dd46e7d7043d7d1814b7a23ac755624af0af4c69
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775795"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Erstellen von Netzwerkregionenverbindungen in Skype for Business Server
 
Erstellen oder Ändern von Netzwerkregionenverbindungen, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden. 
  
Regionen in einem Netzwerk sind über eine physische WAN-Verbindung verbunden. Eine Netzwerkregionenverbindung erstellt eine Verbindung zwischen zwei Regionen, die für die Anrufsteuerung (Call Admission Control, CAC) konfiguriert sind, und legt die Bandbreiteneinschränkungen für Audio- und Videodatenverkehr zwischen diesen Regionen fest.
  
Die Beispieltopologie weist eine Verbindung zwischen den Regionen Nordamerika und APAC sowie eine Verbindung zwischen den Regionen EMEA und APAC auf. Jede dieser Regionenverbindungen ist durch die WAN-Bandbreite eingeschränkt, wie in der Tabelle "Informationen zur Regionsverbindungsbandbreite" im [Beispiel beschrieben: Erfassen von Anforderungen für die Anrufsteuerung in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie Netzwerkregionenverbindungen mithilfe Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das Cmdlet New-CsNetworkRegionLink aus, um die Regionsverbindungen zu erstellen und geeignete Bandbreitenrichtlinienprofile anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie Netzwerkregionenverbindungen mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **"Regionslink".**
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite **"Neue Regionenverbindung"** auf **"Name",** und geben Sie dann einen Namen für die Netzwerkregionenverbindung ein.
    
6. Klicken Sie auf **Netzwerkregion Nr. 1** und dann auf die Netzwerkregion in der Liste, die Sie mit Netzwerkregion Nr. 2 verknüpfen möchten.
    
7. Klicken Sie auf **Netzwerkregion Nr. 2** und dann auf eine Netzwerkregion in der Liste, die Sie mit Netzwerkregion Nr. 1 verknüpfen möchten.
    
8. Klicken Sie optional auf **Bandbreitenrichtlinie,** und wählen Sie dann das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionenverbindung anwenden möchten.
    
    > [!NOTE]
    > Wenden Sie eine Bandbreitenrichtlinie nur an, wenn die Netzwerkregionenverbindung bandbreitenbeschränkt ist und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr für diese Verbindung zu steuern. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Regionen, um die Erstellung von Netzwerkregionenverbindungen für Ihre Topologie abzuschließen.
    
## <a name="see-also"></a>Weitere Informationen

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)