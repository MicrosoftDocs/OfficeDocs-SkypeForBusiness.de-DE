---
title: 'Lync Server 2013: Installieren von Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce694fe34451d6465f1fff31119ecf40c13e82d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Installieren von Windows PowerShell 3,0 für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-27_

Um lync Server 2013 erfolgreich bereitzustellen, benötigen Sie Windows PowerShell 3,0 auf jedem Computer, der Teil ihrer lync Server Topologie ist.

Für Systeme, die Windows Server 2012 oder Windows Server 2012 R2 ausführen, müssen Sie jetzt nichts mehr tun und können zur nächsten Bereitstellungsphase übergehen, da PowerShell 3,0 in diesen Betriebssystemen enthalten ist.

<div>


> [!IMPORTANT]  
> Für Systeme, die Windows Server 2008 R2 SP1 ausführen, müssen Sie jedoch PowerShell 3,0 als Voraussetzung installieren, bevor Sie lync Server 2013 installieren, oder es funktioniert nicht. Informationen zum Installieren von PowerShell 3,0 finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Dies ist ein direkter Link zur PowerShell 3,0-Download Seite sowie Informationen zur erfolgreichen Installation.



</div>

Wenn Sie die Installation abgeschlossen haben oder nur überprüfen möchten, bevor Sie mit der lync Server-Bereitstellung fortfahren, ist es ziemlich einfach, sich zu vergewissern, dass sich PowerShell 3,0 auf einem Server befindet:

1.  Wählen Sie auf dem Server, den Sie überprüfen möchten, **Start**aus, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie auf **Windows PowerShell**, und klicken Sie dann auf **Windows PowerShell**.

2.  Geben Sie in der Windows PowerShell Konsole den folgenden Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
    
        Get-Host | Select-Object Version

3.  Wenn Windows PowerShell 3,0 installiert ist, sehen Sie die Ausgabe wie folgt aus:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

