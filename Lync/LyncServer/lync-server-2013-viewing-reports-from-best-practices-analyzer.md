---
title: 'Lync Server 2013: Anzeigen von Berichten aus Best Practices Analyzer'
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
ms.openlocfilehash: e79732661152ba0929b62ae64f46b0cbfdb95217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="82645-102">Anzeigen von Berichten von Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82645-102">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82645-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="82645-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="82645-104">Wenn Sie Best Practices Analyzer zum Überprüfen Ihrer Umgebung verwenden, geben Sie einen Namen für die Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="82645-104">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan.</span></span> <span data-ttu-id="82645-105">Nachdem Best Practices Analyzer eine Überprüfung abgeschlossen hat, speichert Sie die Überprüfungsergebnisse in Berichten und speichert Sie unter dem Namen der Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="82645-105">After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan.</span></span> <span data-ttu-id="82645-106">Nach Abschluss der Überprüfung können Sie die für diesen Scan generierten Berichte anzeigen, indem Sie direkt auf der Seite **Scannen abgeschlossen** auf **Bericht anzeigen dieser bewährten Methoden prüfen** klicken.</span><span class="sxs-lookup"><span data-stu-id="82645-106">Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page.</span></span> <span data-ttu-id="82645-107">Sie können die Berichte auch zu einem späteren Zeitpunkt über diesen Scan oder vorherige Scans anzeigen.</span><span class="sxs-lookup"><span data-stu-id="82645-107">You can also view the reports from that scan or previous scans at a later time.</span></span> <span data-ttu-id="82645-108">Sie können Berichte auf dem lokalen Computer anzeigen, auf dem die Überprüfung ausgeführt wurde, die Überprüfungsergebnisse von einem anderen Computer importieren oder die Scanergebnisse exportieren, um die Berichte auf einem anderen Computer anzuzeigen, auf dem Best Practices Analyzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="82645-108">You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="82645-109">Die Scan Ergebnisse werden in den folgenden Berichtstypen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="82645-109">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="82645-110">Listen Berichte</span><span class="sxs-lookup"><span data-stu-id="82645-110">List reports</span></span>

  - <span data-ttu-id="82645-111">Strukturberichte</span><span class="sxs-lookup"><span data-stu-id="82645-111">Tree reports</span></span>

  - <span data-ttu-id="82645-112">Andere Berichte</span><span class="sxs-lookup"><span data-stu-id="82645-112">Other reports</span></span>

<span data-ttu-id="82645-113">Diese Berichte umfassen Fehler, Warnungen und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="82645-113">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="82645-114">Ausführliche Informationen zu jedem dieser Arten von Berichten und Problemen finden Sie unter [Grundlegendes zu berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="82645-114">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="82645-115">Gehen Sie wie folgt vor, um die zuvor von Best Practices Analyzer generierten Scanergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="82645-115">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="82645-116">So zeigen Sie Berichte aus einer vorherigen Überprüfung an</span><span class="sxs-lookup"><span data-stu-id="82645-116">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="82645-117">Melden Sie sich bei einem Computer an, auf dem Best Practices Analyzer installiert ist, und verwenden Sie ein Konto, das Mitglied des lokalen Benutzerkontos ist.</span><span class="sxs-lookup"><span data-stu-id="82645-117">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="82645-118">Sie können die Ergebnisse eines Scans mit einem Konto anzeigen, das Mitglied der lokalen Gruppe Administratoren ist, aber Sie können nur dann einen Scan ausführen, wenn Sie über die entsprechenden Benutzerrechte und Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="82645-118">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="82645-119">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="82645-119">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="82645-120">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="82645-120">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="82645-121">Klicken Sie auf der **Willkommens** Seite auf **die anzuzeigenden Scanergebnisse auswählen**.</span><span class="sxs-lookup"><span data-stu-id="82645-121">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="82645-122">Führen Sie auf der Seite **Wählen Sie eine bewährte Vorgehensweise für die Anzeige aus** , eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82645-122">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="82645-123">Wenn Sie Berichte aus der Liste der lokal gespeicherten Scanergebnisse anzeigen möchten, klicken Sie auf den Namen des Scans, und klicken Sie dann auf **Bericht dieser Überprüfung anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="82645-123">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="82645-124">Der Best Practices Analyzer erstellt die Liste der lokalen Dateien aus dem &lt;Ordner&gt;\\System Drive Dokumente\\&lt;und&gt;Einstellungen Benutzer-Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="82645-124">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="82645-125">Wenn Sie Berichte zu den Ergebnissen eines Scans anzeigen möchten, die an einem anderen Speicherort gespeichert sind, klicken Sie auf **Scan importieren**, suchen Sie die Datei, die die Überprüfungsergebnisse enthält, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="82645-125">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="82645-126">Wenn die Version von Best Practices Analyzer auf diesem Computer nicht mit der Version übereinstimmt, die zum Sammeln der Daten in der importierten Datei verwendet wurde, analysiert das Tool auf Ihrem Computer die Datei möglicherweise erneut, nachdem Sie importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="82645-126">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="82645-127">Führen Sie auf der Seite " **Best Practices-Bericht anzeigen** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82645-127">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="82645-128">Klicken Sie auf **Listen Berichte**, und klicken Sie dann entweder auf die Registerkarte **alle Probleme** oder auf die Registerkarte **Informationselemente** , um Berichte in einer nach Serverkomponente organisierten Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="82645-128">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="82645-129">Klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **detaillierte Ansicht** oder auf die Registerkarte **Zusammenfassungsansicht** , um Berichte als hierarchische Liste anzuzeigen, die nach Arten von Ergebnissen sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="82645-129">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="82645-130">Wenn Sie andere Berichte anzeigen möchten, klicken Sie auf **Weitere Berichte**.</span><span class="sxs-lookup"><span data-stu-id="82645-130">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="82645-131">Details zu den Berichten zu Best Practices Analyzer und den von Ihnen identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden</A> , und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert</A>werden.</span><span class="sxs-lookup"><span data-stu-id="82645-131">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>

