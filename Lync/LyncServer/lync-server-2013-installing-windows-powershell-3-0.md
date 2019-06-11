---
title: 'Lync Server 2013: Installieren von Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Installieren von Windows PowerShell 3.0 für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-27_

Damit Sie lync Server 2013 erfolgreich bereitstellen können, benötigen Sie Windows PowerShell 3,0 auf jedem Computer, der Teil ihrer lync Server-Topologie ist.

Bei Systemen, auf denen Windows Server 2012 oder Windows Server 2012 R2 ausgeführt wird, müssen Sie jetzt nichts tun, und Sie können den nächsten Bereitstellungsschritt fortführen, da PowerShell 3,0 in diesen Betriebssystemen enthalten ist.

<div>


> [!IMPORTANT]  
> Bei Systemen, auf denen Windows Server 2008 R2 SP1 ausgeführt wird, müssen Sie jedoch PowerShell 3,0 als Voraussetzung installieren, bevor Sie lync Server 2013 installieren, oder es funktioniert nicht. Informationen zum Installieren von PowerShell 3,0 finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Hierbei handelt es sich um einen direkten Link zur PowerShell 3,0-Download Seite sowie Informationen zur erfolgreichen Installation.



</div>

Nachdem Sie die Installation abgeschlossen haben, oder wenn Sie nur überprüfen möchten, bevor Sie mit der lync Server-Bereitstellung fortfahren, können Sie sicherstellen, dass sich PowerShell 3,0 auf einem Server befindet, wenn Sie Folgendes tun:

1.  Wählen Sie auf dem Server, den Sie überprüfen möchten, **Start**aus, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie auf **Windows PowerShell**, und klicken Sie dann auf **Windows PowerShell**.

2.  Geben Sie in der Windows PowerShell-Konsole an der Eingabeaufforderung den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-Host | Select-Object Version

3.  Wenn Windows PowerShell 3,0 installiert ist, wird die Ausgabe wie folgt angezeigt:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

