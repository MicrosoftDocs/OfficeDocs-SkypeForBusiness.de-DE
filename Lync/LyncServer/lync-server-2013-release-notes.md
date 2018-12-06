---
title: 'Lync Server 2013: Anmerkungen zu dieser Version'
TOCTitle: Anmerkungen zu dieser Version
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205120(v=OCS.15)
ms:contentKeyID: 49294924
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anmerkungen zu dieser Version für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Willkommen bei den Versionshinweisen zu Lync Server 2013. In dieser Datei finden Sie Informationen zu bekannten Problemen von Lync Server 2013.

## Über dieses Dokument

Dieses Dokument enthält wichtige Informationen, die Sie vor der Bereitstellung und Verwendung von Lync Server 2013 lesen sollten. Einzelheiten zu Lync Server 2013 finden Sie in der Dokumentation für [Microsoft Lync Server 2013](microsoft-lync-server-2013.md).

Dieses Dokument enthält die folgenden Abschnitte:

  - Lync 2013-Client

  - Lync Server

  - Installation

  - Mobilität

  - Konferenzen

  - Enterprise-VoIP

  - Anwesenheit

  - Reaktionsgruppenanwendung, Anwendung zum Parken von Anrufen und Annahme von Gruppenanrufen

  - Lync Server-Systemsteuerung, Topologie-Generator und Planungstool

  - Lokalisierung

  - Copyright

## Lync 2013-Client

## Beim Übertragen einer Datei in einer Chatnachricht tritt ein Fehler auf, wenn die Datei in einer anderen Anwendung geöffnet wird (1920369).

**Problem:**

Wenn Sie versuchen, eine Datei wie ein Word-Dokument zu übertragen, indem Sie die Datei in eine Chatnachricht an einen anderen Lync-Benutzer einfügen, scheint die Übertragung erfolgreich gewesen zu sein, tatsächlich wird die Datei aber möglicherweise nicht übertragen. Ein Symbol für den Dateityp wird im Lync-Client angezeigt, aber die Datei kann vom vorgesehenen Empfänger nicht geöffnet werden. Es wird keine Fehlermeldung angezeigt, um Sie zu informieren, dass die Übertragung nicht erfolgreich war.

**Problemumgehung:**

Sie können dieses Problem umgehen, indem Sie die geöffnete Datei oder die Anwendung, in der sie geöffnet ist, schließen, bevor Sie versuchen, die Datei in einer Chatnachricht zu übertragen.

## Lync Server

## Wenn die Speicherdienst-Datenreplikation von Lync Server fehlschlägt, müssen die Administratoren die Leistungsindikatoren auf veraltete Speicherdienst-Warteschleifenelemente (3225121) überprüfen

**Problem:**

Der Lync Server-Speicherdienst nutzt Windows Fabric für die Replikation. Wenn Daten für einen primären Front-End-Server gelöscht werden, aber die Löschung für einen sekundären Front-End-Server fehlschlägt (beispielsweise aufgrund einer unerwarteten Abschaltung oder eines unerwarteten Fehlers des Front-End-Servers), können die Daten zurückgelassen werden und "verwaisen". Die verwaisten Daten können zu Leistungsbeeinträchtigungen und Speicherplatzverschwendung führen.

**Problemumgehung:**

Um dieses Problem zu umgehen, sollten die Administratoren, sofern die Ereignisse LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) und LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) im Ereignisprotokoll generiert werden, den Leistungsindikator für den Front-End-Server unter **LS:LYSS - Storage Service API** mit der Bezeichnung **LYSS - Current number of Storage Service stale queue items** überprüfen. Wenn dieser Leistungsindikator einen hohen Wert hat, beispielsweise größer als 50.000, sollte der Administrator das Tool "CleanuUpStorageServiceData.exe" im Resource Kit für Lync Server 2013 ausführen, mit dessen Hilfe alle verwaisten Daten aus dem Pool gelöscht werden. Einzelheiten zu dem Tool finden Sie in der Lync Server 2013 Resource Kit-Dokumentation.

## Bei jeder Änderung der IP-Adresskonfiguration für einen Server oder Pool müssen die Lync Server-Dienste neu gestartet werden (3212447)

**Problem:**

Beim Ändern der IP-Adresskonfiguration für eine Lync Server 2013-Bereitstellung, beispielsweise von IPv4 in Dualstapel oder von Dualstapel in IPv6, nehmen nicht alle Serverkomponenten die Konfigurationsänderung an, bis die Dienste neu gestartet werden.

**Problemumgehung:**

Starten Sie zur Umgehung dieses Problems die Lync Server-Dienste nach dem Ändern der IP-Adresskonfiguration für die Bereitstellung neu. Führen Sie dazu die folgenden Cmdlets in der Lync Server-Verwaltungsshell aus:

    Stop-CsWindowsService -graceful

   &nbsp;

    Start-CsWindowsService

## Das Cmdlet für die synthetische Transaktion der Einwahlkonferenz ist im Lync Server 2013 Management Pack (3212342) nicht mehr verfügbar

**Problem:**

Das Cmdlet **Test-CsDialInConferencing** für die synthetische Transaktion der Einwahlkonferenz ist im Lync Server 2013 Management Pack nicht mehr verfügbar.

**Problemumgehung:**

Die Verwendung des Cmdlets **Test-CsDialInConferencing** für die synthetische Transaktion der Einwahlkonferenz wird nur intern für Unternehmen unterstützt.

Administratoren können das Cmdlet in Lync Server-Verwaltungsshell weiterhin für Fehlerbehebungszwecke verwenden. Bei Bedarf kann ein Unternehmen auch ein privates Management Pack zur internen Ausführung des Cmdlets entwickeln.

## Der zentralisierte Protokollierungsdienst wird angehalten, wenn der Netzwerkdatenverkehr beim Kopieren von Protokolldateien auf das Netzlaufwerk gestört wird (3212464)

**Problem:**

Wenn der zentralisierte Protokollierungsdienst für die Verwendung eines Netzwerkpfads (der Wert des Parameters "CacheFileNetworkFolder" des **Get-CsClsConfiguration**-Cmdlets ist ein gültiger UNC-Pfad) konfiguriert ist, werden zwischengespeicherte Protokolldateien auf das Netzlaufwerk kopiert. Wenn beim Kopieren der Dateien eine Störung im Netzwerkdatenverkehr auftritt, wird eine Ausnahme ausgelöst, durch die der zentralisierte Protokollierungsdienst angehalten wird.

Der Dienst ist für bis zu drei automatische Neustarts konfiguriert, sodass er ausgehend von den ersten drei Ausnahmen neu gestartet wird.

**Problemumgehung:**

Für dieses Problem existiert keine Problemumgehung. Wenn Sie das Problem identifizieren möchten, überwachen Sie das Ereignisprotokoll für die Ereignis-ID 7031 aus dem Dienststeuerungs-Manager. Mithilfe dieses Managers wird protokolliert, wann der Dienst Zentralisierter Protokollierungsdienstagent für Lync Server unerwartet beendet wurde. Wenn dies öfter als dreimal geschieht, starten Sie den Dienst mithilfe des Cmdlets **Start-CsWindowService** manuell neu.

## Speicherdienst-Warteschleifenelemente müssen manuell importiert werden (3211368)

**Problem:**

Lync Server 2013 speichert Daten zu Konferenzen und Sofortnachrichten, beispielsweise zu archivierten Nachrichten und Kommunikationsdatensätzen (KDS), in einer Datenbank für jede Front-End-Server. Die Daten werden während ihrer Verarbeitung in der Datenbank gespeichert, bevor sie an das gewünschte Ziel gesendet werden. Zur Optimierung der Leistung exportiert Lync Server 2013 die Warteschleifenelemente regelmäßig aus der lokalen Datenbank, die für einen längeren Zeitraum nicht verarbeitet wurden, und sie werden im Dateispeicher gespeichert. Wenn der Dateispeicher nicht verfügbar ist, werden die Elemente unter jeder Front-End-Server gespeichert. Derselbe Vorgang wird zum Verhindern von Datenverlusten bei Failovervorgängen für Pools verwendet.

