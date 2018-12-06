---
title: 'Lync Server 2013: Notfallwiederherstellungstest'
TOCTitle: Notfallwiederherstellungstest
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn747887(v=OCS.15)
ms:contentKeyID: 62293613
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Notfallwiederherstellungstest in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-01-26_

Führen Sie eine Systemwiederherstellung für einen Lync Server 2013-Poolserver durch, um Ihren dokumentierten Notfallwiederherstellungsprozess zu testen. Bei diesem Test wird ein vollständiger Hardwareausfall für einen Server simuliert. Der Test hilft sicherzustellen, dass die Ressourcen, Pläne und Daten zur Wiederherstellung verfügbar sind. Versuchen Sie, den Schwerpunkt des Tests monatlich zu rotieren, damit Ihre Organisation jedes Mal den Ausfall eines anderen Servers oder anderer Komponenten testet.

Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder vernachlässigt werden.


Exportieren Sie Ihre Lync Server 2013-Topologie, -Richtlinien und -Konfigurationseinstellungen in eine Datei. Unter anderem kann diese Datei nach einem Upgrade, einem Hardwareausfall oder einem anderen Problem, das zu Datenverlust geführt hat, zum Wiederherstellen dieser Informationen im zentralen Verwaltungsspeicher verwendet werden.

Importieren Sie Ihre Lync Server 2013-Topologie, -Richtlinien und -Konfigurationseinstellungen entweder in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen gezeigt:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

So sichern Sie Lync Server 2013-Produktionsdaten:

  - Sichern Sie die RTC- und LCSLog-Datenbanken mithilfe des SQL Server-Standardsicherungsprozesses, um die Datenbank in einer Datei oder auf einem Bandsicherungsgerät zu sichern.

  - Verwenden Sie eine Sicherungsanwendung von einem Drittanbieter, um die Daten in einer Datei oder auf einem Band zu sichern.

  - Verwenden Sie das Cmdlet „Export-CsUserData“, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.

  - Verwenden Sie die Dateisystemsicherung oder eine Drittanbieteranwendung, um Besprechungsinhalte und -kompatibilitätsprotokolle zu sichern.

  - Verwenden Sie das Befehlszeilentool „Export-CsConfiguration“, um Lync Server 2013-Einstellungen zu sichern.

Der erste Schritt in der Failoverprozedur besteht in einer erzwungenen Verschiebung von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool.

Es handelt sich dabei um eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerumsetzung zu akzeptieren.

Der Lync Server 2013-Prozess zum Verschieben von Benutzern besteht im Wesentlichen darin, ein Attribut für das Benutzerkontoobjekt zu ändern und einen Eintrag in der RTC-SQL-Datenbank zu aktualisieren.

Diese Daten können mithilfe der folgenden zwei Prozesse wiederhergestellt werden:

  - Die RTC-Datenbank kann vom ursprünglichen Sicherungsgerät vom Produktions-SQL Server über den SQL Server-Standardwiederherstellungsprozess oder ein Hilfsprogramm für die Sicherung/Wiederherstellung eines Drittanbieters wiederhergestellt werden.

  - Benutzerkontaktdaten können mit dem Hilfsprogramm DBIMPEXP.exe über die aus dem SQL Server-Produktionsexport erstellte XML-Datei wiederhergestellt werden.

Nachdem diese Daten wiederhergestellt wurden, können Benutzer erfolgreich eine Verbindung zum Lync Server 2013-Notfallwiederherstellungspool herstellen und wie gewohnt arbeiten.

Damit Benutzer eine Verbindung zum Lync Server 2013-Notfallwiederherstellungspool herstellen können, ist die Änderung eines DNS-Eintrags erforderlich.

Clients verweisen auf den Lync Server 2013-Produktionspool über die Einträge für die automatische Konfiguration und DNS-SRV-Einträge von:

  - SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\>

  - CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\>

Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den DROCSPool-FQDN verweist:

  - CNAME: SIP.\<domain\> /DROCSPool.\<domain\>

  - Sip.\<domain\>

  - AV.\<domain\>

  - webconf.\<domain\>

  - OCSServices.\<domain\>


> [!IMPORTANT]
> Ausführliche Administrations- und Verwaltungsverfahren finden Sie unter <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Sichern und Wiederherstellen von Lync Server&nbsp;2013</A>.



## Siehe auch

#### Konzepte

[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets für Sicherung und hohe Verfügbarkeit](https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps)  

#### Weitere Ressourcen

[Import-CsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsConfiguration)  
[Sichern und Wiederherstellen von Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts in Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)

