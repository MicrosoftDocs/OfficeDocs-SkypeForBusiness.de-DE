---
title: Verwenden von Best Practices Analyzer zum Überprüfen Ihrer Bereitstellung auf potenzielle Probleme
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="a84ab-102">Verwenden von Best Practices Analyzer zum Durchsuchen Ihrer lync Server 2013-Bereitstellung nach potenziellen Problemen</span><span class="sxs-lookup"><span data-stu-id="a84ab-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a84ab-103">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a84ab-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a84ab-104">Wenn Sie einen Best Practices Analyzer-Scan ausführen möchten, müssen Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="a84ab-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="a84ab-105">**Anmeldeinformationen**   Wenn Sie einen Scan durchführen möchten, müssen Sie sich bei einem Computer anmelden, auf dem Best Practices Analyzer installiert ist, indem Sie ein Konto verwenden, das Mitglied der lokalen Gruppe Administratoren ist.</span><span class="sxs-lookup"><span data-stu-id="a84ab-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="a84ab-106">Darüber hinaus müssen Sie sich mit einem Benutzerkonto anmelden, das über die Benutzerrechte und Berechtigungen zum Ausführen der entsprechenden Scans verfügt, oder Sie müssen Anmeldeinformationen angeben, die über die entsprechenden Benutzerrechte und Berechtigungen verfügen, wenn Sie Best Practices Analyzer ausführen.</span><span class="sxs-lookup"><span data-stu-id="a84ab-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="a84ab-107">Ausführliche Informationen finden Sie unter [Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="a84ab-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="a84ab-108">**Scanbereich um**   den Scanbereich anzugeben, wählen Sie die Kategorien und Server aus, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="a84ab-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="a84ab-109">Sie können alle Kategorien, eine oder mehrere Kategorien oder einen oder mehrere Server innerhalb einer bestimmten Kategorie in ihrer lync Server-Umgebung auswählen.</span><span class="sxs-lookup"><span data-stu-id="a84ab-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="a84ab-110">**Art des Scans**   zurzeit ist der Integritäts Prüfungs Scan der einzige verfügbare Scantyp (standardmäßig aktiviert).</span><span class="sxs-lookup"><span data-stu-id="a84ab-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="a84ab-111">Mit dem Integritäts Prüfungs Scan wird ein Bericht generiert, der Fehler, Warnungen und andere Informationen für alle im Bereich angegebenen Server enthält.</span><span class="sxs-lookup"><span data-stu-id="a84ab-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="a84ab-112">\*\*\*\*   Netzwerkgeschwindigkeit-Netzwerk Geschwindigkeitsoptionen umfassen schnelles LAN (100 Mbit/s oder mehr), LAN (10 Mbit/s), fast WAN (1,5 MBit/s) oder WAN (64 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="a84ab-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="a84ab-113">Die geschätzte Zeit zum Durchführen des Scans basiert auf dieser Einstellung.</span><span class="sxs-lookup"><span data-stu-id="a84ab-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="a84ab-114">Diese Einstellung wird auch zum Festlegen des Timeoutzeitraums verwendet.</span><span class="sxs-lookup"><span data-stu-id="a84ab-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="a84ab-115">Während des Scans wartet der Best Practices Analyzer auf eine Antwort von einem Server für einen bestimmten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="a84ab-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="a84ab-116">Wenn Sie innerhalb des angegebenen Timeoutzeitraums keine Antwort erhält, wechselt Sie zum nächsten Server in der Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="a84ab-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="a84ab-117">In langsameren Netzwerken ist dieser angegebene Timeoutzeitraum länger, um längere Netzwerk Latenzen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="a84ab-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="a84ab-118">Wir empfehlen, dass Sie den langsamsten Link in Ihrer Topologie für diesen Parameter auswählen, damit das Tool nicht zu schnell abläuft.</span><span class="sxs-lookup"><span data-stu-id="a84ab-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="a84ab-119">So überprüfen Sie Ihre lync Server 2013-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a84ab-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="a84ab-120">Melden Sie sich bei einem Computer an, auf dem Best Practices Analyzer installiert ist, indem Sie ein Konto verwenden, das Mitglied der lokalen Gruppe Administratoren ist, und über andere erforderliche Benutzerrechte und Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="a84ab-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="a84ab-121">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="a84ab-122">Klicken Sie auf der **Willkommens** Seite auf **Optionen für einen neuen Scan auswählen**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="a84ab-123">Überprüfen Sie auf der Seite **mit Active Directory verbinden** den in **Active Directory Server**angegebenen Namen, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a84ab-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a84ab-124">Wenn Sie einen Scan mit den Anmeldeinformationen ausführen möchten, die Sie für die Anmeldung am Computer verwendet haben, klicken Sie auf mit **dem Active Directory-Server verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="a84ab-125">Wenn Sie andere Anmeldeinformationen angeben möchten, die Sie für Active Directory-Domänendienste, Edgeserver oder Exchange Server verwenden möchten, klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**, aktivieren Sie die einzelnen Kontrollkästchen, für die getrennte Anmeldeinformationen erforderlich sind, geben Sie die Anmeldeinformationen an. für jedes ausgewählte Kontrollkästchen aus, und klicken Sie dann auf **mit dem Active Directory-Server verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a84ab-126">Vor Beginn des Scans führt Best Practices Analyzer eine Netzwerk-und Berechtigungsüberprüfung durch, um sicherzustellen, dass die angegebenen Kontoanmeldeinformationen gültig sind und dass Best Practices Analyzer eine Verbindung mit Active Directory-Domänendiensten herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a84ab-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="a84ab-127">Wenn das Tool auf einem Arbeitsgruppenserver ausgeführt wird, überprüft das Tool auch, ob es eine Verbindung mit Edgeserver im Umkreisnetzwerk herstellen kann (das heißt, wenn Sie in der Überprüfung enthalten sind).</span><span class="sxs-lookup"><span data-stu-id="a84ab-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="a84ab-128">Wählen Sie auf der Seite **neue Best Practices-Überprüfung starten** die Optionen aus, die Sie in die Überprüfung einbeziehen möchten, geben Sie die Netzwerkgeschwindigkeit an, und klicken Sie dann auf über **Prüfung starten**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="a84ab-129">Klicken Sie auf der Seite **Scan abgeschlossen** auf **Bericht anzeigen dieser bewährten Methoden Überprüfung**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="a84ab-130">Führen Sie auf der Seite " **Best Practices-Bericht anzeigen** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a84ab-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a84ab-131">Klicken Sie auf **Listen Berichte**, und klicken Sie dann entweder auf die Registerkarte **alle Probleme** oder auf die Registerkarte **Informationselemente** , um Berichte in einer nach Serverkomponente organisierten Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a84ab-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="a84ab-132">Klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **detaillierte Ansicht** oder auf die Registerkarte **Zusammenfassungsansicht** , um Berichte als hierarchische Liste anzuzeigen, die nach Arten von Ergebnissen sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="a84ab-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="a84ab-133">Wenn Sie andere Berichte anzeigen möchten, klicken Sie auf **Weitere Berichte**.</span><span class="sxs-lookup"><span data-stu-id="a84ab-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a84ab-134">Details zu den Berichten zu Best Practices Analyzer und den von Ihnen identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden</A> , und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer identifiziert werden. in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a84ab-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

