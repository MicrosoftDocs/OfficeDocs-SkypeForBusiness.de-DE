---
title: Erstellen regionenübergreifenden Netzwerkrouten in Skype for Business Server
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
description: Erstellen oder ändern Sie regionenübergreifenden Netzwerkrouten, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822495"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Erstellen regionenübergreifenden Netzwerkrouten in Skype for Business Server
 
Erstellen oder ändern Sie regionenübergreifenden Netzwerkrouten, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden. 
  
Eine regionenübergreifenden Netzwerkroute definiert die Route zwischen zwei Netzwerkregionen. Jedes Netzwerkregionenpaar in Ihrer Bereitstellung für die Anrufsteuerung erfordert eine regionenübergreifenden Netzwerkroute. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.
  
Während bei Regionenverbindungen Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festgelegt werden, bestimmt eine regionenübergreifenden Route, welchen Verbindungspfad die Verbindung von einer Region zu einer anderen durchquert.
  
In der Beispieltopologie müssen regionenübergreifenden Netzwerkrouten für jedes der drei Regionenpaare definiert werden: Nordamerika/EMEA, EMEA/APAC und Nordamerika/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie regionenübergreifenden Netzwerkrouten mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
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
    > Für die regionenübergreifenden Netzwerkroute "Nordamerika/APAC" sind zwei Netzwerkregionsverbindungen erforderlich, da keine direkte Netzwerkregionsverbindung besteht. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie regionenübergreifenden Netzwerkrouten mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.
    
4. Klicken Sie auf **Neu**.
    
5. Klicken Sie **auf der Seite "Neue Regionenroute"** auf **"Name",** und geben Sie einen Namen für die regionenübergreifenden Netzwerkroute ein.
    
6. Klicken Sie auf **Netzwerkregion 1** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 2 erstellt werden soll.
    
7. Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 1 erstellt werden soll.
    
8. Klicken **Sie neben** dem Feld **"Netzwerkregionsverbindungen"** auf "Hinzufügen", und fügen Sie dann eine Netzwerkregionsverbindung hinzu, die in der regionenübergreifenden Netzwerkroute verwendet wird.
    
    > [!NOTE]
    > Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Die regionenübergreifenden Netzwerkroute "Nordamerika/APAC" erfordert beispielsweise zwei Netzwerkregionsverbindungen, da keine direkte Netzwerkregionsverbindung besteht. 
  
9. Klicken Sie auf **Commit ausführen**.
    
10. Um die Erstellung von regionenübergreifenden Netzwerkrouten für Ihre Topologie fertig zu stellen, wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere regionenübergreifenden Netzwerkrouten.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
