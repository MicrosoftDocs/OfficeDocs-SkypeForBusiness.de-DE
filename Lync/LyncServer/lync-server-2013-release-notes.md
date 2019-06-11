---
title: 'Lync Server 2013: Anmerkungen zu dieser Version'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Anmerkungen zu dieser Version für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Willkommen bei den Versionshinweisen zu lync Server 2013. Informationen zu bekannten Problemen mit lync Server 2013 finden Sie in dieser Datei.

<div>

## <a name="about-this-document"></a>Informationen zu diesem Dokument

Dieses Dokument enthält wichtige Informationen, die Sie vor der Bereitstellung und Verwendung von lync Server 2013 wissen sollten. Details zu lync Server 2013 finden Sie in der Dokumentation zu [Microsoft lync Server 2013](microsoft-lync-server-2013.md) .

Dieses Dokument enthält die folgenden Abschnitte:

  - Lync 2013-Client

  - Lync Server

  - Installation

  - Mobilität

  - Konferenzen

  - Enterprise-VoIP

  - Anwesenheit

  - Reaktionsgruppenanwendung und Anwendung zum Parken von Anrufen

  - Lync Server-Systemsteuerung, Topologie-Generator und Planungstool

  - Lokalisierung

  - Copyright

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013-Client

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>Das übertragen einer Datei in einer Chatnachricht schlägt fehl, wenn die Datei in einer anderen Anwendung geöffnet ist

**Problem**

Wenn Sie versuchen, eine Datei (beispielsweise ein Word-Dokument) zu übertragen, indem Sie Sie in eine Chatnachricht an einen anderen lync-Benutzer einbinden, scheint die Übertragung erfolgreich zu sein, kann die Datei jedoch tatsächlich nicht übertragen. Ein Symbol für den Dateityp wird im lync-Client angezeigt, aber die Datei kann nicht vom vorgesehenen Empfänger geöffnet werden. Es wird keine Fehlermeldung angezeigt, in der Sie darüber informiert werden, dass die Übertragung nicht erfolgreich war.

**Workaround**

Um dieses Problem zu umgehen, schließen Sie die geöffnete Datei oder Anwendung, die Sie geöffnet hat, bevor Sie versuchen, die Datei in einer Sofortnachricht zu übertragen.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Wenn die Datenreplikation des lync Server-Speicher Diensts fehlschlägt, müssen Administratoren Leistungsindikatoren für veraltete Speicherdienst-Warteschlangenelemente überprüfen.

**Problem**

Der lync Server-Speicherdienst verwendet Windows-Fabric für die Replikation. Wenn Daten auf einem primären Front-End-Server gelöscht werden, der Löschvorgang auf einem sekundären Front-End-Server jedoch fehlschlägt, beispielsweise wenn ein unerwartetes Herunterfahren oder ein Fehler auf dem Front-End-Server vorliegt, können Daten zurückgelassen und "verwaist" werden. Die verwaisten Daten können dazu führen, dass die Leistung beeinträchtigt und der Festplattenspeicherplatz abgenutzt wird.

**Workaround**

Um dieses Problem zu umgehen, wenn die Ereignisse Lyss\_DB\_Space\_verwendet\_Fehler (ID = 32058) und Lyss\_DB\_Speicher\_Platz\_verwendet kritisch (ID = 32059) werden im Ereignisprotokoll generiert, sollten Administratoren die Überprüfung der Leistungsindikator auf dem Front-End-Server unter **ls: Lyss-Storage Service API** mit dem Namen **Lyss-aktuelle Anzahl von veralteten Warteschlangenelementen des Speicher Diensts**. Wenn dieser Leistungsindikator einen höheren Wert aufweist, beispielsweise größer als 50000, sollte der Administrator das Tool "CleanuUpStorageServiceData. exe" im lync Server 2013 Resource Kit ausführen, in dem alle verwaisten Daten aus dem Pool gelöscht werden. Details zum Tool finden Sie in der Dokumentation zum lync Server 2013 Resource Kit.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Wenn die IP-Adresskonfiguration für einen Server oder Pool geändert wird, müssen die lync Server-Dienste neu gestartet werden.

**Problem**

Wenn die IP-Adressenkonfiguration für eine lync Server 2013-Bereitstellung geändert wird, wie beispielsweise das Wechseln von IPv4 zu Dual Stack oder von Dual Stack zu IPv6, greifen nicht alle Server Komponenten die Konfigurationsänderung an, bis die Dienste neu gestartet werden.

**Workaround**

Um dieses Problem zu umgehen, starten Sie lync Server Services neu, nachdem Sie die IP-Adressenkonfiguration für die Bereitstellung geändert haben. Führen Sie dazu die folgenden Cmdlets in der lync Server-Verwaltungsshell aus:

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Das Cmdlet "synthetische Einwahlkonferenzen" steht im lync Server 2013-Management Pack nicht mehr zur Verfügung.

**Problem**

Das Cmdlet **Test-CsDialInConferencing** für Einwahlkonferenz-synthetische Transaktionen steht im lync Server 2013-Management Pack nicht mehr zur Verfügung.

**Workaround**

Die Verwendung des Cmdlets **Test-CsDialInConferencing** für Einwahlkonferenzen in synthetischen Transaktionen wird nur intern für ein Unternehmen unterstützt.

Administratoren können das Cmdlet weiterhin zur Problembehandlung in der lync Server-Verwaltungsshell verwenden. Falls erforderlich, kann ein Unternehmen auch ein privates Management Pack entwickeln, um das Cmdlet intern auszuführen.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>Der zentralisierte Protokollierungsdienst wird angehalten, wenn der Netzwerkdatenverkehr gestört wird, wenn Protokolldateien auf die Netzwerkfreigabe kopiert werden.

**Problem**

Wenn der zentralisierte Protokollierungsdienst für die Verwendung eines Netzwerkpfads konfiguriert ist (der Wert des CacheFileNetworkFolder-Parameters des Cmdlets **Get-CsClsConfiguration** ist ein gültiger UNC-Pfad), werden zwischengespeicherte Protokolldateien in die Netzwerkfreigabe kopiert. Wenn im Netzwerkdatenverkehr eine Unterbrechung auftritt, während die Dateien kopiert werden, wird eine Ausnahme ausgelöst, die dazu führt, dass der zentralisierte Protokollierungsdienst beendet wird.

Der Dienst ist so konfiguriert, dass er bis zu dreimal automatisch neu gestartet wird, sodass der Dienst nach den ersten drei Ausnahmen wiederhergestellt wird.

**Workaround**

Für dieses Problem gibt es keine Problemumgehung. Um das Problem zu identifizieren, überwachen Sie das Ereignisprotokoll für die Ereignis-ID 7031 aus dem "Dienststeuerungs-Manager", der protokolliert, wenn der Dienst "lync Server-zentralisierter Protokollierungsdienst-Agent" unerwartet beendet wurde. Wenn dies mehr als dreimal passiert, starten Sie den Dienst manuell mit dem Cmdlet **Start-CsWindowService** neu.

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Speicherdienst-Warteschlangenelemente müssen manuell importiert werden

**Problem**

Lync Server 2013 speichert Daten zu Konferenzen und Instant Messaging, wie archivierte Nachrichten und CDR (Call Detail Recording), in einer Datenbank auf jedem Front-End-Server. Die Daten werden während der Verarbeitung in der Datenbank gespeichert, bevor Sie an das vorgesehene Ziel übermittelt werden. Um die Leistung zu verbessern, exportiert lync Server 2013 in regelmäßigen Abständen die Warteschlangenelemente aus der lokalen Datenbank, die für einen längeren Zeitraum nicht verarbeitet werden, und speichert Sie im Dateispeicher. Wenn der Dateispeicher nicht verfügbar ist, werden die Elemente auf jedem Front-End-Server gespeichert. Derselbe Vorgang tritt auf, um Datenverluste während des Pool-Failovers zu verhindern.

