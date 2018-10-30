---
title: 'Anforderungen für die Sicherung und Wiederherstellung: Daten'
TOCTitle: 'Anforderungen für die Sicherung und Wiederherstellung: Daten'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202194(v=OCS.15)
ms:contentKeyID: 52056487
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für die Sicherung und Wiederherstellung: Daten

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server verwendet Einstellungen und Konfigurationsinformationen, die in Datenbanken gespeichert werden, sowie Daten, die in Datenbanken und Datenspeichern gespeichert werden. In diesem Thema werden die Daten beschrieben, die Sie sichern müssen, um die Betriebsbereitschaft wiederherstellen zu können, falls in Ihrer Organisation ein Serverfehler oder -ausfall auftritt. Darüber hinaus werden die von Lync Server verwendeten Daten und Komponenten beschrieben, die Sie separat sichern müssen.

## Einstellungen und Konfigurationsanforderungen

Dieses Thema enthält Verfahren zum Sichern und Wiederherstellen der Einstellungen und Konfigurationsinformationen, die für die Wiederherstellung des Lync Server-Diensts erforderlich sind. Die Konfigurationsinformationen befinden sich im zentralen Verwaltungsspeicher oder in einer anderen Back-End-Datenbank oder auf einem Standard Edition-Server.

In der folgenden Tabelle werden die Einstellungen und Konfigurationsinformationen beschrieben, die Sie sichern und wiederherstellen müssen.

### Einstellungen und Konfigurationsdaten

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
<td><p>zentralen Verwaltungsspeicher (Datenbank: <strong>Xds.mdf</strong>)</p></td>
<td><p>Topologie, Richtlinie und Konfigurationseinstellungen.</p>
<p>Sicherung im Rahmen der regulären Sicherungen und nach der Verwendung der Lync Server-Systemsteuerung oder von Cmdlets zum Ändern von Konfiguration oder Richtlinien.</p></td>
</tr>
<tr class="even">
<td><p>Standortinformationen</p></td>
<td><p>zentralen Verwaltungsspeicher (Datenbank: <strong>Lis.mdf</strong>)</p></td>
<td><p>Enterprise-VoIP-Konfigurationsinformationen für 9-1-1 (erweitert) (E9-1-1). Diese Informationen sind im Allgemeinen statisch.</p>
<p>Sicherung im Rahmen der regulären Sicherungen.</p></td>
</tr>
<tr class="odd">
<td><p>Informationen zur Reaktionsgruppenkonfiguration</p></td>
<td><p>Back-End-Server oder Standard Edition-Server (Datenbank: <strong>RgsConfig.mdf</strong>)</p></td>
<td><p>Agentgruppen, Warteschlangen und Workflows für Reaktionsgruppeen.</p>
<p>Sicherung im Rahmen der regulären Sicherungen und nach dem Hinzufügen oder Ändern von Agentgruppen, Warteschlangen oder Workflows.</p></td>
</tr>
</tbody>
</table>


## Datenanforderungen

Hier eine Liste der Lync Server-Daten, die Sie sichern müssen, damit Sie den Lync Server-Dienst bei einem Ausfall wiederherstellen können.

Beachten Sie, dass einige Datentypen für die Wiederherstellung nicht erforderlich sind. Dieses Thema enthält keine bestimmten Verfahren zum Sichern dieser Datentypen, zu denen folgende gehören:

  - Temporäre Benutzerdaten, wie z. B. Endgeräte und Abonnements, aktive Konferenzserver und vorübergehende Konferenzstatus (Datenbank: **RtcDyn.mdf**)

  - Adressbuchdaten (Datenbanken: **Rtcab.mdf** und **Rtcab1.mdf**). Die Adressbuchdatenbank wird aus Active Directory-Domänendienste automatisch erneut neu generiert.

  - Dynamische Informationen für die Anwendung zum Parken von Anrufen (Datenbank: **CpsDyn.mdf**)

  - Temporäre Reaktionsgruppendaten, wie z. B. Agentanmeldestatus und Anklopfinformationen (Datenbank: **RgsDyn.mdf**)

  - Die Konformitätsdatenbank für Beständiger Chat (Datenbank: **MgcComp.mdf**). Wenn die Konformität für beständigen Chat aktiviert ist, sind die Informationen in der Beständiger Chat-Konformitätsdatenbank temporär, sofern Sie keinen Adapter konfiguriert haben, um Informationen aus der Datenbank zu lesen und in ein alternatives Format zu konvertieren. Daher wird die Konformitätsdatenbank für Beständiger Chat als temporär angesehen.
    
    Der Server für beständigen Chat in Lync Server 2013 wird mit einem XML-Adapter ausgeliefert. Sie können auch benutzerdefinierte Adapter installieren, die diese Daten zu anderen Quellen verschieben, z. B. Exchange Hosted Archives.

