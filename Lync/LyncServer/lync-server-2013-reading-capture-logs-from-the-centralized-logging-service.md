---
title: Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst
TOCTitle: Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49890933
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst

 

_**Letztes Änderungsdatum des Themas:** 2016-12-28_

Die wirklichen Vorteile des Zentraler Protokollierungsdiensts werden Sie erkennen, nachdem Sie die Suche ausgeführt haben und eine Datei vorhanden ist, mit der Sie ein gemeldetes Problem nachverfolgen können. Es gibt eine Reihe von Möglichkeiten, um die Datei zu lesen. Die Ausgabedatei liegt in einem Standardtextformat vor. Sie können Notepad.exe oder ein beliebiges anderes Programm verwenden, mit dem Sie eine Textdatei öffnen und lesen können. Für größere Dateien und komplexere Probleme können Sie ein Tool wie z. B. Snooper.exe verwenden, das zum Lesen und Analysieren der Protokollierungsausgabe von Zentraler Protokollierungsdienst vorgesehen ist. Snooper ist im Lieferumfang der Lync Server 2013-Debugtools enthalten, die als separater Download verfügbar sind. Für die Lync Server 2013-Debugtools werden keine Verknüpfungen oder Menüelemente erstellt. Öffnen Sie nach der Installation der Lync Server 2013-Debugtools Windows Explorer, ein Befehlszeilenfenster oder die Lync Server-Verwaltungsshell, und wechseln Sie zum Verzeichnis (Standardspeicherort) C:\\ProgrammeMicrosoft Lync Server 2013\\Debugging Tools. Doppelklicken Sie auf Snooper.exe, oder geben Sie Snooper.exe ein, und drücken Sie dann die EINGABETASTE, falls Sie die Befehlszeile oder die Lync Server-Verwaltungsshell verwenden.


> [!IMPORTANT]
> In diesem Thema sollen keine Problembehandlungstechniken beschrieben und behandelt werden. Die Problembehandlung und die damit verbundenen Prozesse sind ein komplexes Thema. Ausführliche Informationen zu den Grundlagen der Problembehandlung und zur Problembehandlung bei bestimmten Arbeitsauslastungen finden Sie in der Microsoft Lync Server 2010-Resource Kit-Dokumentation unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=211003%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=211003&amp;clcid=0x407</A>. Die Prozesse und Verfahren gelten auch weiterhin für Lync Server 2013.



In Lync Server 2013 gibt es eine aktualisierte Version von Snooper mit einigen neuen Features. Im folgenden Screenshot ist die Snooper-Version aus Office Communications Server 2007 abgebildet.

![Office Communications 2007-Version von Snooper](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007-Version von Snooper")

Im folgenden Screenshot ist die neue Snooper-Version abgebildet, die in den Lync Server 2013-Debugtools enthalten ist.

![Lync Server 2013-Version von Snooper](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013-Version von Snooper")

Im folgenden Screenshot ist die Symbolleiste mit häufig verwendeten Funktionen abgebildet.

![Snooper 2013-Symbolleiste](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013-Symbolleiste")

Das neueste Feature ist die Diagrammansicht Flow Chart (call flow) (Flussdiagramm (Anruffluss)). Sie wählen auf der Registerkarte **Messages** (Nachrichten) einen Nachrichtenfluss aus und klicken auf die Schaltfläche **Call Flow** (Anruffluss). Beim Navigieren in den Nachrichten wird das Anrufflussdiagramm mit neuen Daten aktualisiert.

![Snooper 2013-Anrufflussdiagramm](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013-Anrufflussdiagramm")

Sie können auf die Diagrammansicht zeigen und Details zu den Nachrichten und Inhalten der Datenflüsse und Nachrichten sowie zu den Serverelementen anzeigen. Klicken Sie auf einen beliebigen Anrufflussrichtungspfeil, um zu der Nachricht in der Nachrichtenansicht zu navigieren.

![Diagramm mit Nachrichtendetails zum Anruffluss](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Diagramm mit Nachrichtendetails zum Anruffluss")

## So öffnen Sie eine Protokolldatei in Snooper

1.  Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff auf die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppen CsAdministrator oder CsServerAdministrator oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle, die eine dieser beiden Gruppen enthält, sein.

2.  Nach der Installation der Lync Server-Debugtools (LyncDebugTools.msi) wechseln Sie in Windows Explorer oder über die Befehlszeile zum Verzeichnis, in dem Snooper.exe gespeichert ist. Die Debugtools werden standardmäßig im Verzeichnis C:\\Programme\\Microsoft Lync Server 2013\\Debugging Tools gespeichert. Doppelklicken Sie, oder führen Sie Snooper.exe aus.

3.  Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **File** (Datei), klicken Sie auf **OpenFile** (Datei öffnen), suchen Sie nach Ihren Protokolldateien, wählen Sie eine Datei im Dialogfeld **Open** (Öffnen) aus, und klicken Sie dann auf **Open** (Öffnen).

4.  Die Ablaufverfolgungsnachrichtender Protokolldatei werden auf der Registerkarte **Trace** (Ablaufverfolgung) angezeigt. Klicken Sie auf die Registerkarte **Messages** (Nachrichten), um die Nachrichteninhalte der erfassten Ablaufverfolgungen anzuzeigen.

## So zeigen Sie ein Anrufflussdiagramm an

1.  Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff auf die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppen CsAdministrator oder CsServerAdministrator oder einer einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle, die eine dieser beiden Gruppen enthält, sein.

2.  Öffnen Sie eine Protokolldatei, und klicken Sie auf die Registerkarte **Messages** (Nachrichten), wählen Sie eine Unterhaltung in der Nachrichtenansicht aus, oder wählen Sie eine Ablaufverfolgungskomponente auf der Registerkarte **Trace** (Ablaufverfolgung) aus.

3.  Klicken Sie auf **Call Flow** (Anruffluss).
    

    > [!NOTE]
    > Wenn Sie auf eine Nachricht oder Ablaufverfolgung klicken, die nicht Bestandteil eines Anrufflusses ist, wird das Diagramm nicht angezeigt. Außerdem wird unten in Snooper eine Statusmeldung angezeigt, dass diese Nachricht nicht für den Anruffluss in Frage kommt. Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus. Der Anruffluss wird angezeigt, falls die Nachricht oder Ablaufverfolgung Bestandteil eines Anrufflusses ist.



4.  Navigieren Sie in den Nachrichten oder Ablaufverfolgungszeilen, und achten Sie darauf, ob das Anrufflussdiagramm aktualisiert oder geändert und ein neues Diagramm angezeigt wird.

5.  Zeigen Sie auf Elemente, um Informationen zu Anrufnachrichten, Endpunkten und sonstigen Komponenten anzuzeigen.

