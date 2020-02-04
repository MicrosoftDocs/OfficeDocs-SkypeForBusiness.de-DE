---
title: 'Lync Server 2013: Sicherungs-und Wiederherstellungsanforderungen: Daten'
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
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Daten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Lync Server verwendet Einstellungen und Konfigurationsinformationen, die in Datenbanken gespeichert sind, und Daten, die in Datenbanken und Datei speichern gespeichert sind. In diesem Thema werden die Daten beschrieben, die Sie sichern müssen, damit der Dienst wiederhergestellt werden kann, wenn in Ihrer Organisation ein Fehler oder ein Ausfall auftritt, und außerdem die von lync Server verwendeten Daten und Komponenten identifiziert werden, die separat gesichert werden müssen.

<div>

## <a name="settings-and-configuration-requirements"></a>Einstellungen und Konfigurationsanforderungen

Dieses Thema enthält Verfahren zum Sichern und Wiederherstellen der Einstellungen und Konfigurationsinformationen, die für die Wiederherstellung des lync Server-Diensts erforderlich sind. Die Konfigurationsinformationen befinden sich im zentralen Verwaltungsspeicher oder in einer anderen Back-End-Datenbank oder auf dem Standard Edition-Server.

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
<th>Art der Daten</th>
<th>Wo gespeichert</th>
<th>Beschreibung/wann sichern</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informationen zur Topologie-Konfiguration</p></td>
<td><p>Zentraler Verwaltungsspeicher (Datenbank: XDS. mdf)</p></td>
<td><p>Topologie-, Richtlinien-und Konfigurationseinstellungen.</p>
<p>Sichern Sie Ihre regelmäßigen Sicherungen und nachdem Sie die lync Server-Systemsteuerung oder Cmdlets verwendet haben, um Ihre Konfiguration oder Richtlinien zu ändern.</p></td>
</tr>
<tr class="even">
<td><p>Standortinformationen</p></td>
<td><p>Zentraler Verwaltungsspeicher (Datenbank: Lis. mdf)</p></td>
<td><p>Enterprise Voice Enhanced 9-1-1 (E9-1-1)-Konfigurationsinformationen. Diese Informationen sind in der Regel statisch.</p>
<p>Sichern Sie Ihre normalen Backups.</p></td>
</tr>
<tr class="odd">
<td><p>Konfigurationsinformationen zur Reaktionsgruppe</p></td>
<td><p>Back-End-Server oder Standard Edition-Server (Datenbank: RgsConfig. mdf)</p></td>
<td><p>Gruppen, Warteschlangen und Workflows für Reaktionsgruppen-Agents</p>
<p>Sichern Sie mit ihren regulären Sicherungen und nach dem Hinzufügen oder Ändern von Agentengruppen, Warteschlangen oder Workflows.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Datenanforderungen

Nachfolgend finden Sie eine Liste der lync Server-Daten, die Sie sichern müssen, damit Sie den lync Server-Dienst im Fall eines Fehlers wiederherstellen können.