In der folgenden Tabelle werden die Daten beschrieben, die Sie sichern und wiederherstellen müssen.

### In Datenbanken gespeicherte Daten

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
<td><p>Back-End-Server oder Standard Edition-Server (Datenbank: <strong>RTCXDS.mdf</strong>)</p></td>
<td><p>Benutzerrechte, Benutzerkontaktlisten, Server- oder Pooldaten, geplante Konferenzen usw. Diese Benutzerdaten enthalten keinen Inhalt, der in eine Konferenz hochgeladen wird.</p>
<p>Sicherung im Rahmen der regulären Sicherungen. Diese Daten sind dynamisch, aber der Verlust von Updates stellt für Lync Server keine Katastrophe dar, falls Sie die letzte reguläre Sicherung wiederherstellen müssen. Sie können diese Daten häufiger sichern, wenn Kontaktlisten für Ihre Organisation eine wichtige Rolle spielen.</p></td>
</tr>
<tr class="even">
<td><p>Archivierungsdaten</p></td>
<td><p>Archivierungsdatenbank (Datenbank: <strong>LcsLog.mdf</strong>)</p>
<p>Diese Daten können in Exchange 2013 gespeichert werden, wenn Sie die Option für die Microsoft Exchange-Integration aktiviert haben. Andernfalls werden diese Daten in einer Lync Server-Archivierungsdatenbank gespeichert, die mit einer anderen Lync Server-Datenbank verbunden oder eine eigenständige Datenbank auf einem separaten Datenbankserver ist.</p></td>
<td><p>Instant Messaging (IM)- und Besprechungsinhalte.</p>
<p>Diese Daten spielen für Lync Server keine wichtige Rolle, jedoch möglicherweise für Ihre Organisation aus Gründen der Einhaltung von Bestimmungen. Legen Sie Ihren Sicherungszeitplan entsprechend fest.</p>
<p>Lync Server unterstützt für Archivierungsdatenbanken nur das einfache Wiederherstellungsmodell. Mit dem einfachen Wiederherstellungsmodell wird die letzte vollständige Sicherung von Datenbanken wiederhergestellt. Das heißt, der Zustand einer Datenbank beim Auftreten eines Fehlers oder zu einem bestimmten Zeitpunkt kann nicht wiederhergestellt werden.</p></td>
</tr>
<tr class="odd">
<td><p>Überwachungsdaten</p></td>
<td><p>Überwachungsdatenbanken (<strong>LcsCDR.mdf</strong> und <strong>QoeMetrics.mdf</strong>)</p>
<p>Diese Datenbanken können mit einer anderen Lync Server-Datenbank verbunden oder eigenständige Datenbanken auf einem separaten Datenbankserver sein.</p></td>
<td><p>Kommunikationsdatensätze (<strong>LcsCDR.mdf</strong>) und Quality of Experience (QoE)-Metriken (<strong>QoeMetrics.mdf</strong>).</p>
<p>Kommunikationsdatensätze sind dynamisch und können für Ihr Unternehmen eine wichtige Rolle spielen. Berücksichtigen Sie bei der Festlegung Ihres Sicherungszeitplans, ob Sie diese Datensätze zur Einhaltung von Bestimmungen benötigen.</p>
<p>QoE-Informationen sind dynamisch. Der Verlust von QoE-Daten spielt für den Betrieb von Lync Server keine wichtige Rolle, jedoch möglicherweise für Ihr Unternehmen. Berücksichtigen Sie bei der Festlegung Ihres Sicherungszeitplans, wie wichtig diese Informationen für Ihre Organisation sind.</p>
<p>Lync Server unterstützt für Überwachungsdatenbanken nur das einfache Wiederherstellungsmodell. Mit dem einfachen Wiederherstellungsmodell wird die letzte vollständige Sicherung von Datenbanken wiederhergestellt. Das heißt, der Zustand einer Datenbank beim Auftreten eines Fehlers oder zu einem bestimmten Zeitpunkt kann nicht wiederhergestellt werden.</p></td>
</tr>
<tr class="even">
<td><p>Daten für beständigen Chat</p></td>
<td><p>Datenbank für beständigen Chat (mgd.mdf).</p>
<p>Diese Datenbank kann mit einer anderen Lync Server-Datenbank verbunden oder eine eigenständige Datenbank auf einem separaten Datenbankserver sein.</p></td>
<td><p>Bei den Daten für beständigen Chat handelt es sich um den Chatinhalt, der in Chatrooms bereitgestellt wird. Diese Daten sind häufig wichtig für das Unternehmen.</p>
<p>Sie können die SQL Server-Sicherung verwenden oder die Datenbank mit dem <strong>Export-CsPersistentChatData</strong>-Cmdlet exportieren, das in Lync Server bereitgestellt wird. Zur Wiederherstellung der Daten können Sie die Datenbank bis zum Zeitpunkt der letzten vollständigen Sicherung importieren und wiederherstellen. Das bedeutet, dass Sie die Datenbank nicht bis zum Zeitpunkt des Ausfalls wiederherstellen können.</p></td>
</tr>
</tbody>
</table>