Während des Exportvorgangs zeichnet der Lync Server-Speicherdienst alle Phasen im Ereignisprotokoll auf. Dabei werden die Ereignis-IDs 32075 (vollständiger Leerungsvorgang wurde gestartet), 32076 (vollständige Leerung ist abgeschlossen), 32082 (Leerung auf Wartungsebene wurde gestartet), 32083 (Leerung auf Wartungsebene wurde abgeschlossen) und 32089 (Leerung aufgrund der Füllung der Datenbank aufgetreten) verwendet. Diese Daten werden nicht automatisch in das System zurückexportiert, um verarbeitet und an das Endziel gesendet zu werden (SQL Server oder Exchange Server).

**Problemumgehung:**

Zum Importieren der Daten in das System müssen Administratoren das ImportStorageServiceData-Tool im Lync Server Resource Kit verwenden, mit dessen Hilfe die Daten für die Verarbeitung und das Senden an das Endziel wieder dem System hinzugefügt werden.

## Suchvorgänge in Adressbuch-Webabfragen schlagen fehl, wenn der Standardwert für UseNormalizationRules in "False" geändert wird (3175514)

**Problem:**

Wenn der Standardwert für UseNormalizationRules in "False" geändert wird, schlagen Adressbuch-Webabfragen fehl. Nach dem Ändern des Standardwerts können Lync Client-Benutzer die Lync-Adressbuch-Webabfrage nicht zum Suchen nach Benutzern verwenden.

**Problemumgehung:**

Wenn Sie den Standardwert für UseNormalizationRules auf "False" festlegen, sodass Benutzer Telefonnummern gemäß Definition in Active Directory-Domänendienste verwenden können, ohne dass in Lync Server 2013 Normalisierungsregeln angewendet werden, können Sie das Problem durch Ausführen der folgenden Aktionen umgehen:

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Ihre Bereitstellung nur Lync Server 2013-Server beinhaltet, führen Sie auf der globalen Ebene das folgende Cmdlet aus, um die Werte für UseNormalizationRules und IgnoreGenericRules auf "True" festzulegen:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Wenn Ihre Bereitstellung eine Kombination aus Lync Server 2013 und Lync Server 2010 oder Office Communications Server 2007 R2 umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Lync Server 2013-Pool in der Topologie zu:

      ```
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
      ```

3.  Warten Sie, bis die CMS-Replikation für alle Pools erfolgt ist.

4.  Ändern Sie die Datei mit den Telefonnormalisierungsregeln für Ihre Bereitstellung, sodass die Inhalte gelöscht werden. Die Datei befindet sich in der Dateifreigabe der einzelnen Lync Server 2013-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit der Bezeichnung "Company\_Phone\_Number\_Normalization\_Rules.txt“.

5.  Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6.  Führen Sie das folgende Cmdlet in den einzelnen Lync Server 2013-Pools in Ihrer Bereitstellung aus.
    
        Update-csAddressBook

## Das Adressbuchserver-Fehlerereignis 21054 wird einmal täglich für alle Lync 2013-Pools generiert (3195918)

**Problem:**

Der Lync Server 2013-Adressbuchserver generiert beim Ausführen der täglichen Wartung einmal täglich das Fehlerereignis 21054. Der Fehler wird auch immer dann generiert, wenn ein Administrator das Cmdlet **Update-csAddressBook** ausführt. Dies ist selbst dann der Fall, wenn die Aktualisierung erfolgreich war. Bei einer erfolgreichen Aktualisierung kann dieses Fehlerereignis jedoch bedenkenlos ignoriert werden.

**Problemumgehung:**

Wenn dieses Fehlerereignis eintritt, führen Sie das folgende Cmdlet aus:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Wenn das Cmdlet meldet, dass keine nicht indizierten oder abgebrochenen Objekte vorhanden sind, kann das Fehlerereignis 21054 bedenkenlos ignoriert werden.

Zudem sollte der Key Health Indicator (KHI) "Adressbuchbenutzer ordnungsgemäß indiziert" im System Center Operations Manager deaktiviert werden.

## Möglicherweise schlagen Anforderungen fehl, wenn IPv6 auf einem Edgepool konfiguriert ist (3205810)

**Problem:**

Wenn IPv6 auf einem Edgepool konfiguriert ist, schlagen möglicherweise einige Anforderungen an den Edgepool fehl.

**Problemumgehung:**

Konfigurieren Sie zur Umgehung dieses Problems Edgepools nicht mit IPv6.

## Das Cmdlet invoke-csPoolFailback ist bei einem Failback-Vorgang für den Pool möglicherweise fehlerhaft (3206153)

**Problem:**

Beim Versuch, einen Failback-Vorgang für einen Pool auszuführen, gibt das Cmdlet **invoke-csPoolFailback** möglicherweise den Fehler "Abschluss des Hydrationsprozesses nach mehreren Versuchen fehlgeschlagen" zurück.

**Problemumgehung:**

Wenn Sie dieses Problem umgehen möchten, führen Sie das Cmdlet erneut aus, und warten Sie, bis das Cmdlet erfolgreich abgeschlossen wurde. Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nehmen kann. Für einen Pool mit 20.000 Benutzern kann dies bis zu 60 Minuten dauern.

## Beim Hinzufügen eines Front-End-Servers zu einem bereits eingerichteten Pool tritt möglicherweise ein Datenverlust ein (3015990) - Hybrid, Skype for Business Online

**Problem:**

Dieses Problem kann in einer Umgebung auftreten, in der ein Pool mehr als einen Front-End-Server enthält, und wenn Sie einen der Front-End-Server neu starten oder einen neuen Front-End-Server hinzufügen, der zuvor nicht zum Pool gehörte.

Bei Benutzern, deren Daten archiviert werden, kommt es möglicherweise zu Datenverlusten, bis eine stabile Verteilung der Datenarchivierung für den Pool hergestellt wurde. Dieser Zeitraum mit potenziellem Datenverlust ist für Konversationen zwischen Personen auf 15 Minuten und für Konferenzen auf 30 Minuten begrenzt.

**Problemumgehung:**

Anstelle beim Ausführen von Wartungsarbeiten im Pool die Front-End-Server einzeln zu starten, sollten Sie für den Pool einen Failover-Vorgang zu einem anderen Pool ausführen und die Wartungsaufgaben dann auf den Servern ausführen. Sie können die Verfügbarkeit des Diensts vor dem Ausführen von Wartungsaufgaben auch aufheben und die Verfügbarkeit dann nach Abschluss der Wartung wiederherstellen.

## Administratoren können die Lizenzanzahl nicht mithilfe des Cmdlets Get-CsClientAccessLicense abrufen (3012255)

**Problem:**

Administratoren können die genaue Clientlizenzverwendung nicht mithilfe des Cmdlets **Get-CsClientAccessLicense** abrufen.

**Problemumgehung:**

Wenn Sie den Serverlizenztyp überprüfen möchten, können Sie das Cmdlet **Get-CsService** ausführen, um die vollqualifizierten Domänennamen (Fully Qualified Domain Names, FDQNs) aller Datenbanken abzurufen. Wenn der FQDN des Front-End-Servers mit dem FQDN der Back-End-Datenbank übereinstimmt, handelt es sich bei der Lizenz um eine Standard Edition-Lizenz. Andernfalls ist die Lizenz eine Enterprise Edition-Lizenz.

## Die Clientlizenzanzahl wird nicht ordnungsgemäß gemeldet (3010175)

**Problem:**

Beim Ermitteln der Clienlizenzanzahl liegen möglicherweise die folgenden Zustände vor:

1.  **Ungenaue Lizenzanzahl für mobile Benutzer**
    
    Die Lizenzanzahl basiert auf der Anzahl eindeutiger IP-Adressen für gerätebasierte Benutzer. Die Lizenzanzahl wird wie folgt begrenzt:
    
      - Es werden zu viele Lizenzen gezählt, wenn sich die IP-Adresse für den Benutzer in Lync-Sitzungen ändert. Dieser Fall kann eintreten, wenn ein Benutzer an mehreren Standorten mit einem Desktopclient eine Verbindung mit Lync Server herstellt.
    
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

**Problemumgehung:**

1.  **Ungenaue Lizenzanzahl für mobile Benutzer**
    
      - Sie können die IP-Adressen, die zu ein und demselben Gerät gehören, manuell identifizieren und dann eine der Adressen aus der Lizenzanzahl entfernen.
    
      - Beim Verbinden mobiler Geräte mit dem Lync-Client kann dieses Problem nicht umgangen werden.

2.  **Für PSTN-Anrufe des Lync-Clients, Lync-Client-Anrufe an PSTN-Leitungen und Lync-Anrufweiterleitungen an PSTN-Leitungen werden Lizenzen doppelt gezählt**
    
    Sie müssen die PSTN-Telefonnummer manuell identifizieren und die für sie generierte Lizenzanzahl entfernen.

3.  **Für angemeldete Lync-Telefone werden keine Lizenzen gezählt**
    
    Sie können das Lync-Telefon so konfigurieren, dass es in einem regelmäßigen Intervall (beispielsweise alle drei Monate) abgemeldet und dann wieder angemeldet wird.

4.  **Gezählte Lizenzen für PSTN-Telefone, die Konferenzen beitreten**
    
    Sie können die PSTN-Telefonnummer, die für den Konferenzbeitritt verwendet wird, manuell identifizieren und die von der Telefonnummer generierte Lizenz entfernen.

## Lync Server-Systemsteuerung funktioniert in einer VMware-Umgebung nach dem Upgrade auf Silverlight 5 nicht mehr (3010077)

**Problem:**

Wenn Sie Lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert Lync Server-Systemsteuerung nach dem Upgrade von Microsoft Silverlight auf Version 5 möglicherweise nicht mehr.

