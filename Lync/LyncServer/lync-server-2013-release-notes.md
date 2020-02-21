---
title: Anmerkungen zur lync Server 2013-Version
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f572c120d86c5f89fb82e23066a6262e957e5e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Anmerkungen zur Version für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-08_

Willkommen bei den Anmerkungen zur lync Server 2013-Version. In dieser Datei erhalten Sie Informationen zu bekannten Problemen mit lync Server 2013.

<div>

## <a name="about-this-document"></a>Über dieses Dokument

Dieses Dokument enthält wichtige Informationen, die Sie kennen sollten, bevor Sie lync Server 2013 bereitstellen und verwenden. Ausführliche Informationen zu lync Server 2013 finden Sie in der [Microsoft lync Server 2013](microsoft-lync-server-2013.md) -Dokumentation.

Dieses Dokument enthält die folgenden Abschnitte:

  - Lync 2013-Client

  - Lync Server

  - Installation

  - Mobilität

  - Konferenzen

  - Enterprise-VoIP

  - Anwesenheit

  - Reaktionsgruppenanwendung und Anrufparkanwendung

  - Systemsteuerung, Topologie-Generator und Planungstool von Lync Server

  - Lokalisierung

  - Copyright

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013-Client

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>Das übertragen einer Datei in einer Sofortnachricht schlägt fehl, wenn die Datei in einer anderen Anwendung geöffnet ist.

**Problem**

Wenn Sie versuchen, eine Datei (beispielsweise ein Word-Dokument) zu übertragen, indem Sie Sie in eine Sofortnachricht an einen anderen lync-Benutzer einbinden, wird die Übertragung erfolgreich ausgeführt, die Datei kann jedoch tatsächlich nicht übertragen werden. Ein Symbol für den Dateityp wird im lync-Client angezeigt, die Datei kann jedoch nicht vom vorgesehenen Empfänger geöffnet werden. Es wird keine Fehlermeldung angezeigt, die Sie darüber informiert, dass die Übertragung nicht erfolgreich war.

**Problemumgehung**

Um dieses Problem zu umgehen, schließen Sie die geöffnete Datei oder Anwendung, die Sie geöffnet hat, bevor Sie versuchen, die Datei in einer Sofortnachricht zu übertragen.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Wenn lync Server Datenreplikation für den Speicherdienst fehlschlägt, müssen Administratoren die Leistungsindikatoren für Warteschlangenelemente für veraltete Speicherdienste überprüfen.

**Problem**

Der lync Server Speicherdienst verwendet Windows Fabric für die Replikation. Wenn Daten auf einem primären Front-End-Server gelöscht werden, aber der Löschvorgang für einen sekundären Front-End-Server fehlschlägt (beispielsweise wenn ein unerwartetes Herunterfahren oder ein Fehler auf dem Front-End-Server vorliegt), können Daten zurückgelassen und "verwaiste" werden. Die verwaisten Daten können zu Leistungsbeeinträchtigungen und Speicherplatzverschwendung führen.

**Problemumgehung**

Um dieses Problem zu umgehen, sollten Administratoren den Leistungs\_Indikator\_auf\_dem\_Front-End-Server unter **ls: Lyss-Storage Service API** mit\_dem\_Namen **Lyss-Current number of Storage Service veraltete Warteschlangenelemente**überprüfen, wenn die Ereignisse Lyss DB Space used Error (ID = 32058) und Lyss\_DB\_Space Critical (ID = 32059) im Ereignisprotokoll generiert wird. Wenn dieser Leistungsindikator einen hohen Wert aufweist (beispielsweise größer als 50000), sollte der Administrator das Tool CleanuUpStorageServiceData. exe im lync Server 2013 Resource Kit ausführen, mit dem alle verwaisten Daten aus dem Pool gelöscht werden. Ausführliche Informationen zum Tool finden Sie in der Dokumentation zum lync Server 2013 Resource Kit.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Wenn die IP-Adresskonfiguration für einen Server oder Pool geändert wird, müssen lync Server Dienste neu gestartet werden.

**Problem**

Wenn die IP-Adresskonfiguration für eine lync Server 2013-Bereitstellung geändert wird, beispielsweise von IPv4 in Dual Stack oder von Dual-Stack zu IPv6, greifen nicht alle Server Komponenten die Konfigurationsänderung an, bis die Dienste neu gestartet werden.

**Problemumgehung**

Um dieses Problem zu umgehen, starten Sie lync Server Dienste neu, nachdem Sie die IP-Adresskonfiguration für die Bereitstellung geändert haben. Führen Sie dazu die folgenden Cmdlets im lync Server-Verwaltungsshell aus:

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Das Cmdlet "synthetische Transaktion für Einwahlkonferenzen" steht im lync Server 2013 Management Pack nicht mehr zur Verfügung.

**Problem**

Das Cmdlet **Test-CsDialInConferencing** für die Einwahlkonferenz synthetische Transaktionen steht im lync Server 2013 Management Pack nicht mehr zur Verfügung.

**Problemumgehung**

Die Verwendung des Cmdlets **Test-CsDialInConferencing** für die synthetische Transaktion der Einwahlkonferenz wird nur intern für Unternehmen unterstützt.

Administratoren können das Cmdlet in lync Server-Verwaltungsshell zu Problembehandlungszwecken weiterhin verwenden. Bei Bedarf kann ein Unternehmen auch ein privates Management Pack zur internenen Ausführung des Cmdlets entwickeln.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>Der zentralisierte Protokollierungsdienst wird angehalten, wenn der Netzwerkdatenverkehr unterbrochen wird, wenn Protokolldateien in die Netzwerkfreigabe kopiert werden.

**Problem**

Wenn der zentralisierte Protokollierungsdienst für die Verwendung eines Netzwerkpfads (der Wert des Parameters "CacheFileNetworkFolder" des **Get-CsClsConfiguration**-Cmdlets ist ein gültiger UNC-Pfad) konfiguriert ist, werden zwischengespeicherte Protokolldateien auf das Netzlaufwerk kopiert. Wenn beim Kopieren der Dateien eine Störung im Netzwerkdatenverkehr auftritt, wird eine Ausnahme ausgelöst, durch die der zentralisierte Protokollierungsdienst angehalten wird.

Der Dienst ist für bis zu drei automatische Neustarts konfiguriert, sodass er ausgehend von den ersten drei Ausnahmen neu gestartet wird.

**Problemumgehung**

Das Problem kann nicht umgangen werden. Um das Problem zu identifizieren, überwachen Sie das Ereignisprotokoll für die Ereignis-ID 7031 aus dem Dienststeuerungs-Manager, der protokolliert, wenn der Dienst Agent für lync Server zentralisierten Protokollierungsdienst unerwartet beendet wurde. Wenn dies mehr als dreimal geschieht, starten Sie den Dienst manuell mit dem Cmdlet " **Start-CsWindowService** " neu.

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Speicherdienst-Warteschlangenelemente müssen manuell importiert werden

**Problem**

In lync Server 2013 werden Daten zu Konferenzen und Chatnachrichten (beispielsweise archivierte Nachrichten und Aufzeichnung von Kommunikationsdatensätzen) in einer Datenbank auf jeder Front-End-Server gespeichert. Die Daten werden während der Verarbeitung in der Datenbank gespeichert, bevor Sie an das vorgesehene Ziel übermittelt werden. Um die Leistung zu verbessern, exportiert lync Server 2013 die Warteschlangenelemente regelmäßig aus der lokalen Datenbank, die für einen längeren Zeitraum nicht verarbeitet werden, und speichert Sie im Dateispeicher. Wenn der Dateispeicher nicht verfügbar ist, werden die Elemente auf jeder Front-End-Server gespeichert. Derselbe Vorgang wird zum Verhindern von Datenverlusten bei Failovervorgängen für Pools verwendet.

