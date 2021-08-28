---
title: Erstellen regionenübergreifender Netzwerkrouten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Erstellen oder Ändern von regionenübergreifenden Netzwerkrouten, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 0d4e4977cbd2aed82de9c8299f326f301551321a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594719"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Erstellen regionenübergreifender Netzwerkrouten in Skype for Business Server
 
Erstellen oder Ändern von regionenübergreifenden Netzwerkrouten, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden. 
  
Eine regionenübergreifende Netzwerkroute definiert die Route zwischen zwei Netzwerkregionen. Jedes Netzwerkregionenpaar in Ihrer Bereitstellung zur Anrufsteuerung erfordert eine regionenübergreifende Netzwerkroute. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.
  
Während Regionenverbindungen Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen, bestimmt eine regionenübergreifende Route, welchen verknüpften Pfad die Verbindung von einer Region zu einer anderen durchläuft.
  
In der Beispieltopologie müssen regionenübergreifende Netzwerkrouten für jedes der drei Regionenpaare definiert werden: Nordamerika/EMEA, EMEA/APAC und Nordamerika/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie regionenübergreifende Netzwerkrouten mithilfe Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das Cmdlet **New-CsNetworkInterRegionRoute** aus, um die erforderlichen Routen zu definieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > Die regionenübergreifende Netzwerkroute "Nordamerika/APAC" erfordert zwei Netzwerkregionenverbindungen, da zwischen ihnen keine direkte Netzwerkregionenverbindung besteht. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie regionenübergreifende Netzwerkrouten mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite **"Neue Regionenroute"** auf **"Name",** und geben Sie dann einen Namen für die regionenübergreifende Netzwerkroute ein.
    
6. Klicken Sie auf **Netzwerkregion 1** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 2 erstellt werden soll.
    
7. Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 1 erstellt werden soll.
    
8. Klicken Sie neben dem Feld **"Netzwerkregionenverbindungen"** auf **"Hinzufügen",** und fügen Sie dann eine Netzwerkregionenverbindung hinzu, die in der regionenübergreifenden Netzwerkroute verwendet wird.
    
    > [!NOTE]
    > Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Beispielsweise erfordert die regionenübergreifende Netzwerkroute "Nordamerika/APAC" zwei Netzwerkregionenverbindungen, da zwischen ihnen keine direkte Netzwerkregionenverbindung besteht. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere regionenübergreifende Netzwerkrouten, um die Erstellung regionenübergreifender Netzwerkrouten für Ihre Topologie abzuschließen.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)