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
ms.openlocfilehash: ebb1ec3ebde4f1277d6304190aceafa2e0fe2884
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="fa543-102">Lesen von Erfassungs Protokollen aus dem zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa543-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa543-103">_**Letztes Änderungsstand des Themas:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="fa543-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="fa543-104">Sie erkennen den tatsächlichen Vorteil des zentralisierten Protokollierungsdiensts nach dem Ausführen der Suche, und Sie verfügen über eine Datei, die Sie zum Aufspüren eines gemeldeten Problems verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fa543-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="fa543-105">Es gibt eine Reihe von Möglichkeiten, wie Sie die Datei lesen können.</span><span class="sxs-lookup"><span data-stu-id="fa543-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="fa543-106">Die Ausgabedatei hat ein Standardtextformat und Sie können Notepad. exe oder andere Programme verwenden, mit denen Sie eine Textdatei öffnen und lesen können.</span><span class="sxs-lookup"><span data-stu-id="fa543-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="fa543-107">Für größere Dateien und komplexere Probleme können Sie ein Tool wie Snooper. exe verwenden, das zum Lesen und Analysieren der Protokollierungsausgabe vom zentralisierten Protokollierungsdienst entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="fa543-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="fa543-108">Snooper ist in den lync Server 2013 Debug-Tools enthalten, die als separater Download zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="fa543-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="fa543-109">Sie können die lync Server 2013 Debug-Tools hier herunter [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)laden:.</span><span class="sxs-lookup"><span data-stu-id="fa543-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="fa543-110">Wenn Sie die lync Server 2013 Debug-Tools installieren, werden keine Kurzschnitte und Menüelemente erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa543-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="fa543-111">Nachdem Sie die lync Server 2013 Debug-Tools installiert haben, öffnen Sie Windows Explorer, ein Befehlszeilenfenster oder lync Server-Verwaltungsshell und wechseln Sie zum Verzeichnis (Standardspeicherort) C\\: Programm\\Dateien\\Microsoft lync Server 2013 Debugging-Tools.</span><span class="sxs-lookup"><span data-stu-id="fa543-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="fa543-112">Doppelklicken Sie auf Snooper. exe, oder geben Sie Snooper. exe ein, und drücken Sie dann die EINGABETASTE, wenn Sie die Befehlszeile oder lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa543-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fa543-113">Die Absicht dieses Themas ist nicht detailliert und besprechen die Problembehandlungstechniken.</span><span class="sxs-lookup"><span data-stu-id="fa543-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="fa543-114">Die Problembehandlung und die Prozesse um Sie herum sind ein komplexes Thema.</span><span class="sxs-lookup"><span data-stu-id="fa543-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="fa543-115">Ausführliche Informationen zur grundlegenden Problembehandlung und zur Problembehandlung bei bestimmten Arbeitsauslastungen finden <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Sie im Microsoft lync Server 2010 Resource Kit-Buch unter.</span><span class="sxs-lookup"><span data-stu-id="fa543-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="fa543-116">Die Prozesse und Verfahren gelten weiterhin für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa543-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="fa543-117">Lync Server 2013 stellt eine aktualisierte Version von Snooper vor, die einige neue Features enthält.</span><span class="sxs-lookup"><span data-stu-id="fa543-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="fa543-118">Der folgende Screenshot zeigt die Version von Snooper aus Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="fa543-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="fa543-119">![Office Communications 2007-Version von Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007-Version von Snooper.")</span><span class="sxs-lookup"><span data-stu-id="fa543-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="fa543-120">Der folgende Screenshot zeigt die neue Version von Snooper, die in den lync Server 2013 Debug-Tools enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fa543-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="fa543-121">![Lync Server 2013 Version von Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 Version von Snooper.")</span><span class="sxs-lookup"><span data-stu-id="fa543-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="fa543-122">Der folgende Screenshot zeigt die Symbolleiste mit häufig verwendeten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="fa543-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="fa543-123">![Snooper 2013 Toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 Toolbar.")</span><span class="sxs-lookup"><span data-stu-id="fa543-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="fa543-124">Und das neueste Feature, das einen Wert hinzufügt, ist die Diagrammansicht Flussdiagramm (Anruffluss).</span><span class="sxs-lookup"><span data-stu-id="fa543-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="fa543-125">Sie wählen einen Nachrichtenfluss auf der Registerkarte **Nachricht** aus und klicken auf die Schaltfläche **Anruffluss** .</span><span class="sxs-lookup"><span data-stu-id="fa543-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="fa543-126">Während Sie die Nachrichten durchlaufen, wird das Anruffluss Diagramm mit neuen Daten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fa543-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="fa543-127">![Snooper 2013-Anruffluss Diagramm.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013-Anruffluss Diagramm.")</span><span class="sxs-lookup"><span data-stu-id="fa543-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="fa543-128">Sie können mit dem Mauszeiger auf die Diagrammansicht zeigen und Details zu den Nachrichten und dem Inhalt der Fluss-und Nachrichtenübermittlung sowie der Server Elemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="fa543-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="fa543-129">Klicken Sie auf einen Anruffluss Pfeil, um zur Nachricht in der Ansicht Nachrichten zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="fa543-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="fa543-130">![Nachrichtendetails zum Anruffluss Diagramm.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Nachrichtendetails zum Anruffluss Diagramm.")</span><span class="sxs-lookup"><span data-stu-id="fa543-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="fa543-131">So öffnen Sie eine Protokolldatei in Snooper</span><span class="sxs-lookup"><span data-stu-id="fa543-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="fa543-132">Um Snooper zu verwenden und Protokolldateien zu öffnen, benötigen Sie Lesezugriff auf die Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="fa543-132">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="fa543-133">Um Snooper verwenden und auf die Protokolldateien zugreifen zu können, müssen Sie Mitglied der CsAdministrator-oder der CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="fa543-133">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="fa543-134">Ändern Sie nach der Installation der lync Server Debugging-Tools (LyncDebugTools. msi) das Verzeichnis in den Speicherort von Snooper. exe mithilfe von Windows Explorer oder über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="fa543-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="fa543-135">Standardmäßig befinden sich die Debug-Tools in C:\\Program Files\\Microsoft lync Server 2013\\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="fa543-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="fa543-136">Doppelklicken Sie auf oder führen Sie Snooper. exe aus.</span><span class="sxs-lookup"><span data-stu-id="fa543-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="fa543-137">Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **Datei**, klicken Sie auf **OpenFile**, suchen Sie nach ihren Protokolldateien, wählen Sie im Dialogfeld **Öffnen** eine Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="fa543-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="fa543-138">Die **Ablauf Verfolgungs** Meldungen der Protokolldatei werden auf der Registerkarte **Ablaufverfolgung** angezeigt. Klicken Sie auf die Registerkarte **Nachrichten** , um den Nachrichteninhalt der gesammelten Ablaufverfolgungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa543-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="fa543-139">So zeigen Sie ein Anruffluss Diagramm an</span><span class="sxs-lookup"><span data-stu-id="fa543-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="fa543-140">Um Snooper zu verwenden und Protokolldateien zu öffnen, benötigen Sie Lesezugriff auf die Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="fa543-140">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="fa543-141">Um Snooper verwenden und auf die Protokolldateien zugreifen zu können, müssen Sie Mitglied der CsAdministrator oder der CsServerAdministrator-Sicherheitsgruppen für rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="fa543-141">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="fa543-142">Öffnen Sie eine Protokolldatei, klicken Sie auf die Registerkarte **Nachrichten** , wählen Sie eine Unterhaltung in der Ansicht Nachrichten aus, oder wählen Sie auf der Registerkarte **Ablauf** Verfolgung eine Ablauf Verfolgungs Komponente</span><span class="sxs-lookup"><span data-stu-id="fa543-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="fa543-143">Klicken Sie auf **Anruffluss**.</span><span class="sxs-lookup"><span data-stu-id="fa543-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa543-144">Wenn Sie auf eine Nachricht oder Ablaufverfolgung klicken, die nicht Teil eines Anrufflusses ist, wird das Diagramm nicht angezeigt, und es wird eine Statusmeldung unten in Snooper angezeigt, die besagt, dass "diese Nachricht nicht für callfow geeignet ist".</span><span class="sxs-lookup"><span data-stu-id="fa543-144">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="fa543-145">Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus, und der Anruffluss wird angezeigt, wenn die Nachricht oder Ablaufverfolgung Teil eines Anrufflusses ist.</span><span class="sxs-lookup"><span data-stu-id="fa543-145">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="fa543-146">Navigieren Sie durch die Nachrichten oder die Ablauf Verfolgungszeilen, und notieren Sie, ob das Anruffluss Diagramm aktualisiert oder geändert wird, um ein neues Diagramm anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa543-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="fa543-147">Bewegen Sie den Mauszeiger über Elemente, um Informationen zu Anruf Nachrichten, Endpunkten und anderen Komponenten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fa543-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

