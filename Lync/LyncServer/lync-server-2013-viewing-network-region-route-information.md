---
title: 'Lync Server 2013: Anzeigen von Informationen zur Netzwerk Regions Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6acf4fbc1766adbe2c2a14a28cfbeef16f199b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Anzeigen von Routeninformationen für netzwerkregionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Verwenden Sie die folgenden Verfahren, um die vorhandenen Netzwerk Regions Routen in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell anzuzeigen. Ausführliche Informationen zum Erstellen oder Ändern von Netzwerk Regions Routen finden Sie unter [erstellen oder Ändern von Netzwerk Regions Routen in lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>So zeigen Sie Netzwerk Regions-Routeninformationen in lync Server-Systemsteuerung an

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionsroute**.

4.  Klicken Sie auf der Seite **Regionsroute** auf die Regionsroute, die Sie anzeigen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können nur jeweils eine Regionsroute anzeigen.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Routeninformationen für netzwerkregionen mithilfe von Windows PowerShell-Cmdlets

Informationen zur Netzwerk Regions Route können mit Windows PowerShell und dem Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-view-network-region-route-information"></a>So zeigen Sie Netzwerk Regions-Routeninformationen an

  - Geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Routen ihrer netzwerkregion anzuzeigen:
    
        Get-CsNetworkInterRegionRoute
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von Netzwerk Regions Routen in lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Löschen vorhandener Netzwerk Regions Routen in lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