Beachten Sie, dass für die Wiederherstellung einige Datentypen nicht erforderlich sind. Dieses Thema enthält keine Verfahren zum Sichern dieser Datentypen, einschließlich der folgenden:

  - Vorübergehende Benutzerdaten wie Endpunkte und Abonnements, aktive Konferenzserver und transiente Konferenz Zustände (Datenbank: RtcDyn. mdf)

  - Adressbuchdaten (Datenbanken: RTCAb. mdf und Rtcab1. mdf). Die Adressbuchdatenbank wird automatisch aus den Active Directory-Domänendiensten neu erstellt.

  - Dynamische Informationen für die Anwendung des Anruf Parks (Datenbank: CpsDyn. mdf)

  - Flüchtige Antwortgruppen Daten wie Agenten-Anmeldestatus und warte Informationen für Anrufe (Datenbank: RgsDyn. mdf)

  - Die Kompatibilitätsdatenbank für beständigen Chat (Datenbank: MgcComp. mdf). Wenn die Compliance für beständigen Chat aktiviert ist, sind die Informationen in der beständigen Chat-Kompatibilitätsdatenbank vorübergehend, solange Sie über einen Adapter verfügen, der zum Lesen von Informationen aus der Datenbank konfiguriert ist und in ein anderes Format konvertiert werden kann. Daher gilt die Compliance-Datenbank für beständigen Chat als vorübergehend.
    
    Lync Server 2013 beständiger Chat Server wird mit einem XML-Adapter ausgeliefert. Sie können auch benutzerdefinierte Adapter installieren, die diese Daten übernehmen und in andere Quellen, wie etwa Exchange Hosted Archives, verschieben.

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
<th>Art der Daten</th>
<th>Wo gespeichert</th>
<th>Beschreibung/wann sichern</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Beständige Benutzerdaten</p></td>
<td><p>Back-End-Server oder Standard Edition-Server (Datenbank: RTCXDS. mdf)</p></td>
<td><p>Benutzerrechte, Benutzer Kontaktlisten, Server-oder Pooldaten, geplante Konferenzen usw. Diese Benutzerdaten beinhalten keine Inhalte, die in eine Konferenz hochgeladen wurden.</p>
<p>Sichern Sie Ihre normalen Backups. Diese Informationen sind dynamisch, doch der Verlust von Updates ist für lync Server nicht katastrophal, wenn Sie die letzte reguläre Sicherung wiederherstellen müssen. Wenn Kontaktlisten für Ihre Organisation wichtig sind, können Sie diese Daten häufiger sichern.</p></td>
</tr>
<tr class="even">
<td><p>Archivieren von Daten</p></td>
<td><p>Archivierungsdatenbank (Datenbank: LcsLog. mdf)</p>
<p>Diese Daten werden möglicherweise auf Exchange 2013 gespeichert, wenn Sie die Microsoft Exchange-Integrations Option aktiviert haben. Andernfalls werden diese Daten in einer lync Server-Archivierungsdatenbank aufbewahrt, die sich möglicherweise mit einer anderen lync Server-Datenbank oder eigenständigen auf einem separaten Datenbankserver befindet.</p></td>
<td><p>Instant Messaging (im) und Besprechungsinhalte.</p>
<p>Diese Daten sind für lync Server nicht wichtig, können aber für Ihre Organisation für regulatorische Zwecke wichtig sein. Legen Sie den Sicherungszeitplan entsprechend fest.</p></td>
</tr>
<tr class="odd">
<td><p>Überwachen von Daten</p></td>
<td><p>Überwachungsdatenbanken (LcsCDR. mdf und Datenbank QoEMetrics werden. mdf)</p>
<p>Diese Datenbankenkönnen mit einer anderen lync Server-Datenbank oder eigenständigen auf einem separaten Datenbankserver bereitgestellt werden.</p></td>
<td><p>Anruf Detaildatensätze (LcsCDR. mdf) und QoE-Metrik (Quality of Experience) (Datenbank QoEMetrics werden. mdf).</p>
<p>Anruf Detaildatensätze sind dynamisch und können für Ihr Unternehmen von entscheidender Bedeutung sein. Ermitteln Sie den Sicherungszeitplan, indem Sie erwägen, ob Sie diese Einträge aus regulatorischen Gründen benötigen.</p>
<p>Die Qualität der Erfahrungs Informationen ist dynamisch. Der Verlust von QoE-Daten ist für den Betrieb von lync Server nicht entscheidend, kann aber für Ihr Unternehmen von entscheidender Bedeutung sein. Ermitteln Sie den Sicherungszeitplan basierend auf der Wichtigkeit dieser Informationen für Ihre Organisation.</p></td>
</tr>
<tr class="even">
<td><p>Persistente Chat-Daten</p></td>
<td><p>Persistent Chat-Datenbank (MGD. mdf).</p>
<p>Diese Datenbank kann mit einer anderen lync Server-Datenbank oder eigenständigen auf einem separaten Datenbankserver bereitgestellt werden.</p></td>
<td><p>Beständige Chat-Daten sind tatsächliche Chatinhalte, die in Chatrooms gepostet werden. Diese Daten sind häufig geschäftskritisch.</p>
<p>Sie können die SQL Server-Sicherung verwenden oder die Datenbank mithilfe des Cmdlets <strong>Export-CsPersistentChatData</strong> exportieren, das in lync Server bereitgestellt wird. Zur Wiederherstellung der Daten können Sie die Datenbank bis zum Zeitpunkt der letzten vollständigen Sicherung importieren und wiederherstellen, was bedeutet, dass Sie die Datenbank nicht bis zum Zeitpunkt des Fehlers wiederherstellen können.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Dateispeicher-Datenanforderungen

In einer Enterprise Edition-Bereitstellung befindet sich der lync Server-Dateispeicher normalerweise auf einem Datei Server. Bei einer Standard Edition-Bereitstellung befindet sich der lync Server-Dateispeicher standardmäßig auf dem Standard Edition-Server. In der Regel gibt es einen lync Server-Dateispeicher, der für eine Website freigegeben wurde. Der Dateispeicher für beständigen Chat verwendet dieselbe Dateifreigabe wie der lync Server-Dateispeicher.

