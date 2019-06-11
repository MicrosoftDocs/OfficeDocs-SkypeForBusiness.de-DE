---
title: 'Lync Server 2013: Lesen von Erfassungs Protokollen vom zentralen Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lesen von Aufnahme Protokollen vom zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-28_

Sie erkennen den wirklichen Vorteil des zentralen Protokollierungsdiensts, nachdem Sie die Suche ausgeführt haben, und Sie verfügen über eine Datei, mit der Sie ein gemeldetes Problem nachvollziehen können. Es gibt eine Reihe von Möglichkeiten, wie Sie die Datei lesen können. Die Ausgabedatei befindet sich in einem Standardtextformat, und Sie können Notepad. exe oder alle anderen Programme verwenden, die es Ihnen ermöglichen, eine Textdatei zu öffnen und zu lesen. Für größere Dateien und komplexere Probleme können Sie ein Tool wie Snooper. exe verwenden, das zum Lesen und Analysieren der Protokollierungsausgabe vom zentralen Protokollierungsdienst entwickelt wurde. Snooper ist in den lync Server 2013-Debug-Tools enthalten, die als separater Download zur Verfügung stehen. Sie können die lync Server 2013-Debug-Tools hier [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)herunterladen:. Wenn Sie die lync Server 2013-Debug-Tools installieren, werden keine kurzen Schnitte und Menüelemente erstellt. Nachdem Sie die lync Server 2013-Debug-Tools installiert haben, öffnen Sie den Windows-Explorer, ein Befehlszeilenfenster oder die lync Server-Verwaltungsshell, und wechseln Sie zu dem\\Verzeichnis (\\Standardspeicherort) C\\: Programmdateien Microsoft lync Server 2013 Debug-Tools. Doppelklicken Sie auf Snooper. exe, oder geben Sie Snooper. exe ein, und drücken Sie dann die EINGABETASTE, wenn Sie die Befehlszeile oder die lync Server-Verwaltungsshell verwenden.

<div>


> [!IMPORTANT]  
> In diesem Thema sollen keine Problembehandlungstechniken beschrieben und behandelt werden. Die Problembehandlung und die damit verbundenen Prozesse sind ein komplexes Thema. Details zu den Grundlagen der Problembehandlung und zur Problembehandlung bei bestimmten Arbeitslasten finden Sie im Microsoft lync <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Server 2010 Resource Kit-Handbuch unter. Die Prozesse und Verfahren gelten weiterhin für lync Server 2013.



</div>

Lync Server 2013 führt eine aktualisierte Version von Snooper mit einigen neuen Features ein. Der folgende Screenshot zeigt die Version von Snooper von Office Communications Server 2007.

![Office Communications 2007-Version von Snooper.] (images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007-Version von Snooper.")

Der folgende Screenshot zeigt die neue Version von Snooper, die in den lync Server 2013-Debug-Tools enthalten ist.

![Lync Server 2013-Version von Snooper.] (images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013-Version von Snooper.")

Der folgende Screenshot zeigt die Symbolleiste mit häufig verwendeten Funktionen.

![Snooper 2013-Symbolleiste.] (images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013-Symbolleiste.")

Und das neueste Feature, das einen Wert hinzufügt, ist die Diagrammansicht Flussdiagramm (Anruffluss). Sie wählen einen Nachrichtenfluss auf dem Reiter **Nachricht** und klicken Sie auf die Schaltfläche **Anruffluss** . Während Sie die Nachrichten durchlaufen, wird das Anruffluss Diagramm mit neuen Daten aktualisiert.

![Snooper 2013-Anruffluss Diagramm] (images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013-Anruffluss Diagramm")

Sie können mit der Maus auf die Diagrammansicht zeigen und Details zu den Nachrichten und dem Inhalt der Flüsse und Nachrichten sowie zu den Serverelementen abrufen. Klicken Sie auf einen beliebigen Anruffluss Pfeil, um in der Ansicht Nachrichten zu der Nachricht zu wechseln.

![Nachrichtendetails des Anruffluss Diagramms.] (images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Nachrichtendetails des Anruffluss Diagramms.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>So öffnen Sie eine Protokolldatei in Snooper

1.  Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält.

2.  Wechseln Sie nach der Installation der lync Server-Debugging-Tools (LyncDebugTools. msi) mithilfe von Windows-Explorer oder über die Befehlszeile in den Speicherort von Snooper. exe. Standardmäßig befinden sich die Debug-Tools unter C:\\Programmdateien\\Microsoft lync Server 2013\\-Debugging-Tools. Führen Sie „Snooper.exe“ mittels Doppelklick aus.

3.  Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **File** (Datei), klicken Sie auf **OpenFile** (Datei öffnen), suchen Sie nach Ihren Protokolldateien, wählen Sie eine Datei im Dialogfeld **Open** (Öffnen) aus und klicken Sie dann auf **Open** (Öffnen).

4.  Die Ablaufverfolgungsmeldungen**** werden auf der Registerkarte **Trace** (Ablaufverfolgung) angezeigt. Klicken Sie auf die Registerkarte **Messages** (Nachrichten), um die Nachrichteninhalte der erfassten Ablaufverfolgungen anzuzeigen.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>So zeigen Sie ein Anrufflussdiagramm an

1.  Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält.

2.  Öffnen Sie eine Protokolldatei und klicken Sie auf die Registerkarte **Messages** (Nachrichten), wählen Sie eine Unterhaltung in der Nachrichtenansicht aus oder wählen Sie eine Ablaufverfolgungskomponente auf der Registerkarte **Trace** (Ablaufverfolgung) aus.

3.  Klicken Sie auf **Call Flow** (Anruffluss).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie auf eine Nachricht oder Ablaufverfolgung klicken, die nicht Bestandteil eines Anrufflusses ist, wird das Diagramm nicht angezeigt. Außerdem wird unten in Snooper die Statusmeldung angezeigt, dass diese Nachricht nicht für den Anruffluss in Frage kommt. Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus. Der Anruffluss wird angezeigt, falls die Nachricht oder Ablaufverfolgung Bestandteil eines Anrufflusses ist.

    
    </div>

4.  Navigieren Sie in den Nachrichten oder Ablaufverfolgungszeilen und überprüfen Sie, ob das Anrufflussdiagramm aktualisiert oder geändert und ein neues Diagramm angezeigt wird.

5.  Zeigen Sie auf Elemente, um Informationen zu Anrufnachrichten, Endpunkten und sonstigen Komponenten anzuzeigen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

