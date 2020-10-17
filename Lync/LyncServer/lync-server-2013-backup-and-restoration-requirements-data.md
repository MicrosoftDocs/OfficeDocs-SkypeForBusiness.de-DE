---
title: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Daten'
description: 'Lync Server 2013: Anforderungen an die Sicherung und Wiederherstellung: Data.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563181"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-26_

Lync Server verwendet Einstellungen und Konfigurationsinformationen, die in Datenbanken gespeichert sind, sowie Daten, die in Datenbanken und Datei speichern gespeichert sind. In diesem Thema werden die Daten beschrieben, die Sie sichern müssen, damit der Dienst wiederhergestellt werden kann, wenn in Ihrer Organisation ein Fehler oder Ausfall auftritt, sowie die von lync Server verwendeten Daten und Komponenten identifiziert werden, die separat gesichert werden müssen.

<div>

## <a name="settings-and-configuration-requirements"></a>Einstellungen und Konfigurationsanforderungen

Dieses Thema enthält Verfahren zum Sichern und Wiederherstellen der Einstellungen und Konfigurationsinformationen, die für die Wiederherstellung des lync Server Diensts erforderlich sind. Die Konfigurationsinformationen befinden sich im zentralen Verwaltungsspeicher oder in einer anderen Back-End-Datenbank oder auf Standard Edition-Server.

In der folgenden Tabelle sind die Einstellungen und Konfigurationsinformationen aufgeführt, die Sie sichern und wiederherstellen müssen.

### <a name="settings-and-configuration-data"></a>Einstellungen und Konfigurationsdaten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Datentyp</th>
<th>Speicherort</th>
<th>Beschreibung/Sicherungszeitpunkt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Topologiekonfigurationsinformationen</p></td>
<td><p>Zentraler Verwaltungsspeicher (Datenbank: XDS. mdf)</p></td>
<td><p>Topologie, Richtlinie und Konfigurationseinstellungen.</p>
<p>Sichern Sie sich mit ihren regulären Sicherungen und nachdem Sie lync Server-Systemsteuerung oder Cmdlets zum Ändern Ihrer Konfiguration oder Richtlinien verwendet haben.</p></td>
</tr>
<tr class="even">
<td><p>Standortinformationen</p></td>
<td><p>Zentraler Verwaltungsspeicher (Datenbank: Lis. mdf)</p></td>
<td><p>Enterprise-VoIP-Konfigurationsinformationen für 9-1-1 (erweitert) (E9-1-1). Diese Informationen sind im Allgemeinen statisch.</p>
<p>Sicherung im Rahmen der regulären Sicherungen.</p></td>
</tr>
<tr class="odd">
<td><p>Informationen zur Reaktionsgruppenkonfiguration</p></td>
<td><p>Back-End-Server oder Standard Edition-Server (Datenbank: RgsConfig. mdf)</p></td>
<td><p>Gruppen, Warteschlangen und Workflows für Reaktionsgruppen-Agents.</p>
<p>Sicherung im Rahmen der regulären Sicherungen und nach dem Hinzufügen oder Ändern von Agentgruppen, Warteschlangen oder Workflows.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Datenanforderungen

Im folgenden finden Sie eine Liste der lync Server Daten, die Sie sichern müssen, damit Sie lync Server Dienst im Falle eines Fehlers wiederherstellen können.

Beachten Sie, dass einige Datentypen für die Wiederherstellung nicht erforderlich sind. Dieses Thema enthält keine Verfahren zum Sichern dieser Datentypen, einschließlich der folgenden:

  - Temporäre Benutzerdaten, wie z. B. Endgeräte und Abonnements, aktive Konferenzserver und vorübergehende Konferenzstatus (Datenbank: RtcDyn.mdf)

  - Adressbuchdaten (Datenbanken: RTCAb. mdf und Rtcab1. mdf). Die Adressbuchdatenbank wird automatisch aus Active Directory-Domänendienste neu generiert.

  - Dynamische Informationen für den Anwendung zum Parken von Anrufen (Datenbank: CpsDyn. mdf)

  - Transiente Reaktionsgruppen Daten wie Agent-Anmeldestatus und warte Informationen für Anrufe (Datenbank: RgsDyn. mdf)

  - Die Kompatibilitätsdatenbank für den beständigen Chat (Datenbank: MgcComp. mdf). Wenn Sie die Compliance für beständigen Chat aktiviert haben, sind die Informationen in der Kompatibilitätsdatenbank für beständigen Chat vorübergehend, solange Sie einen Adapter konfiguriert haben, um Informationen aus der Datenbank zu lesen und in ein alternatives Format zu konvertieren. Die Kompatibilitätsdatenbank für den beständigen Chat wird daher als vorübergehend betrachtet.
    
    Beständiger Chat von lync Server 2013 Server wird mit einem XML-Adapter ausgeliefert. Sie können auch benutzerdefinierte Adapter installieren, die diese Daten entgegennehmen und in andere Quellen wie Exchange Hosted Archives migrieren.

