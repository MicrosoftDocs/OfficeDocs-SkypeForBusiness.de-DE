---
title: Lync Server 2013; Erstellen von Netzwerk interregions-Routen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 3909c41328e18302ef1104ac05d9a7c7987f57d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Erstellen von Netzwerk interregions-Routen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Eine *Netzwerk-interregions-Route* definiert die Route zwischen zwei netzwerkregionen. Für jedes Paar von netzwerkregionen in der Bereitstellung für die Anrufsteuerung ist eine Netzwerk-interregions-Route erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.

Während die Region Links Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegt, bestimmt eine interregions Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einem anderen durchlaufen wird.

Details zum Arbeiten mit Netzwerk interregions-Routen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

In der Beispieltopologie müssen Netzwerk interregions-Routen für jedes der drei Regions Paare definiert werden: Nordamerika/EMEA, EMEA/APAC und Nordamerika/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>So erstellen Sie Netzwerk interregions-Routen mithilfe der lync Server-Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkInterRegionRoute** aus, um die erforderlichen Routen zu definieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Für die Route Nordamerika/APAC-Netzwerk Interregion sind zwei Netzwerk Regions Verknüpfungen erforderlich, da zwischen Ihnen keine direkte Netzwerk Regions Verbindung besteht.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>So erstellen Sie Netzwerk interregions-Routen mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **neue Regions Route** auf **Name** , und geben Sie dann einen Namen für die Route des Netzwerk interregions ein.

6.  Klicken Sie auf **netzwerkregion \#1**, und klicken Sie dann in der Liste auf einen Netzwerkbereich, den Sie an \#netzwerkregion 2 weiterleiten möchten.

7.  Klicken Sie auf **netzwerkregion \#2**, und klicken Sie dann in der Liste auf einen Netzwerkbereich, den Sie an \#netzwerkregion 1 weiterleiten möchten.

8.  Klicken Sie neben dem Feld **Netzwerk Regions Verknüpfungen** auf **Hinzufügen** , und fügen Sie dann einen Netzwerk Regions Link hinzu, der in der Netzwerk interregions-Route verwendet wird.
    
    <div class=" ">
    

    > [!NOTE]  
    > Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Beispielsweise erfordert die Route Nordamerika/APAC-Netzwerk Interregion zwei Netzwerk Regions Verknüpfungen, da zwischen Ihnen keine direkte Netzwerk Regions Verbindung besteht.

    
    </div>

9.  Klicken Sie auf **Commit ausführen**.

10. Um das Erstellen von Netzwerk interregions-Routen für Ihre Topologie abzuschließen, wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Netzwerk interregions-Routen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