Während des Exportvorgangs zeichnet der lync Server-Speicherdienst alle Phasen im Ereignisprotokoll mit Ereignis-IDs von 32075 auf (vollständiger Flush-Vorgang wird gestartet), 32076 (vollständiger Flush ist abgeschlossen), 32082 (Maintenance Level Flush wird gestartet), 32083 (Wartungsebene bündig ist abgeschlossen), 32089 (Flush ist aufgrund des Befüllens der Datenbank aufgetreten). Diese Daten werden nicht automatisch zurück in das System importiert, um verarbeitet und an das endgültige Ziel (SQL Server oder Exchange Server) übermittelt zu werden.

**Workaround**

Um die Daten in das System zu importieren, müssen Administratoren das ImportStorageServiceData-Tool im lync Server Resource Kit verwenden, das die Daten wieder in das System einfügt, damit Sie verarbeitet und an das endgültige Ziel übermittelt werden.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Bei der Suche von Adressbuch-Webabfragen tritt ein Fehler auf, wenn der Standardwert für UseNormalizationRules in false geändert wird.

**Problem**

Wenn der Standardwert für UseNormalizationRules in false geändert wird, schlägt die Suche nach Adressbuch-Webabfragen fehl. Nachdem der Standardwert geändert wurde, können lync-Client Benutzer keine lync-Adressbuch-Webabfrage verwenden, um nach Benutzern zu suchen.

**Workaround**

Wenn der Standardwert für UseNormalizationRules auf "false" festgelegt ist, damit Benutzer Telefonnummern verwenden können, die in Active Directory-Domänendiensten ohne lync Server 2013 angewendet werden, um Normalisierungsregeln anzuwenden, gehen Sie wie folgt vor, um dieses Problem zu umgehen:

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Ihre Bereitstellung nur lync Server 2013-Server umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für UseNormalizationRules und IgnoreGenericRules auf "true" zu ändern:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013-Pool in der Topologie zu:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Warten Sie, bis die CMS-Replikation in allen Pools durchgeführt wird.

4.  Ändern Sie die Regeldatei für die Telefon Normalisierungsregeln für Ihre Bereitstellung, um den Inhalt zu löschen. Die Datei befindet sich auf der Dateifreigabe der einzelnen lync Server 2013-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen\_"\_unter\_nehmens\_-Telefonnummern-Normalisierungsregeln. txt".

5.  Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6.  Führen Sie das folgende Cmdlet für jeden lync Server 2013-Pool in Ihrer Bereitstellung aus.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>Das Adressbuch Server-Fehlerereignis 21054 wird einmal täglich für jeden lync 2013-Pool generiert.

**Problem**

Der lync Server 2013-Adressbuchserver generiert das Fehlerereignis 21054 einmal täglich, wenn die tägliche Wartung durchgeführt wird. Der Fehler wird auch jedes Mal generiert, wenn ein Administrator das **Update-csAddressBook-** Cmdlet ausführt, auch wenn das Update erfolgreich ausgeführt wurde. Dieses Fehlerereignis kann jedoch bedenkenlos ignoriert werden, wenn das Update erfolgreich ist.

**Workaround**

Wenn dieses Fehlerereignis auftritt, führen Sie das folgende Cmdlet aus:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Wenn das Cmdlet meldet, dass keine nicht indizierten oder verlassenen Objekte vorhanden sind, kann das Fehlerereignis 21054 problemlos ignoriert werden.

Darüber hinaus sollte der Schlüssel Integritätsindikator (Khi) "Adressbuch Benutzer richtig indiziert" in System Center Operations Manager deaktiviert sein.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Anforderungen können fehlschlagen, wenn IPv6 in einem Edge-Pool konfiguriert ist

**Problem**

Wenn IPv6 in einem Edge-Pool konfiguriert ist, treten möglicherweise einige Anforderungen an den Edge-Pool fehl.

**Workaround**

Um dieses Problem zu umgehen, konfigurieren Sie keinen Edge-Pool mit IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>Das Cmdlet "Invoke-csPoolFailback" schlägt möglicherweise während des Failback des Pools fehl

**Problem**

Beim Versuch, einen Pool zurückzukehren, schlägt das Cmdlet **Invoke-csPoolFailback** möglicherweise mit dem Fehler "Fehler beim Durchführen des hydratations Prozesses nach wiederholtem Versuch" fehl.

**Workaround**

Um dieses Problem zu umgehen, führen Sie das Cmdlet erneut aus, und warten Sie, bis das Cmdlet erfolgreich ausgeführt wurde. Beachten Sie, dass die Ausführung des Failback-Vorgangs einige Minuten dauern kann. Für einen Pool mit 20.000-Benutzern kann es bis zu 60 Minuten dauern.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Datenverlust kann auftreten, wenn Sie einen Front-End-Server zu einem bereits eingerichteten Pool hinzufügen – Hybrid, Skype for Business Online

**Problem**

Dieses Problem kann in einer Umgebung auftreten, in der ein Pool über mehr als einen Front-End-Server verfügt und Sie entweder einen der Front-End-Server neu starten oder einen neuen Front-End-Server hinzufügen, der zuvor nicht Teil des Pools war.

Benutzer, deren Daten archiviert werden, können Datenverluste erfahren, bis eine stabile Verteilung der Datenarchivierung für den Pool eingerichtet ist. Dieser Zeitraum des potenziellen Datenverlusts ist auf 15 Minuten für Gespräche zwischen zwei Personen und 30 Minuten für Konferenzen limitiert.

**Workaround**

Wenn Sie die Wartung durchführen, sollten Sie statt der Front-End-Server einzeln im Pool einen Failover für den Pool zu einem anderen Pool durchführen und dann Wartungsaufgaben auf den Servern ausführen. Sie können den Dienst auch vor dem Ausführen von Wartungsaufgaben nicht mehr verfügbar machen und dann die Verfügbarkeit wiederherstellen, wenn die Wartung abgeschlossen ist.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Administratoren können die Anzahl der Lizenznehmer nicht mithilfe des Cmdlets Get-CsClientAccessLicense abrufen.

**Problem**

Administratoren können mit dem Cmdlet **Get-CsClientAccessLicense** keine genaue Clientlizenz Verwendung erhalten.

**Workaround**

Zum Überprüfen des Server Lizenztyps können Sie das Cmdlet **Get-CsService** ausführen, um die vollqualifizierten Domänennamen (FDQNs) aller Datenbanken abzurufen. Wenn der FQDN des Front-End-Servers mit dem FQDN der Back-End-Datenbank identisch ist, handelt es sich bei der Lizenz um eine Standard Edition-Lizenz. Andernfalls handelt es sich bei der Lizenz um eine Enterprise Edition-Lizenz.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>Anzahl der Client-Lizenzen wird nicht genau gemeldet

**Problem**

Wenn Sie die Anzahl der Clientlizenzen ermitteln, treten möglicherweise die folgenden Bedingungen auf:

1.  **Ungenaue Lizenzanzahl für mobile Benutzer**
    
    Die Anzahl der Lizenzen basiert auf der Anzahl der eindeutigen IP-Adressen für gerätebasierte Benutzer. Die Anzahl der Lizenzen ist wie folgt limitiert:
    
      - Lizenzen werden über gezählt, wenn sich die IP-Adresse des Benutzers während lync-Sitzungen ändert. Dies kann auftreten, wenn ein Benutzer mit einem Desktop Client eine Verbindung mit lync Server von mehr als einem Standort herstellt.
    
      - Lizenzen werden untersucht, wenn ein Benutzer eine Verbindung mit einem mobilen Client herstellt, weil die IP-Adresse für das Gerät nicht ermittelt werden kann.

2.  **Lizenzen werden zweimal für PSTN-Anrufe (Public Switched Telephone Network) an lync-Client, lync-Client Anrufe an PSTN-Leitungen und lync-Anrufe, die an PSTN-Leitungen weitergeleitet werden, gezählt.**
    
    In den folgenden Szenarien werden zwei zusätzliche Lizenzen anstatt eines gezählt, weil sowohl die Telefonnummer als auch der lync-Benutzer gezählt werden, um die Anzahl der verwendeten Lizenzen zu ermitteln. Um genaue Lizenzierungsdaten zu erhalten, entfernen Sie manuell die von einer Telefonnummer generierten Lizenzen.
    
      - Ein PSTN-Telefonanruf an lync
    
      - Ein lync-Anruf an eine PSTN-Leitung
    
      - Ein PSTN-Anruf an lync, und lync leitet den Anruf an eine PSTN-Leitung weiter. Eine der PSTN-Linien wird gezählt.

3.  **Eine Lizenz wird nicht für ein angemeldetes lync-Telefon gezählt**
    
    Wenn ein Benutzer ein lync-zertifiziertes Telefon verwendet, wenn sich das Telefon anmeldet und verbunden bleibt, wodurch sein Anmeldestatus beibehalten wird, wird das Telefon nicht als Verwendung einer Lizenz gewertet, wenn die Abfrage für Lizenzen nach dem Einloggen des Telefons erfolgt.

4.  **Lizenzen für PSTN-Telefone, die an Konferenzen teilnehmen**
    
    Wenn ein Benutzer mit einem PSTN-Telefon an einer Konferenz teilnimmt, wird eine Lizenz für die Teilnahme an der Konferenz ungenau gezählt. Es ist jedoch keine Lizenz erforderlich, um mit einem PSTN-Telefon an einer Konferenz teilzunehmen.

**Workaround**

1.  **Ungenaue Lizenzanzahl für mobile Benutzer**
    
      - Sie können die IP-Adressen, die zum gleichen Gerät gehören, manuell identifizieren und dann eine davon in der Anzahl der Lizenzen entfernen.
    
      - Für dieses Problem gibt es keine Problemumgehung bei mobilen Geräten, die mit dem lync-Client verbunden sind.

2.  **Lizenzen werden zweimal für PSTN-Anrufe an lync-Client, lync-Client Anrufe an PSTN-Leitungen und lync-Anrufe an PSTN-Leitungen weitergeleitet.**
    
    Sie müssen die PSTN-Telefonnummer manuell identifizieren und die für Sie generierte Lizenzanzahl entfernen.

3.  **Eine Lizenz wird nicht für ein angemeldetes lync-Telefon gezählt**
    
    Sie können das lync-Telefon so konfigurieren, dass es sich abmeldet, und sich dann in regelmäßigen Abständen erneut anmelden, beispielsweise alle drei Monate.

4.  **Lizenzen für PSTN-Telefone, die an Konferenzen teilnehmen**
    
    Sie können die PSTN-Telefonnummer, die für die Teilnahme an der Konferenz verwendet wird, manuell identifizieren und die von der Telefonnummer generierte Lizenz entfernen.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Die lync Server-Systemsteuerung funktioniert nach dem Upgrade auf Silverlight 5 nicht mehr in einer VMware-Umgebung

**Problem**

Wenn Sie die lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert die lync Server-Systemsteuerung nach dem Upgrade von Microsoft Silverlight auf Version 5 möglicherweise nicht mehr.

**Workaround**

Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:

  - Deinstallieren Sie Silverlight 5, und installieren Sie Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)4 aus.

  - Greifen Sie auf die lync Server-Systemsteuerung auf einem Computer zu, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.
    
    Zu diesem Zweck können Sie die lync Server-Systemsteuerung über das Windows- **Startmenü** auf dem Server starten, wenn die lync Server-Verwaltungstools auf dem Computer installiert sind.
    
    Sie können auch mithilfe eines Webbrowsers auf die lync Server-Systemsteuerung zugreifen. Die URL ist\<mit dem FQDN\_\_\>des https://-Front-Pools vergleichbar/CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Benutzerinformationen im Adressbuchdienst werden nicht aktualisiert, nachdem der Distinguished Name für den Benutzer in Active Directory geändert wurde.

**Problem**

Wenn der Distinguished Name eines Benutzers (auch bekannt als DN) in den Active Directory-Domänendiensten geändert wird, werden alle weiteren Änderungen im Adressbuchdienst (ABS) nicht aktualisiert. Dies wirkt sich nicht auf die Anmeldung oder Anwesenheit des Benutzers aus, es wird jedoch die Kommunikation für den Benutzer verhindert, wenn die SIP-Adresse ebenfalls geändert wird, da durch Suchvorgänge eine veraltete SIP-Adresse zurückgegeben wird.

**Workaround**

Um dieses Problem zu umgehen, ändern Sie den DN eines Benutzers nicht. Wenn Sie den DN für den Benutzer auf den vorherigen Wert zurücksetzen, werden Updates im Adressbuchdienst wiedergegeben.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Installation

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>Die Verwendung von nicht-ASCII-Zeichen kann dazu führen, dass lync Server nicht gestartet wird

**Problem**

Das Setup schlägt fehl, wenn der Name des Zielordners nicht-ASCII-Zeichen enthält (einschließlich Unicode, Doppelbyte-Zeichensatz (DBCS), UTF-8 und UTF-16). Darüber hinaus kann Setup erfolgreich ausgeführt werden, aber der Server wird nicht gestartet, wenn in einer der folgenden nicht-ASCII-Zeichen enthalten sind:

  - Computer Name

  - Domänenname

  - Benutzername

  - SIP-URI des Benutzers

  - Dienstkontoname

**Workaround**

Verwenden Sie nur ASCII-Zeichen im Zielordnernamen, Computername, Domänenname, Benutzername, SIP-URI des Benutzers und Dienstkontonamen.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>Der Hotfix für "Heap Beschädigung tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5" aufruft, muss vor der Installation von lync Server 2013 installiert werden.

**Problem**

Der Hotfix für "Heap Beschädigungen tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" () aufruft, die im Microsoft[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)Knowledge Base-Artikel 264886 () beschrieben wird, muss vor der Installation von lync Server 2013 installiert werden.

**Workaround**

Laden Sie den Hotfix aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)herunter, und installieren Sie ihn.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 kann unter ITA Windows Server 2012 OS RTM-Version nicht installiert werden

**Problem**

Die Installation von lync Server 2013 schlägt auf ITA Windows Server 2012 aufgrund einer fehlgeschlagenen Windows-Fabric-Installation fehl.

Die Windows-Fabric-Installation schlägt fehl, da Fabric-Ablaufverfolgungen mit dem Zeitformat HH: mm: SS erstellt werden. In ITA Windows Server ist das Uhrzeitformat jedoch hh. MM.SS.

**Workaround**

Um dieses Problem zu umgehen, aktualisieren Sie die Systemregistrierung, bevor Sie lync Server 2013 installieren. Der Registrierungsschlüssel, der aktualisiert werden muss, lautet:\_HKEY\\-Benutzer. Standard\\mäßiges\\Control\\Panel für internationale sTimeFormat. Ändern Sie den Wert von sTimeFormat in hh: mm: SS, indem Sie die Windows PowerShell-Befehlszeilenschnittstelle wie folgt verwenden:

1.  Starten Sie Windows PowerShell, und führen Sie die folgenden Cmdlets aus:
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Führen Sie zum Anzeigen des aktuellen Werts das folgende Cmdlet aus:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Notieren Sie sich den aktuellen Wert für sTimeFormat, damit er nach Abschluss der Installation wiederhergestellt werden kann.

3.  Wenn Sie auf neuen Wert setzen möchten, führen Sie das folgende Cmdlet aus:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Nachdem lync Server 2013 erfolgreich installiert wurde, stellen Sie den ursprünglichen Wert für sTimeFormat wieder her, indem Sie das folgende Cmdlet ausführen:
    
        - Setitemproperty $a-Name sTimeFormat-Wert "<Wert, der in Schritt 3 notiert wurde. über> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilität

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Probleme für mobile Clients während des Server Failover-Prozesses

**Problem**

Wenn ein lync-Server ausfällt und der Failoverprozess beginnt, können sich die folgenden Probleme auf Mobile Client-Benutzer auswirken:

  - Kein eingehender lync-Anruf oder Signal für bis zu 10 Minuten nach Beginn des Failovers.

  - Eingehende Chat-Anfragen können nicht akzeptiert werden

  - Teilnahme an Besprechungen ist nicht möglich, wenn der fehlerhafte Server der Stammserver für den Benutzer ist

**Workaround**

Für dieses Problem gibt es keine Problemumgehung. Die normale Funktionalität wird nach Abschluss des Failover-Vorgangs wiederhergestellt.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Wenn ein mobiler Benutzer einen eingehenden Anruf von einem anderen lync-Endpunkt ablehnt, wird der Anruf als verpasste Konvertierung auf lync Mobile-Clients angezeigt.

**Problem**

Wenn ein mobiler Benutzer einen eingehenden Anruf ablehnt und der Anruf von einem anderen lync-Endpunkt stammt, wird der Anruf im lync Mobile-Client anstelle eines Anrufs in der Geräte Anrufliste als verpasste Unterhaltung angezeigt.

**Workaround**

Für dieses Problem gibt es keine Problemumgehung.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Beim Suchen nach Kontakten wird vom mobilen Client möglicherweise der Anzeigename des verbundenen Kontakts nicht angezeigt

**Problem**

Der Anzeigename für Verbund Kontakte wird in einigen Szenarien möglicherweise nicht angezeigt, beispielsweise bei der Suche nach einem Verbundkontakt in der Kontaktliste. Dies kann auftreten, wenn das Abonnement für den Kontakt nicht über den lync Mobile-Client vorhanden ist.

**Workaround**

Für dieses Problem gibt es keine Problemumgehung.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>In einer verpassten Unterhaltung, bei der es sich um eine Einladung zu einer Konferenz handelt, fehlen im mobilen Clientinformationen zu invite und TIMESTAMP.

**Problem**

Wenn eine verpasste Unterhaltung im mobilen Client eine Einladung zu einer Konferenz ist, fehlen die Informationen zum einladen und Zeitstempel in der Nachricht für verpasste Unterhaltungen.

**Workaround**

Für dieses Problem gibt es keine Problemumgehung.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Benutzer von mobilen Clients, die VoIP-Anrufe tätigen, können Voicemail nicht für Benutzer hinterlassen, deren Voicemail in Exchange 2010 oder früheren Versionen konfiguriert ist.

**Problem**

Wenn ein mobiler Client-Benutzer VoIP für Anrufe verwendet, kann der Benutzer keine Voicemail-Nachrichten für Benutzer hinterlassen, die für die Verwendung von Voicemail in Microsoft Exchange Server 2007 oder Microsoft Exchange Server 2010 konfiguriert sind.

**Workaround**

Um dieses Problem zu umgehen, verwenden Sie Exchange 2010 mit SP1 oder einer höheren Version von Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Bei Verwendung von Block mit URL für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt

**Problem**

Bei Verwendung von **Block mit URL** für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt, wenn die Client Version nicht unterstützt wird.

**Workaround**

Um dieses Problem zu umgehen, konfigurieren Sie die Client Versions Konfiguration so, dass **Block** anstelle von **Block mit URL**verwendet wird.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Konferenzen

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Antivirensoftware, die auf den lync Server 2013-Front-End-Servern ausgeführt wird, kann zu einer Anwendungsdomänen Wiederverwendung führen, die den Dienst für lync Web App 2013, lync Mobile 2010 und lync Mobile 2013-Clients vorübergehend unterbricht.

**Problem**

Antivirensoftware kann Neustart der Anwendungsdomäne auslösen, was dazu führen kann, dass lync Mobility Service 2013 und Unified Communications (UC) Web-API-Clientanwendungen (lync Web App 2013, lync Mobile 2010 und lync Mobile 2013) ihren Zustand verlieren.

**Workaround**

Um dieses Problem zu umgehen, schließen Sie die Ordner, die Webkomponenten und .NET Framework enthalten, von der Antivirus-Prüfung aus. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 312592, "PRB: zufällige Anwendungsneustarts mit der Anwendung wird neu gestartet"-Fehler in ASP.net [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).

Die folgenden Ordner sollten ausgeschlossen werden:

  - % Programme%\\Microsoft lync Server 2013\\Web Components\\MCX\\ext

  - % Programme%\\Microsoft lync Server 2013\\Web Components\\MCX\\int

  - % Programme%\\Microsoft lync Server 2013\\Web Components\\Ucwa\\int

  - % Programme%\\Microsoft lync Server 2013\\Web Components\\Ucwa\\ext

  - % Windir%\\Microsoft.net\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>ActiveX-Steuerelemente oder Native XMLHTTP-Unterstützung müssen in Windows Internet Explorer aktiviert sein, damit Sie erfolgreich an Konferenzen teilnehmen können.

**Problem**

Wenn ein Benutzer sowohl ActiveX-Steuerelemente als auch die Native XMLHTTP-Unterstützung in den Internetbrowsereinstellungen von Windows Internet Explorer deaktiviert hat, kann der Benutzer nicht an einer Besprechung teilnehmen, wenn Internet Explorer als Standardbrowser ausgewählt ist.

**Workaround**

Aktivieren Sie entweder ActiveX-Steuerelemente oder "Native XMLHTTP-Unterstützung" in Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Der lync Server-Webkonferenzdienst kann im kritischen Modus nicht wiederhergestellt werden

**Problem**

Wenn der kritische Modus für die Archivierung aktiviert ist, wird bei Systemfehlern der kritische Modus gestartet, und die Konferenzen funktionieren nicht mehr für die Teilnehmer. Nachdem der Administrator die Systemfehler (wie das Beheben eines Datenbankproblems) behoben hat, wird der Datenkonferenzdienst nicht automatisch wiederhergestellt, und der Administrator muss den Konferenzdienst manuell neu starten, damit die Konferenz fortgesetzt werden kann.

**Workaround**

Ein Administrator muss den Konferenzdienst manuell neu starten, nachdem der Systemfehler behoben wurde.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Webkonferenzdienst ignoriert den HTTP-Proxy für externe Office Web App-Server

**Problem**