Während des Exportvorgangs zeichnet der lync Server Speicherdienst jede Stufe im Ereignisprotokoll mit den Ereignis-IDs 32075 (vollständiger Löschvorgang wird gestartet), 32076 (vollständiger Flush ist abgeschlossen), 32082 (Wartungsebene wird gestartet), 32083 (Wartungsebene bündig ist abgeschlossen), 32089 (Flush erfolgte aufgrund des Füllens der Datenbank). Diese Daten werden nicht automatisch zurück in das System importiert, damit Sie verarbeitet und an ihr endgültiges Ziel (SQL Server oder Exchange Server) übermittelt werden.

**Problemumgehung**

Um die Daten in das System zu importieren, müssen Administratoren das ImportStorageServiceData-Tool im lync Server Resource Kit verwenden, mit dem die Daten wieder in das System eingefügt werden, damit Sie verarbeitet und an ihr endgültiges Ziel übermittelt werden.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Bei der Suche nach Adressbuch-Webabfragen tritt ein Fehler auf, wenn der Standardwert für UseNormalizationRules in false geändert wird.

**Problem**

Wenn der Standardwert für UseNormalizationRules in "False" geändert wird, schlagen Adressbuch-Webabfragen fehl. Nach dem Ändern des Standardwerts können Lync Client-Benutzer die Lync-Adressbuch-Webabfrage nicht zum Suchen nach Benutzern verwenden.

**Problemumgehung**

Wenn der Standardwert für UseNormalizationRules auf false festgelegt ist, damit Benutzer Telefonnummern wie in Active Directory-Domänendienste definiert verwenden können, ohne Normalisierungsregeln lync Server 2013 anzuwenden, umgehen Sie dieses Problem, indem Sie folgende Schritte ausführen:

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Ihre Bereitstellung nur lync Server 2013 Server enthält, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für UseNormalizationRules und IgnoreGenericRules in true zu ändern:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013 Pool in der Topologie zu:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Warten Sie, bis die CMS-Replikation für alle Pools erfolgt ist.

4.  Ändern Sie die Datei mit den Telefonnormalisierungsregeln für Ihre Bereitstellung, sodass die Inhalte gelöscht werden. Die Datei befindet sich in der Dateifreigabe der einzelnen lync Server 2013 Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen\_"\_Normalisierung\_\_Rules. txt" für Firmen Telefonnummern.

5.  Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6.  Führen Sie das folgende Cmdlet für jeden lync Server 2013 Pool in der Bereitstellung aus.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>Das Adressbuch Server-Fehlerereignis 21054 wird einmal täglich für jeden lync 2013 Pool generiert.

**Problem**

Lync Server 2013 Adressbuch Server generiert ein Fehlerereignis 21054 einmal täglich, wenn die tägliche Wartung ausgeführt wird. Der Fehler wird auch jedes Mal generiert, wenn ein Administrator das Cmdlet **Update-csAddressBook** ausführt, auch wenn das Update erfolgreich ausgeführt wird. Bei einer erfolgreichen Aktualisierung kann dieses Fehlerereignis jedoch bedenkenlos ignoriert werden.

**Problemumgehung**

Wenn dieses Fehlerereignis eintritt, führen Sie das folgende Cmdlet aus:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Wenn das Cmdlet meldet, dass keine nicht indizierten oder verlassenen Objekte vorhanden sind, kann das Error-Ereignis 21054 sicher ignoriert werden.

Zudem sollte der Key Health Indicator (KHI) "Adressbuchbenutzer ordnungsgemäß indiziert" im System Center Operations Manager deaktiviert werden.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Für Anforderungen kann ein Fehler auftreten, wenn IPv6 auf einem Edgepool konfiguriert ist.

**Problem**

Wenn IPv6 auf einem Edgepool konfiguriert ist, schlagen möglicherwesie einige Anforderungen an den Edgepool fehl.

**Problemumgehung**

Konfigurieren Sie zur Umgehung dieses Problems Edgepools nicht mit IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>Das Invoke-csPoolFailback-Cmdlet schlägt möglicherweise beim Failback des Pools fehl

**Problem**

Beim Versuch, einen Failback-Vorgang für einen Pool auszuführen, gibt das Cmdlet **invoke-csPoolFailback** möglicherweise den Fehler "Abschluss des Hydrationsprozesses nach mehreren Versuchen fehlgeschlagen" zurück.

**Problemumgehung**

Wenn Sie dieses Problem umgehen möchten, führen Sie das Cmdlet erneut aus, und warten Sie, bis das Cmdlet erfolgreich abgeschlossen wurde. Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruchen nehmen kann. Für einen Pool mit 20.000 Benutzern kann dies bis zu 60 Minuten dauern.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Datenverlust kann auftreten, wenn Sie eine Front-End-Server zu einem bereits vorhandenen Pool hinzufügen – Hybrid, Skype for Business Online

**Problem**

Dieses Problem kann in einer Umgebung auftreten, in der ein Pool über mehr als eine Front-End-Server verfügt, und Sie können entweder einen der Front-End-Server neu starten oder einen neuen Front-End-Server hinzufügen, der zuvor nicht Teil des Pools war.

Bei Benutzern, deren Daten archiviert werden, kommt es möglicherweise zu Datenverlusten, bis eine stabile Verteilung der Datenarchivierung für den Pool hergestellt wurde. Dieser Zeitraum mit potenziellem Datenverlust ist für Konversationen zwischen Personen auf 15 Minuten und für Konferenzen auf 30 Minuten begrenzt.

**Problemumgehung**

Wenn Sie die Wartung durchführen, statt Front-End-Server einzeln im Pool zu starten, sollten Sie einen Failover des Pools zu einem anderen Pool durchführen und dann Wartungsaufgaben auf den Servern ausführen. Sie können die Verfügbarkeit des Diensts vor dem Ausführen von Wartungsaufgaben auch aufheben und die Verfügbarkeit dann nach Abschluss der Wartung wiederherstellen.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Administratoren können die Anzahl der Lizenznehmer nicht mithilfe des Get-csclientaccesslicense abrufen-Cmdlets abrufen.

**Problem**

Administratoren können die genaue Clientlizenzverwendung nicht mithilfe des Cmdlets **Get-CsClientAccessLicense** abrufen.

**Problemumgehung**

Wenn Sie den Serverlizenztyp überprüfen möchten, können Sie das Cmdlet **Get-CsService** ausführen, um die vollqualifizierten Domänennamen (Fully Qualified Domain Names, FDQNs) aller Datenbanken abzurufen. Wenn der FQDN des Front-End-Server mit dem FQDN der Back-End-Datenbank identisch ist, handelt es sich bei der Lizenz um eine Standard Edition-Lizenz. Andernfalls ist die Lizenz eine Enterprise Edition-Lizenz.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>Anzahl der Client Lizenzen wird nicht genau gemeldet

**Problem**

Beim Ermitteln der Clienzlizenzanzahl liegen möglicherweise die folgenden Zustände vor:

1.  **Ungenaue Lizenzanzahl für mobile Benutzer**
    
    Die Lizenzanzahl basiert auf der Anzahl eindeutiger IP-Adressen für gerätebasierte Benutzer. Die Lizenzanzahl wird wie folgt begrenzt:
    
      - Es werden zu viele Lizenzen gezählt, wenn sich die IP-Adresse für den Benutzer in Lync-Sitzungen ändert. Dies kann auftreten, wenn ein Benutzer mit einem Desktop Client eine Verbindung mit lync Server von mehr als einem Standort herstellt.
    
      - Es werden zu wenig Lizenzen gezählt, wenn ein Benutzer eine Verbindung mit einem mobilen Client herstellt, weil die IP-Adresse für das Gerät nicht bestimmt werden kann.