**Problemumgehung:**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Deinstallieren Sie Silverlight 5 und installieren Sie Silverlight 4 unter [http://go.microsoft.com/fwlink/p/?LinkID=149156](http://go.microsoft.com/fwlink/p/?linkid=149156).

  - Greifen Sie von einem Computer, bei dem es sich nicht um einen virtuellen VMware-Computer handelt, auf Lync Server-Systemsteuerung zu.
    
    Dazu können Sie Lync Server-Systemsteuerung im Menü **Start** von Windows auf dem Server starten, sofern die Lync Server-Verwaltungsserver auf dem Computer installiert sind.
    
    Der Zugriff auf Lync Server-Systemsteuerung ist auch mithilfe eines Webbrowsers möglich. Die URL ähnelt "https://\<frontend\_pool\_fqdn\>/cscp".

## Benutzerinformationen im Adressbuchdienst werden nicht aktualisiert, nachdem der definierte Name für den Benutzer in Active Directory geändert wird (3211549)

**Problem:**

Wenn der definierte Name (auch als DN bezeichnet) eines Benutzers in Active Directory-Domänendienste geändert wird, werden zusätzliche Änderungen im Adressbuchdienst (Address Book Service, ABS) nicht aktualisiert. Dies wirkt sich nicht auf die Anmeldung oder die Existenz des Benutzers aus. Die Kommunikation wird jedoch für den Benutzer verhindert, sofern die SIP-Adresse ebenfalls geändert wird, da die Suchvorgänge dann eine veraltete SIP-Adresse zurückgeben.

**Problemumgehung:**

Wenn Sie dieses Problem umgehen möchten, ändern Sie den DN eines Benutzers nicht. Wenn Sie den DN für den Benutzer auf den vorherigen Wert zurücksetzen, spiegeln sich Aktualisierungen im Adressbuchdienst wider.

## Installation

## Die Verwendung von Nicht-ASCII-Zeichen kann dazu führen, dass Lync Server nicht gestartet wird

**Problem:**

Das Setup schlägt fehl, wenn der Zielordner Nicht-ASCII-Zeichen (einschließlich UNICODE, Doppelbyte-Zeichensatz (DBCS), UTF-8 und UTF-16). Außerdem könnte der Server möglicherweise nicht starten, obwohl das Setup erfolgreich verlaufen ist, wenn eines der folgenden Elemente Nicht-ASCII-Zeichen enthält:

  - Computername

  - Domänenname

  - Benutzername

  - Benutzer-SIP-URI

  - Dienstkontoname

**Problemumgehung:**

Verwenden Sie für den Name des Zielordners, den Computernamen, Domänennamen, Benutzernamen, Benutzer-SIP-URI und die Dienstkontonamen ausschließlich ASCII-Zeichen.

## Vor dem Installieren von Lync Server 2013 muss der Hotfix für "Beim Aufrufen der Methode 'InsertEntityBody' in IIS 7.5 durch ein Modul tritt eine Heapbeschädigung auf" installiert werden.

**Problem:**

Der Hotfix für "Beim Aufrufen der Methode 'InsertEntityBody' in IIS 7.5 durch ein Modul tritt eine Heapbeschädigung auf" ( [http://go.microsoft.com/fwlink/?linkid=268602\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268602%26clcid=0x407)), der im Microsoft Knowledge Base-Artikel 264886 ( [http://go.microsoft.com/fwlink/?linkid=268603\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268603%26clcid=0x407)) beschrieben wird, muss vor dem Installieren von Lync Server 2013 installiert werden.

**Problemumgehung:**

Laden Sie den Hotfix vom Microsoft Download Center unter [http://go.microsoft.com/fwlink/?linkid=268602\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268602%26clcid=0x407) herunter, und installieren Sie ihn.

## Lync Server 2013 kann in ITA Windows Server 2012 OS RTM-Version nicht installiert werden (3179467)

**Problem:**

Die Lync Server 2013-Installation ist in ITA Windows Server 2012 aufgrund eines Fehlers bei der Windows Fabric-Installation fehlerhaft.

Die Windows Fabric-Installation ist fehlerhaft, weil Fabric-Ablaufverfolgungen im Zeitformat "HH:MM:SS" erstellt werden. Das Zeitformat in ITA Windows Server lautet jedoch "HH.MM.SS".

**Problemumgehung:**

Wenn Sie dieses Problem umgehen möchten, aktualisieren Sie die Systemregistrierung, bevor Sie Lync Server 2013 installieren. Der zu aktualisierende Registrierungsschlüssel lautet: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat. Ändern Sie den Wert von "sTimeFormat" in "HH:mm:ss", indem Sie Windows PowerShell-Befehlszeilenschnittstelle wie folgt verwenden:

1.  Starten Sie Windows PowerShell, und führen Sie die folgenden Cmdlets aus:
    
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS

       &nbsp;
    
        $a="HKU:\.Default\Control Panel\International"

2.  Führen Sie zum Anzeigen des aktuellen Werts das folgende Cmdlet aus:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Notieren Sie den aktuellen Wert für "sTimeFormat", sodass er nach Abschluss der Installation wiederhergestellt werden kann.

3.  Führen Sie zum Festlegen auf den neuen Wert das folgende Cmdlet aus:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Nachdem Lync Server 2013 erfolgreich installiert wurde, stellen Sie den ursprünglichen Wert für "sTimeFormat" wieder her, indem Sie das folgende Cmdlet ausführen:
    
        - Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3. above>"

## Mobilität

## Probleme für mobile Clients während des Server-Failovervorgangs (3345992)

**Problem:**

Wenn ein Lync-Server ausfällt und der Failovervorgang beginnt, können Benutzer von mobilen Clients von den folgenden Problemen betroffen werden:

  - Keine eingehenden Lync-Anrufe bzw. kein Signal für bis zu 10 Minuten nach dem Beginn des Failovers.

  - Eingehende Chatanforderungen können nicht akzeptiert werden

  - Eine Teilnahme an Besprechungen ist nicht möglich, wenn der ausgefallene Server der Homeserver des Benutzers ist

**Problemumgehung:**

Es ist keine Umgehung für dieses Problem verfügbar. Nach Abschluss des Failovervorgangs wird die normale Funktionalität wiederhergestellt.

## Wenn ein mobiler Benutzer einen eingehenden Anruf von einem anderen Lync-Endpunkt ablehnt, wird der Anruf auf Lync Mobile-Clients als verpasste Unterhaltung angezeigt (3346251)

**Problem:**

Wenn ein mobiler Benutzer einen eingehenden Anruf ablehnt, der von einem anderen Lync-Endpunkt stammt, wird der Anruf als verpasste Unterhaltung im Lync Mobile-Client statt als Anruf in der Anrufliste des Geräts angezeigt.

**Problemumgehung:**

Es ist keine Umgehung für dieses Problem verfügbar.

## Im mobilen Client wird der Anzeigename eines Verbundkontakts bei der Suche nach Kontakten möglicherweise nicht angezeigt (3346256)

**Problem:**

Der Anzeigename für Verbundkontakte wird in einigen Szenarien möglicherweise nicht angezeigt, etwa beim Suchen nach einem Verbundkontakt in der Kontaktliste. Dies kann geschehen, wenn auf dem mobilen Lync-Client kein aktives Anwesenheitsabonnement für den Kontakt besteht.

**Problemumgehung:**

Es ist keine Umgehung für dieses Problem verfügbar.

## Im mobilen Client fehlen in verpassten Unterhaltungen, die zugleich Einladungen zu einer Konferenz sind, die Informationen zu den Eingeladenen und der Zeitstempel (3346265)

**Problem:**

Wenn eine verpasste Unterhaltung zugleich eine Konferenzeinladung darstellt, fehlen im mobilen Client die Informationen zu den Eingeladenen und der Zeitstempel in der Nachricht über die verpasste Unterhaltung.

**Problemumgehung:**

Es ist keine Umgehung für dieses Problem verfügbar.

## Benutzer von mobilen Clients, die Anrufe über VoIP führen, können keine Voicemail für Benutzer hinterlassen, deren Voicemail in Exchange 2010 oder früheren Versionen konfiguriert ist (3346260)

**Problem:**

Wenn ein Benutzer eines mobilen Clients VoIP für Anrufe verwendet, kann er keine Voicemailnachrichten für Benutzer zurücklassen, deren Voicemail in Microsoft Exchange Server 2007 oder Microsoft Exchange Server 2010 konfiguriert ist.

**Problemumgehung:**

Verwenden Sie zur Umgehung dieses Problems Exchange 2010 mit SP1 oder eine höhere Version von Microsoft Exchange Server.

## Bei der Verwendung von Mit URL blockieren für die Clientversionskonfiguration auf mobilen Clients wird möglicherweise eine unzutreffende Fehlermeldung angezeigt (3346258)

**Problem:**

Bei der Verwendung von **Mit URL blockieren** für die Clientversionskonfiguration auf mobilen Clients wird möglicherweise eine unzutreffende Fehlermeldung angezeigt, wenn die Clientversion nicht unterstützt wird.

**Problemumgehung:**

Zum Umgehen dieses Problems konfigurieren Sie die Clientversionskonfiguration für die Verwendung von **Blockieren** anstelle von **Mit URL blockieren**.

## Konferenzen

## Unter Lync Server 2013Front-End-Server ausgeführte Antivirensoftware kann ein Anwendungsdomänenrecycling verursachen, wodurch der Dienst für Clients von Lync Web App 2013, Lync Mobile 2010 und Lync Mobile 2013 vorübergehend unterbrochen wird (3212531)

**Problem:**

Durch Antivirensoftware können Neustarts von Anwendungsdomänen verursacht werden, die dazu führen können, dass Lync Mobility Service 2013 und Unified Communications (UC) Web API-Clientanwendungen (Lync Web App 2013, Lync Mobile 2010 und Lync Mobile 2013) ihren Status verlieren.

**Problemumgehung:**

Wenn Sie dieses Problem umgehen möchten, schließen Sie die Ordner mit Webkomponenten und .NET Framework aus dem Virenschutzprogramm aus. Einzelheiten dazu finden Sie im Microsoft Knowledge Base-Artikel 312592 "PRB: Zufällige Anwendungsneustartes mit dem Fehler 'Die Anwendung wird neu gestartet' in ASP.NET" unter [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x407).

Die folgenden Ordner sollten ausgeschlossen werden:

  - %Programme%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext

  - %Programme%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int

  - %Programme%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int

  - %Programme%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext

  - %Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config

## ActiveX-Steuerelemente oder die systemeigene XMLHTTP-Unterstützung muss in Windows Internet Explorer aktiviert werden, um Konferenzen erfolgreich beitreten zu können (2798163)

**Problem:**

Wenn ein Benutzer ActiveX-Steuerelemente und die systemeigene XMLHTTP-Unterstützung in den Internetbrowsereinstellungen von Windows Internet Explorer deaktiviert hat, kann der Benutzer keiner Besprechung beitreten, falls Internet Explorer als Standardbrowser ausgewählt ist.

**Problemumgehung:**

Aktivieren Sie in Internet Explorer ActiveX-Steuerelemente oder die "systemeigene XMLHTTP-Unterstützung".

## Der Lync Server-Webkonferenzdienst wird im kritischen Modus nicht automatisch wiederhergestellt (2788663)

**Problem:**

Wenn der kritische Modus zur Archivierung aktiviert ist, startet der kritische Modus im Falle eines Systemausfalls, und die Konferenz ist für die Teilnehmer nicht mehr zugänglich. Nachdem der Administrator die Systemausfälle behoben hat (beispielsweise ein Datenbankproblem), wird der Datenkonferenzdienst nicht automatisch wiederhergestellt, und der Administrator muss den Konferenzdienst zum Fortsetzen der Konferenz manuell neu starten.

**Problemumgehung:**

Ein Administrator muss den Konferenzdienst manuell neu starten, nachdem der Systemausfall behoben wurde.

## Webkonferenzdienst ignoriert den HTTP-Proxy für externe Office Web App-Server (2602182)

**Problem:**

Wenn Sie einen externen Office Web Apps-Server für den Webkonferenzdienst (d. h. einen Server, der sich nicht im internen Unternehmensnetzwerk befindet) im Internet oder Umkreisnetzwerk bereitgestellt haben und der HTTP-Proxy für den Webkonferenzdienst eine Verbindung damit herstellen muss, schlägt die Office Web Apps-Server-Ermittlung fehl. Der Webkonferenzdienst ignoriert die HTTP-Proxyeinstellung, die im Topologie-Generator für die Einrichtung von Office Web Apps-Servern definiert wurde. Demzufolge kann der Lync-Client keine Microsoft PowerPoint 2010-Freigabe für andere Teilnehmer in der Konferenz ausführen. Wenn Sie Lync Server lokal installieren und Office Web Apps-Server auch lokal im internen Netzwerk konfigurieren, ist keine Proxy-Konfiguration erforderlich.

**Problemumgehung:**

Das Problem kann nur umgangen werden, indem laut Bereitstellungskonfiguration kein HTTP-Proxy mit einem externen Office Web Apps-Server kommunizieren muss.

## Das Hinzufügen von Videos zu einem Audiokonferenzanbieter wird nicht unterstützt (2603861)

**Problem:**

Das Hinzufügen eines Videos wird nicht unterstützt, wenn der Benutzer einer Audiokonferenz eines Audiokonferenzanbieters beitritt.

**Problemumgehung:**

Es ist keine Umgehung für dieses Problem verfügbar.

## In Topologien mit aktiviertem IPv6 wird die automatische Aktualisierung des Lync Web App-Silverlight-Plug-Ins gezwungen, die Funktion der Bildschirmfreigabefunktionalität in Lync Web App sicherzustellen (2604634)

**Problem:**

Wenn eine Topologie mit aktiviertem IPv6 konfiguriert wird, können die Benutzer ihren Bildschirm nicht über den Lync Web App-Client freigeben, falls bereits eine ältere Version des Bildschirmfreigabe-Plug-Ins installiert ist.

**Problemumgehung:**

Wenn Sie beim Konferenzbeitritt via Lync Web App eine Aktualisierung auf die neueste Version des Bildschirmfreigabe-Plug-Ins erzwingen möchten, ändern Sie den Wert für **MinSupportedBuildVersion** in beiden der folgenden Dateien von "4.0.7457.0" in "4.0.7577.380":

  - %Programme%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml

  - %Programme%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml

## Enterprise-VoIP

## In einigen Fällen unterstützt ein Lync-Client, der auf einem Computer ausgeführt wird, der für die Verwendung eines dualen IPv4- und IPv6-Stapels konfiguriert ist, Funktionalitäten nicht, die sich auf das IP-Subnetz des Computers stützen, wie E911, Medienumgehung, Anrufsteuerung und standortbasiertes Routing (3335508)


> [!NOTE]
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server&nbsp;2013: February&nbsp;2013.



**Problem:**

Wenn ein Lync-Client auf einem Computer ausgeführt wird, der für dualen IPv4- und IPv6-Stapel aktiviert ist und auf der DNS-Auflösung des Proxyservers aufbaut, verwendet der Client möglicherweise die IPv6-Adresse des Computers, um sich anzumelden. Anschließend unterstützt der Lync-Client nur die Funktionalitäten, die in IPv6 unterstützt werden, was E911, Medienumgehung, Anrufsteuerung und standortbasiertes Routing ausschließt.

**Problemumgehung:**

Um dieses Problem zu umgehen, deaktivieren Sie die IPv6-Unterstützung auf dem Clientcomputer.

## Wenn Enterprise-VoIP für einen Benutzer nicht konfiguriert wird, muss der Benutzer zum Auswählen aus einer Konferenz das E164-Format verwenden (3215342)

**Problem:**

Wenn Enterprise-VoIP für einen Benutzer nicht konfiguriert wird, muss der Benutzer für das erfolgreiche Auswählen aus einer Konferenz das E164-Format verwenden. Wird das E164-Format nicht verwendet, kann sich der Benutzer nicht aus der Konferenz auswählen.

**Problemumgehung:**

Zur Umgehung dieses Problems sollten sich Benutzer, die nicht für Enterprise-VoIP aktiviert sind, mithilfe von Zahlen im E164-Format aus einer Konferenz auswählen.

## Anwesenheit

## Wenn ein Benutzer die Option "Alle Einladungen und gesamte Kommunikation blockieren" ausgewählt hat, während der einheitliche Kontaktspeicher für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn dies der Fall sein sollte (3204526)

**Problem:**

Wenn ein Benutzer die Option "Alle Einladungen und gesamte Kommunikaktion blockieren" ausgewählt hat, während der einheitliche Kontaktspeicher für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn dies der Fall sein sollte.

**Problemumgehung:**

Zur Umgehung dieses Problems können Sie den einheitlichen Kontaktspeicher für den Benutzer deaktivieren. Führen Sie dazu die folgenden Cmdlets aus:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Beispiel:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

## Lokal verwaltete Office Communications Server 2007 R2-Benutzer können den Anwesenheitsstatus von Skype for Business Online-Benutzern in Hybrid-Bereitstellungen nicht anzeigen (3014624) - Hybrid

**Problem:**

Das Problem kann in einer Hybrid-Bereitstellung auftreten, wenn Sie einen Lync Server 2013-Director verwenden.

Der Anwesenheitsstatus für in Skype for Business Online verwaltete Benutzer wird für lokale Benutzer als "Anwesenheitsstatus nicht bekannt" angezeigt. Zudem können in Skype for Business Online verwaltete Benutzer den Anwesenheitsstatus für lokale Benutzer von Office Communications Server R2 nicht anzeigen.

**Problemumgehung:**

Wenn Sie dieses Problem teilweise umgehen möchten, ändern Sie den Homeserver (msrtcsip-presencehomeserver) der Skype for Business Online-Benutzer, sodass er auf einen lokalen Lync Server 2013-Pool anstatt auf den Lync Server 2013-Director verweist. Sie können diese Einstellung für den lokalen Front-End-Server ändern.

Durch diese Problemumgehung wird der Anwesenheitsstatus von Benutzern, die in Office Communications Server 2007 R2 verwaltet werden, für Skype for Business Online-Benutzer ordnungsgemäß angezeigt.

## Reaktionsgruppenanwendung, Anwendung zum Parken von Anrufen und Annahme von Gruppenanrufen

## Ein Anrufer hört möglicherweise während der Einrichtung eines Anrufs mit dem empfangenden Teilnehmer eine Sekunde Wartemusik (3334097)


> [!NOTE]
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server&nbsp;2013: February&nbsp;2013.



**Problem:**

Wenn ein Anruf über die Annahme von Gruppenanrufen abgerufen wird, hört der Anrufer möglicherweise während der Einrichtung des Anrufs beim empfangenden Teilnehmer eine Sekunde lang Wartemusik.

**Problemumgehung:**

Es ist keine Umgehung für dieses Problem verfügbar.

## Ein Reaktionsgruppe-Agent kann sich nur über eine Lync Server 2010-Agentkonsole bei formellen Lync Server 2010-Agentgruppen an- und abmelden (2773455)

**Problem:**

Ein Lync Server 2013Reaktionsgruppe-Agent kann sich nur über eine Lync Server 2010-Agentkonsole bei formellen Lync Server 2010-Agentgruppen an- und abmelden. In der Lync Server 2010-Agentkonsole können die Benutzer nur die Lync Server 2010Reaktionsgruppe anzeigen, zu der sie gehören. Sie können keine der Lync Server 2013-Reaktionsgruppen anzeigen, zu denen sie gehören.

**Problemumgehung:**

Wenn der Reaktionsgruppe-Agent ein Lync Server 2013-Benutzer ist und zu einer formellen Lync Server 2013-Agentgruppe gehört, muss der Benutzer direkt über einen Weblink in einem Browser auf die Lync Server 2013-Agentkonsole zugreifen, um sich bei Lync Server 2013-Agentgruppen an- und abzumelden.

## Ein Lync Server 2010Reaktionsgruppe-Agent kann keine Anrufe im Namen einer Lync Server 2013- Reaktionsgruppe tätigen (2773471)

**Problem:**

Ein Lync Server 2010-Benutzer, der ein Agent einer Lync Server 2013- Reaktionsgruppe ist, kann im Namen der Reaktionsgruppe keine Anrufe tätigen. Die Lync Server 2013- Reaktionsgruppe ist im Lync-Client nicht zum Tätigen eines Anrufs verfügbar.

**Problemumgehung:**

Zum Umgehen dieses Problems müssen Sie den Lync Server 2010-Benutzer nach Lync Server 2013 verschieben.

## Wenn Sie eine Reaktionsgruppe aus Lync Server 2010 nach erfolgter Migration zu Lync Server 2013 entfernen, wird verhindert, dass Reaktionsgruppe eingehende Anrufe akzeptiert (3016227)

**Problem:**

Wenn eine Reaktionsgruppe, die von Lync Server 2010 zu Lync Server 2013 migriert wurde, aus Lync Server 2010 über Lync Server-Systemsteuerung oder Lync Server-Verwaltungsshell entfernt wird, empfängt die Reaktionsgruppe in Lync Server 2013 keine eingehenden Anrufe mehr.

**Problemumgehung:**

Entfernen Sie zum Umgehen dieses Problems keine Reaktionsgruppen aus Lync Server 2010, die von Lync Server 2010 zu Lync Server 2013 migriert wurden.

Wenn die Reaktionsgruppe bereits entfernt wurde, sollten Sie sie erneut in Lync Server 2013 bereitstellen.

## Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv festgelegt wird, gibt die Bereitstellung des Workflows einen Fehler zurück (3207527)

**Problem:**

Wenn ein neuer verwalteter Workflow bei seiner Erstellung auf inaktiv festgelegt wird, gibt die Bereitstellung des Workflows einen Fehler zurück. Dieses Problem tritt auf, wenn der Workflow bei seiner Erstellung auf inaktiv festgelegt wird. Es wirkt sich jedoch nicht auf einen Workflow aus, der nach seiner Bereitstellung bearbeitet wurde, um auf inaktiv festgelegt zu werden.

**Problemumgehung:**

Wenn Sie einen Workflow erstellen und bereitstellen, legen Sie den Workflow als aktiv fest, und stellen Sie ihn anschließend bereit. Nachdem der Workflow erfolgreich bereitgestellt wurde, kann er bearbeitet und auf inaktiv festgelegt werden.

## Durch das Entfernen einer Reaktionsgruppe aus dem Besitzerpool wird verhindert, dass die Reaktionsgruppe des Sicherungspools während des Failover-Vorgangs eingehende Anrufe akzeptiert, wenn die Reaktionsgruppe in den Sicherungspool importiert wurde (3016214)

**Problem:**

Wenn eine Reaktionsgruppe, die in Besitz des primären Pools ist, in den Sicherungspool importiert wurde, ohne den Besitzer zu überschreiben, und die Reaktionsgruppe aus dem Besitzerpool entfernt wird, akzeptiert die Reaktionsgruppe im Sicherungspool während des Failover-Vorgangs keine eingehenden Anrufe.

**Problemumgehung:**

Sie müssen die Reaktionsgruppe im primären Pool erneut bereitstellen. Anschließend müssen Sie die Reaktionsgruppe-Konfiguration aus dem primären Pool exportieren und wieder in den Sicherungspool importieren.

Sie können die Reaktionsgruppe auch im Sicherungspool neu erstellen. In diesem Fall ist der Sicherungspool der Besitzerpool der Reaktionsgruppe.

## Ein geparkter Anruf kann nicht aus der Anwendung zum Parken von Anrufen abgerufen werden, wenn die Abrufanforderung im Namen einer Reaktionsgruppe erfolgt (3211798)

**Problem:**

Wenn die folgenden Bedingungen wahr sind, schlägt eine Abrufanforderung für einen geparkten Anruf fehl:

  - Ein Agent ist Teil einer anonymen Reaktionsgruppe

  - Der Agent versucht, über die anonyme Reaktionsgruppe einen geparkten Anruf aus der Anwendung zum Parken von Anrufen abzurufen

  - Der Agent versucht, den Anruf durch Wählen der Orbitnummer über die Option "Anruf im Namen von" oder über dieselbe Option im Lync-Telefonzentralen-Client abzurufen

**Problemumgehung:**

Das Problem kann nicht umgangen werden. Der geparkte Anruf sollte abgerufen werden, ohne dies im Namen einer Reaktionsgruppe zu tun.

## Lync Server-Systemsteuerung, Topologie-Generator und Planungstool

## Einschränkungen des Planungstools (3331056 and 3331059)


> [!NOTE]
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server&nbsp;2013: February&nbsp;2013.



**Problem:**

Das Planungstool unterliegt beim Planen Ihrer Bereitstellung folgenden Einschränkungen:

  - Es werden maximal 10 zentrale Standorte unterstützt

  - Für jeden zentralen Standort können maximal 14 Zweigniederlassungen bestehen

  - Jeder zentrale Standort kann maximal 240.000 Benutzer aufweisen

Außerdem enthält das Planungstool beim Errechnen der empfohlenen Topologie keine Werte für Folgendes:

  - Die Anzahl der Benutzer, die online verwaltet werden

  - Den Prozentsatz der Benutzer, die für XMPP-Partnerverbund aktiviert sind

  - Den Prozentsatz der Benutzer, die Lync Web App verwenden

**Problemumgehung:**

Es ist keine Umgehung für diese Probleme verfügbar. Weitere Informationen zum Planungstool finden Sie unter [Entwerfen der Topologie für Lync Server 2013 unter Verwendung des Planungstools](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

## Das Planungstool verwendet möglicherweise beim Aktualisieren von Optionen nicht die zuvor definierten IP-Adressen für das Umkreisnetzwerk

**Problem:**

Wenn Sie, nachdem Sie Ihren Entwurf mithilfe des Planungstools abgeschlossen haben, Änderungen an den Optionen für das Umkreisnetzwerk vornehmen, werden dem Entwurf möglicherweise zusätzliche IP-Adressen hinzugefügt, statt dass die vorhandenen IP-Adressen aktualisiert werden. Dies kann geschehen, wenn Sie die Details des Umkreisnetzwerk-Diagramms anzeigen, **Hier klicken, um die Optionen zu aktualisieren** auswählen und dann im Dialogfeld "Konfigurationsoptionen" bei aktiviertem Umkreisnetzwerk die Option **Ich möchte die gleichen FQDNs und IP-Adressen, jedoch unterschiedliche Ports für die Edgedienste auf dem Edgeserver verwenden** aktivieren. Das Übernehmen jeglicher Änderungen kann dazu führen, dass dem Entwurf neue IP-Adressen und Edgeserver hinzugefügt werden.

**Problemumgehung:**

Zurzeit ist keine Umgehung für dieses Problem verfügbar.

## In Lync Server-Systemsteuerung wird die Funktion "Alle Benutzer in Pool verschieben" möglicherweise nicht erwartungsgemäß ausgeführt (3199270)

**Problem:**

Wenn Sie Lync Server-Systemsteuerung zum Verschieben aller Benutzer von einem Pool in einen anderen Pool in einer komplexen Active Directory-Umgebung (beispielsweise in einer Umgebung mit mehreren Domänencontrollern und über-/untergeordneten Domänen) verwenden, wird möglicherweise die Fehlermeldung "Der angegebene Benutzer ist kein Legacybenutzer. Verwenden Sie stattdessen das Cmdlet 'Move-CsUser'." zurückgegeben. Die Ursache dafür sind längere Replikationszeiten in komplexen Active Directory-Umgebungen.

**Problemumgehung:**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Verwenden Sie Filter in der Lync Server-Systemsteuerung, um nach Legacybenutzern zu suchen. Wählen Sie diese Benutzer aus, und verwenden Sie dann den Befehl **Ausgewählte Benutzer in Pool verschieben** anstelle des Befehls **Alle Benutzer in Pool verschieben** .

  - Verwenden Sie die Lync Server-Verwaltungsshell zum Verschieben von Legacybenutzern in Batches mithilfe von Lync Server-Cmdlets.

## Lync Server-Systemsteuerung funktioniert in einer VMware-Umgebung nicht mehr, nachdem Microsoft Silverlight-Browser-Plug-In auf Version 5 aktualisiert wurde (3199270)

**Problem:**

Wenn Sie Lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert Lync Server-Systemsteuerung möglicherweise nach einem Upgrade von Silverlight auf Version 5 nicht mehr.

**Problemumgehung:**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Deinstallieren Sie Silverlight 5, und installieren Sie dann Silverlight 4 von der Website [http://go.microsoft.com/fwlink/?linkid=149156\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=149156%26clcid=0x407).

  - Öffnen Sie die Lync Server-Systemsteuerung auf einem Computer, bei dem es sich nicht um einen virtuellen VMware-Computer handelt.
    
    Wenn Sie die Lync Server-Systemsteuerung auf einem Remotecomputer öffnen möchten, installieren Sie die Lync Server-Verwaltungstools auf dem Computer, und starten Sie dann die Lync Server-Systemsteuerung über das Windows-Menü **Start** .
    
    Sie können die Lync Server-Systemsteuerung auch öffnen, indem Sie die URL in einen Webbrowser eingeben. Die URL ähnelt dem Format "https://\<frontend\_pool\_fqdn\>/cscp".

## Ein Administrator kann das Cmdlet Uninstall-csMirrorDB nach dem Entfernen der Spiegelungsdatenbank im Topologie-Generator nicht ausführen (3199266)

**Problem:**

Wenn ein Administrator eine Spiegelungsdatenbank im Topologie-Generator deaktiviert und die Spiegelungsdatenbank dann im Topologie-Generator löscht, wird in der Aufgabenliste des Administrators eine Meldung mit dem Hinweis angezeigt, dass er das **Uninstall-csMirrorDatabase**-Cmdlet zum Entfernen der Spiegelung aus SQL Server ausführen soll. Wenn der Administrator versucht, das Cmdlet auszuführen, wird ein Fehler zurückgegeben.

**Problemumgehung:**

Zum Entfernen der SQL-Spiegelung eines Pools im Topologie-Generator müssen Sie zunächst ein Cmdlet zum Entfernen des Spiegels in SQL Server verwenden. Anschließend können Sie mit dem Topologie-Generator den Spiegel aus der Topologie entfernen. Verwenden Sie zum Entfernen des Spiegels in SQL Server das folgende Cmdlet:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Der Parameter *DropExistingDatabasesOnMirror* bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden. Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1.  Klicken Sie in Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten** .

2.  Deaktivieren Sie die Option **Spiegelung des SQL-Speichers aktivieren** , und klicken Sie auf **OK** .

3.  Veröffentlichen Sie die Topologie.


> [!IMPORTANT]
> Bei jeder Änderung einer Beziehung für die Back-End-Datenbankspiegelung müssen Sie alle Front-End-Server im Pool neu starten.



## Wenn ein Administrator versucht, eine Bereitstellung mit einem Front-End-Pool, der über einen verknüpften Zeugenspeicher verfügt, zu löschen, werden im Topologie-Generator Validierungsfehler zurückgegeben (3199266)

**Problem:**

Wenn ein Administrator versucht, mithilfe des Befehls **Bereitstellung entfernen** im Topologie-Generator eine Bereitstellung zu entfernen, die einen Front-End-Pool mit verknüpftem Zeugenspeicher enthält, wird in Topologie-Generator ein Validierungsfehler angezeigt, und die Aktion wird nicht fortgesetzt.

**Problemumgehung:**

Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:

  - Entfernen Sie den Zeugenspeicher, bevor Sie versuchen, die Bereitstellung zu entfernen.

  - Fügen Sie einen Zeugenspeicher für den Front-End-Pool hinzu, und entfernen Sie ihn dann.

## Server für beständigen Chat-Bereitstellungsinformationen zwischen dem Planungstool und dem Topologie-Generator sind inkonsistent (3012228)

**Problem:**

Wenn das Lync Server 2013, Planungstool das Standorttopologiediagramm für eine Server für beständigen Chat-Bereitstellung mit aktivierter Notfallwiederherstellung ausgibt, enthält das Standorttopologiediagramm mehrere (physikalische) Standorte mit gleichmäßig zugeordneten Server für beständigen Chat an den einzelnen Standorten. Im Topologie-Generator werden alle Server für beständigen Chat so dargestellt, als würden sie zu einem einzelnen (logischen) Standort gehören, und sie werden unter demselben Serverpool für beständigen Chat-Knoten aufgelistet.

**Problemumgehung:**

Derzeit kann dieses Problem nicht umgangen werden. Der Benutzer sollte die Planungstool-Ausgabe für die Server für beständigen Chat-Bereitstellung analysieren und den Plan an seine jeweiligen Anforderungen anpassen.

## Lokalisierung

## Monitoring

## Im Assistenten zum Bereitstellen von Überwachungsberichten werden unter bestimmten Umständen falsche Zeichen angezeigt, wenn die ostasiatische Version von Lync Server verwendet wird (3113565)

**Problem:**

Bei Verwendung einer ostasiatischen Version von Lync Server 2013 \\endash beispielsweise Chinesisch (vereinfacht), Chinesisch (Traditionell), Japanisch oder Koreanisch \\endash in einem Betriebssystem, bei dem das Systemgebietsschema nicht auf eine ostasiatische Sprache festgelegt ist, werden im Assistenten zum Bereitstellen von Überwachungsberichten anstelle von lokalisierten Meldungen Fragezeichen oder andere Zeichen angezeigt.

**Problemumgehung:**

Legen Sie zum Umgehen dieses Problems das Gebietsschema für das Betriebssystem und Lync Server 2013 auf dieselbe Sprache fest. Dann werden sämtliche Meldungen ordnungsgemäß angezeigt.

## Lync Server-Systemsteuerung

## In bestimmten Fällen wird beim Klicken auf das letzte Element in der oberen Navigationsleiste das erste Element in der oberen Navigationsleiste auf einer Seite der Lync Server-Systemsteuerung nicht mehr angezeigt (3158118)

**Problem:**

Es existieren drei bekannte Fälle, in denen beim Klicken auf das letzte Element in der oberen Navigationsleiste auf einer Seite der Lync Server-Systemsteuerung das erste Element in der oberen Navigationsleiste nicht mehr angezeigt wird:

  - In der französischen Version wird auf der Seite "Féderation et accès externe" das Element "Stratégie d'accès externe" nicht mehr angezeigt, wenn der Benutzer auf "Partenaires fédérés XMPP" klickt.

  - In der deutschen Version wird auf der Seite "Clients" das Element "Clientversionskonfiguration" nicht mehr angezeigt, wenn der Benutzer auf "Pushbenachrichtigungskonfiguration" klickt.

  - In der russischen Version wird auf der Seite "Конфигурация сети" das Element "Глобально" nicht mehr angezeigt, wenn der Benutzer auf "Маршрут региона" klickt.

**Problemumgehung:**

Wenn Sie dieses Problem beheben möchten, aktualisieren Sie die Seite von Lync Server-Systemsteuerung in Ihrem Browser. Daraufhin wird die Seite im Browser geladen, und alle Elemente in der oberen Navigationsleiste werden angezeigt.

## Adressbuch

## Die Indizierung im Adressbuch funktioniert in einigen Sprachen nicht erwartungsgemäß (3336047)


> [!NOTE]
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server&nbsp;2013: February&nbsp;2013.



Wenn in den Eigenschaften eines Benutzers ein indiziertes Feld enthalten ist und dieses Feld nur Zeichen enthält, die nicht indiziert werden können, taucht der Benutzer in dem vom Adressbuch ausgeführten Suchvorgängen nicht auf.

Die folgenden Zeichen und Gebietsschemas können nicht indiziert werden:

  - Große kyrillische, griechische und armenische Zeichen

  - Große Zeichen mit Akzent

  - Thailändisch

  - Laotisch

  - Birmanisch

  - Devanagari

  - Äthiopisch

  - Tibetisch (Bhutan)

  - Bengali

  - Gudscharati

  - Telugu

  - Alle anderen indischen Schriften

## Lync Web App, Webplaner und Webkomponenten

## Der Fallback-Vorgang für die Sprache funktioniert für bestimmte Sprachen im Lync-Webplaner, in der Einwahl, im Join Launcher, in der Verwaltung beständiger Chatrooms und für OCTab möglicherweise nicht wie erwartet (3079700)

**Problem:**

Das Auswählen eines neutralen Gebietsschemas in einem Webbrowser (in Internet Explorer beispielsweise der Name der Sprache ohne weitere Angaben wie "Norwegisch \[no\]") anstelle eines Gebietsschemas mit Angabe der Sprache, des Skripts und des Gebietsschemas (beispielsweise "Norwegisch, Bokmål (Norwegen) \[nb-NO\]") kann zu einem unerwarteten Anzeigeverhalten für bestimmte Sprachen im Lync-Webplaner, in der Einwahl, in Join Launcher, in der Verwaltung beständiger Chatrooms und für OCTab führen. Beispielsweise wird den Benutzern beim Auswählen einer der folgenden Sprachen möglicherweise die englische Seite angezeigt:

  - Norwegisch

  - Portugiesisch

  - Serbisch

**Problemumgehung:**

Wenn Sie eine Sprache mit neutralem Gebietsschema auswählen möchten, achten Sie darauf, dass Sie in der Spracheinstellungsliste Ihres Browsers auch die Sprache mit einem spezifischen Gebietsschema (einschließlich Skript und/oder Ländercode) als zusätzliche Sprache hinzufügen.

## Für die Gebietsschemas Aserbaidschanisch und Usbekisch besteht in einigen Webbrowsern bei der Verwendung des Lync-Webplaners, bei der Einwahl, in Join Launcher, bei der Verwaltung beständiger Chatrooms und in OCTab nur eingeschränkte Unterstützung (3336748)


> [!NOTE]
> Die Informationen in diesem Abschnitt beziehen sich auf kumulierte Updates für Lync Server&nbsp;2013: February&nbsp;2013.



**Problem:**

Wenn Sie Internet Explorer 8 oder Internet Explorer 9 verwenden und die Browsersprache auf Aserbaidschanisch (Lateinisch) oder Usbekisch (Lateinisch) festlegen, werden die Seiten "Einwahl" und "Join Launcher" auf Englisch oder in der für den Browser festgelegten bevorzugten Sprache angezeigt.

Wenn Sie die Browser Firefox oder Chrome verwenden und die Browsersprache auf Aserbaidschanisch (Lateinisch) oder Usbekisch (Lateinisch) festlegen, werden Lync Web App, der Lync-Webplaner und RGS OCTab auf Englisch oder in der für den Browser festgelegten bevorzugten Sprache angezeigt.

Das Gebietsschema Usbekisch (Lateinisch) wird im Safari-Browser nicht unterstützt.

**Problemumgehung:**

Es ist keine Umgehung für diese Probleme verfügbar.

## In der rumänischen Version von Lync Web App fehlt der Dropdownpfeil für die Liste "An Besprechung teilnehmen über" (3154899)

**Problem:**

Wenn ein Benutzer, der die rumänische Version von Lync Web App verwendet, die folgenden Schritte ausführt, wird der Pfeil für **An Besprechung teilnehmen** nicht in der Dropdownliste angezeigt:

1.  Wählen Sie auf der Registerkarte **Allgemein** die Option **Meine Daten auf diesem Computer speichern** aus.

2.  Wählen Sie die Registerkarte **Telefon** aus.

3.  Klicken Sie auf die Dropdownliste unter **An Besprechung teilnehmen über** .
    
    Den Benutzern wird kein Pfeil angezeigt, der angibt, dass neben der Standardeinstellung **Lync Web App** weitere Optionen verfügbar sind. Diese lauten wie folgt: **Nicht an Audiobesprechung teilnehmen** (in der rumänischen Version "Nu se asociaža la componenta audio") und **Neue Nummer** (in der rumänischen Version "Numar nou").

**Problemumgehung:**

Obwohl der Pfeil für diese Dropdownliste nicht angezeigt wird, können die Benutzer die zusätzlichen Einstellungen in der Liste auswählen, indem Sie auf den Standardwert klicken.

## Bei Verwendung der türkischen Version des Lync-Webplaners kann eine Besprechung nicht gespeichert werden, wenn die Benutzer die Option "Von mir ausgewählte Personen" unter "Wer agiert als Referent" verwenden (3169483)

**Problem:**

Beim Erstellen oder Bearbeiten einer Besprechung in der türkischen Version des Lync-Webplaners wird die Option "Von mir ausgewählte Personen" unter "Wer agiert als Referent" nicht unterstützt. Bei Auswahl dieser Option kann die Besprechung nicht gespeichert werden. Stattdessen wird eine Fehlermeldung mit dem Hinweis angezeigt, dass eine oder mehrere Personen nicht als Referenten agieren können.

**Problemumgehung:**

Um dieses Problem zu umgehen, können die Benutzer die Standardoption "Personen in meinem Unternehmen" oder eine andere Option wie "Nur Organisator" oder "Alle, auch Personen außerhalb meines Unternehmens" verwenden. Der Organisator kann Personen später auf die richtigen Rollen herunter- oder heraufstufen, nachdem sie der Besprechung beigetreten sind.

Alternativ dazu können Benutzer, die eine andere Sprache verstehen, die Sprachauswahl in ihrem Browser in eine der anderen 43 unterstützten Sprachen ändern und versuchen, die Option "Von mir ausgewählte Personen" zu verwenden.

## Copyright

Dieses Dokument unterstützt eine Vorabversion eines Softwareprodukts, die vor der endgültigen Freigabe für den Handel wesentlich geändert werden kann. Im Dokument sind geschützte und vertrauliche Informationen von Microsoft enthalten. Das Informationsmaterial wird gemäß einer Vertraulichkeitsvereinbarung zwischen dem Empfänger und Microsoft zugänglich gemacht. Dieses Dokument dient nur zu Informationszwecken, und Microsoft schließt jede ausdrückliche oder konkludente Gewährleistung für dieses Dokument aus. Die in diesem Dokument enthaltenen Informationen, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden. Das gesamte Risiko bezüglich der Verwendung oder der Ergebnisse der Verwendung dieses Dokuments verbleibt beim Benutzer. Die in den Beispielen verwendeten Namen von Firmen, Organisationen, Produkten, Domänen, Personen, Orten, Ereignissen sowie E-Mail-Adressen und Logos sind frei erfunden, soweit nichts anderes angegeben ist. Jede Ähnlichkeit mit tatsächlichen Firmen, Organisationen, Produkten, Domänennamen, Personen, Orten, Ereignissen, E-Mail-Adressen und Logos ist rein zufällig. Die Benutzer/innen sind verpflichtet, sich an alle anwendbaren Urheberrechtsgesetze zu halten. Unabhängig von der Anwendbarkeit der entsprechenden Urheberrechtsgesetze darf ohne ausdrückliche schriftliche Erlaubnis der Microsoft Corporation kein Teil dieses Dokuments für irgendwelche Zwecke vervielfältigt oder in einem Datenempfangssystem gespeichert oder darin eingelesen werden, unabhängig davon, auf welche Art und Weise oder mit welchen Mitteln (elektronisch, mechanisch, durch Fotokopieren, Aufzeichnen usw.) dies geschieht.

Microsoft kann Inhaber von Patenten oder Patentanträgen, Marken, Urheberrechten oder anderem geistigen Eigentum sein, die den Inhalt dieses Dokuments betreffen. Die Bereitstellung dieses Dokuments gewährt keinerlei Lizenzrechte an diesen Patenten, Marken, Urheberrechten oder anderem geistigen Eigentum, es sei denn, dies wurde ausdrücklich durch einen schriftlichen Lizenzvertrag mit der Microsoft Corporation vereinbart.

© 2012 Microsoft Corporation. Alle Rechte vorbehalten.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook und SQL Server sind eingetragene Marken oder Marken der Microsoft Corporation in den USA und/oder anderen Ländern/Regionen.

Alle anderen Marken sind Eigentum der jeweiligen Inhaber.