Wenn Sie einen Office Web Apps-Server außerhalb des Webkonferenz Diensts (also einen Server, der sich nicht im internen Unternehmensnetzwerk befindet) im Internet, Umkreisnetzwerk und dem Webkonferenzdienst bereitgestellt haben, erfordert ein HTTP-Proxy eine Verbindung mit diesem Die Server Ermittlung in Office Web Apps schlägt fehl. Der Webkonferenzdienst ignoriert die http-Proxyeinstellung, wie Sie im Topologie-Generator für Office Web Apps Server-Setup definiert ist. Infolgedessen kann der lync-Client keine Microsoft PowerPoint 2010-Freigabe für andere Teilnehmer an der Konferenz durchführen. Wenn Sie lync Server lokal installieren und auch Office Web Apps Server lokal im internen Netzwerk konfigurieren, ist keine Proxykonfiguration erforderlich.

**Workaround**

Die einzige Problemumgehung besteht darin, keine Bereitstellungskonfiguration zu verwenden, die die Verwendung des HTTP-Proxys für die Kommunikation mit einem externen Office Web Apps-Server erfordert.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>Das Hinzufügen von Video zu einer Konferenz für Audiokonferenz-Anbieter wird nicht unterstützt

**Problem**

Das Hinzufügen eines Videos wird nicht unterstützt, wenn der Benutzer zu einer Konferenz für Audio-Konferenz für Audio beigetreten ist.

**Workaround**

Für dieses Problem gibt es keine Problemumgehung.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologien mit aktiviertem IPv6 erzwingen die automatische Aktualisierung der lync Web App Silverlight-Plug-in, um sicherzustellen, dass die Bildschirmfreigabe Funktionalität in lync Web App funktionieren kann.

**Problem**

Wenn eine Topologie mit aktiviertem IPv6 konfiguriert ist, können Benutzer Ihren Bildschirm nicht über den lync Web App-Client freigeben, wenn bereits eine frühere Version des Plug-Ins für die Bildschirmfreigabe installiert ist.

**Workaround**

Wenn Sie ein Update auf die neueste Version des Plug-ins "Bildschirmübertragung" erzwingen möchten, wenn Sie über lync Web App an einer Besprechung teilnehmen, ändern Sie den Wert von **MinSupportedBuildVersion** von "4.0.7457.0" in "4.0.7577.380" in den beiden folgenden Dateien:

  - % Programme%\\Microsoft lync Server 15\\-\\Webkomponenten\\erreichen\\int\\-\\Client-Plugins ReachAppShPluginProperties. XML

  - % Programme%\\Microsoft lync Server 15\\-\\Webkomponenten\\erreichen\\Ext\\-\\Client-Plugins ReachAppShPluginProperties. XML

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise-VoIP

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>In einigen Fällen unterstützt ein lync-Client, der auf einem Computer ausgeführt wird, der für die Verwendung von IPv4 und IPv6 Dual Stack konfiguriert ist, möglicherweise keine Funktionen, die im IP-Subnetz des Computers wie E911, medienumgehung, Anrufsteuerung und standortbasiertes Routing basieren.

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.



</div>

**Problem**

Wenn ein lync-Client auf einem Computer ausgeführt wird, der für IPv4 und IPv6 Dual Stack aktiviert ist, und basierend auf der DNS-Auflösung des Proxyservers, kann der Client die IPv6-Adresse des Computers zur Anmeldung verwenden. Anschließend unterstützt der lync-Client nur die Funktionen, die für IPv6 unterstützt werden, was E911, medienumgehung, Anrufsteuerung und standortbasiertes Routing ausschließt.

**Workaround**

Um dieses Problem zu umgehen, deaktivieren Sie die IPv6-Unterstützung auf dem Clientcomputer.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss der Benutzer das E164-Format verwenden, um aus einer Konferenz heraus zu wählen.

**Problem**

Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss dieser Benutzer das E164-Format verwenden, um sich erfolgreich aus einer Konferenz zu wählen. Wenn das E164-Format nicht verwendet wird, kann der Benutzer nicht aus der Konferenz wählen.

**Workaround**

Um dieses Problem zu umgehen, sollten Benutzer, die nicht für Enterprise-VoIP aktiviert sind, mithilfe von Zahlen im E164-Format aus einer Konferenz wählen.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Anwesenheit

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Wenn ein Benutzer "alle Einladungen und Kommunikationen blockieren" ausgewählt hat, während der Unified Contact Store für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn er

**Problem**

Wenn ein Benutzer "alle Einladungen und Kommunikationen blockieren" ausgewählt hat, während der Unified Contact Store für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn er sein sollte.

**Workaround**

Um dieses Problem zu umgehen, können Sie den einheitlichen Kontaktspeicher für den Benutzer deaktivieren. Führen Sie dazu die folgenden Cmdlets aus:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Beispiel:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office Communications Server 2007 R2-Benutzer, die lokal gehostet werden, können den Anwesenheitsstatus von Skype for Business Online-Benutzern in hybridbereitstellungen nicht anzeigen – Hybrid

**Problem**

Das Problem kann bei einer hybridbereitstellung auftreten, wenn Sie einen lync Server 2013-Director verwenden.

Der Anwesenheitsstatus für Benutzer, die in Skype for Business Online verwaltet werden, wird als "Anwesenheitsstatus unbekannt" für lokale Benutzer angezeigt. Darüber hinaus können Benutzer, die in Skype for Business Online verwaltet werden, den Anwesenheitsstatus für Office Communications Server R2-lokale Benutzer nicht sehen.

**Workaround**

Um dieses Problem teilweise zu umgehen, ändern Sie den Home-Server (Attribut msRTCSIP-presencehomeserver) der Skype for Business Online-Benutzer so, dass Sie auf einen lokalen lync Server 2013-Pool anstatt auf den lync Server 2013-Director verweisen. Sie können diese Einstellung auf dem lokalen Front-End-Server ändern.

Mit dieser Problemumgehung wird der Anwesenheitsstatus von Benutzern, die in Office Communications Server 2007 R2 verwaltet werden, für Skype for Business Online-Benutzer korrekt angezeigt.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Antwortgruppen Anwendung, Anruf Park Anwendung und Gruppenanruf Abholung

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Ein Anrufer kann während der Einrichtung eines Anrufs mit der abrufenden Person eine Sekunde Musik hören

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.



</div>

**Problem**

Wenn ein Anruf über Gruppenanruf abgeholt wird, kann der Anrufer während der Einrichtung des Anrufs mit der Retriever-Partei eine Sekunde Musik hören.

**Workaround**

Für dieses Problem gibt es keine Problemumgehung.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Ein Reaktionsgruppen-Agent kann sich über eine lync Server 2010-Agent-Konsole an lync Server 2010 formelle Agentengruppen anmelden und abmelden.

**Problem**

Ein lync Server 2013-Reaktionsgruppen-Agent kann sich über eine lync Server 2010-Agent-Konsole an lync Server 2010 formelle Agentengruppen anmelden und abmelden. In der lync Server 2010-Agent-Konsole können Benutzer nur die lync Server 2010-Reaktionsgruppe sehen, der Sie angehören. Sie können keine der lync Server 2013-Antwortgruppen sehen, denen Sie angehören.

**Workaround**

Wenn der Reaktionsgruppen-Agent ein lync Server 2013-Benutzer und Teil einer formellen Agentengruppe von lync Server 2013 ist, muss der Benutzer direkt über einen Weblink in einem Browser auf die lync Server 2013-Agent-Konsole zugreifen, um sich bei lync Server 2013-Agentengruppen anzumelden und sich abzumelden.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Ein lync Server 2010-Reaktionsgruppen-Agent kann keine Anrufe im Auftrag einer lync Server 2013-Reaktionsgruppe tätigen

**Problem**