2.  **Für Lync-Client-Anrufe über das Festnetz (Public Switched Telephone Network, PSTN), Lync-Client-Anrufe an PSTN-Leitungen und Lync-Anrufweiterleitungen an PSTN-Leitungen werden die Lizenzen doppelt gezählt**
    
    In den folgenden Szenarien werden anstatt einer zwei zusätzliche Lizenzen gezählt, da zum Ermitteln der Anzahl verwendeter Lizenzen sowohl die Telefonnummer als auch der Lync-Benutzer gezählt wird. Wenn Sie die richtigen Lizenzierungsdaten abrufen möchten, entfernen Sie die von einer Telefonnummer generierten Lizenzen manuell.
    
      - Ein PSTN-Telefonanruf an Lync
    
      - Ein Lync-Anruf an eine PSTN-Leitung
    
      - Ein PSTN-Anruf an Lync und anschließende Anrufweiterleitung durch Lync an eine PSTN-Leitung. Eine der PSTN-Leitungen wird gezählt.

3.  **Für ein angemeldetes Lync-Telefon wird keine Lizenz gezählt**
    
    Wenn ein Benutzer ein Lync-zertifiziertes Telefon verwendet, das Telefon angemeldet wird und verbunden bleibt und der Anmeldestatus beibehalten wird, wird das Telefon nicht für die Verwendung einer Lizenz gezählt, sofern die Abfrage nach Lizenzen nach der Anmeldung des Telefons erfolgt.

4.  **Gezählte Lizenzen für PSTN-Telefone, die Konferenzen beitreten**
    
    Wenn ein Benutzer mit einem PSTN-Telefon einer Konferenz beitritt, wird fälschlicherweise eine Lizenz für den Beitritt zu der Konferenz gezählt. Für den Beitritt zu einer Konferenz mit einem PSTN-Telefon wird keine Lizenz benötigt.

**Problemumgehung**

1.  **Ungenaue Lizenzanzahl für mobile Benutzer**
    
      - Sie können die IP-Adressen, die zu ein und demselben Gerät gehören, manuell identifizieren und dann eine der Adressen aus der Lizenzanzahl entfernen.
    
      - Beim Verbinden mobiler Geräte mit dem Lync-Client kann dieses Problem nicht umgangen werden.

2.  **Für PSTN-Anrufe des Lync-Clients, Lync-Client-Anrufe an PSTN-Leitungen und Lync-Anfrufweiterleitungen an PSTN-Leitungen werden Lizenzen doppelt gezählt**
    
    Sie müssen die PSTN-Telefonnummer manuell identifizieren und die für sie generierte Lizenzanzahl entfernen.

3.  **Für angemeldete Lync-Telefone werden keine Lizenzen gezählt**
    
    Sie können das Lync-Telefon so konfigurieren, dass es in einem regelmäßigen Intervall (beispielsweise alle drei Monate) abgemeldet und dann wieder angemeldet wird.

4.  **Gezählte Lizenzen für PSTN-Telefone, die Konferenzen beitreten**
    
    Sie können die PSTN-Telefonnummer, die für den Konferenzbeitritt verwendet wird, manuell identifizieren und die von der Telefonnummer generierte Lizenz entfernen.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Das lync Server-Systemsteuerung in einer VMware-Umgebung nach dem Upgrade auf Silverlight 5 nicht mehr funktioniert

**Problem**

Wenn Sie das lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert das lync Server-Systemsteuerung nach dem Upgrade Microsoft Silverlight auf Version 5 möglicherweise nicht mehr.

**Problemumgehung**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Deinstallieren Sie Silverlight 5, und installieren Sie Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)4 aus.

  - Greifen Sie auf den lync Server-Systemsteuerung von einem Computer aus, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.
    
    Dazu können Sie die lync Server-Systemsteuerung im Windows- **Startmenü** auf dem Server starten, wenn die lync Server Verwaltungstools auf dem Computer installiert sind.
    
    Sie können auch über einen Webbrowser auf die lync Server-Systemsteuerung zugreifen. \<Die URL ähnelt dem FQDN\_\_\>des https://-Front-End-Pools/CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Benutzerinformationen im Adressbuchdienst werden nicht aktualisiert, nachdem der Distinguished Name für den Benutzer in Active Directory geändert wurde.

**Problem**

Wenn die Distinguished Name (auch als DN bekannt) eines Benutzers in Active Directory-Domänendienste geändert wird, werden alle weiteren Änderungen nicht im Adressbuchdienst (ABS) aktualisiert. Dies wirkt sich nicht auf die Anmeldung oder Anwesenheit des Benutzers aus, verhindert jedoch die Kommunikation des Benutzers, wenn die SIP-Adresse ebenfalls geändert wird, da durch Suchvorgänge eine veraltete SIP-Adresse zurückgegeben wird.

**Problemumgehung**

Wenn Sie dieses Problem umgehen möchten, ändern Sie den DN eines Benutzers nicht. Wenn Sie den DN für den Benutzer auf den vorherigen Wert zurücksetzen, spiegeln sich Aktualisierungen im Adressbuchdienst wider.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Installation

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>Das Verwenden von nicht-ASCII-Zeichen kann dazu führen, dass lync Server nicht gestartet wird

**Problem**

Das Setup schlägt fehl, wenn der Name des Zielordners nicht-ASCII-Zeichen enthält (einschließlich Unicode, Doppelbyte-Zeichensatz (DBCS), UTF-8 und UTF-16). Darüber hinaus kann Setup erfolgreich ausgeführt werden, aber der Server wird nicht gestartet, wenn in einem der folgenden nicht-ASCII-Zeichen enthalten sind:

  - Name des Computers

  - Domänenname

  - Benutzername

  - SIP-URI des Benutzers

  - Dienstkontoname

**Problemumgehung**

Verwenden Sie nur ASCII-Zeichen im Namen des Zielordners, des Computernamens, des Domänennamens, des Benutzernamens, des SIP-URI des Benutzers und der Dienstkontonamen.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>Der Hotfix für "Heap Beschädigung tritt auf, wenn ein Modul ruft die InsertEntityBody-Methode in IIS 7,5" muss vor der Installation von lync Server 2013 installiert werden

**Problem**

Der Hotfix für "Heap Beschädigung tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)" () aufruft, die im Microsoft Knowledge[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)Base-Artikel 264886 () beschrieben wird, muss vor der Installation von lync Server 2013 installiert werden.

**Problemumgehung**

Laden Sie das Hotfix aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)herunter, und installieren Sie es.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 kann nicht auf ITA-Windows Server 2012 OS RTM-Version installiert werden

**Problem**

Lync Server 2013 Installation schlägt auf ITA-Windows Server 2012 fehl, da Windows Fabric-Installation fehlschlägt.

Die Windows Fabric-Installation ist fehlerhaft, weil Fabric-Ablaufverfolgunge im Zeitformat "HH:MM:SS" erstellt werden. Das Zeitformat in ITA Windows Server lautet jedoch "HH.MM.SS".

**Problemumgehung**

Um dieses Problem zu umgehen, aktualisieren Sie die Systemregistrierung, bevor Sie lync Server 2013 installieren. Der Registrierungsschlüssel, der aktualisiert werden muss, lautet:\_HKEY\\-Benutzer. Standard\\mäßige\\System\\Steuerung internationale sTimeFormat. Ändern Sie den Wert von sTimeFormat in hh: mm: SS, indem Sie die Befehlszeilenschnittstelle Windows PowerShell wie folgt verwenden:

1.  Starten Sie Windows PowerShell, und führen Sie die folgenden Cmdlets aus:
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Führen Sie zum Anzeigen des aktuellen Werts das folgende Cmdlet aus:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Notieren Sie den aktuellen Wert für "sTimeFormat", sodass er nach Abschluss der Installation wiederhergestellt werden kann.

3.  Führen Sie zum Festlegen auf den neuen Wert das folgende Cmdlet aus:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Nachdem lync Server 2013 erfolgreich installiert wurde, stellen Sie den ursprünglichen Wert für das sTimeFormat-Objekt wieder her, indem Sie das folgende Cmdlet ausführen:
    
        - Festlegen-ItemProperty $a-Name sTimeFormat-Wert "<Wert, der in Schritt 3 notiert wurde. oberhalb> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilität

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Probleme für mobile Clients während des Server Failover-Prozesses

**Problem**

Wenn ein lync Server fehlschlägt und der Failoverprozess beginnt, können sich die folgenden Probleme auf Mobile Client-Benutzer auswirken:

  - Kein eingehender lync-Anruf oder Signal für bis zu 10 Minuten nach dem Start des Failovers.

  - Eingehende Chat Anforderungen können nicht akzeptiert werden

  - Kann nicht an Besprechungen teilnehmen, wenn der fehlerhafte Server der Stammserver für den Benutzer ist

**Problemumgehung**

Das Problem kann nicht umgangen werden. Die normale Funktionalität wird nach Abschluss des Failover-Prozesses wiederhergestellt.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Wenn ein mobiler Benutzer einen eingehenden Anruf von einem anderen lync-Endpunkt ablehnt, wird der Anruf als verpasste Konvertierung für lync Mobile-Clients angezeigt.

**Problem**

Wenn ein mobiler Benutzer einen eingehenden Anruf ablehnt und der Anruf von einem anderen lync-Endpunkt stammt, wird der Anruf im lync Mobile-Client anstelle eines Anrufs in der Geräte Anrufliste als verpasste Unterhaltung angezeigt.

**Problemumgehung**

Das Problem kann nicht umgangen werden.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Der Anzeigename eines verbundenen Kontakts wird beim Suchen nach Kontakten vom mobilen Client möglicherweise nicht angezeigt.

**Problem**

Der Anzeigename für Partnerverbund Kontakte wird in einigen Szenarien möglicherweise nicht angezeigt, beispielsweise bei der Suche nach einem Verbundkontakt in der Kontaktliste. Dies kann auftreten, wenn das aktive Anwesenheits Abonnement für den Kontakt vom mobilen lync-Client nicht vorhanden ist.

**Problemumgehung**

Das Problem kann nicht umgangen werden.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>Im mobilen Client fehlen die Informationen zum einladen und zum Zeitstempel bei einer verpassten Unterhaltung, die eine Einladung zu einer Konferenz darstellt.

**Problem**

Wenn im mobilen Client eine verpasste Unterhaltung eine Einladung zu einer Konferenz ist, fehlen die Informationen zum einladen und zum Zeitstempel in der Nachricht verpasste Unterhaltung.

**Problemumgehung**

Das Problem kann nicht umgangen werden.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Benutzer von Mobiltelefonen, die VoIP-Anrufe tätigen, können Voicemail für Benutzer, deren Voicemail in Exchange 2010 oder früheren Versionen konfiguriert ist, nicht mehr hinterlassen.

**Problem**

Wenn ein mobiler Client-Benutzer VoIP zum Platzieren von Anrufen verwendet, kann der Benutzer keine Voicemail-Nachrichten für Benutzer, die für die Verwendung von Voicemail in Microsoft Exchange Server 2007 oder Microsoft Exchange Server 2010 konfiguriert sind, hinterlassen.

**Problemumgehung**

Um dieses Problem zu umgehen, verwenden Sie Exchange 2010 mit SP1 oder einer höheren Version von Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Bei Verwendung von Block mit URL für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt.

**Problem**

Bei Verwendung von **Block mit URL** für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt, wenn die Client Version nicht unterstützt wird.

**Problemumgehung**

Um dieses Problem zu umgehen, konfigurieren Sie die Client Versions Konfiguration so, dass **Block** anstelle von **Block mit URL**verwendet wird.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Konferenzen

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Antivirensoftware, die auf lync Server 2013-Front-End-Servern läuft, kann eine Wiederverwendung der Anwendungsdomäne verursachen, wodurch der Dienst für lync Web App 2013-, lync Mobile 2010-und lync Mobile 2013-Clients vorübergehend unterbrochen wird.

**Problem**

Antivirensoftware kann Anwendungsdomänen Neustarts auslösen, was dazu führen kann, dass lync Mobility Service 2013 und Unified Communications (UC)-WebAPI-Clientanwendungen (lync Web App 2013, lync Mobile 2010 und lync Mobile 2013) ihren Status verlieren.

**Problemumgehung**

Wenn Sie dieses Problem umgehen möchten, schließen Sie die Ordner mit Webkomponenten und .NET Framework aus dem Virenschutzprogramm aus. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 312592, "PRB: zufällige Anwendungsneustarts mit" Anwendung ist ein Neustart "Error in ASP.net" unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).

Die folgenden Ordner sollten ausgeschlossen werden:

  - % Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\MCX ext

  - % Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\MCX int

  - % Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\Ucwa int

  - % Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\Ucwa ext

  - % Windir%\\Microsoft.net\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>ActiveX-Steuerelemente oder systemeigene XMLHTTP-Unterstützung müssen in Windows Internet Explorer aktiviert werden, um Konferenzen erfolgreich beizutreten.

**Problem**

Wenn ein Benutzer ActiveX-Steuerelemente und die systemeigene XMLHTTP-Unterstützung in den Internetbrowsereinstellungen von Windows Internet Explorer deaktiviert hat, kann der Benutzer keiner Besprechung beitreten, falls Internet Explorer als Standardbrowser ausgewählt ist.

**Problemumgehung**

Aktivieren Sie in Internet Explorer ActiveX-Steuerelemente oder die "systemeigene XMLHTTP-Unterstützung".

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Webkonferenzdienst kann nicht im kritischen Modus wiederhergestellt werden

**Problem**

Wenn der kritische Modus zur Archivierung aktiviert ist, startet der kritische Modus im Falle eines Systemausfalls, und die Konferenz ist für die Teilnehmer nicht mehr zugänglich. Nachdem der Administrator die Systemausfälle behoben hat (beispielsweise ein Datenbankproblem), wird der Datenkonferenzdienst nicht automatisch wiederhergestellt, und der Administrator muss den Konferenzdienst zum Fortsetzen der Konferenz manuell neu starten.

**Problemumgehung**

Ein Administrator muss den Konferenzdienst manuell neu starten, nachem der Systemausfall behoben wurde.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Webkonferenzdienst ignoriert den HTTP-Proxy für externe Office-Webanwendungsserver

**Problem**

Wenn Sie einen Office Web Apps-Server außerhalb des Webkonferenzdienst bereitgestellt haben (also ein Server, der sich nicht im internen Unternehmensnetzwerk befindet) im Internet, Umkreisnetzwerk und der Webkonferenzdienst ein HTTP-Proxy erfordert, um eine Verbindung mit diesem herzustellen, wird der Die Office-webapps-Server Ermittlung schlägt fehl. Im Webkonferenzdienst wird die http-Proxyeinstellung ignoriert, wie im Topologie-Generator für Office-webapps-Server Setup definiert. Daher kann der lync-Client Microsoft PowerPoint 2010 Freigabe für andere Teilnehmer an der Konferenz nicht durchführen. Wenn Sie lync Server lokal installieren und außerdem Office-webapps Server lokal im internen Netzwerk konfigurieren, ist keine Proxykonfiguration erforderlich.