## Dateispeicher-Datenanforderungen

In einer Enterprise Edition-Bereitstellung befindet sich der Lync Server-Dateispeicher in der Regel auf einem Dateiserver. In einer Standard Edition-Bereitstellung befindet sich der Lync Server-Dateispeicher standardmäßig auf dem Standard Edition-Server. Normalerweise gibt es einen Lync Server-Dateispeicher, der gemeinsam für einen Standort verwendet wird. Der Beständiger Chat-Dateispeicher verwendet dieselbe Dateifreigabe wie der Lync Server-Dateispeicher.

Dateispeicherorte haben das Format **\\\\Server\\Freigabename**. Die speziellen Speicherorte Ihrer Dateispeicher finden Sie im Topologie-Generator unter dem Knoten **Dateispeicher**.

In der folgenden Tabelle werden die Dateispeicher beschrieben, die Sie sichern und wiederherstellen müssen.

### Dateispeicher

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
<td><p>In der Regel auf einem Dateiserver, in einem Dateicluster oder auf einem Standard Edition-Server</p></td>
<td><p>Besprechungsinhalte, Metadaten zu Besprechungsinhalten, Protokolle für Besprechungskompatibilität, Anwendungsdatendateien, Updatedateien für Geräteupdates, Audiodateien für Reaktionsgruppen- und Ankündigungsanwendungen sowie für Anwendungen zum Parken von Anrufen und in beständigen Chatrooms bereitgestellte Dateien.</p>
<p>Sicherung im Rahmen der regulären Sicherungen.</p></td>
</tr>
</tbody>
</table>


## Zusätzliche Sicherungsanforderungen

