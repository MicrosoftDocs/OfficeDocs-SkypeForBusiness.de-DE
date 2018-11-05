---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
TOCTitle: Veröffentlichen der Topologie
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425880(v=OCS.15)
ms:contentKeyID: 49293732
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen der Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-01_

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Administratorrechte und -berechtigungen zu delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

Nachdem Sie Ihre Topologie im Topologie-Generator definiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen. Mit dem zentralen Verwaltungsspeicher erzielen Sie eine zuverlässige, schematisierte Speicherung der Daten, die zum Definieren, Einrichten, Warten, Verwalten, Beschreiben und zum Betrieb einer Lync Server 2013-Bereitstellung benötigt werden. Darüber hinaus werden die Daten überprüft, zur Sicherstellung einer konsistente Konfiguration beizutragen. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch Synchronisierungsprobleme beseitigt werden. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen.


> [!NOTE]
> SQL Server benötigt mindestens 20 GB freien Festplattenspeicher, damit die anfängliche Topologie erfolgreich veröffentlicht werden kann und um den zentralen Verwaltungsserver zu erstellen.




> [!NOTE]
> Nur Enterprise Edition: Zum Veröffentlichen der Topologie muss der SQL&nbsp;Server-basierte Back-End-Server online und über die eingerichteten Firewallausnahmen erreichbar sein. Ausführliche Informationen zum Festlegen von Firewallausnahmen finden Sie unter <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Grundlegendes zu den Firewallanforderungen für SQL&nbsp;Server mit Lync Server 2013</A>. Ausführliche Informationen zum Konfigurieren von SQL&nbsp;Server finden Sie unter <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Konfigurieren von SQL&nbsp;Server für Lync Server&nbsp;2013</A>.



## So veröffentlichen Sie eine Topologie

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Öffnen Sie die Topologie aus einer lokalen Datei. Wenn Sie an dem Computer arbeiten, an dem Sie die Topologie definiert haben, ist dies der Speicherort, an dem Sie die Datei zuvor gespeichert haben. In der Regel ist dies der Ordner "Dokumente" des Benutzers, der die Topologie konfiguriert hat.

3.  Klicken Sie mit der rechten Maustaste auf den Knoten **Lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen** .

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter** .

5.  Wählen Sie auf der Seite **Datenbanken erstellen** die Datenbanken, die Sie veröffentlichen möchten.
    

    > [!NOTE]
    > Wenn Sie nicht die geeigneten Rechte zum Erstellen der Datenbanken besitzen, können Sie die Kontrollkästchen neben diesen Datenbanken deaktivieren. Ein anderer Benutzer mit geeigneten Rechten kann die Datenbanken später erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in Lync Server 2013</A>.



6.  Klicken Sie optional auf **Erweitert** . Es stehen die folgende erweiterten Optionen zur Platzierung von SQL Server-Datendateien zur Verfügung:
    
      - **Speicherort für Datenbankdateien automatisch bestimmen** - Bei Auswahl dieser Option wird optimale Leistung basierend auf der Festplattenkonfiguration für Ihren SQL Server-basierten Server gewährleistet, indem die Protokoll- und Datendateien verteilt platziert werden.
    
      - **Standardpfade der SQL Server-Instanz verwenden** - Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK** und dann auf **Weiter** .

7.  Wählen Sie auf der Seite **Zentralen Verwaltungsserver auswählen** einen Front-End-Pool aus.

8.  Klicken Sie optional auf **Erweitert** . Es stehen die folgende erweiterten Optionen zur Platzierung von SQL Server-Datendateien zur Verfügung:
    
      - **Speicherort für Datenbankdateien automatisch bestimmen** - Bei Auswahl dieser Option wird optimale Leistung basierend auf der Festplattenkonfiguration für Ihren SQL Server-basierten Server gewährleistet, indem die Protokoll- und Datendateien verteilt platziert werden.
    
      - **Standardpfade der SQL Server-Instanz verwenden** - Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK** .

9.  Klicken Sie auf **Weiter** , um die Veröffentlichung abzuschließen.

10. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen** .
    
    Nach dem erfolgreichen Veröffentlichen der Topologie können Sie damit beginnen, ein lokales Replikat vom zentralen Verwaltungsspeicher auf jedem Server in Ihrer Topologie zu installieren, auf dem Lync Server 2013 ausgeführt wird. Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen.

## Siehe auch

#### Weitere Ressourcen

[Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)