**Problemumgehung**

Die einzige Problemumgehung besteht darin, dass keine Bereitstellungskonfiguration vorliegt, bei der die Verwendung des HTTP-Proxys für die Kommunikation mit einem externen Office-webapps-Server erforderlich ist.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>Das Hinzufügen von Video zu einer Konferenz für einen Audiokonferenz-Anbieter wird nicht unterstützt

**Problem**

Das Hinzufügen eines Videos wird nicht unterstützt, wenn der Benutzer einer Audiokonferenz eines Audiokonferenzanbieters beitritt.

**Problemumgehung**

Das Problem kann nicht umgangen werden.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologien mit aktivierter IPv6 erzwingen, dass die lync Web App Silverlight-Plug-in automatisch aktualisiert wird, um sicherzustellen, dass die Bildschirmfreigabe Funktion in lync Web App funktioniert.

**Problem**

Wenn eine Topologie mit aktiviertem IPv6 konfiguriert ist, können Benutzer Ihren Bildschirm nicht über den lync Web App-Client freigeben, wenn bereits eine frühere Version des Plug-Ins für die Bildschirmfreigabe installiert ist.

**Problemumgehung**

Wenn Sie eine Aktualisierung der neuesten Version des Plug-Ins für die Bildschirmfreigabe beim Beitritt zur Besprechung über lync Web App erzwingen möchten, ändern Sie den Wert von **MinSupportedBuildVersion** von "4.0.7457.0" in "4.0.7577.380" in den beiden folgenden Dateien:

  - % Programme%\\Microsoft lync Server 15\\-\\Webkomponenten\\erreichen\\int\\-\\Client-Plugins ReachAppShPluginProperties. XML

  - % Programme%\\Microsoft lync Server 15\\-\\Webkomponenten\\erreichen\\Ext\\-\\Client-Plugins ReachAppShPluginProperties. XML

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise-VoIP

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>In einigen Fällen unterstützt ein lync-Client auf einem Computer, der für die Verwendung von IPv4-und IPv6-dualen Stapeln konfiguriert ist, möglicherweise keine Funktionen, die im IP-Subnetz des Computers wie E911, medienumgehung, Anrufsteuerung und Standort basiertem Routing basieren.

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.



</div>

**Problem**

Wenn ein lync-Client auf einem Computer läuft, der für IPv4 und IPv6 Dual Stack aktiviert ist, und basierend auf der DNS-Auflösung des Proxyservers, kann der Client die IPv6-Adresse des Computers zur Anmeldung verwenden. Anschließend unterstützt der lync-Client nur die für IPv6 unterstützten Funktionen, die E911, medienumgehung, Anrufsteuerung und standortbasiertes Routing ausschließen.

**Problemumgehung**

Um dieses Problem zu umgehen, deaktivieren Sie die IPv6-Unterstützung auf dem Clientcomputer.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss der Benutzer das E164-Format verwenden, um sich aus einer Konferenz abzuwählen.

**Problem**

Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss dieser Benutzer das E164-Format verwenden, um sich erfolgreich aus einer Konferenz auszuwählen. Wird das E164-Format nicht verwendet, kann sich der Benutzer nicht aus der Konferenz auswählen.

**Problemumgehung**

Um dieses Problem zu umgehen, sollten Benutzer, die nicht für Enterprise-VoIP aktiviert sind, aus einer Konferenz wählen, indem Sie zahlen im E164-Format verwenden.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Anwesenheit

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Wenn ein Benutzer die Option "alle Einladungen und Kommunikationen blockieren" ausgewählt hat, während der einheitliche Kontaktspeicher für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn er

**Problem**

Wenn ein Benutzer die Option "Alle Einladungen und gesamte Kommunikaktion blockieren" ausgewählt hat, während der einheitliche Kontaktspeicher für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn dies der Fall sein sollte.

**Problemumgehung**

Zur Umgehung dieses Problems können Sie den einheitlichen Kontaktspeicher für den Benutzer deaktivieren. Führen Sie dazu die folgenden Cmdlets aus:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Beispiel:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office Communications Server 2007 R2 Benutzer, die lokal verwaltet werden, können den Anwesenheitsstatus von Skype for Business Online Benutzern in hybridbereitstellungen nicht anzeigen – Hybrid

**Problem**

Das Problem kann in einer hybridbereitstellung auftreten, wenn Sie einen lync Server 2013 Director verwenden.

Der Anwesenheitsstatus für Benutzer, die Skype for Business Online verwaltet werden, wird als Anwesenheit unbekannt für lokale Benutzer angezeigt. Außerdem können Benutzer, die Skype for Business Online verwaltet werden, den Anwesenheitsstatus für lokale Benutzer von Office Communications Server R2 nicht sehen.

**Problemumgehung**

Um dieses Problem teilweise zu umgehen, ändern Sie den Stamm Server (msRTCSIP-presencehomeserver) der Skype for Business Online Benutzer so, dass er auf einen lync Server 2013 lokalen Pool anstatt auf den lync Server 2013 Director zeigt. Sie können diese Einstellung für das lokale Front-End-Server ändern.

Diese Problemumgehung zeigt ordnungsgemäß den Anwesenheitsstatus von Benutzern an, die Office Communications Server 2007 R2 für Skype for Business Online Benutzer verwaltet werden.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Reaktionsgruppenanwendung, Anwendung zum Parken von Anrufen und gruppenanrufannahme

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Ein Anrufer hört möglicherweise eine Sekunde der Wartemusik während der Erstellung eines Anrufs mit dem abrufenden Teilnehmer.

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.



</div>

**Problem**

Wenn ein Anruf über die gruppenanrufannahme abgerufen wird, hört der Anrufer möglicherweise eine Sekunde der Wartemusik während der Einrichtung des Anrufs mit dem Retriever-Teilnehmer.

**Problemumgehung**

Das Problem kann nicht umgangen werden.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Ein Reaktionsgruppen-Agent kann sich über eine lync Server 2010-Agent-Konsole anmelden und abmelden, um nur lync Server 2010 formellen Agentgruppen

**Problem**

Ein lync Server 2013 Reaktionsgruppen-Agent kann sich über eine lync Server 2010 Agent-Konsole anmelden und nur lync Server 2010 formellen Agentgruppen abmelden. In der lync Server 2010-Agent-Konsole können Benutzer nur die lync Server 2010 Reaktionsgruppe sehen, der Sie angehören. Sie können keine der lync Server 2013 Reaktionsgruppen sehen, zu denen Sie gehören.

**Problemumgehung**

Wenn der Reaktionsgruppen-Agent ein lync Server 2013er Benutzer und Teil einer lync Server 2013 formellen Agentgruppe ist, muss der Benutzer direkt über einen Weblink in einem Browser auf die lync Server 2013-Agent-Konsole zugreifen, um sich bei lync Server 2013 Agentgruppen anzumelden und abzumelden.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Ein lync Server 2010 Reaktionsgruppen-Agent kann keine Anrufe im Namen einer lync Server 2013 Reaktionsgruppe tätigen.

**Problem**

Ein lync Server 2010 Benutzer, der ein Agent einer lync Server 2013 Reaktionsgruppe ist, kann im Namen der Reaktionsgruppe keinen Anruf tätigen. Die lync Server 2013 Reaktionsgruppe steht im lync-Client nicht zur Verfügung, um einen Anruf zu tätigen.

