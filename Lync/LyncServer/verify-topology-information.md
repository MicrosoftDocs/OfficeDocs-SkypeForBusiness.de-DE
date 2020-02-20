---
title: Überprüfen der Topologieinformationen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69add03365fa55ba3b08ac4c6b7a1dd60a6294f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Überprüfen der Topologieinformationen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Der erste Schritt bei der Überprüfung der erfolgreichen Zusammenführung besteht darin, die Informationen Office Communications Server 2007 R2 Topologie anzuzeigen, die Sie mit lync Server 2013 zusammengeführt haben. Im Topologie-Generator zeigt der Knoten **BackCompatSite** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aller Office Communications Server 2007 R2 Pools und Server an, die Sie zusammengeführt haben.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>So zeigen Sie den Knoten "BackCompatSite" im Topologie-Generator an

1.  Öffnen Sie in Ihrer Office Communications Server 2007 R2 Umgebung das Verwaltungstool Office Communications Server 2007 R2, und notieren Sie sich die FQDNs der Legacy Pools und-Server.

2.  Öffnen Sie in ihrer lync Server 2013 Umgebung den Topologie-Generator, und erweitern Sie dann den Knoten **BackCompatSite** .

3.  Stellen Sie sicher, dass die FQDNs für die zusammenzuführenden Pools und Server angezeigt werden.
    
    <div>
    

    > [!NOTE]  
    > Unter <STRONG>BackCompatSite</STRONG> werden keine Informationen für Serverrollen angezeigt, die mit einem Front-End-Server oder Standard Edition-Server verbunden sind. Es werden nur Serverrollen angezeigt, die für die Interoperabilität zwischen Office Communications Server 2007 R2 und lync Server 2013 erforderlich sind.

    
    </div>

![Dialogfeld "Topologie-Generator BackCompatSite"](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Dialogfeld "Topologie-Generator BackCompatSite"")

Sie können auch lync Server 2013-Systemsteuerung verwenden, um die zusammengeführte Topologie anzuzeigen. In lync Server 2013 Systemsteuerung werden die einzelnen Server-FQDN, der Pool-FQDN und der Websitename für die zusammengeführte Topologie angezeigt. Zusammengeführte Server haben den **Standort**namen **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>So zeigen Sie die zusammengeführte Topologie in lync Server 2013 Systemsteuerung an

1.  Öffnen Sie lync Server 2013 Systemsteuerung.

2.  Klicken Sie auf **Topologie**.

3.  Stellen Sie auf der Registerkarte **Status** sicher, dass die zusammengeführten Pools und Server angezeigt werden, indem Sie in der Spalte **Standort** nach **BackCompatSite** suchen.

![Lync Server-Systemsteuerung anzeigen der zusammengeführten Topologie](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server-Systemsteuerung anzeigen der zusammengeführten Topologie")

Wenn Sie weitere Einzelheiten zu einem zusammengeführten Pool anzeigen möchten, verwenden Sie das Cmdlet **Get-CsPool**. Zusätzlich zu den Informationen, die im Topologie-Generator und in lync Server 2013 Systemsteuerung zur Verfügung stehen, zeigt dieses Cmdlet die Dienste an, die im lync Server 2013-Pool ausgeführt werden.

<div>


> [!NOTE]  
> Wenn Sie die Topologie nach dem Ausführen des Merge-Assistenten im Topologie-Generator veröffentlichen, werden die Konferenzverzeichnisse mit lync Server 2013 zusammengeführt. Konferenzverzeichnisse können Sie überprüfen, indem Sie das Cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> ausführen.



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>So zeigen Sie Dienste in einem zusammengeführten Pool an

1.  Öffnen Sie die lync Server 2013 Management-Shell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Beispiel:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>So überprüfen Sie zusammengeführte Konferenzverzeichnisse

1.  Öffnen Sie die lync Server 2013 Management-Shell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsConferenceDirectory

3.  Stellen Sie sicher, dass sich alle Konferenzverzeichnisse für den Pool oder Server, den Sie zusammenführen, jetzt in lync Server 2013 befinden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

