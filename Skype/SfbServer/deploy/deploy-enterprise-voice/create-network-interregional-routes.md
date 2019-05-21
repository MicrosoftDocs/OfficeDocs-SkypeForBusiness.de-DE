---
title: Erstellen interregionaler Netzwerkrouten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Erstellen oder ändern Sie Netzwerk interregionale Routen, die von der Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: aec289143e2b6dd54e2b52cfc231239fe5d73b7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286369"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Erstellen interregionaler Netzwerkrouten in Skype for Business Server
 
Erstellen oder ändern Sie Netzwerk interregionale Routen, die von der Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden. 
  
Eine regionenübergreifende Netzwerkroute definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine regionenübergreifende Netzwerkroute erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.
  
Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen, bestimmt eine regionenübergreifende Route, welchen Verknüpfungspfad die Verbindung von einer Region zur anderen nimmt.
  
In der Beispieltopologie müssen für jedes der drei Regionenpaare regionenübergreifende Netzwerkrouten definiert werden: „North America/EMEA“, „EMEA/APAC“ und „North America/APAC“. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie Netzwerk interregionale Routen mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das Cmdlet **New-CsNetworkInterRegionRoute** aus, um die erforderlichen Routen zu definieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > Für die regionenübergreifende Netzwerkroute „North America/APAC“ werden zwei Netzwerkregionenverbindungen benötigt, da zwischen diesen beiden Regionen keine direkte Netzwerkregionenverbindung vorhanden ist. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie Netzwerk interregionale Routen mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie auf der Seite **Neue Regionenroute** auf **Name** und geben Sie einen Namen für die regionenübergreifende Netzwerkroute ein.
    
6. Klicken Sie auf **Netzwerkregion 1** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 2 erstellt werden soll.
    
7. Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Verbindung zu Netzwerkregion 1 erstellt werden soll.
    
8. Klicken Sie neben dem Feld **Netzwerkregionenverbindungen** auf **Hinzufügen** und fügen Sie eine Netzwerkregionenverbindung hinzu, die in der regionenübergreifenden Netzwerkroute verwendet werden soll.
    
    > [!NOTE]
    > Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Für die regionenübergreifende Netzwerkroute „North America/APAC“ werden beispielsweise zwei Netzwerkregionenverbindungen benötigt, da zwischen diesen beiden Regionen keine direkte Netzwerkregionenverbindung vorhanden ist. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere regionenübergreifende Netzwerkrouten, um die Erstellung von regionenübergreifenden Netzwerkrouten für Ihre Topologie abzuschließen.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
