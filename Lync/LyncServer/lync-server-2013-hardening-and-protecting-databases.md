---
title: 'Lync Server 2013: Sichern und Schützen der Datenbanken'
TOCTitle: Sichern und Schützen der Datenbanken von Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518330(v=OCS.15)
ms:contentKeyID: 60476345
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sichern und Schützen der Datenbanken von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2013 nutzt außerdem SQL Server-Datenbanken zum Speichern von Benutzerdaten, Konferenzstatus, Archivierungsdaten und Kommunikationsdatensätzen (KDS). Sie können die Verfügbarkeit von Lync Server 2013-Daten in Lync Server-Back-End-Datenbanken erhöhen, indem Sie die Anwendungsdaten so partitionieren, dass eine bessere Fehlertoleranz und eine einfachere Problembehandlung ermöglicht wird. Partitionieren Sie die Anwendungsdaten wie folgt, um diese Ziele zu erreichen:

  - **Verwenden der bewährten Methoden für die Serverpartitionierung**   Speichern Sie das Betriebssystem sowie Anwendungen und Programmdateien getrennt von den Datendateien.

  - **Speichern von Transaktionsprotokolldateien und Datenbankdateien**   Speichern Sie diese Dateien zur Verbesserung der Fehlertoleranz und zur Optimierung der Wiederherstellung getrennt voneinander und speichern Sie sie auf einem verschlüsselten Datenträger oder Volume.

  - **Verwenden von Serverclustering**   Bilden Sie zur Optimierung der Verfügbarkeit des Lync Server 2013-Systems Back-End-Servercluster.

  - **Sicherstellen, dass alle Datensicherungen verschlüsselt sind und ordnungsgemäß gehandhabt werden**   Verlorene, gelöschte oder falsch platzierte Sicherungsmedien können eine erhebliche Gefährdung der Datensicherheit in Lync Server 2013-Bereitstellungen darstellen.

Der Remotezugriff auf die SQL Server Express-Instanz (RTCLOCAL-Instanz) ist auf keinem Lync Server 2013-Server außer dem Standard Edition-Server möglich und es werden keine lokalen Firewallausnahmen erstellt, außer auf einem Standard Edition-Server für SQL Server Express. Auf einem Standard Edition-Server sind sowohl die Back-End-Datenbank als auch der Verwaltungsspeicher (CMS) für den Remotezugriff eingerichtet. Zum Verstärken der Sicherheit von SQL Server-Datenbanken haben Sie folgende Möglichkeiten:

  - Passen Sie die SQL Server Express-Firewall auf Standard Edition-Servern an und beschränken Sie dabei den Bereich der Server, die Remotezugriff auf die Datenbank haben. Standardmäßig kann jede IP-Adresse remote auf die Datenbank zugreifen.

  - Verwenden Sie den SQL Server-Konfigurations-Manager, um die Protokolle, IP-Adressen und Ports für den SQL-Remotezugriff anzugeben:
    
      - Lync Server 2013 verwendet das TCP/IP-Protokoll. Es unterstützt IP Version 4 (IPv4), aber nicht IP Version 6 (IPv6).
        

        > [!NOTE]
        > Lync Server 2013 kann in einem Netzwerk mit aktiviertem dualem&nbsp;IP-Stapel funktionieren.

    
      - Lync Server 2013 unterstützt mehrere IP-Adressen (Multihoming-Netzwerkadresskarten). Sie können festlegen, dass SQL Server nur bestimmte IP-Adressen überwacht (einzelne Adressen oder per Subnetz) und nur bestimmte Protokolle verwendet.
    
      - Lync Server 2013 unterstützt statische und dynamische SQL Server-Ports.

  - Führen Sie SQL Server auf einem statischen Port (nicht dem Standardport) aus und führen Sie nicht den SQL Server-Browser aus (damit der Überwachungsport nicht an den Client übermittelt wird). Dies erfordert eine benutzerdefinierte Konfiguration auf jedem SQL Server-Client, einschließlich Front-End-Server, Monitoring Server, Archivierungsserver und Verwaltungskonsolen (auf denen die Lync Server-Verwaltungsshell, die Lync Server-Systemsteuerung oder der Topologie-Generator ausgeführt wird) sowie alle anderen Server, auf denen Lync Server-Datenbanken ausgeführt werden).


> [!NOTE]
> Der Zugriff auf Datenbanken muss auf vertrauenswürdige Datenbankadministratoren beschränkt sein. Ein bösartiger Datenbankadministrator könnte Daten in die Datenbanken einfügen oder sie verändern, um Rechte über die Lync Server 2013-Server zu erlangen oder vertrauliche Informationen von den Diensten zu erhalten, auch wenn dem Datenbankadministrator kein direkter Zugriff auf bzw. keine Steuerung der Lync Server 2013-Server übertragen wurde.



Ausführliche Informationen zu benutzerdefinierten Konfigurationen und zum Schützen von SQL Server-Datenbanken finden Sie im NextHop-Blog-Artikel zur Verwendung von Lync Server 2010 mit benutzerdefinierter SQL Server-Netzwerkkonfiguration unter [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).


> [!NOTE]
> Sie können auch Betriebssysteme und Anwendungsserver schützen sowie Gruppenrichtlinien zum Implementieren von Sicherheitssperren in Ihrer Lync Server-Bereitstellung verwenden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Sichern und Schützen von Servern und Anwendungen für Lync Server 2013</A>.