**Problemumgehung**

Um dieses Problem zu umgehen, müssen Sie den lync Server 2010 Benutzer in lync Server 2013 bewegen.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Wenn Sie eine Reaktionsgruppe aus lync Server 2010 entfernen, nachdem Sie zu lync Server 2013 migriert wurde, wird verhindert, dass die Reaktionsgruppe eingehende Anrufe akzeptiert.

**Problem**

Wenn eine Reaktionsgruppe, die von lync Server 2010 zu lync Server 2013 migriert wurde, aus lync Server 2010 über das lync Server-Systemsteuerung oder den lync Server-Verwaltungsshell entfernt wird, wird die Reaktionsgruppe in lync Server 2013 keine eingehenden Anrufe mehr empfangen.

**Problemumgehung**

Um dieses Problem zu umgehen, entfernen Sie keine Reaktionsgruppen aus lync Server 2010, die von lync Server 2010 zu lync Server 2013 migriert wurden.

Wenn die Reaktionsgruppe bereits entfernt wurde, sollten Sie Sie in lync Server 2013 erneut bereitstellen.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv festgelegt ist, wird die Bereitstellung des Workflows fehlschlagen.

**Problem**

Wenn ein neuer verwalteter Workflow bei seiner Erstellung auf inaktiv festgelegt wird, gibt die Bereitstellung des Workflows einen Fehler zurück. Dieses Problem tritt auf, wenn der Workflow bei seiner Erstellung auf inaktiv festgelegt wird. Es wirkt sich jedoch nicht auf einen Workflow aus, der nach seiner Bereitstellung bearbeitet wurde, um auf inaktiv festgelegt zu werden.

**Problemumgehung**

Wenn Sie einen Workflow erstellen und bereitstellen, legen Sie den Workflow als aktiv fest, und stellen Sie ihn anschließend bereit. Nachdem der Workflow erfolgreich bereitgestellt wurde, kann er bearbeitet und auf inaktiv festgelegt werden.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>Durch das Entfernen einer Reaktionsgruppe aus dem Besitzer Pool wird verhindert, dass die Reaktionsgruppe des Sicherungs Pools eingehende Anrufe während eines Failovers akzeptiert, wenn die Reaktionsgruppe in den Sicherungspool importiert wurde.

**Problem**

Wenn eine Reaktionsgruppe, die dem primären Pool gehört, in den Sicherungspool importiert wurde, ohne den Besitzer zu überschreiben, und die Reaktionsgruppe aus dem Besitzer Pool entfernt wurde, akzeptiert die Reaktionsgruppe im Sicherungspool keine eingehenden Anrufe während eines Failovers.

**Problemumgehung**

Sie müssen die Reaktionsgruppe im primären Pool erneut bereitstellen. Anschließend müssen Sie die Reaktionsgruppen Konfiguration aus dem primären Pool exportieren und erneut in den Sicherungspool importieren.

Sie können die Reaktionsgruppe auch im Sicherungspool neu erstellen. In diesem Fall ist der Sicherungspool der Besitzer Pool der Reaktionsgruppe.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Ein geparkter Anruf kann nicht aus dem Anwendung zum Parken von Anrufen abgerufen werden, wenn die Abrufanforderung im Namen einer Reaktionsgruppe erfolgt.

**Problem**

Wenn die folgenden Bedingungen wahr sind, schlägt eine Abrufanforderung für einen geparkten Anruf fehl:

  - Ein Agent ist Teil einer anonymen Reaktionsgruppe

  - Der Agent versucht, einen geparkten Anruf aus dem Anwendung zum Parken von Anrufen über die anonyme Reaktionsgruppe abzurufen.

  - Der Agent versucht, den Anruf durch Wählen der Orbitnummer über die Option "Anruf im Namen von" oder über dieselbe Option im Lync-Telefonzentralen-Client abzurufen

**Problemumgehung**

Das Problem kann nicht umgangen werden. Der geparkte Anruf sollte ohne dies im Namen einer Reaktionsgruppe abgerufen werden.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server-Systemsteuerung, -Topologie-Generator und -Planungstool

<div>

## <a name="planning-tool-limitations"></a>Einschränkungen des Planungstools

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.



</div>

**Problem**

Das Planungs Tool weist bei der Planung Ihrer Bereitstellung die folgenden Einschränkungen auf:

  - Es werden maximal 10 Zentrale Standorte unterstützt.

  - Jeder zentrale Standort kann maximal 14 Zweigstellen aufweisen.

  - Jeder zentrale Standort kann maximal 240.000 Benutzer aufweisen.

Darüber hinaus enthält das Planungs Tool bei der Berechnung der empfohlenen Topologie keine Werte für Folgendes:

  - Die Anzahl der Benutzer, die Online verwaltet werden

  - Der Prozentsatz der Benutzer, die für den XMPP-Partnerverbund aktiviert sind.

  - Prozentsatz der Benutzer, die lync Web App verwenden

**Problemumgehung**

Es gibt keine Umgehungslösung für diese Probleme. Weitere Informationen zum Planungstool finden Sie unter [Entwerfen der Topologie für lync Server 2013 mithilfe des Planungstools](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>Planungs Tool verwendet möglicherweise nicht zuvor definierte IP-Adressen für das Edge-Netzwerk beim Aktualisieren von Optionen

**Problem**

Nachdem Sie Ihren Entwurf mit dem Planungs Tool abgeschlossen haben und Änderungen an den Edge-Netzwerkoptionen vorgenommen haben, werden dem Entwurf möglicherweise zusätzliche IP-Adressen hinzugefügt, anstatt die vorhandenen IP-Adressen zu aktualisieren. Dies kann auftreten, wenn Sie die Details des Edge-Netzplandiagramms anzeigen, wählen Sie **Klicken Sie hier, um Ihre Optionen zu aktualisieren**, und wählen Sie dann im Dialogfeld Konfigurationsoptionen die Option Edge-Netzwerk auswählen **Ich möchte dieselben FQDNs und IP-Adressen verwenden, aber unterschiedliche Ports für die Edge-Dienste auf meinem Edgeserver**. Das Anwenden von Änderungen kann dazu führen, dass neue IP-Adressen und Edgeserver zum Entwurf hinzugefügt werden.

**Problemumgehung**

Es gibt derzeit keine Umgehungslösung für dieses Problem.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>In lync Server-Systemsteuerung kann "alle Benutzer in Pool migrieren" möglicherweise nicht erwartungsgemäß ausgeführt werden.

**Problem**

Wenn Sie die lync Server-Systemsteuerung verwenden, um alle Benutzer von einem Pool in einen anderen Pool in einer komplexen Active Directory Umgebung zu versetzen, beispielsweise mit mehreren Domänencontrollern und übergeordneten/untergeordneten Domänen, wird möglicherweise eine Fehlermeldung zurückgegeben, die besagt, dass "der angegebene Benutzer kein älterer Benutzer ist" stattdessen das Cmdlet "CsUser" verwendet. Dies ist ein Ergebnis längerer Replikationszeiten in komplexen Active Directory Umgebungen.

**Problemumgehung**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Verwenden Sie Filter im lync Server-Systemsteuerung, um nach älteren Benutzern zu suchen, wählen Sie diese Benutzer aus, und verwenden Sie dann den **Befehl ausgewählte Benutzer zum Pool verlegen** , anstatt **alle Benutzer in den Pool**zu stellen.

  - Verwenden Sie die lync Server-Verwaltungsshell, um ältere Benutzer in Batches mithilfe von lync Server-Cmdlets zu migrieren.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Das lync Server-Systemsteuerung funktioniert in einer VMware-Umgebung nicht mehr, nachdem das Plug-in Microsoft Silverlight Browser auf Version 5 aktualisiert wurde.

**Problem**

Wenn Sie das lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert das lync Server-Systemsteuerung nach dem Upgrade von Silverlight auf Version 5 möglicherweise nicht mehr.

**Problemumgehung**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Deinstallieren Sie Silverlight 5, und installieren Sie dann Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)4 aus.

  - Öffnen Sie die lync Server-Systemsteuerung von einem Computer, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.
    
    Um die lync Server-Systemsteuerung von einem Remotecomputer aus zu öffnen, installieren Sie lync Server Verwaltungstools auf dem Computer, und starten Sie dann die lync Server-Systemsteuerung aus dem Windows- **Startmenü** .
    
    Sie können das lync Server-Systemsteuerung auch öffnen, indem Sie die URL in einen Webbrowser eingeben. \<Die URL ähnelt dem FQDN\_\_\>des https://-Front-End-Pools/CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Ein Administrator kann das Cmdlet "Uninstall-csMirrorDB" nicht ausführen, nachdem die Spiegelungsdatenbank im Topologie-Generator entfernt wurde.