Um sicherzustellen, dass Sie Lync Server-Dienste bei einem Ausfall wiederherstellen können, müssen Sie einige erforderliche Komponenten sichern, die nicht Teil von Lync Server selbst sind. Die folgenden Komponenten werden im Rahmen des in diesem Dokument beschriebenen Sicherungs- und Wiederherstellungsverfahrens von Lync Server nicht gesichert oder wiederhergestellt:

  - **Active Directory-Domänendienste**   Sie müssen AD DS mithilfe der Active Directory-Tools gleichzeitig mit Lync Server sichern. Es ist wichtig, dass AD DS stets mit Lync Server synchronisiert ist. So können Probleme vermieden werden, die auftreten können, wenn von Lync Server Kontaktobjekte erwartet werden, die nicht mit denen in AD DS übereinstimmen. AD DS speichert die folgenden Einstellungen, die von Lync Server verwendet werden:
    
      - Den Benutzer-SIP-URI und andere Benutzereinstellungen
    
      - Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale
    
      - Ein Verweis auf den zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt) und Lync Server-Sicherheitsgruppen
    
    Ausführliche Informationen zum Sichern und Wiederherstellen von AD DS in Windows Server 2008 finden Sie im Artikel "Schrittweise Anleitung zur AD DS-Sicherung und -Wiederherstellung" unter <http://go.microsoft.com/fwlink/?linkid=209105>.

  - **Zertifizierungsstelle und Zertifikate**   Verwenden Sie die Richtlinie Ihrer Organisation zum Sichern der Zertifizierungsstelle und Zertifikate. Wenn Sie exportierbare private Schlüssel verwenden, können Sie das Zertifikat und den privaten Schlüssel sichern und anschließend exportieren, falls Sie die Verfahren in diesem Dokument zum Wiederherstellen von Lync Server verwenden. Wenn Sie eine interne Zertifizierungsstelle verwenden, können Sie sich erneut anmelden, falls Sie Lync Server wiederherstellen müssen. Sie müssen den privaten Schlüssel unbedingt an einem sicheren Ort verwahren, damit er beim Ausfall eines Computers verfügbar ist.

  - **System Center Operations Manager**   Wenn Sie Microsoft System Center Operations Manager (früher Microsoft Operations Manager) zum Überwachen Ihrer Lync Server-Bereitstellung verwenden, können Sie optional die beim Überwachen von Lync Server erstellten Daten sichern. Verwenden Sie den standardmäßigen SQL Server-Sicherungsvorgang zum Sichern von System Center Operations Manager-Dateien. Diese Dateien werden nicht in die Wiederherstellung einbezogen.

  - **Konfiguration des PSTN-Gateways**   Wenn Sie Enterprise-VoIP oder Survivable Branch Appliances verwenden, müssen Sie die Konfiguration des PSTN-Gateways sichern. Informationen zum Sichern und Wiederherstellen der Konfiguration von PSTN-Gateways erhalten Sie vom jeweiligen Hersteller.

  - **Parallele Versionen von Lync Server oder Office Communications Server**   Wenn parallel zu Ihrer Lync Server 2013-Bereitstellung Lync Server 2010 oder eine frühere Version von Office Communications Server vorhanden ist, können Sie die in diesem Dokument beschriebenen Verfahren nicht zum Sichern oder Wiederherstellen der früheren Version verwenden. Stattdessen müssen Sie die speziell für Ihre frühere Version dokumentierten Sicherungs- und Wiederherstellungsverfahren verwenden. Ausführliche Informationen zum Sichern und Wiederherstellen von Lync Server 2010 finden Sie unter <http://go.microsoft.com/fwlink/?linkid=265417> . Ausführliche Informationen zum Sichern und Wiederherstellen von Microsoft Office Communications Server 2007 R2 finden Sie unter<http://go.microsoft.com/fwlink/?linkid=168162>.

  - **Infrastrukturinformationen**   Sie müssen die Informationen zu Ihrer Infrastruktur sichern, wie z. B. die Firewallkonfiguration, die Konfiguration für den Lastenausgleich, die Konfiguration für Internetinformationsdienste (Internet Information Services, IIS), DNS-Einträge (Domain Name System) und IP-Adressen sowie die DHCP-Konfiguration (Dynamic Host Configuraton-Protokoll). Ausführliche Informationen zum Sichern dieser Komponenten erhalten Sie vom jeweiligen Hersteller.

  - **Microsoft Exchange und Exchange Unified Messaging (UM)**   Gehen Sie zum Sichern und Wiederherstellen von Microsoft Exchange und Exchange UM wie in der Microsoft Exchange-Dokumentation beschrieben vor. Ausführliche Informationen zum Sichern und Wiederherstellen von Exchange Server 2013 finden Sie unter <http://go.microsoft.com/fwlink/?linkid=285384>. Ausführliche Informationen zum Sichern und Wiederherstellen von Exchange Server 2010 finden Sie unter <http://go.microsoft.com/fwlink/?linkid=209179>.
    
    Beachten Sie, dass es in Lync Server 2013 jetzt möglich ist, Benutzerkontaktlisten, HD-Benutzerfotos und Archivierungsdaten in Exchange 2013 zu speichern. Der folgenden Liste können Sie entnehmen, wie diese Datentypen gesichert werden:
    
      - **HD-Fotos** werden als Teil der Exchange Server-Sicherung gesichert.
    
      - Der **einheitliche Kontaktspeicher** wird in Lync Server 2013 eingeführt. Der einheitliche Kontaktspeicher ermöglicht Benutzern, ihre gesamten Kontaktinformationen in Exchange 2013 zu speichern.
        
        Sie sollten sicherstellen, dass die Sicherungen für Benutzer aktuell sind, wenn es darum geht, ob die Benutzerkontakte im einheitlichen Kontaktspeicher oder auf dem Lync-Back-End-Server gespeichert werden. Die folgenden Szenarien veranschaulichen, wann die Migration von Benutzerkontakten zum einheitlichen Kontaktspeicher zu Problemen beim Sicherungs- und Wiederherstellungsprozess führen kann.
        
        **Szenario 1:** Benutzerkontakte werden zum einheitlichen Kontaktspeicher migriert, und aus einer Lync Server-Sicherung, die vor der Migration der Benutzerkontakte erstellt wurde, wird eine Wiederherstellung durchgeführt. In diesem Szenario hat der Benutzer für einen Zeitraum von bis zu einem Tag veraltete Kontakte, bis die Lync Server-Migrationsaufgabe mit dem Migrieren von Benutzerkontakten zu Exchange beginnt. (Hinweis: Da die Benutzerkontakte zuvor zum einheitlichen Kontaktspeicher migriert wurden, werden die Exchange-Kontaktinformationen verwendet). In diesem Szenario ist kein Eingreifen des Administrators erforderlich.
        
        **Szenario 2:** Für die zuvor im einheitlichen Kontaktspeicher gespeicherten Benutzerkontakte wird ein Rollback ausgeführt. Aus einer Lync Server-Sicherung, die beim Speichern der Benutzerkontakte im einheitlichen Kontaktspeicher erstellt wurde, wird eine Wiederherstellung durchgeführt. In diesem Szenario kann die Fehlermeldung `Error: Incorrect Exchange Version` in den Client- oder Lyss-Serverprotokollen darauf hindeuten, dass ein Problem vorliegt. Der Benutzer kann direkt von Exchange aus auf seine Kontaktliste in Lync 2013 zugreifen, aber der Clientstatus entspricht nicht dem Lync Server-Status. Um dieses Problem zu beheben, muss ein Administrator die **Invoke-CsUCSRollback**-Cmdlets für die betroffenen Benutzer ausführen.
    
      - **Archivierungsdaten** können in Exchange 2013 gespeichert werden. Diese Daten spielen für Lync Server keine wichtige Rolle, jedoch möglicherweise für Ihre Organisation aus Gründen der Einhaltung von Bestimmungen. Wenn die Archivierungsdaten in Exchange gespeichert werden und für Ihre Organisation wichtig sind, folgen Sie den Exchange-Sicherungs- und -Wiederherstellungsverfahren. Beachten Sie, dass die in Exchange gespeicherten Archivierungsdaten nicht zurück zu Lync Server verschoben werden können. Darüber hinaus gibt es keine Möglichkeit, die bereits in der Lync-Archivierungsdatenbank gespeicherten Daten zu Exchange zu verschieben.

