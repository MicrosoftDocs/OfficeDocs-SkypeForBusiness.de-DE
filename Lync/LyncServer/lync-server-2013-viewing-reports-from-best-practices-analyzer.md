---
title: 'Lync Server 2013: Anzeigen von Berichten aus Best Practices Analyzer'
description: 'Lync Server 2013: Anzeigen von Berichten aus Best Practices Analyzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44e0f1ed8d48f5c8fb7e35187ecdda2778091407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542361"
---
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="2313f-103">Anzeigen von Berichten aus Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2313f-103">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2313f-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2313f-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2313f-p101">Wenn Sie Best Practices Analyzer zur Überprüfung Ihrer Umgebung verwenden, geben Sie einen Namen für die Überprüfung an. Nach Abschluss der Überprüfung speichert Best Practices Analyzer die Überprüfungsergebnisse in Berichten und speichert diese Berichte unter dem Namen der Überprüfung. Sobald die Überprüfung abgeschlossen ist, können Sie die erstellten Berichte anzeigen, indem Sie direkt auf der Seite **Überprüfung abgeschlossen** auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen** klicken. Sie können die Berichte für diese oder frühere Überprüfungen auch zu einem späteren Zeitpunkt anzeigen. Sie können die Berichte auf dem lokalen Computer anzeigen, auf dem die Überprüfung erfolgt ist, die Überprüfungsergebnisse von einem anderen Computer importieren oder die Überprüfungsergebnisse exportieren, um sie auf einem Computer anzuzeigen, auf dem Best Practices Analyzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2313f-p101">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan. After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan. Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page. You can also view the reports from that scan or previous scans at a later time. You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="2313f-110">Die Überprüfungsergebnisse werden in den folgenden Arten von Berichten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2313f-110">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="2313f-111">Listenberichte</span><span class="sxs-lookup"><span data-stu-id="2313f-111">List reports</span></span>

  - <span data-ttu-id="2313f-112">Strukturberichte</span><span class="sxs-lookup"><span data-stu-id="2313f-112">Tree reports</span></span>

  - <span data-ttu-id="2313f-113">Sonstige Berichte</span><span class="sxs-lookup"><span data-stu-id="2313f-113">Other reports</span></span>

<span data-ttu-id="2313f-114">Diese Berichte umfassen Fehler, Warnungen und andere Informationen.</span><span class="sxs-lookup"><span data-stu-id="2313f-114">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="2313f-115">Ausführliche Informationen zu diesen Arten von Berichten und Problemen finden Sie unter [Understanding Reports by Best Practices Analyzer created in lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="2313f-115">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="2313f-116">Verwenden Sie das folgende Verfahren, um die Überprüfungsergebnisse anzuzeigen, die zuvor mit Best Practices Analyzer erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2313f-116">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="2313f-117">So zeigen Sie Berichte aus einer früheren Überprüfung an</span><span class="sxs-lookup"><span data-stu-id="2313f-117">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="2313f-118">Melden Sie sich auf einem Computer an, auf dem Best Practices Analyzer installiert ist. Verwenden Sie dabei ein Konto, das Mitglied des Kontos für lokale Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="2313f-118">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="2313f-119">Sie können zwar die Ergebnisse einer Überprüfung anzeigen, wenn Sie ein Konto verwenden, das Mitglied der lokalen Administratorengruppe ist; Sie können jedoch nur eine Überprüfung ausführen, wenn Sie über die erforderlichen Benutzerrechte und Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2313f-119">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="2313f-120">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2313f-120">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="2313f-121">Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="2313f-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="2313f-122">Klicken Sie im Willkommensbildschirm\*\*\*\* auf **Anzuzeigende Überprüfungsergebnisse auswählen**.</span><span class="sxs-lookup"><span data-stu-id="2313f-122">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="2313f-123">Führen Sie auf der Seite **Bewährte Methoden-Überprüfung zum Anzeigen auswählen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2313f-123">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2313f-124">Wenn Sie Berichte aus der Liste der lokal gespeicherten Überprüfungsergebnisse anzeigen möchten, klicken Sie auf den Namen der Überprüfung, und klicken Sie dann auf **Bericht für diese Überprüfung anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2313f-124">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="2313f-125">Der Best Practices Analyzer erstellt die Liste der lokalen Dateien aus dem &lt; Ordner &gt; \\ System Drive Dokumente und Einstellungen \\ &lt; Benutzer &gt; Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="2313f-125">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="2313f-126">Wenn Sie Berichte zu Ergebnissen einer Überprüfung anzeigen möchten, die sich an einem anderen Speicherort befinden, klicken Sie auf **Überprüfung importieren**, suchen Sie nach der Datei, in der die Überprüfungsergebnisse enthalten sind, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="2313f-126">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="2313f-127">Wenn die Version von Best Practices Analyzer auf diesem Computer nicht mit der Version übereinstimmt, die verwendet wurde, um die Daten in der importierten Datei zu erfassen, wird die Datei von dem Tool auf Ihrem Computer möglicherweise nach dem Import erneut analysiert.</span><span class="sxs-lookup"><span data-stu-id="2313f-127">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="2313f-128">Führen Sie auf der Seite **Bewährte Methoden-Bericht anzeigen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2313f-128">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2313f-129">Wenn Sie Berichte in einer Liste anzeigen möchten, die nach Serverkomponenten angeordnet ist, klicken Sie auf **Berichte auflisten**, und klicken Sie dann entweder auf die Registerkarte **Alle Probleme** oder auf **Informationselemente**.</span><span class="sxs-lookup"><span data-stu-id="2313f-129">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="2313f-130">Wenn Sie Berichte als hierarchische Liste anzeigen möchten, die nach Ergebnistypen angeordnet ist, klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **Detaillierte Ansicht** oder auf **Zusammenfassungsansicht**.</span><span class="sxs-lookup"><span data-stu-id="2313f-130">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="2313f-131">Wenn Sie sonstige Berichte anzeigen möchten, klicken Sie auf **Sonstige Berichte**.</span><span class="sxs-lookup"><span data-stu-id="2313f-131">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="2313f-132">Ausführliche Informationen zu den Best Practices Analyzer-Berichten und den identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer erstellt wurden, in lync Server 2013</A> und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert</A>wurden.</span><span class="sxs-lookup"><span data-stu-id="2313f-132">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>