In der folgenden Tabelle sind die Daten aufgeführt, die Sie sichern und wiederherstellen müssen.

### <a name="data-stored-in-databases"></a>In Datenbanken gespeicherte Daten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Datentyp</th>
<th>Speicherort</th>
<th>Beschreibung/Sicherungszeitpunkt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dauerhafte Benutzerdaten</p></td>
<td><p>Back-End-Server oder Standard Edition-Server (Datenbank: "rtcxds". mdf)</p></td>
<td><p>Benutzerrechte, Benutzerkontaktlisten, Server- oder Pooldaten, geplante Konferenzen usw. In eine Konferenz hochgeladene Inhalte sind in diesen Benutzerdaten nicht enthalten.</p>
<p>Sicherung im Rahmen der regulären Sicherungen. Diese Informationen sind dynamisch, aber der Verlust von Updates ist für lync Server nicht katastrophal, wenn Sie die letzte reguläre Sicherung wiederherstellen müssen. Sie können diese Daten häufiger sichern, wenn Kontaktlisten für Ihre Organisation eine wichtige Rolle spielen.</p></td>
</tr>
<tr class="even">
<td><p>Archivierungsdaten</p></td>
<td><p>Archivierungsdatenbank (Datenbank: LcsLog.mdf)</p>
<p>Diese Daten können auf Exchange 2013 gespeichert werden, wenn Sie die Option Microsoft Exchange Integration aktiviert haben. Andernfalls werden diese Daten in einer lync Server Archivierungsdatenbank aufbewahrt, die möglicherweise mit einer anderen lync Server Datenbank oder eigenständig auf einem separaten Daten Bank Server verbunden ist.</p></td>
<td><p>Instant Messaging (IM)- und Besprechungsinhalte.</p>
<p>Diese Daten sind für lync Server nicht wichtig, aber Sie können für Ihre Organisation für regulatorische Zwecke von entscheidender Bedeutung sein. Legen Sie Ihren Sicherungszeitplan entsprechend fest.</p></td>
</tr>
<tr class="odd">
<td><p>Überwachungsdaten</p></td>
<td><p>Überwachungsdatenbanken (LcsCDR.mdf und QoeMetrics.mdf)</p>
<p>Diese Datenbankenkönnen mit einer anderen lync Server Datenbank oder eigenständig auf einem separaten Daten Bank Server zusammengestellt werden.</p></td>
<td><p>Kommunikationsdatensätze (LcsCDR. mdf) und QoE-Metrik (Quality of Experience) (QoeMetrics. mdf).</p>
<p>Kommunikationsdatensätze sind dynamisch und können für Ihr Unternehmen eine wichtige Rolle spielen. Berücksichtigen Sie bei der Festlegung Ihres Sicherungszeitplans, ob Sie diese Datensätze zur Einhaltung von Bestimmungen benötigen.</p>
<p>QoE-Informationen sind dynamisch. Der Verlust von QoE-Daten ist für den Betrieb von lync Server nicht entscheidend, kann jedoch für Ihr Unternehmen von entscheidender Bedeutung sein. Berücksichtigen Sie bei der Festlegung Ihres Sicherungszeitplans, wie wichtig diese Informationen für Ihre Organisation sind.</p></td>
</tr>
<tr class="even">
<td><p>Daten für beständigen Chat</p></td>
<td><p>Datenbank für beständigen Chat (MGD. mdf).</p>
<p>Diese Datenbank kann mit einer anderen lync Server Datenbank oder eigenständig auf einem separaten Daten Bank Server zusammengestellt werden.</p></td>
<td><p>Daten für beständigen Chat sind tatsächliche Chatinhalte, die in Chatrooms veröffentlicht werden. Diese Daten sind oft geschäftskritisch.</p>
<p>Sie können SQL Server Sicherung verwenden oder die Datenbank mithilfe des Cmdlets <strong>Export-CsPersistentChatData</strong> exportieren, das in lync Server bereitgestellt wird. Für die Wiederherstellung der Daten können Sie die Datenbank bis zum Ende der letzten vollständigen Sicherung importieren und wiederherstellen, was bedeutet, dass Sie die Datenbank nicht bis zum Fehler zurücksetzen können.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Dateispeicher-Datenanforderungen

In einer Enterprise Edition-Bereitstellung befindet sich der lync Server Dateispeicher in der Regel auf einem Datei Server. In einer Standard Edition-Bereitstellung befindet sich der lync Server Dateispeicher standardmäßig auf dem Standard Edition-Server. In der Regel gibt es einen lync Server Dateispeicher, der für eine Website freigegeben ist. Der Dateispeicher für beständigen Chat verwendet dieselbe Dateifreigabe wie der lync Server Dateispeichers.

