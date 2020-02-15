---
title: 'Lync Server 2013: Lesen von Erfassungs Protokollen aus dem zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5abf7b2f6962dbf38f90f52ff82c54b035d9aa0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lesen von Erfassungs Protokollen aus dem zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-28_

Sie erkennen den tatsächlichen Vorteil des zentralisierten Protokollierungsdiensts nach dem Ausführen der Suche, und Sie verfügen über eine Datei, die Sie zum Aufspüren eines gemeldeten Problems verwenden können. Es gibt eine Reihe von Möglichkeiten, wie Sie die Datei lesen können. Die Ausgabedatei hat ein Standardtextformat und Sie können Notepad. exe oder andere Programme verwenden, mit denen Sie eine Textdatei öffnen und lesen können. Für größere Dateien und komplexere Probleme können Sie ein Tool wie Snooper. exe verwenden, das zum Lesen und Analysieren der Protokollierungsausgabe vom zentralisierten Protokollierungsdienst entwickelt wurde. Snooper ist in den lync Server 2013 Debug-Tools enthalten, die als separater Download zur Verfügung stehen. Sie können die lync Server 2013 Debug-Tools hier herunter [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)laden:. Wenn Sie die lync Server 2013 Debug-Tools installieren, werden keine Kurzschnitte und Menüelemente erstellt. Nachdem Sie die lync Server 2013 Debug-Tools installiert haben, öffnen Sie Windows Explorer, ein Befehlszeilenfenster oder lync Server-Verwaltungsshell und wechseln Sie zum Verzeichnis (Standardspeicherort) C\\: Programm\\Dateien\\Microsoft lync Server 2013 Debugging-Tools. Doppelklicken Sie auf Snooper. exe, oder geben Sie Snooper. exe ein, und drücken Sie dann die EINGABETASTE, wenn Sie die Befehlszeile oder lync Server-Verwaltungsshell verwenden.

<div>


> [!IMPORTANT]  
> Die Absicht dieses Themas ist nicht detailliert und besprechen die Problembehandlungstechniken. Die Problembehandlung und die Prozesse um Sie herum sind ein komplexes Thema. Ausführliche Informationen zur grundlegenden Problembehandlung und zur Problembehandlung bei bestimmten Arbeitsauslastungen finden <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Sie im Microsoft lync Server 2010 Resource Kit-Buch unter. Die Prozesse und Verfahren gelten weiterhin für lync Server 2013.



</div>

Lync Server 2013 stellt eine aktualisierte Version von Snooper vor, die einige neue Features enthält. Der folgende Screenshot zeigt die Version von Snooper aus Office Communications Server 2007.

![Office Communications 2007-Version von Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007-Version von Snooper.")

Der folgende Screenshot zeigt die neue Version von Snooper, die in den lync Server 2013 Debug-Tools enthalten ist.

![Lync Server 2013 Version von Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 Version von Snooper.")

Der folgende Screenshot zeigt die Symbolleiste mit häufig verwendeten Funktionen.

![Snooper 2013 Toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 Toolbar.")

Und das neueste Feature, das einen Wert hinzufügt, ist die Diagrammansicht Flussdiagramm (Anruffluss). Sie wählen einen Nachrichtenfluss auf der Registerkarte **Nachricht** aus und klicken auf die Schaltfläche **Anruffluss** . Während Sie die Nachrichten durchlaufen, wird das Anruffluss Diagramm mit neuen Daten aktualisiert.

![Snooper 2013-Anruffluss Diagramm.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013-Anruffluss Diagramm.")

Sie können mit dem Mauszeiger auf die Diagrammansicht zeigen und Details zu den Nachrichten und dem Inhalt der Fluss-und Nachrichtenübermittlung sowie der Server Elemente abrufen. Klicken Sie auf einen Anruffluss Pfeil, um zur Nachricht in der Ansicht Nachrichten zu wechseln.

![Nachrichtendetails zum Anruffluss Diagramm.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Nachrichtendetails zum Anruffluss Diagramm.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>So öffnen Sie eine Protokolldatei in Snooper

1.  Um Snooper zu verwenden und Protokolldateien zu öffnen, benötigen Sie Lesezugriff auf die Protokolldateien. Um Snooper verwenden und auf die Protokolldateien zugreifen zu können, müssen Sie Mitglied der CsAdministrator-oder der CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält.

2.  Ändern Sie nach der Installation der lync Server Debugging-Tools (LyncDebugTools. msi) das Verzeichnis in den Speicherort von Snooper. exe mithilfe von Windows Explorer oder über die Befehlszeile. Standardmäßig befinden sich die Debug-Tools in C:\\Program Files\\Microsoft lync Server 2013\\Debugging Tools. Doppelklicken Sie auf oder führen Sie Snooper. exe aus.

3.  Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **Datei**, klicken Sie auf **OpenFile**, suchen Sie nach ihren Protokolldateien, wählen Sie im Dialogfeld **Öffnen** eine Datei aus, und klicken Sie dann auf **Öffnen**.

4.  Die **Ablauf Verfolgungs** Meldungen der Protokolldatei werden auf der Registerkarte **Ablaufverfolgung** angezeigt. Klicken Sie auf die Registerkarte **Nachrichten** , um den Nachrichteninhalt der gesammelten Ablaufverfolgungen anzuzeigen.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>So zeigen Sie ein Anruffluss Diagramm an

1.  Um Snooper zu verwenden und Protokolldateien zu öffnen, benötigen Sie Lesezugriff auf die Protokolldateien. Um Snooper verwenden und auf die Protokolldateien zugreifen zu können, müssen Sie Mitglied der CsAdministrator oder der CsServerAdministrator-Sicherheitsgruppen für rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält.

2.  Öffnen Sie eine Protokolldatei, klicken Sie auf die Registerkarte **Nachrichten** , wählen Sie eine Unterhaltung in der Ansicht Nachrichten aus, oder wählen Sie auf der Registerkarte **Ablauf** Verfolgung eine Ablauf Verfolgungs Komponente

3.  Klicken Sie auf **Anruffluss**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie auf eine Nachricht oder Ablaufverfolgung klicken, die nicht Teil eines Anrufflusses ist, wird das Diagramm nicht angezeigt, und es wird eine Statusmeldung unten in Snooper angezeigt, die besagt, dass "diese Nachricht nicht für callfow geeignet ist". Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus, und der Anruffluss wird angezeigt, wenn die Nachricht oder Ablaufverfolgung Teil eines Anrufflusses ist.

    
    </div>

4.  Navigieren Sie durch die Nachrichten oder die Ablauf Verfolgungszeilen, und notieren Sie, ob das Anruffluss Diagramm aktualisiert oder geändert wird, um ein neues Diagramm anzuzeigen.

5.  Bewegen Sie den Mauszeiger über Elemente, um Informationen zu Anruf Nachrichten, Endpunkten und anderen Komponenten zu erhalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

