---
title: Überprüfen von Topologieinformationen
TOCTitle: Überprüfen von Topologieinformationen
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205151(v=OCS.15)
ms:contentKeyID: 49295041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen von Topologieinformationen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Wenn Sie sicherstellen möchten, dass die Zusammenführung erfolgreich abgeschlossen wurde, besteht der erste Schritt darin, die Topologieinformationen für Office Communications Server 2007 R2 anzuzeigen, die Sie mit Lync Server 2013 zusammengeführt haben. Im Topologie-Generator zeigt der Knoten **BackCompatSite** den vollqualifizierten Domänennamen (FQDN) jedes zusammengeführten Office Communications Server 2007 R2-Pools und -Servers an.

## So zeigen Sie den Knoten "BackCompatSite" im Topologie-Generator an

1.  Öffnen Sie in der Office Communications Server 2007 R2-Umgebung das Office Communications Server 2007 R2-Verwaltungstool, und notieren Sie die FQDNs der Legacypools und -server.

2.  Öffnen Sie in der Lync Server 2013-Umgebung den Topologie-Generator, und erweitern Sie dann den Knoten **BackCompatSite** .

3.  Stellen Sie sicher, dass die FQDNs für die zusammenzuführenden Pools und Server angezeigt werden.
    

    > [!NOTE]
    > Unter <STRONG>BackCompatSite</STRONG> werden keine Informationen für Serverrollen angezeigt, die mit einem Front-End-Server oder Standard Edition-Server verbunden sind. Es werden nur die Serverrollen angezeigt, die für die Interoperabilität zwischen Office Communications Server 2007 R2 und Lync Server 2013 erforderlich sind.



![Topologie-Generator: BackCompatSite (Dialogfeld)](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topologie-Generator: BackCompatSite (Dialogfeld)")

Sie können auch die Systemsteuerung für Lync Server 2013 verwenden, um die zusammengeführte Topologie anzuzeigen. In der Systemsteuerung für Lync Server 2013 werden alle Server-FQDNs, Pool-FQDNs und Standortnamen für die zusammengeführte Topologie angezeigt. Zusammengeführte Server haben den **Standort** namen **BackCompatSite** .

## So zeigen Sie die zusammengeführte Topologie in der Systemsteuerung für Lync Server 2013 an

1.  Öffnen Sie die Systemsteuerung für Lync Server 2013.

2.  Klicken Sie auf **Topologie** .

3.  Stellen Sie auf der Registerkarte **Status** sicher, dass die zusammengeführten Pools und Server angezeigt werden, indem Sie in der Spalte **Standort** nach **BackCompatSite** suchen.

![Lync Server-Systemsteuerung mit zusammengeführter Topologie](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server-Systemsteuerung mit zusammengeführter Topologie")

Wenn Sie weitere Einzelheiten zu einem zusammengeführten Pool anzeigen möchten, verwenden Sie das Cmdlet **Get-CsPool** . Zusätzlich zu den Informationen, die im Topologie-Generator und in der Systemsteuerung für Lync Server 2013 verfügbar sind, zeigt dieses Cmdlet die Dienste an, die im Lync Server 2013-Pool ausgeführt werden.


> [!NOTE]
> Wenn Sie die Topologie nach dem Ausführen des Zusammenführungs-Assistenten im Topologie-Generator veröffentlichen, werden Konferenzverzeichnisse mit Lync Server 2013 zusammengeführt. Konferenzverzeichnisse können Sie überprüfen, indem Sie das Cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> ausführen.



## So zeigen Sie Dienste in einem zusammengeführten Pool an

1.  Öffnen Sie die Verwaltungsshell für Lync Server 2013.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Beispiel:
    
        Get-CsPool -Identity pool02.contoso.net

## So überprüfen Sie zusammengeführte Konferenzverzeichnisse

1.  Öffnen Sie die Verwaltungsshell für Lync Server 2013.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsConferenceDirectory

3.  Stellen Sie sicher, dass alle Konferenzverzeichnisse für den Pool oder Server, den Sie zusammenführen, jetzt in Lync Server 2013 vorhanden sind.

