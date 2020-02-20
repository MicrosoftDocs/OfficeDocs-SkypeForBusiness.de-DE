---
title: 'Lync Server 2013: Notfall Wiederherstellungstest'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b9aa12f7b3ae9b0c160147ad473976c92ab32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Notfall Wiederherstellungstest in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-01-26_

Führen Sie eine Systemwiederherstellung für einen lync Server 2013 Pool Server aus, um Ihren dokumentierten Notfall Wiederherstellungsprozess zu testen. Bei diesem Test wird ein vollständiger Hardwarefehler für einen Server simuliert, und es wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung zur Verfügung stehen. Versuchen Sie, den Fokus des Tests jeden Monat zu drehen, damit Ihre Organisation jedes Mal den Fehler eines anderen Servers oder eines anderen Geräts testet.

Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfall Wiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Tests zur Notfallwiederherstellung nicht ignoriert oder vernachlässigt werden.

<div>


Exportieren Sie die lync Server 2013 Topologie, Richtlinien und Konfigurationseinstellungen in eine Datei. Diese Datei kann unter anderem dann verwendet werden, um diese Informationen im zentralen Verwaltungsspeicher wiederherzustellen, nachdem ein Upgrade, ein Hardwarefehler oder ein anderes Problem zu Datenverlust geführt hat.

Importieren Sie die lync Server 2013 Topologie, Richtlinien und Konfigurationseinstellungen in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen dargestellt:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

So sichern Sie Produktions lync Server 2013 Daten:

  - Sichern Sie die RTC-und LCSLog-Datenbanken, indem Sie den Standard SQL Server Sicherungsvorgang verwenden, um die Datenbank auf ein Datei-oder Bandsicherungsgerät zu kippen.

  - Verwenden Sie die Sicherungsanwendung eines Drittanbieters, um die Daten in Datei oder auf Band zu sichern.

  - Verwenden Sie das Cmdlet Export-csuserdata ", um einen XML-Export der gesamten RTC-Datenbank zu erstellen.

  - Verwenden Sie die Dateisystemsicherung oder Drittanbieter, um Besprechungsinhalte und Kompatibilitäts Protokolle zu sichern.

  - Verwenden Sie das Befehlszeilentool Export-CsConfiguration, um lync Server 2013 Einstellungen zu sichern.

Der erste Schritt beim Failover-Verfahren umfasst die erzwungene Verlagerung von Benutzern aus dem Produktionspool in den Notfall Wiederherstellungs Pool.

Dies ist eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzer Verlagerung zu akzeptieren.

Der lync Server 2013 Prozess "Benutzer verlegen" ist eine Änderung an einem Attribut für das Benutzerkontoobjekt zusätzlich zu einer Datensatzaktualisierung in der RTC SQL-Datenbank.

Diese Daten können über die folgenden beiden Prozesse wiederhergestellt werden:

  - Die RTC-Datenbank kann vom ursprünglichen Sicherungsspeicher Gerät aus dem Produktions SQL Server mithilfe des standardmäßigen SQL Server Wiederherstellungsprozesses oder mithilfe eines Sicherungs-/Wiederherstellungstools eines Drittanbieters wiederhergestellt werden.

  - Benutzer Kontaktdaten können mit dem Dienstprogramm DBIMPEXP. exe mithilfe der XML-Datei, die aus dem Export der Produktions SQL Server erstellt wurde, wiederhergestellt werden.

Nachdem diese Daten wiederhergestellt wurden, können Benutzer effektiv eine Verbindung mit dem Notfall Wiederherstellungs lync Server 2013-Pool herstellen und wie gewohnt arbeiten.

Damit Benutzer eine Verbindung mit dem Notfall Wiederherstellungs lync Server 2013-Pool herstellen können, ist eine Änderung des DNS-Eintrags erforderlich.

Auf den Produktions lync Server 2013 Pool wird von Clients verwiesen, die die Auto-Konfiguration und DNS-SRV-Einträge von verwenden:

  - SRV: \_SIP. \_TLS. \<Domäne\> /CNAME: SIP. \<Domäne\>

  - CNAME: SIP. \<Domänen\> /CVC-Pool-1. \<Domäne\>

Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den FQDN des DROCSPool verweist:

  - CNAME: SIP. \<Domänen\> /DROCSPool. \<Domäne\>

  - SIP. \<Domäne\>

  - AV.\<Domäne\>

  - webconf. \<Domäne\>

  - OCSServices. \<Domäne\>

<div>


> [!IMPORTANT]  
> Ausführliche Verwaltungs-und Verwaltungsverfahren finden Sie unter <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Sichern und Wiederherstellen von lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets für Sicherung und hohe Verfügbarkeit in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Sichern und Wiederherstellen lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Verwalten von lync Server 2013 Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

