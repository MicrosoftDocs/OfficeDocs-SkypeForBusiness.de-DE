---
title: 'Lync Server 2013: Importieren der lync Server 2013-Verwaltungspakete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="78647-102">Importieren der lync Server 2013-Verwaltungspakete</span><span class="sxs-lookup"><span data-stu-id="78647-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78647-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="78647-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="78647-104">Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die festlegt, welche Elemente System Center Operations Manager überwachen kann, und wie diese Elemente überwacht werden sollen und wie Benachrichtigungen ausgelöst werden sollen und berichtet.</span><span class="sxs-lookup"><span data-stu-id="78647-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="78647-105">Lync Server 2013 umfasst zwei System Center Operations Manager-Verwaltungspakete, die die folgenden Funktionen bieten:</span><span class="sxs-lookup"><span data-stu-id="78647-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="78647-106">Das Komponenten-und Benutzer Verwaltungspaket (Microsoft.ls.2013.Monitoring.ComponentAndUser.MP) verfolgt lync-Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Anruf Detaildatensätzen (CDR) oder der Quality of Experience (QoE) protokolliert wurden. Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="78647-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="78647-107">Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Sofortnachricht oder SMS-Messaging benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="78647-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="78647-108">SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem mobilen Gerät an einen anderen zu senden.)</span><span class="sxs-lookup"><span data-stu-id="78647-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78647-109">Details zum Konfigurieren der Operations Manager-Benachrichtigung finden Sie unter Konfigurieren der Benachrichtigung in der TechNet <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>-Bibliothek unter.</span><span class="sxs-lookup"><span data-stu-id="78647-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="78647-110">Das Active Monitoring Management Pack (Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP) testet die wichtigsten lync Server-Komponenten proaktiv, beispielsweise die Anmeldung beim System, den Austausch von Sofortnachrichten oder das tätigen von Anrufen an ein Telefon, das sich im öffentlichen Switch befindet Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="78647-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="78647-111">Diese Tests werden mithilfe der Cmdlets für synthetische lync Server-Transaktionen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="78647-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="78647-112">So können Sie beispielsweise das Cmdlet **Test-CsIM** verwenden, um eine Chat Unterhaltung zwischen zwei Testbenutzern zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="78647-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="78647-113">Wenn diese simulierte Nachrichten Unterhaltung fehlschlägt, wird eine Benachrichtigung generiert.</span><span class="sxs-lookup"><span data-stu-id="78647-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="78647-114">Sie müssen die Management Packs importieren.</span><span class="sxs-lookup"><span data-stu-id="78647-114">You need to import the management packs.</span></span> <span data-ttu-id="78647-115">Wenn Sie die Management Packs nicht importieren, können Sie Operations Manager nicht verwenden, um lync Server-Ereignisse zu überwachen oder synthetische lync Server-Transaktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="78647-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="78647-116">Das Komponenten-und Benutzer Verwaltungspaket wird nur zum Überwachen von lync Server 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="78647-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="78647-117">Wenn Sie sich in einem Koexistenz-Szenario befinden, in dem sowohl lync Server 2013 als auch lync Server 2010 installiert sind, sollten Sie weiterhin die lync Server 2010-Verwaltungspakete für Ihre lync Server 2010-Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="78647-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78647-118">Zu den Management Packs für lync Server 2010 gehören das lync Server 2010-Überwachungs Management Pack und das lync Server 2010-Überwachungs Management Pack für Gruppenchats.</span><span class="sxs-lookup"><span data-stu-id="78647-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="78647-119">Zum Importieren der Management Packs können folgende Tools verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="78647-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="78647-120">**System Center Operations Manager**   mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für lync Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="78647-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="78647-121">**Operations Manager-Shell**   Sie können die Operations Manager-Shell verwenden, um direkt zu importieren oder Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.</span><span class="sxs-lookup"><span data-stu-id="78647-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="78647-122">Importieren der Management Packs mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="78647-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="78647-123">Laden Sie die Dateien Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP und Microsoft.ls.2013.Monitoring.ComponentAndUser.MP.</span><span class="sxs-lookup"><span data-stu-id="78647-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="78647-124">Klicken Sie in System Center Operations Manager auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="78647-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="78647-125">Klicken Sie im **Verwaltungs** Bereich mit der rechten Maustaste auf **Management Packs**, und klicken Sie dann auf **Management Packs importieren**.</span><span class="sxs-lookup"><span data-stu-id="78647-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="78647-126">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="78647-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="78647-127">Klicken Sie im Dialogfeld **Online Katalogverbindung** auf **Abbrechen** , um zu verhindern, dass Operations Manager Online geht, um festzustellen, ob für die lync Server-Management Packs Abhängigkeiten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="78647-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="78647-128">Wenn Sie System Center Operations Manager 2012 verwenden, klicken Sie auf **Nein**.</span><span class="sxs-lookup"><span data-stu-id="78647-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="78647-129">Suchen Sie im Dialogfeld **zu importierende Management Packs auswählen nach** den Dateien **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** und **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** , und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="78647-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="78647-130">Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie die STRG-Taste gedrückt, und klicken Sie dann auf die zweite Datei.</span><span class="sxs-lookup"><span data-stu-id="78647-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="78647-131">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="78647-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="78647-132">Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="78647-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="78647-133">Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner, und starten Sie den Import-und Installationsvorgang erneut.</span><span class="sxs-lookup"><span data-stu-id="78647-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="78647-134">Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="78647-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="78647-135">Beachten Sie, dass für den Import-und Installationsvorgang möglicherweise mehrere Minuten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="78647-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="78647-136">Importieren von Management Packs mithilfe der Operations Manager-Shell</span><span class="sxs-lookup"><span data-stu-id="78647-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="78647-137">Im Allgemeinen ist es einfacher, die Management Packs mithilfe von Operations Manager zu importieren. Wenn jedoch ein Fehler auftritt und der Import fehlschlägt, bietet die Konsole nicht immer angemessene Fehlerberichte.</span><span class="sxs-lookup"><span data-stu-id="78647-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="78647-138">Im Vergleich dazu bietet die Operations Manager-Shell detaillierte Informationen.</span><span class="sxs-lookup"><span data-stu-id="78647-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="78647-139">Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Probleme auftreten, importieren Sie das Pack mithilfe der Operations Manager-Shell.</span><span class="sxs-lookup"><span data-stu-id="78647-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="78647-140">Die Operations Manager-Shell bietet weitere Informationen, die Ihnen bei der Entscheidung helfen können, warum der Import fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="78647-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="78647-141">Wenn Sie System Center Operations Manager 2007 R2 verwenden, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="78647-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="78647-142">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **System Center Operations Manager 2007 R2**, und klicken Sie dann auf **Operations Manager-Shell**.</span><span class="sxs-lookup"><span data-stu-id="78647-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="78647-143">Geben Sie in der Operations Manager-Shell an der Eingabeaufforderung den folgenden Befehl unter Verwendung des tatsächlichen Pfads zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="78647-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="78647-144">Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang mit dem Pfad zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ComponentAndUser.MP:</span><span class="sxs-lookup"><span data-stu-id="78647-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="78647-145">Schließen Sie die Operations Manager-Shell.</span><span class="sxs-lookup"><span data-stu-id="78647-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="78647-146">Wenn Sie System Center Operations Manager 2012 verwenden, führen Sie stattdessen dieses Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="78647-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="78647-147">Klicken Sie auf **Start**, klicken Sie dann auf **Alle Programme**, anschließend auf **Microsoft System Center 2012**, dann auf **Operations Manager** und anschließend auf **Operations Manager-Shell**.</span><span class="sxs-lookup"><span data-stu-id="78647-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="78647-148">Geben Sie in der Operations Manager-Shell an der Eingabeaufforderung den folgenden Befehl unter Verwendung des tatsächlichen Pfads zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="78647-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="78647-149">Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang mit dem Pfad zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ComponentAndUser.MP:</span><span class="sxs-lookup"><span data-stu-id="78647-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