Ein lync Server 2010-Benutzer, der ein Agent einer lync Server 2013-Reaktionsgruppe ist, kann keinen Anruf im Namen der Reaktionsgruppe tätigen. Die lync Server 2013-Reaktionsgruppe ist im lync-Client nicht verfügbar, um einen Anruf zu tätigen.

**Workaround**

Um dieses Problem zu umgehen, müssen Sie den lync Server 2010-Benutzer in lync Server 2013 verschieben.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Wenn Sie eine Reaktionsgruppe aus lync Server 2010 entfernen, nachdem Sie zu lync Server 2013 migriert wurde, wird verhindert, dass die Reaktionsgruppe eingehende Anrufe akzeptiert.

**Problem**

Wenn eine Reaktionsgruppe, die von lync Server 2010 zu lync Server 2013 migriert wurde, aus lync Server 2010 über die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell entfernt wird, wird die Antwortgruppe in lync Server 2013 keine eingehenden Anrufe mehr empfangen.

**Workaround**

Um dieses Problem zu umgehen, entfernen Sie keine Antwortgruppen aus lync Server 2010, die von lync Server 2010 zu lync Server 2013 migriert wurden.

Wenn die Reaktionsgruppe bereits entfernt wurde, sollten Sie Sie in lync Server 2013 erneut bereitstellen.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv eingestellt ist, schlägt die Bereitstellung des Workflows fehl

**Problem**

Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv eingestellt ist, schlägt die Bereitstellung des Workflows fehl. Dieses Problem tritt auf, wenn der Workflow bei der Erstellung auf inaktiv festgesetzt wird, sich aber nicht auf einen Workflow auswirkt, der bearbeitet wird, um ihn nach der Bereitstellung von is auf inaktiv festzulegen.

**Workaround**

Wenn Sie einen Workflow erstellen und bereitstellen, legen Sie den Workflow als aktiv und dann bereitstellen. Nachdem der Workflow erfolgreich bereitgestellt wurde, kann der Workflow bearbeitet und auf inaktiv eingestellt werden.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>Durch das Entfernen einer Reaktionsgruppe aus dem Besitzer Pool wird verhindert, dass die Reaktionsgruppe des Sicherungs Pools eingehende Anrufe während eines Failovers akzeptiert, wenn die Reaktionsgruppe in den Sicherungspool importiert wurde.

**Problem**

Wenn eine Reaktionsgruppe, die im Besitz des primären Pools ist, in den Sicherungspool importiert wurde, ohne den Besitzer zu überschreiben, und die Reaktionsgruppe aus dem Besitzer Pool entfernt wird, akzeptiert die Reaktionsgruppe im Sicherungspool keine eingehenden Anrufe während eines Failovers.

**Workaround**

Sie müssen die Reaktionsgruppe im primären Pool erneut bereitstellen. Sie müssen dann die Konfiguration der Reaktionsgruppe aus dem primären Pool exportieren und erneut in den Sicherungspool importieren.

Sie können die Reaktionsgruppe auch im Sicherungspool neu erstellen. In diesem Fall ist der Sicherungspool der Besitzer Pool der Reaktionsgruppe.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Ein geparkter Anruf kann nicht aus der Anwendung für den Anruf Park abgerufen werden, wenn die Abrufanforderung im Auftrag einer Reaktionsgruppe erfolgt

**Problem**

Wenn die folgenden Bedingungen erfüllt sind, schlägt eine Abrufanforderung für einen geparkten Anruf fehl:

  - Ein Agent ist Teil einer anonymen Reaktionsgruppe

  - Der Agent versucht, einen geparkten Anruf aus der Anwendung "Anruf parken" über die Gruppe "anonyme Antwort" abzurufen.

  - Der Agent versucht, den Anruf abzurufen, indem er die Umlaufbahn Nummer über die Option "Anruf im Auftrag" oder über die gleiche Option im lync Attendant-Client anwählt.

**Workaround**

Für dieses Problem gibt es keine Problemumgehungen. Der geparkte Anruf sollte ohne diese Vorgehensweise im Namen einer Reaktionsgruppe abgerufen werden.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server-Systemsteuerung, Topologie-Generator und Planungstool

<div>

## <a name="planning-tool-limitations"></a>Einschränkungen des Planungstools

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.



</div>

**Problem**

Das Planungs Tool weist bei der Planung der Bereitstellung die folgenden Einschränkungen auf:

  - Es werden maximal 10 zentrale Websites unterstützt.

  - Jede zentrale Website kann maximal 14 Zweigstellen aufweisen.

  - Für jeden zentralen Standort können maximal 240.000-Benutzer vorhanden sein.

Darüber hinaus enthält das Planungs Tool beim Berechnen der empfohlenen Topologie keine Werte für die folgenden Elemente:

  - Die Anzahl der Benutzer, die Online verwaltet werden

  - Der Prozentsatz der Benutzer, die für die XMPP-Föderation aktiviert sind

  - Prozentsatz der Benutzer, die lync Web App verwenden

**Workaround**

Für diese Probleme gibt es keine Problemumgehung. Weitere Informationen zum Planungstool finden Sie unter [Entwerfen der Topologie für lync Server 2013 mithilfe des Planungstools](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>Das Planungs Tool verwendet beim Aktualisieren von Optionen möglicherweise nicht zuvor definierte IP-Adressen für das Edge-Netzwerk.

**Problem**

Nachdem Sie Ihren Entwurf mithilfe des Planungstools abgeschlossen haben, können Sie, wenn Sie Änderungen an den Edge-Netzwerkoptionen vornehmen, dem Entwurf zusätzliche IP-Adressen hinzugefügt werden, anstatt die vorhandenen IP-Adressen zu aktualisieren. Dies kann auftreten, wenn Sie die Details des Edge-Netzwerkdiagramms anzeigen, wählen Sie **Klicken Sie hier, um Ihre Optionen zu aktualisieren**, und wählen Sie dann im Dialogfeld Konfigurationsoptionen die Option Edge-Netzwerk auswählen **Ich möchte dieselben FQDNs und IP-Adressen verwenden, aber verschiedene Ports für die Edgedienst auf meinem Edgeserver** Das Anwenden von Änderungen kann dazu führen, dass neue IP-Adressen und Edgeserver dem Entwurf hinzugefügt werden.

**Workaround**

Für dieses Problem gibt es zurzeit keine Problemumgehung.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>In der lync Server-Systemsteuerung ist "alle Benutzer in Pool verschieben" möglicherweise nicht erwartungsgemäß

**Problem**

Wenn Sie die lync Server-Systemsteuerung verwenden, um alle Benutzer von einem Pool in einen anderen Pool in einer komplexen Active Directory-Umgebung zu verschieben, wie etwa eine mit mehreren Domänencontrollern und übergeordneten/untergeordneten Domänen, wird möglicherweise eine Fehlermeldung zurückgegeben, die besagt: "der angegebene Benutzer ist kein Legacy-Benutzer, verwenden Sie stattdessen das Cmdlet Move-CsUser. " Dies ist ein Ergebnis längerer Replikationszeiten in komplexen Active Directory-Umgebungen.

**Workaround**

Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:

  - Verwenden Sie Filter in der lync Server-Systemsteuerung, um nach Legacy Benutzern zu suchen, wählen Sie diese Benutzer aus, und verwenden Sie dann den **Befehl ausgewählte Benutzer in Pool verschieben,** anstatt **alle Benutzer in Pool zu verschieben**.

  - Verwenden Sie die lync Server-Verwaltungsshell, um ältere Benutzer in Batches mithilfe von lync Server-Cmdlets zu verschieben.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Die lync Server-Systemsteuerung funktioniert nicht mehr in einer VMware-Umgebung, nachdem das Microsoft Silverlight-Browser-Plug-in auf Version 5 aktualisiert wurde.

**Problem**

Wenn Sie die lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert die lync Server-Systemsteuerung nach dem Upgrade von Silverlight auf Version 5 möglicherweise nicht mehr.

**Workaround**

Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:

  - Deinstallieren Sie Silverlight 5, und installieren Sie dann Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)4 aus.

  - Öffnen Sie die lync Server-Systemsteuerung von einem Computer, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.
    
    Wenn Sie die lync Server-Systemsteuerung von einem Remotecomputer aus öffnen möchten, installieren Sie die lync Server-Verwaltungstools auf dem Computer, und starten Sie dann die lync Server-Systemsteuerung über das Windows- **Startmenü** .
    
    Sie können die lync Server-Systemsteuerung auch öffnen, indem Sie die URL in einem Webbrowser eingeben. Die URL ist\<mit dem FQDN\_\_\>des https://-Front-Pools vergleichbar/CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Ein Administrator kann das Cmdlet "deinstallieren-csMirrorDB" nach dem Entfernen der Spiegelungsdatenbank im Topologie-Generator nicht ausführen.

