---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
TOCTitle: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49890662
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Die Migration der Anwendung zum Parken von Anrufen von Lync Server 2010 zu Lync Server 2013 umfasst die Bereitstellung des Lync Server 2013-Pools mit beliebigen Wartemusikdateien, die in Lync Server 2010 hochgeladen wurden, die Wiederherstellung von Serviceleveleinstellungen und das Neuzuweisen von Anrufparkorbits zum Lync Server 2013-Pool. Wenn im Lync Server 2010-Pool angepasste Wartemusikdateien konfiguriert wurden, müssen diese Dateien in den neuen Lync Server 2013-Pool kopiert werden. Zudem wird empfohlen, jede angepasste Wartemusikdatei für das Parken von Anrufen aus Lync Server 2010 unter einem anderen Ziel zu sichern. So verfügen Sie über eine separate Sicherungskopie der angepassten Musikdateien, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Wartemusikdateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Zum Kopieren der Audiodateien aus einem Dateispeicher des Lync Server 2010-Pools in einen Lync Server 2013-Dateispeicher verwenden Sie den **Xcopy**-Befehl mit den folgenden Parametern:

    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>

&nbsp;

    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 

Nachdem alle angepassten Audiodateien in den Lync Server 2013-Dateispeicher kopiert wurden, müssen die Einstellungen der Anwendung zum Parken von Anrufen des Lync Server 2013-Pools konfiguriert werden. Zudem müssen die Bereiche für den Anrufparkorbit, die mit dem Lync Server 2010-Pool verknüpft sind, erneut dem Lync Server 2013-Pool zugewiesen werden.

Zu den Einstellungen der Anwendung zum Parken von Anrufen gehören die Auswahl des Timeoutschwellenwerts für die Anrufannahme, das Aktivieren oder Deaktivieren der Wartemusik, die maximale Anzahl von Versuchen der Anrufannahme und die Timeoutanforderung. Zum Verwalten der Einstellungen der Anwendung zum Parken von Anrufen müssen Sie die Lync Server-Verwaltungsshell verwenden, um das Cmdlet **Set-CsCpsConfiguration** auszuführen. Sie können die Einstellungen der Anwendung zum Parken von Anrufen nicht mit Lync Server-Systemsteuerung verwalten.

**Erneutes Konfigurieren der Einstellungen für den Dienst zum Parken von Anrufen**

1.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    

    > [!NOTE]
    > Wenn Ihre Lync Server 2013-Einstellungen für die Anwendung zum Parken von Anrufen mit den Lync Server 2010-Legacyeinstellungen identisch sind, können Sie diesen Schritt überspringen. Wenn sich die Einstellungen für die Anwendung zum Parken von Anrufen in den Lync Server 2013- und Lync Server 2010-Umgebungen unterscheiden, verwenden Sie das folgende Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.

    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

Um alle Bereiche für den Anrufparkorbit aus dem Lync Server 2010-Pool dem Lync Server 2013-Pool neu zuzuweisen, können Sie entweder Lync Server-Systemsteuerung oder die Lync Server-Verwaltungsshell verwenden.

**Neuzuordnen aller Bereiche für den Anrufparkorbit mit der Lync Server-Systemsteuerung**

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Wählen Sie im linken Bereich **VoIP-Funktionen** aus.

3.  Wählen Sie die Registerkarte **Parken von Anrufen** aus.

4.  Bearbeiten Sie für jeden Bereich für den Anrufparkorbit, der einem Lync Server 2010-Pool zugeordnet ist, die Einstellung **FQDN des Zielservers**, und wählen Sie den Lync Server 2013-Pool aus, der die Anforderungen zum Parken von Anrufen verarbeitet.

5.  Klicken Sie auf **Commit ausführen**, um Ihre Änderungen zu speichern.

**Neuzuordnen aller Bereiche für den Anrufparkorbit mit der Lync Server-Verwaltungsshell**

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsCallParkOrbit
    
    Dieses Cmdlet listet alle Bereiche für den Anrufparkorbit in der Bereitstellung auf. Alle Anrufparkorbits, für die die Parameter **CallParkServiceId** und **CallParkServerFqdn** als Lync Server 2010-Pool festgelegt sind, müssen neu zugewiesen werden.
    
    Geben Sie an der Befehlszeile den folgenden Befehl ein, um Lync Server 2010-Anrufparkorbits dem Lync Server 2013-Pool neu zuzuweisen:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

Nachdem Sie alle Anrufparkorbits dem Lync Server 2013-Pool neu zugewiesen haben, wird der Migrationsprozess für die Anwendung zum Parken von Anrufen abgeschlossen, und der Lync Server 2013-Pool behandelt alle künftigen Anforderungen zum Parken von Anrufen.

