---
title: Erstellen von Netzwerkregionenverbindungen in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Erstellen oder Ändern von netzwerkregionenverbindungen, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.
ms.openlocfilehash: f2b9ba5d6ccf2c2648bf755306001350f82c2931
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a>Erstellen von Netzwerkregionenverbindungen in Skype for Business Server 2015
 
Erstellen oder Ändern von netzwerkregionenverbindungen, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden. 
  
Regionen in einem Netzwerk sind über physische WAN-Verbindungen miteinander verbunden. Eine netzwerkregionenverbindung erstellt eine Verbindung zwischen zwei Regionen für Call Admission Control (CAC) konfiguriert und die Netzwerkbandbreite ist eingeschränkt auf audio und video-Datenverkehr zwischen diesen Regionen festgelegt.
  
Die Beispieltopologie weist eine Verbindung zwischen den Regionen „North America“ und „APAC“ sowie zwischen den Regionen „EMEA“ und „APAC“ auf. Diese Region links wird von WAN-Bandbreite eingeschränkt, wie beschrieben in Tabelle Bandbreiteninformationen [Beispiel: Sammeln von Anforderungen für die anrufsteuerung in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Erstellen Sie netzwerkregionenverbindungen mithilfe von Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das Cmdlet „New-CsNetworkRegionLink“ aus, um die Regionenverbindungen zu erstellen und geeignete Bandbreitenrichtlinienprofile anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Erstellen Sie netzwerkregionenverbindungen mithilfe von Skype Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Regionenverbindung**.
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite **Neue Netzwerkregionenverbindung** auf **Name** und geben Sie einen Namen für die Netzwerkregionenverbindung ein.
    
6. Klicken Sie auf **Netzwerkregion 1** und anschließend auf die Netzwerkregion in der Liste, für die eine Verbindung mit Netzwerkregion 2 erstellt werden soll.
    
7. Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Verbindung mit Netzwerkregion 1 erstellt werden soll.
    
8. Klicken Sie optional auf **Bandbreitenrichtlinie** und wählen Sie das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionenverbindung anwenden möchten.
    
    > [!NOTE]
    > Wenden Sie nur dann eine Bandbreitenrichtlinie an, wenn die Netzwerkregionenverbindung eine Bandbreiteneinschränkung aufweist und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr in dieser Verbindung zu steuern. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Zum Abschließen der Erstellung von Netzwerkregionenverbindungen für Ihre Topologie wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für weitere Regionen.
    
## <a name="see-also"></a>Siehe auch

#### 

[Neue CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