**Problem**

Wenn ein Administrator eine Spiegelungsdatenbank im Topologie-Generator deaktiviert und dann die Spiegelungsdatenbank im Topologie-Generator löscht, wird eine Meldung in der Aufgabenliste angezeigt, damit der Administrator das Deinstallations **-csMirrorDatabase-** Cmdlet ausführt, um es zu entfernen. Spiegelung von SQL Server. Wenn der Administrator versucht, das Cmdlet auszuführen, schlägt er fehl.

**Workaround**

Um die SQL-Spiegelung eines Pools in Topology Builder zu entfernen, müssen Sie zuerst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen. Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen. Verwenden Sie das folgende Cmdlet, um den Spiegel in SQL Server zu entfernen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Wenn Sie beispielsweise die Spiegelung entfernen und die Datenbanken für die Benutzerdatenbanken löschen möchten, geben Sie Folgendes ein:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Der *DropExistingDatabasesOnMirror* -Parameter bewirkt, dass die betroffenen Datenbanken aus der Spiegelung gelöscht werden. Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Deaktivieren Sie **SQL Store-Spiegelung aktivieren** , und klicken Sie auf **OK**.

3.  Veröffentlichen Sie die Topologie.

<div class="">


> [!IMPORTANT]  
> Wenn Sie eine Änderung an einer Back-End-Daten Bank Spiegelungs Beziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Validierungsfehler werden im Topologie-Generator zurückgegeben, wenn ein Administrator versucht, eine Bereitstellung mit einem Front-End-Pool zu entfernen, der einen zugeordneten Zeugen Speicher hat.

**Problem**

Wenn ein Administrator versucht, mithilfe des Befehls " **Bereitstellung entfernen** " im Topologie-Generator eine Bereitstellung zu entfernen, die einen Front-End-Pool mit einem zugeordneten Zeugen Speicher enthält, wird im Topologie-Generator ein Validierungsfehler angezeigt, und die Aktion wird nicht fortgesetzt. .

**Workaround**

Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:

  - Entfernen Sie den Zeugen Speicher, bevor Sie versuchen, die Bereitstellung zu entfernen.

  - Fügen Sie einen Zeugen Speicher für den Front-End-Pool hinzu, und entfernen Sie ihn.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>Bereitstellungsinformationen für beständigen Chat Server sind inkonsistent zwischen dem Planungs Tool und dem Topologie-Generator

**Problem**

Wenn vom lync Server 2013, Planungs Tool das Website Topologie-Diagramm für eine persistent Chat Server-Bereitstellung mit aktivierter Disaster Recovery-Funktion ausgegeben wird, enthält das Standorttopologie-Diagramm mehrere (physische) Websites mit gleichmäßig zugewiesenen beständigen Chatservern. Website. Im Topologie-Generator werden alle beständigen Chat Server als einer einzelnen (logischen) Website dargestellt und unter dem gleichen beständigen Chat Server-Poolknoten aufgeführt.

**Workaround**

Derzeit gibt es keine Problemumgehung für dieses Problem. Der Benutzer sollte die Ausgabe des Planungstools für die Bereitstellung des beständigen Chat Servers analysieren und den Plan so ändern, dass er seinen spezifischen Anforderungen entspricht.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Lokalisierung

<div>

## <a name="monitoring"></a>Überwachung

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>Der Assistent zum Bereitstellen von Überwachungsberichten zeigt unter bestimmten Umständen falsche Zeichen an, wenn die ostasiatische Version von lync Server verwendet wird.

**Problem**

Bei Verwendung einer ostasiatischen Version von lync Server 2013 – beispielsweise Chinesisch (vereinfacht), Chinesisch (traditionell), Japanisch oder Koreanisch – unter einem Betriebssystem, bei dem das Systemgebietsschema nicht auf eine ostasiatische Sprache festgesetzt ist, wird der Assistent zum Bereitstellen von Überwachungsberichten Anzeigen von Fragezeichen oder anderen Zeichen anstelle lokalisierter Nachrichten

**Workaround**

Um dieses Problem zu beheben, setzen Sie das Gebietsschema für das Betriebssystem und lync Server 2013 auf die gleiche Sprache, in der alle Nachrichten ordnungsgemäß angezeigt werden.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server-Systemsteuerung

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>In bestimmten Fällen verschwindet das erste Element in der oberen Navigationsleiste auf einer Seite der lync Server-Systemsteuerung, wenn auf das letzte Element in der oberen Navigationsleiste geklickt wird.

**Problem**

Es gibt drei bekannte Fälle, in denen beim Klicken auf das letzte Element auf der oberen Navigationsleiste auf einer Seite der lync Server-Systemsteuerung das erste Element in der oberen Navigationsleiste ausgeblendet wird:

  - In der Version Französisch auf der Seite "Féderation et accès externe" verschwindet das Element "stratégie accès externe", wenn auf "Partenaires Fédérés XMPP" geklickt wird.

  - In der deutschen Version wird auf der Seite "Clients" das Element "Clientversionskonfiguration" nicht mehr angezeigt, wenn auf "Pushbenachrichtigungskonfiguration" geklickt wird.

  - In der russischen Version wird auf der Seite "Конфигурация сети" das Element "Глобально" nicht mehr angezeigt, wenn auf "Маршрут региона" geklickt wird.

**Workaround**

Um dieses Problem zu umgehen, aktualisieren Sie die Seite der lync Server-Systemsteuerung in Ihrem Browser. Die Seite wird im Browser geladen, wobei alle Elemente in der oberen Navigationsleiste angezeigt werden.

</div>

</div>

<div>

## <a name="address-book"></a>Adressbuch

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>Die Indizierung im Adressbuch funktioniert in einigen Sprachen nicht erwartungsgemäß

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.



</div>

Wenn die Eigenschaften eines Benutzers ein indiziertes Feld enthalten und dieses Feld nur Zeichen enthält, die nicht indiziert werden können, wird der Benutzer nicht in Suchvorgängen angezeigt, die im Adressbuch durchgeführt werden.

Die folgenden Zeichen und Gebietsschemas können nicht indiziert werden:

  - Großbuchstaben für Kyrillisch, Griechisch und Armenische Zeichen

  - Großbuchstaben mit Akzenten

  - Thai

  - Laos

  - Myanmar

  - Devanagari

  - Äthiopisch

  - Tibetischen

  - Bengali

  - Gujarati

  - Telugu

  - Alle anderen indischen Skripts

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, Web Scheduler und Web Components

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Sprach-Fallback für bestimmte Sprachen in lync Web Scheduler, Einwahl, Teilnehmer-Startfeld, beständige chatroomverwaltung und OCTab funktionieren möglicherweise nicht erwartungsgemäß