**Problem**

Wenn ein Administrator eine Spiegelungsdatenbank im Topologie-Generator deaktiviert und dann die Spiegelungsdatenbank im Topologie-Generator löscht, wird eine Meldung in der Aufgabenliste angezeigt, mit der der Administrator das Cmdlet **Uninstall-csMirrorDatabase** ausführt, um die Spiegelung von SQL Server zu entfernen. Wenn der Administrator versucht, das Cmdlet auszuführen, wird ein Fehler zurückgegebenl.

**Problemumgehung**

Zum Entfernen der SQL-Spiegelung eines Pools im Topologie-Generator müssen Sie zunächst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen. Anschließend können Sie den Topologie-Generator verwenden, um den Spiegel aus der Topologie zu entfernen. Verwenden Sie das folgende Cmdlet, um die Spiegelung in SQL Server zu entfernen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Der Parameter *DropExistingDatabasesOnMirror* bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden. Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Deaktivieren Sie die Option **Spiegelung des SQL-Speichers aktivieren**, und klicken Sie auf **OK**.

3.  Veröffentlichen Sie die Topologie.

<div class="">


> [!IMPORTANT]  
> Wenn Sie eine Änderung an einer Back-End-Datenbank-Spiegelungs Beziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Validierungsfehler werden im Topologie-Generator zurückgegeben, wenn ein Administrator versucht, eine Bereitstellung mit einem Front-End-Pool zu entfernen, der über einen zugeordneten Zeugen Speicher verfügt.

**Problem**

Wenn ein Administrator versucht, den Befehl " **Bereitstellung entfernen** " im Topologie-Generator zu verwenden, um eine Bereitstellung zu entfernen, die eine Front-End-Pool mit einem zugeordneten Zeugen Speicher enthält, wird im Topologie-Generator ein Validierungsfehler angezeigt, und die Aktion wird nicht fortgesetzt.

**Problemumgehung**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Entfernen Sie den Zeugenspeicher, bevor Sie versuchen, die Bereitstellung zu entfernen.

  - Fügen Sie einen Zeugenspeicher für den Front-End-Pool hinzu, und entfernen Sie ihn dann.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>Bereitstellungsinformationen für persistent Chat Server sind inkonsistent zwischen dem Planungs Tool und dem Topologie-Generator

**Problem**

Wenn lync Server 2013 das Planungs Tool das Website Topologie-Diagramm für eine Server Bereitstellung für beständigen Chat bereitstellt und die Notfallwiederherstellung aktiviert ist, enthält das Diagramm für die Standorttopologie mehrere (physikalische) Websites mit gleichmäßig zugewiesenen beständigen Chatservern in jedem der beiden Seiten. Website. Im Topologie-Generator werden alle Server für beständigen Chat als Zugehörigkeit zu einem einzigen (logischen) Standort dargestellt und unter demselben Serverpool Knoten für beständigen Chat aufgeführt.

**Problemumgehung**

Derzeit kann dieses Problem nicht umgangen werden. Der Benutzer sollte die Ausgabe des Planungstools für die Server Bereitstellung für beständigen Chat analysieren und den Plan so ändern, dass er den spezifischen Anforderungen entspricht.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Lokalisierung

<div>

## <a name="monitoring"></a>Überwachung

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>Der Assistent zum Bereitstellen von Überwachungsberichten zeigt unter bestimmten Umständen falsche Zeichen an, wenn Sie die ostasiatische Version von lync Server verwenden.

**Problem**

Bei Verwendung einer ostasiatischen Version von lync Server 2013-beispielsweise Chinesisch (vereinfacht), Chinesisch (traditionell), Japanisch oder Koreanisch – auf einem Betriebssystem, auf dem das Systemgebietsschema nicht auf eine ostasiatische Sprache festgelegt ist, wird der Assistent zum Bereitstellen von Überwachungsberichten Anzeigen von Fragezeichen oder anderen Zeichen anstelle lokalisierter Nachrichten.

**Problemumgehung**

Um dieses Problem zu beheben, legen Sie das Gebietsschema für das Betriebssystem und die lync Server 2013 auf dieselbe Sprache fest, in der alle Nachrichten ordnungsgemäß angezeigt werden.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server-Systemsteuerung

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>In bestimmten Fällen wird das erste Element in der oberen Navigationsleiste auf einer Seite mit lync Server-Systemsteuerung ausgeblendet, wenn das letzte Element in der oberen Navigationsleiste geklickt wird.

**Problem**

Es gibt drei bekannte Fälle, in denen durch Klicken auf das letzte Element in der oberen Navigationsleiste auf einer Seite des lync Server-Systemsteuerung das erste Element in der oberen Navigationsleiste ausgeblendet wird:

  - In der französischen Version wird auf der Seite "Féderation et accès externe" das Element "Stratégie d'accès externe" nicht mehr angezeigt, wenn der Benutzer auf "Partenaires fédérés XMPP" klickt.

  - In der deutschen Version wird auf der Seite "Clients" das Element "Clientversionskonfiguration" nicht mehr angezeigt, wenn der Benutzer auf "Pushbenachrichtigungskonfiguration" klickt.

  - In der russischen Version wird auf der Seite "Конфигурация сети" das Element "Глобально" nicht mehr angezeigt, wenn der Benutzer auf "Маршрут региона" klickt.

**Problemumgehung**

Um dieses Problem zu umgehen, aktualisieren Sie die Seite des lync Server-Systemsteuerung in Ihrem Browser. Daraufhin wird die Seite im Browser geladen, und alle Elemente in der oberen Navigationsleiste werden angezeigt.

</div>

</div>

<div>

## <a name="address-book"></a>Adressbuch

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>Die Indizierung im Adressbuch funktioniert in einigen Sprachen nicht wie erwartet.

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.



</div>

Wenn die Eigenschaften eines Benutzers ein indiziertes Feld enthalten und dieses Feld nur Zeichen enthält, die nicht indiziert werden können, wird der Benutzer nicht in Suchvorgängen angezeigt, die im Adressbuch ausgeführt werden.

Die folgenden Zeichen und Gebietsschemas können nicht indiziert werden:

  - Großschreibung Kyrillisch, Griechisch und Armenisch Zeichen

  - Großbuchstaben mit akzentuierten Zeichen

  - Thailändisch

  - Laotisch

  - Myanmar

  - Devanagari

  - Äthiopisch

  - Tibetanisch

  - Bengali

  - Gujarati

  - Telugu

  - Alle anderen indischen Skripts

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App-, Webplaner-und Webkomponenten

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Sprach Fallback für bestimmte Sprachen in lync-Webplaner, Einwahl, Startprogramm, beständiger chatroomverwaltung und OCTab funktionieren möglicherweise nicht wie erwartet

