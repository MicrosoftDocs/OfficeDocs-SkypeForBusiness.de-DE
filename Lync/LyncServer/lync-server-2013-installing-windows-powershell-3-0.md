---
title: 'Lync Server 2013: Installieren von Windows PowerShell 3.0'
TOCTitle: Installieren von Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205328(v=OCS.15)
ms:contentKeyID: 49295576
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Windows PowerShell 3.0 für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für eine erfolgreiche Bereitstellung von Lync Server 2013 benötigen Sie Windows PowerShell 3.0 auf jedem Computer innerhalb der Lync Server-Topologie.

Bei Systemen unter Windows Server 2012 oder Windows Server 2012 R2 brauchen Sie hier also nichts zu unternehmen und können direkt mit der nächsten Stufe der Bereitstellung fortfahren, da PowerShell 3.0 in diesen Betriebssystemen bereits enthalten ist.


> [!IMPORTANT]
> Bei Windows Server 2008 R2 SP1-Systemen ist es jedoch zwingend erforderlich, zuerst PowerShell 3.0 zu installieren, bevor Sie Lync Server 2013 installieren. Informationen zur Installation von PowerShell 3.0 finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>. Diese Seite enthält einen direkten Link zur Downloadseite von PowerShell 3.0 sowie eine Installationsanleitung.



Nachdem Sie die Installation ausgeführt haben oder wenn Sie einfach nur sichergehen möchten, bevor Sie mit der Bereitstellung von Lync Server fortfahren, ist es recht einfach zu überprüfen, ob sich PowerShell 3.0 auf einem Server befindet:

1.  Klicken Sie auf dem Server auf **Start**, dann auf **Alle Programm**, **Zubehör**, **Windows PowerShell** und dann auf **Windows PowerShell**.

2.  Geben Sie in der Windows PowerShell-Konsole den folgenden Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
    
        Get-Host | Select-Object Version

3.  Falls Windows PowerShell 3.0 installiert ist, wird die folgende Ausgabe angezeigt:
    
        Version
        -------
        3.0