**Problem**

Bei der Auswahl eines neutralen Gebietsschemas in einem Webbrowser (beispielsweise in Internet Explorer, dem Namen der Sprache ohne weitere Angabe wie " \[Norwegisch\]Nein") anstelle eines Gebietsschemas, das Sprache, Skript und Gebietsschema angibt (wie "Norwegisch, Nynorsk ( Norwegen) \[nb-no\]") kann zu einem unerwarteten Anzeigeverhalten für bestimmte Sprachen in lync Web Scheduler, Einwahl, Teilnehmer-Startfeld, beständiger Chatroom-Verwaltung und OCTab führen. Beispielsweise können Benutzer die englische Seite sehen, wenn eine der folgenden Sprachen ausgewählt ist:

  - Norwegisch

  - Portugiesisch

  - Serbisch

**Workaround**

Wenn Sie eine Sprache mit einem neutralen Gebietsschema auswählen möchten, stellen Sie immer sicher, dass Sie auch die Sprache mit einem bestimmten Gebietsschema (mit Skript und/oder Landesvorwahl) als zusätzliche Sprache in der Liste der Spracheinstellungen Ihres Browsers hinzufügen.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Bei der Verwendung von lync Web Scheduler, Einwahl, Startfeld-Startprogramm, beständiger chatroomverwaltung und OCTab in einigen Webbrowsern ist die Unterstützung für aserbaidschanische und usbekische Gebietsschemas nur bedingt verfügbar.

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.



</div>

**Problem**

Wenn Sie Internet Explorer 8 oder Internet Explorer 9 verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden die Seiten für Einwahl-und Teilnehmer-Startfeld in englischer Sprache oder in der bevorzugten Sprache angezeigt, die im Browser eingestellt ist.

Wenn Sie Firefox-oder Chrome-Browser verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden lync Web App, lync Web Scheduler und RGS-OCTab in englischer Sprache oder in der bevorzugten Sprache für den Browser angezeigt.

Das usbekische Gebietsschema wird im Safari-Browser nicht unterstützt.

**Workaround**

Für diese Probleme gibt es keine Problemumgehung.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>Der Dropdownpfeil fehlt für die Liste "an Besprechung teilnehmen" in der rumänischen Version von lync Web App.

**Problem**

Wenn ein Benutzer, der die rumänische Version von lync Web App verwendet, die folgenden Schritte ausführt, wird der Dropdownpfeil für die Teilnahme an einer **Besprechung** in der Dropdownliste nicht angezeigt:

1.  Wählen Sie auf der Registerkarte **Allgemein** auf **diesem Computer speichern** aus.

2.  Wählen Sie die Registerkarte **Telefon** .

3.  Klicken Sie auf die Dropdownliste für an **Besprechung teilnehmen**.
    
    Benutzern wird kein Pfeil angezeigt, der angibt, dass es mehr Optionen als die **lync Web App**gibt, die Folgendes beinhalten: **keine Teilnahme an Audio** (in Rumänisch, "Nu SE asociaža La Componenta Audio") und **neue Nummer**(in rumänischer Sprache, "Număr Nou").

**Workaround**

Auch wenn der Pfeil für diese Dropdownliste nicht angezeigt wird, können die Benutzer weiterhin die zusätzlichen Einstellungen in der Liste auswählen, indem Sie auf den Standardwert klicken.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Bei Verwendung der türkischen Version von lync Web Scheduler kann eine Besprechung nicht gespeichert werden, wenn die Option "Personen, die ich wähle" unter "Wer ist ein Referent" ist

**Problem**

Wenn Sie eine Besprechung in der türkischen Version des lync Web Scheduler erstellen oder bearbeiten, wird die Option "Personen, die ich wähle" unter "Wer ist ein Referent" nicht unterstützt. Wenn diese Option ausgewählt ist, kann die Besprechung nicht gespeichert werden. Stattdessen wird eine Fehlermeldung angezeigt, die besagt, dass eine oder mehrere Personen keine Referenten darstellen können.

**Workaround**

Um dieses Problem zu umgehen, können Benutzer die Standardoption "Personen aus meinem Unternehmen" oder eine beliebige andere Wahl verwenden, beispielsweise "nur Organisator" oder "jeder, einschließlich Personen außerhalb meines Unternehmens". Der Organisator kann später, nachdem er der Besprechung beigetreten ist, Personen zu den richtigen Rollen zurückstufen oder heraufstufen.

Alternativ können Benutzer, die eine andere Sprache verstehen, die Sprachauswahl in Ihrem Browser auf eine der anderen 43-unterstützten Sprachen ändern und versuchen, die Option "Personen, die ich wähle" zu verwenden.

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Copyright

Dieses Dokument unterstützt eine Vorabversion eines Softwareprodukts, das vor der endgültigen kommerziellen Veröffentlichung erheblich geändert werden kann, und ist die vertrauliche und proprietäre Information der Microsoft Corporation. Sie wird gemäß einer Vertraulichkeitsvereinbarung zwischen dem Empfänger und Microsoft veröffentlicht. Dieses Dokument wird nur zu Informationszwecken bereitgestellt, und Microsoft übernimmt in diesem Dokument keine Garantien, weder ausdrücklich noch implizit. Die Informationen in diesem Dokument, einschließlich der URL und anderer Verweise auf Internet Websites, können ohne Vorankündigung geändert werden. Das gesamte Risiko der Nutzung oder der Ergebnisse der Nutzung dieses Dokuments verbleibt beim Nutzer. Sofern nicht anders angegeben, sind die Unternehmen, Organisationen, Produkte, Domänennamen, e-Mail-Adressen, Logos, Personen, Orte und Ereignisse, die in Beispielen hierin dargestellt sind, fiktiv. Keine Assoziation mit einem wirklichen Unternehmen, einer Organisation, einem Produkt, einem Domänennamen, einer e-Mail-Adresse, einem Logo, einer Person, einem Ort oder einem Ereignis ist beabsichtigt oder sollte abgeleitet werden. Die Einhaltung aller anwendbaren Urheberrechtsgesetze obliegt dem Nutzer. Ohne Einschränkung der Rechte unter dem Urheberrecht darf kein Teil dieses Dokuments reproduziert, gespeichert oder in ein Retrievalsystem aufgenommen oder in irgendeiner Form oder auf andere Weise (elektronisch, mechanisch, Fotokopieren, aufzeichnen oder auf andere Weise) oder für einen beliebigen Zweck übertragen werden. ohne die ausdrückliche schriftliche Genehmigung der Microsoft Corporation.

Microsoft hat möglicherweise Patente, Patentanmeldungen, Marken, Urheberrechte oder andere Rechte an geistigem Eigentum, die Inhalte dieses Dokuments abdecken. Sofern nicht ausdrücklich in einem schriftlichen Lizenzvertrag von Microsoft vorgesehen, gibt Ihnen die Einrichtung dieses Dokuments keine Lizenz für diese Patente, Marken, Urheberrechte oder sonstiges geistiges Eigentum.

© 2012 Microsoft Corporation. Alle Rechte vorbehalten.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook und SQL Server sind entweder eingetragene Marken oder Marken der Microsoft Corporation in den Vereinigten Staaten und/oder anderen Ländern/Regionen.

Alle anderen Marken sind Eigentum ihrer jeweiligen Eigentümer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

