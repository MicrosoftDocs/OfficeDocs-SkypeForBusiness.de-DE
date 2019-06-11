---
title: 'Lync Server 2013: Notfallwiederherstellungstest'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Notfallwiederherstellungstest in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-01-26_

Führen Sie eine Systemwiederherstellung für einen lync Server 2013-Pool Server aus, um Ihren dokumentierten Disaster Recovery-Prozess zu testen. Mit diesem Test wird ein vollständiger Hardwarefehler für einen Server simuliert, und es wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung verfügbar sind. Versuchen Sie, den Fokus des Tests monatlich zu drehen, damit Ihre Organisation den Fehler eines anderen Servers oder eines anderen Geräts jedes Mal testet.

Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder vernachlässigt werden.

<div>


Exportieren Sie Ihre lync Server 2013-Topologie,-Richtlinien und-Konfigurationseinstellungen in eine Datei. Unter anderem kann diese Datei nach einem Upgrade, einem Hardwareausfall oder einem anderen Problem, das zu Datenverlust geführt hat, zum Wiederherstellen dieser Informationen im zentralen Verwaltungsspeicher verwendet werden.

Importieren Sie Ihre lync Server 2013-Topologie,-Richtlinien und-Konfigurationseinstellungen entweder in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen gezeigt:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

So sichern Sie Production lync Server 2013-Daten:

  - Sichern Sie die RTC-und LCSLog-Datenbanken mithilfe des standardmäßigen SQL Server-Sicherungsprozesses, um die Datenbank auf ein Datei-oder Bandspeicher Abbildgerät zu übernehmen.

  - Verwenden Sie eine Sicherungsanwendung von einem Drittanbieter, um die Daten in einer Datei oder auf einem Band zu sichern.

  - Verwenden Sie das Cmdlet „Export-CsUserData“, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.

  - Verwenden Sie die Dateisystemsicherung oder eine Drittanbieteranwendung, um Besprechungsinhalte und -kompatibilitätsprotokolle zu sichern.

  - Verwenden Sie das Befehlszeilentool "Exportieren-CsConfiguration", um die lync Server 2013-Einstellungen zu sichern.

Der erste Schritt in der Failoverprozedur besteht in einer erzwungenen Verschiebung von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool.

Es handelt sich dabei um eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerumsetzung zu akzeptieren.

Der lync Server 2013 Move-Benutzerprozess ist eine Änderung an einem Attribut für das Benutzerkontoobjekt sowie eine Datensatzaktualisierung in der RTC SQL-Datenbank.

Diese Daten können mithilfe der folgenden zwei Prozesse wiederhergestellt werden:

  - Die RTC-Datenbank kann vom ursprünglichen Sicherungsspeicher Abbild-Gerät aus dem Produktions-SQL Server mithilfe des Standard Wiederherstellungsprozesses von SQL Server oder mithilfe eines Sicherungs-/Wiederherstellungstools eines Drittanbieters wiederhergestellt werden.

  - Benutzerkontaktdaten können mit dem Hilfsprogramm DBIMPEXP.exe über die aus dem SQL Server-Produktionsexport erstellte XML-Datei wiederhergestellt werden.

Nach der Wiederherstellung dieser Daten können Benutzer eine Verbindung mit dem Disaster Recovery lync Server 2013-Pool herstellen und wie gewohnt funktionieren.

Damit Benutzer eine Verbindung mit dem Disaster Recovery lync Server 2013-Pool herstellen können, ist eine Änderung des DNS-Eintrags erforderlich.

Clients, die die automatischen Konfigurations-und DNS-SRV-Einträge verwenden, werden auf den lync Server 2013-Produktionspool verwiesen:

  - SRV: \_SIP. \_TLS. \<Domäne\> /CNAME: SIP. \<Domäne\>

  - CNAME: SIP. \<Domänen\> /CVC-Pool-1. \<Domäne\>

Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den DROCSPool-FQDN verweist:

  - CNAME: SIP. \<Domänen\> /DROCSPool. \<Domäne\>

  - SIP. \<Domäne\>

  - AV.\<Domain\>

  - webconf. \<Domäne\>

  - OCSServices. \<Domäne\>

<div>


> [!IMPORTANT]  
> Detaillierte Verwaltungs-und Verwaltungsverfahren finden Sie unter <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Sichern und Wiederherstellen von lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets für Backup und höhere Verfügbarkeit in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Importieren-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Sichern und Wiederherstellen von lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts in Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

