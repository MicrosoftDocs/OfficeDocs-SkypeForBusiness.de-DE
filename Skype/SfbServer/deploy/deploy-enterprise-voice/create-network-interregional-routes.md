---
title: Erstellen von regionenübergreifenden Netzwerkrouten in Skype for Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Erstellen oder Ändern von überregionalen Netzwerkrouten, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093123"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Erstellen von regionenübergreifenden Netzwerkrouten in Skype for Business Server
 
Erstellen oder Ändern von überregionalen Netzwerkrouten, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden. 
  
Eine überregionale Netzwerkroute definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Der Bereitstellung der Anrufsteuerung ist eine überregionale Netzwerkroute erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.
  
Während regionsverknüpfungen Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen, bestimmt eine interregionale Route, welchen verknüpften Pfad die Verbindung von einer Region zu einer anderen durchquert.
  
In der Beispieltopologie müssen interregionale Netzwerkrouten für jedes der drei Regionspaare definiert werden: Nordamerika/EMEA, EMEA/APAC und Nordamerika/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie überregionale Netzwerkrouten mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
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
    > Für die interregionale Nord-Amerika-APAC-Netzwerkroute sind zwei Netzwerkregionsverbindungen erforderlich, da keine direkte Netzwerkregionsverbindung besteht. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie überregionale Netzwerkrouten mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite Neue **Regionsroute** auf **Name,** und geben Sie dann einen Namen für die überregionale Netzwerkroute ein.
    
6. Klicken Sie auf **Netzwerkregion 1** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 2 erstellt werden soll.
    
7. Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 1 erstellt werden soll.
    
8. Klicken **Sie** neben dem **Feld Netzwerkregionslinks** auf Hinzufügen, und fügen Sie dann eine Netzwerkregionsverbindung hinzu, die in der überregionalen Netzwerkroute verwendet wird.
    
    > [!NOTE]
    > Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Beispielsweise erfordert die interregionale Netzwerkroute Nordamerika/APAC zwei Netzwerkregionsverbindungen, da keine direkte Netzwerkregionsverbindung besteht. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere überregionale Netzwerkrouten, um das Erstellen von überregionalen Netzwerkrouten für Ihre Topologie zu beenden.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)