Speicherorte für Dateispeicher werden als \\ \\ Server \\ Freigabename identifiziert. Um die spezifischen Speicherorte ihrer Dateispeicher zu finden, öffnen Sie den Topologie-Generator und schauen Sie sich den Knoten **Dateispeicher** an.

In der folgenden Tabelle werden die Dateispeicher beschrieben, die Sie sichern und wiederherstellen müssen.

### <a name="file-stores"></a>Dateispeicher

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Datentyp</th>
<th>Speicherort</th>
<th>Beschreibung/Sicherungszeitpunkt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server-Dateispeicher</p></td>
<td><p>Normalerweise auf einem Dateiserver, einem Dateicluster oder einem Standard Edition-Server</p></td>
<td><p>Besprechungsinhalte, Metadaten für Besprechungsinhalte, Kompatibilitäts Protokolle für Anwendungsdateien, Updatedateien für Geräte Updates, Audiodateien für Reaktionsgruppen, Parken von Anrufen und Ankündigungs Anwendungen sowie Dateien, die in beständigen Chatrooms bereitgestellt werden.</p>
<p>Sicherung im Rahmen der regulären Sicherungen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Zusätzliche Sicherungsanforderungen

Um sicherzustellen, dass lync Server Dienste im Falle eines Fehlers wiederhergestellt werden können, müssen Sie einige erforderliche Komponenten sichern, die nicht Teil von lync Server selbst sind. Die folgenden Komponenten werden im Rahmen des in diesem Dokument beschriebenen lync Server Sicherungs-und Wiederherstellungsprozesses nicht gesichert oder wiederhergestellt:

  - **Active Directory-Domänendienste**     Sie müssen AD DS mithilfe von Active Directory Tools sichern, gleichzeitig mit der Sicherung lync Server. Es ist wichtig, dass AD DS mit lync Server synchronisiert bleibt, um Probleme zu vermeiden, die auftreten können, wenn lync Server Kontaktobjekte erwartet, die nicht mit denen in AD DS übereinstimmen. In AD DS werden die folgenden Einstellungen gespeichert, die von lync Server verwendet werden:
    
      - SIP-URI des Benutzers und andere Benutzereinstellungen.
    
      - Kontaktobjekte für Anwendungen wie Reaktionsgruppen und Konferenzzentrale.
    
      - Ein Zeiger auf das zentraler Verwaltungsspeicher.
    
      - Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt) und lync Server Sicherheitsgruppen.
    
    Ausführliche Informationen zum Sichern und Wiederherstellen AD DS in Windows Server 2008 finden Sie unter "AD DS Schritt-für-Schritt-Anleitung zur Sicherung und Wiederherstellung" unter [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .

  - **Zertifizierungsstelle und Zertifikate**     Verwenden Sie die Richtlinie Ihrer Organisation für die Sicherung Ihrer Zertifizierungsstelle (Certification Authority, ca) und Zertifikate. Wenn Sie exportierbare private Schlüssel verwenden, können Sie das Zertifikat und den privaten Schlüssel sichern und dann exportieren, wenn Sie die Verfahren in diesem Dokument verwenden, um lync Server wiederherzustellen. Wenn Sie eine interne Zertifizierungsstelle verwenden, können Sie sich erneut anmelden, wenn Sie lync Server wiederherstellen müssen. Sie müssen den privaten Schlüssel unbedingt an einem sicheren Ort verwahren, damit er beim Ausfall eines Computers verfügbar ist.

  - **System Center Operations Manager**     Wenn Sie Microsoft System Center Operations Manager (ehemals Microsoft Operations Manager) zum Überwachen Ihrer lync Server-Bereitstellung verwenden, können Sie optional die Daten sichern, die beim Überwachen von lync Server erstellt werden. Verwenden Sie den standardmäßigen SQL Server Sicherungsprozess zum Sichern von System Center Operations Manager-Dateien. Diese Dateien werden nicht in die Wiederherstellung einbezogen.

  - **Konfiguration des PSTN-Gateways (Public Switched Telephone Network)**     Wenn Sie Enterprise-VoIP oder Survivable Branch Appliances verwenden, müssen Sie die Konfiguration des PSTN-Gateways sichern. Informationen zum Sichern und Wiederherstellen der Konfiguration von PSTN-Gateways erhalten Sie vom jeweiligen Hersteller.

  - Nebeneinander **vorhandene Versionen von lync Server oder Office Communications Server**     Wenn Ihre lync Server 2013-Bereitstellung mit lync Server 2010 oder einer früheren Version von Office Communications Server koexistiert, können Sie die Verfahren in diesem Dokument nicht zum Sichern oder Wiederherstellen der früheren Version verwenden. Stattdessen müssen Sie die speziell für Ihre frühere Version dokumentierten Sicherungs- und Wiederherstellungsverfahren verwenden. Ausführliche Informationen zum Sichern und Wiederherstellen von lync Server 2010 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) . Ausführliche Informationen zum Sichern und Wiederherstellen von Microsoft Office Communications Server 2007 R2 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .

  - **Infrastruktur Informationen**     Sie müssen Informationen zu Ihrer Infrastruktur sichern, beispielsweise Ihre Firewall-Konfiguration, Lastenausgleichskonfiguration, Internet Information Services (IIS) Konfiguration, Domain Name System (DNS) Datensätzen und IP-Adressen sowie die DHCP-Konfiguration (Dynamic Host Configuration Protocol). Ausführliche Informationen zum Sichern dieser Komponenten erhalten Sie vom jeweiligen Hersteller.

  - **Microsoft Exchange und Exchange Unified Messaging (um)**     Sichern und Wiederherstellen Microsoft Exchange und Exchange um, wie in der Microsoft Exchange Dokumentation beschrieben. Ausführliche Informationen zum Sichern und Wiederherstellen von Exchange Server 2013 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) . Ausführliche Informationen zum Sichern und Wiederherstellen von Exchange Server 2010 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .
    
    Beachten Sie, dass lync Server 2013 die Möglichkeit bietet, Benutzer Kontaktlisten, hochauflösende Benutzer Fotos und in Exchange 2013 gespeicherte Archivdaten zu haben. In der folgenden Liste finden Sie Informationen zum Sichern dieser Datentypen:
    
      - **Hochauflösende Fotos** werden im Rahmen der Exchange Server Sicherung gesichert.
    
      - In lync Server 2013 wird ein **einheitlicher Kontaktspeicher** eingeführt. Mit dem einheitlichen Kontaktspeicher können Benutzer alle Ihre Kontaktinformationen in Exchange 2013 speichern.
        
        Sie sollten sicherstellen, dass Sicherungen für Benutzer auf dem neuesten Stand sind, ob Ihre Benutzer Kontakte im einheitlichen Kontaktspeicher oder auf dem lync-Back-End-Server gespeichert sind. In den folgenden Szenarien wird veranschaulicht, wo das Migrieren von Benutzerkontakten zum einheitlichen Kontaktspeicher zu Problemen beim Sicherungs-und Wiederherstellungsvorgang führen kann.
        
        **Szenario 1:** Benutzer Kontakte werden zum einheitlichen Kontaktspeicher migriert, und eine Wiederherstellung erfolgt über eine lync Server Sicherung, die vor der Migration von Benutzerkontakten durchgeführt wurde. In diesem Szenario verfügt der Benutzer über einen Status veralteter Kontakte für bis zu einem Tag, bis lync Server Migrations Task die Migration von Benutzerkontakten zu Exchange beginnt. (Beachten Sie, dass die Exchange-Kontaktinformationen verwendet werden, da die Benutzer Kontakte zuvor zum einheitlichen Kontaktspeicher migriert wurden). In diesem Szenario ist kein Administratoreingriff erforderlich.
        
        **Szenario 2:** Benutzer Kontakte wurden zuvor im einheitlichen Kontaktspeicher gespeichert, dann jedoch zurückgesetzt. Eine Wiederherstellung wird von einer lync Server Sicherung durchgeführt, die ausgeführt wurde, als die Benutzer Kontakte im einheitlichen Kontaktspeicher gespeichert wurden. In diesem Szenario zeigt eine Fehlermeldung von `Error: Incorrect Exchange Version` in den Client-oder Lyss-Serverprotokollen möglicherweise dies als Problem an. Der Benutzer kann direkt in Exchange auf seine Kontaktliste in lync 2013 zugreifen, der Status des Clients stimmt jedoch nicht mit dem lync Server Zustand überein. Um dies zu beheben, muss ein Administrator die **Invoke-CsUCSRollback-** Cmdlets für die betroffenen Benutzer ausführen.
    
      - **Archivierungsdaten** können in Exchange 2013 gespeichert werden. Diese Daten sind für lync Server nicht wichtig, aber Sie können für Ihre Organisation für regulatorische Zwecke von entscheidender Bedeutung sein. Wenn Archivierungsdaten in Exchange gespeichert werden und für Ihre Organisation wichtig sind, folgen Sie den Exchange-Sicherungs-und Wiederherstellungsverfahren. Beachten Sie, dass die in Exchange gespeicherten Archivierungsdaten nicht wieder in lync Server verschoben werden können. Darüber hinaus gibt es keine Möglichkeit, bereits in der lync-Archivierungsdatenbank gespeicherte Daten in Exchange zu migrieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