**Problem**

Bei der Auswahl eines neutralen Gebietsschemas in einem Webbrowser (in Internet Explorer beispielsweise kann der Name der Sprache ohne weitere Angaben wie " \[Norwegisch\]Nein" anstelle eines Gebietsschemas, das die Sprache, das Skript und das Gebietsschema angibt (wie "Norwegisch \[, Nynorsk (\]Norwegen) nb-no") zu unerwartetem Anzeigeverhalten für bestimmte Sprachen in lync-Webplaner, Einwahl, Join Launcher, beständiger chatroomverwaltung und OCTab führen. Beispielsweise wird den Benutzern beim Auswählen einer der folgenden Sprachen möglicherweise die englische Seite angezeigt:

  - Norwegisch

  - Portugiesisch

  - Serbisch

**Problemumgehung**

Wenn Sie eine Sprache mit neutralem Gebietsschema auswählen möchten, achten Sie darauf, dass Sie in der Spracheinstellungsliste Ihres Browsers auch die Sprache mit einem spezifischen Gebietsschema (einschließlich Skript und/oder Ländercode) als zusätzliche Sprache hinzufügen.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Es gibt nur beschränkte Unterstützung für aserbaidschanische und usbekische Gebietsschemas bei Verwendung von lync-Webplaner, Einwahl, Join Launcher, beständiger chatroomverwaltung und OCTab in einigen Webbrowsern.

<div class="">


> [!NOTE]  
> Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.



</div>

**Problem**

Wenn Sie Internet Explorer 8 oder Internet Explorer 9 verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden die Seiten für Einwahl-und Join-Startprogramm in Englisch oder im Browser als bevorzugte Sprache angezeigt.

Wenn Sie Firefox oder Chrome Browser verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden lync Web App, lync-Webplaner und RGS-OCTab in Englisch oder in der bevorzugten Spracheinstellung für den Browser angezeigt.

Das Gebietsschema usbekischen (lateinisch) wird im Safari-Browser nicht unterstützt.

**Problemumgehung**

Es gibt keine Umgehungslösung für diese Probleme.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>Der Dropdownpfeil fehlt bei der Liste "an der Besprechung teilnehmen" in der rumänischen Version von lync Web App

**Problem**

Wenn ein Benutzer, der die rumänische Version von lync Web App verwendet, die folgenden Schritte ausführt, wird der Dropdownpfeil für **Teilnahme an Besprechung** in der Dropdownliste nicht angezeigt:

1.  Wählen Sie auf der Registerkarte **Allgemein** die Option **Meine Daten auf diesem Computer speichern** aus.

2.  Wählen Sie die Registerkarte **Telefon** aus.

3.  Klicken Sie auf die Dropdownliste unter **An Besprechung teilnehmen über**.
    
    Benutzern wird kein Pfeil angezeigt, der angibt, dass es mehr Optionen als die Standard **lync Web App**gibt, die Folgendes umfassen: **Join Audio** (in Rumänisch, "Nu SE asociaža La Componenta Audio") und **New Number**"(in rumänischer Sprache," Număr Nou ").

**Problemumgehung**

Obwohl der Pfeil für diese Dropdownliste nicht angezeigt wird, können die Benutzer die zusätzlichen Einstellungen in der Liste auswählen, indem Sie auf den Standardwert klicken.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Bei Verwendung der türkischen Version von lync-Webplaner kann eine Besprechung nicht gespeichert werden, wenn die Option "Personen, die ich auswählen" unter "Wer ist ein Referent ist" verwendet wird.

**Problem**

Beim Erstellen oder Bearbeiten einer Besprechung in der türkischen Version des Lync-Webplaners wird die Option "Von mir ausgewählte Personen" unter "Wer agiert als Referent" nicht unterstützt. Bei Auswahl dieser Option kann die Besprechung nicht gespeichert werden. Stattdessen wird eine Fehlermeldung mit dem Hinweis angezeigt, dass eine oder mehrere Personen nicht als Referenten agieren können.

**Problemumgehung**

Um dieses Problem zu umgehen, können die Benutzer die Standardoption "Personen in meinem Unternehmen" oder eine andere Option wie "Nur Organisator" oder "Alle, auch Personen außerhalb meines Unternehmens" verwenden. Der Organisator kann Personen später auf die richtigen Rollen herunter- oder heraufstufen, nachdem sie der Besprechung beigetreten sind.

Alternativ dazu können Benutzer, die eine andere Sprache verstehen, die Sprachauswahl in ihrem Browser in eine der anderen 43 unterstützten Sprachen ändern und versuchen, die Option "Von mir ausgewählte Personen" zu verwenden.

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Copyright

Dieses Dokument unterstützt eine Vorabversion eines Softwareprodukts, die vor der endgültigen Freigabe für den Handel wesentlich geändert werden kann. Im Dokument sind geschützte und vertrauliche Informationen von Microsoft enthalten. Das Informationsmaterial wird gemäß einer Vertraulichkeitsvereinbarung zwischen dem Empfänger und Microsoft zugänglich gemacht. Dieses Dokument dient nur zu Informationszwecken, und Microsoft schließt jede ausdrückliche oder konkludente Gewährleistung für dieses Dokument aus. Die in diesem Dokument enthaltenen Informationen, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden. Das gesamte Risiko bezüglich der Verwendung oder der Ergebnisse der Verwendung dieses Dokuments verbleibt beim Benutzer. Die in den Beispielen verwendeten Namen von Firmen, Organisationen, Produkten, Domänen, Personen, Orten, Ereignissen sowie E-Mail-Adressen und Logos sind frei erfunden, soweit nichts anderes angegeben ist. Jede Ähnlichkeit mit tatsächlichen Firmen, Organisationen, Produkten, Domänennamen, Personen, Orten, Ereignissen, E-Mail-Adressen und Logos ist rein zufällig. Die Benutzer/innen sind verpflichtet, sich an alle anwendbaren Urheberrechtsgesetze zu halten. Unabhängig von der Anwendbarkeit der entsprechenden Urheberrechtsgesetze darf ohne ausdrückliche schriftliche Erlaubnis der Microsoft Corporation kein Teil dieses Dokuments für irgendwelche Zwecke vervielfältigt oder in einem Datenempfangssystem gespeichert oder darin eingelesen werden, unabhängig davon, auf welche Art und Weise oder mit welchen Mitteln (elektronisch, mechanisch, durch Fotokopieren, Aufzeichnen usw.) dies geschieht.

Microsoft kann Inhaber von Patenten oder Patentanträgen, Marken, Urheberrechten oder anderem geistigen Eigentum sein, die den Inhalt dieses Dokuments betreffen. Die Bereitstellung dieses Dokuments gewährt keinerlei Lizenzrechte an diesen Patenten, Marken, Urheberrechten oder anderem geistigen Eigentum, es sei denn, dies wurde ausdrücklich durch einen schriftlichen Lizenzvertrag mit der Microsoft Corporation vereinbart.

© 2012 Microsoft Corporation. Alle Rechte vorbehalten.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook und SQL Server sind eingetragene Marken oder Marken der Microsoft Corporation in den USA und/oder anderen Ländern/Regionen.

Alle anderen Marken sind Eigentum der jeweiligen Inhaber.

</div>

</div>

<span> </span>

</div>

</div>

</div>