Dateispeicherorte werden als \\ \\Server\\Freigabename identifiziert. Wenn Sie die spezifischen Speicherorte ihrer Dateispeicher finden möchten, öffnen Sie den Topologie-Generator, und schauen Sie im Knoten **Dateispeicher** nach.

In der folgenden Tabelle sind die Dateispeicher aufgeführt, die Sie sichern und wiederherstellen müssen.

### <a name="file-stores"></a>Dateispeicher

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Art der Daten</th>
<th>Wo gespeichert</th>
<th>Beschreibung/wann sichern</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server-Dateispeicher</p></td>
<td><p>In der Regel auf einem Dateiserver, einem Dateicluster oder einem Standard Edition-Server</p></td>
<td><p>Besprechungsinhalte, Metadaten für Besprechungsinhalte, Konformitäts Protokolle für Anwendungen, Anwendungsdatendateien, Updatedateien für Geräte Updates, Audiodateien für die Reaktionsgruppe, Anruf Park-und Ankündigungs Anwendungen sowie Dateien, die in beständigen Chatrooms gepostet wurden.</p>
<p>Sichern Sie Ihre normalen Backups.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Zusätzliche Sicherungsanforderungen

Wenn Sie sicherstellen möchten, dass Sie die lync Server-Dienste bei einem Fehler wiederherstellen können, müssen Sie einige erforderliche Komponenten sichern, die nicht Teil von lync Server selbst sind. Die folgenden Komponenten werden nicht im Rahmen des in diesem Dokument beschriebenen lync Server-Sicherungs-und Wiederherstellungsprozesses gesichert oder wiederhergestellt:

  - **Active Directory-Domänendienste**   Sie müssen AD DS sichern, indem Sie die Active Directory-Tools zur gleichen Zeit sichern, in der Sie lync Server sichern. Es ist wichtig, dass AD DS mit lync Server synchronisiert bleibt, um Probleme zu vermeiden, die auftreten können, wenn lync Server Kontaktobjekte erwartet, die nicht mit denen in AD DS übereinstimmen. In AD DS werden die folgenden von lync Server verwendeten Einstellungen gespeichert:
    
      - SIP-URI des Benutzers und andere Benutzereinstellungen.
    
      - Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale.
    
      - Ein Zeiger auf den zentralen Verwaltungsspeicher.
    
      - Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt) und lync Server-Sicherheitsgruppen.
    
    Details zum Sichern und Wiederherstellen von AD DS in Windows Server 2008 finden Sie unter schrittweise Anleitung zur AD DS-Sicherung und-Wiederherstellung unter [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).

  - **Zertifizierungsstellen und Zertifikate**   verwenden Sie die Richtlinie Ihrer Organisation für das Sichern Ihrer Zertifizierungsstelle (Certification Authority, ca) und Zertifikate. Wenn Sie exportierbare private Schlüssel verwenden, können Sie das Zertifikat und den privaten Schlüssel sichern und dann exportieren, wenn Sie die in diesem Dokument beschriebenen Verfahren zum Wiederherstellen von lync Server verwenden. Wenn Sie eine interne Zertifizierungsstelle verwenden, können Sie die Registrierung erneut registrieren, wenn Sie lync Server wiederherstellen müssen. Es ist wichtig, dass Sie den privaten Schlüssel an einem sicheren Ort aufbewahren, wo er verfügbar ist, wenn ein Computer ausfällt.

  - **System Center Operations Manager**   Wenn Sie Microsoft System Center Operations Manager (vormals Microsoft Operations Manager) zum Überwachen Ihrer lync Server-Bereitstellung verwenden, können Sie optional die Daten sichern, die beim Überwachen von lync Server erstellt werden. Verwenden Sie den standardmäßigen SQL Server-Sicherungsvorgang zum Sichern von System Center Operations Manager-Dateien. Diese Dateien werden während der Wiederherstellung nicht wiederhergestellt.

  - **PSTN-Gateway-Konfiguration (Public Switched Telephone Network)**   Wenn Sie Enterprise-VoIP oder Survivable Branch-Appliances verwenden, müssen Sie die Konfiguration des PSTN-Gateways sichern. Informationen zum Sichern und Wiederherstellen von Konfigurationen für PSTN-Gateways finden Sie in Ihrem Anbieter.

  - **Nebeneinander vorhandene Versionen von lync Server oder Office Communications Server**   Wenn Ihre lync Server 2013-Bereitstellung mit lync Server 2010 oder einer früheren Version von Office Communications Server koexistiert, können Sie die Verfahren in diesem Dokument nicht zum Sichern oder Wiederherstellen der vorherigen Version verwenden. Stattdessen müssen Sie die Sicherungs-und Wiederherstellungsverfahren verwenden, die speziell für ihre frühere Version dokumentiert sind. Weitere Informationen zum Sichern und Wiederherstellen von lync Server 2010 finden Sie [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) unter. Weitere Informationen zum Sichern und Wiederherstellen von Microsoft Office Communications Server 2007 R2 finden Sie [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)unter.

  - **Infrastruktur Informationen**   , die Sie benötigen, um Informationen zu Ihrer Infrastruktur zu sichern, beispielsweise Ihre Firewall-Konfiguration, Konfiguration des Lastenausgleichs, Konfiguration der Internet Informationsdienste (IIS), DNS-Einträge (Domain Name System) und IP-Adressen sowie DHCP-Konfiguration (Dynamic Host Configuration Protocol). Informationen zum Sichern dieser Komponenten finden Sie bei den jeweiligen Anbietern.

  - **Microsoft Exchange und Exchange Unified Messaging (um)**   sichern und Wiederherstellen von Microsoft Exchange und Exchange um, wie in der Microsoft Exchange-Dokumentation beschrieben. Weitere Informationen zum Sichern und Wiederherstellen von Exchange Server 2013 finden Sie [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)unter. Weitere Informationen zum Sichern und Wiederherstellen von Exchange Server 2010 finden Sie [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)unter.
    
    Beachten Sie, dass lync Server 2013 die Möglichkeit bietet, Benutzer Kontaktlisten, HD-Benutzer Fotos und Archivierungsdaten in Exchange 2013 zu speichern. Sehen Sie sich die folgende Liste an, um zu erfahren, wie Sie diese Datentypen sichern:
    
      - **Fotos mit höherer Auflösung** werden im Rahmen der Exchange Server-Sicherung gesichert.
    
      - Der **Unified Contact Store** wird in lync Server 2013 eingeführt. Mit dem Unified Contact Store können Benutzer alle Ihre Kontaktinformationen in Exchange 2013 behalten.
        
        Stellen Sie sicher, dass die Sicherungen für Benutzer auf dem neuesten Stand sind, indem Sie angeben, ob Ihre Benutzer Kontakte im Unified Contact Store oder auf dem lync-Back-End-Server gespeichert sind. Die folgenden Szenarien veranschaulichen, wo die Migration von Benutzerkontakten in den Unified Contact Store zu Problemen beim Sicherungs-und Wiederherstellungsprozess führen kann.
        
        **Szenario 1:** Benutzer Kontakte werden in den einheitlichen Kontaktspeicher migriert, und eine Wiederherstellung erfolgt über eine lync Server-Sicherung, die vor der Migration von Benutzerkontakten ausgeführt wurde. In diesem Szenario hat der Benutzer einen Status veralteter Kontakte bis zu einem Tag, bis der lync Server-Migrations Task die Migration von Benutzerkontakten zu Exchange beginnt. (Beachten Sie, dass die Exchange-Kontaktinformationen verwendet werden, da die Benutzer Kontakte zuvor in den Unified Contact Store migriert wurden). In diesem Szenario ist kein Administratoreingriff erforderlich.
        
        **Szenario 2:** Benutzer Kontakte wurden zuvor im Unified Contact Store gespeichert, anschließend aber zurückgesetzt. Eine Wiederherstellung erfolgt über eine lync Server-Sicherung, die durchgeführt wurde, wenn die Benutzer Kontakte im Unified Contact Store gespeichert wurden. In diesem Szenario zeigt eine Fehlermeldung `Error: Incorrect Exchange Version` in den Serverprotokollen des Clients oder Lyss möglicherweise ein Problem an. Der Benutzer kann direkt von Exchange aus auf seine Kontaktliste in lync 2013 zugreifen, der Zustand des Clients entspricht aber nicht dem lync-Server Zustand. Um dies zu beheben, muss ein Administrator die **Invoke-CsUCSRollback-** Cmdlets für die betroffenen Benutzer ausführen.
    
      - **Archivierungsdaten** können in Exchange 2013 gespeichert werden. Diese Daten sind für lync Server nicht wichtig, können aber für Ihre Organisation für regulatorische Zwecke wichtig sein. Wenn Archivierungsdaten in Exchange gespeichert sind und für Ihre Organisation wichtig sind, folgen Sie den Exchange-Sicherungs-und Wiederherstellungsverfahren. Beachten Sie, dass Archivierungsdaten, die in Exchange gespeichert sind, nicht zurück zu lync Server verschoben werden können. Darüber hinaus gibt es keine Möglichkeit, Daten, die bereits in der lync-Archivierungsdatenbank gespeichert sind, in Exchange zu verschieben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

