---
title: Verwenden von Best Practices Analyzer zum Überprüfen der Bereitstellung auf mögliche Probleme
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afda261fc3e57750afaabbf349eb31631adea275
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="20505-102">Verwenden von Best Practices Analyzer zum Überprüfen Ihrer lync Server 2013-Bereitstellung auf mögliche Probleme</span><span class="sxs-lookup"><span data-stu-id="20505-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20505-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="20505-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="20505-104">Zum Ausführen einer Best Practices Analyzer-Überprüfung müssen Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="20505-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="20505-105">**Anmeldeinformationen**   zum Ausführen eines Scans müssen Sie sich bei einem Computer anmelden, auf dem Best Practices Analyzer installiert ist, indem Sie ein Konto verwenden, das Mitglied der lokalen Gruppe Administratoren ist.</span><span class="sxs-lookup"><span data-stu-id="20505-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="20505-106">Außerdem müssen Sie sich mit einem Benutzerkonto anmelden, das über die erforderlichen Benutzerrechte und Berechtigungen verfügt, um die geeigneten Überprüfungen auszuführen, oder Sie müssen beim Ausführen von Best Practices Analyzer Anmeldeinformationen angeben, die über die erforderlichen Benutzerrechte und Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="20505-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="20505-107">Ausführliche Informationen finden Sie unter [Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="20505-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="20505-108">**Umfang**   der Überprüfung um den Umfang der Überprüfung anzugeben, wählen Sie die Kategorien und Server aus, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="20505-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="20505-109">Sie können alle Kategorien, eine oder mehrere Kategorien oder einen oder mehrere Server in einer bestimmten Kategorie in ihrer lync Server Umgebung auswählen.</span><span class="sxs-lookup"><span data-stu-id="20505-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="20505-110">**Typ der**   Überprüfung derzeit ist der Integritäts Prüfungs Scan der einzige verfügbare Scantyp (standardmäßig ausgewählt).</span><span class="sxs-lookup"><span data-stu-id="20505-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="20505-111">Die Integritätsprüfung generiert einen Bericht mit Fehlern, Warnungen und weiteren Informationen für alle Server, die sich im angegebenen Bereich befinden.</span><span class="sxs-lookup"><span data-stu-id="20505-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="20505-112">**Netzwerkgeschwindigkeit**   Netzwerk Geschwindigkeitsoptionen umfassen schnelles LAN (100 Mbit/s oder mehr), LAN (10 Mbit/s), schnelles WAN (1,5 MBit/s) oder WAN (64 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="20505-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="20505-113">Die geschätzte Dauer der Überprüfung basiert auf dieser Einstellung.</span><span class="sxs-lookup"><span data-stu-id="20505-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="20505-114">Zudem wird diese Einstellung auch zum Festlegen des Timeouts verwendet.</span><span class="sxs-lookup"><span data-stu-id="20505-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="20505-115">Während der Überprüfung wartet der Best Practices Analyzer eine angegebene Zeitdauer auf eine Serverantwort.</span><span class="sxs-lookup"><span data-stu-id="20505-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="20505-116">Erfolgt innerhalb des angegebenen Timeout-Zeitraums keine Antwort, wird zum nächsten Server in der Überprüfung gewechselt.</span><span class="sxs-lookup"><span data-stu-id="20505-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="20505-117">In langsameren Netzwerken ist dieser Timeout-Zeitraum länger, um längere Netzwerklatenzen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="20505-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="20505-118">Wir empfehlen die Auswahl der langsamsten Verbindung in Ihrer Topologie für diesen Parameter, damit das Tool nicht zu schnell einen Timeout ausgibt.</span><span class="sxs-lookup"><span data-stu-id="20505-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="20505-119">So führen Sie eine Überprüfung Ihrer Lync Server 2013-Bereitstellung durch</span><span class="sxs-lookup"><span data-stu-id="20505-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="20505-120">Melden Sie sich an einem Computer an, auf dem Best Practices Analyzer installiert ist. Verwenden Sie dabei ein Konto, das Mitglied der lokalen Administratorengruppe ist und über weitere erforderliche Benutzerrechte und -berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="20505-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="20505-121">Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="20505-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="20505-122">Klicken Sie auf der **Willkommensseite** auf **Optionen für neue Überprüfung auswählen**.</span><span class="sxs-lookup"><span data-stu-id="20505-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="20505-123">Überprüfen Sie auf der Seite **Mit Active Directory verbinden** den in **Active Directory-Server** angegebenen Namen, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="20505-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="20505-124">Zum Ausführen einer Überprüfung mit den Anmeldeinformationen, die Sie zur Anmeldung an Computer verwendet haben, klicken Sie auf **Mit Active Directory-Server verbinden**.</span><span class="sxs-lookup"><span data-stu-id="20505-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="20505-125">Zum Angeben verschiedener Anmeldeinformationen, die Sie für Active Directory Domain Services, Edgeserver oder Exchange Server verwenden möchten, klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**, aktivieren Sie alle Kontrollkästchen, für die separate Anmeldeinformationen erforderlich sind, geben Sie die Anmeldeinformationen für jedes aktivierte Kontrollkästchen an, und klicken Sie dann auf **Mit Active Directory-Server verbinden**.</span><span class="sxs-lookup"><span data-stu-id="20505-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="20505-p105">Vor dem Beginn der Überprüfung führt Best Practices Analyzer eine Netzwerk- und Berechtigungsprüfung durch, um sicherzustellen, dass die angegebenen Kontoanmeldeinformationen gültig sind und Best Practices Analyzer eine Verbindung mit Active Directory Domain Services herstellen kann. Wird das Tool auf einem Arbeitsgruppenserver ausgeführt, überprüft es auch, ob eine Verbindung mit Edgeservern im Umkreisnetzwerk möglich ist (falls diese in die Überprüfung eingeschlossen sind).</span><span class="sxs-lookup"><span data-stu-id="20505-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="20505-128">Wählen Sie auf der Seite **Neue Bewährte Methoden-Überprüfung starten** die Optionen, die die Überprüfung umfassen soll, geben Sie die Netzwerkgeschwindigkeit an, und klicken Sie dann auf **Überprüfung starten**.</span><span class="sxs-lookup"><span data-stu-id="20505-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="20505-129">Klicken Sie auf der Seite **Überprüfung abgeschlossen** auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="20505-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="20505-130">Führen Sie auf der Seite **Bewährte Methoden-Bericht anzeigen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="20505-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="20505-131">Wenn Sie Berichte in einer Liste anzeigen möchten, die nach Serverkomponenten angeordnet ist, klicken Sie auf **Berichte auflisten**, und klicken Sie dann entweder auf die Registerkarte **Alle Probleme** oder auf **Informationselemente**.</span><span class="sxs-lookup"><span data-stu-id="20505-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="20505-132">Wenn Sie Berichte als hierarchische Liste anzeigen möchten, die nach Ergebnistypen angeordnet ist, klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **Detaillierte Ansicht** oder auf **Zusammenfassungsansicht**.</span><span class="sxs-lookup"><span data-stu-id="20505-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="20505-133">Wenn Sie sonstige Berichte anzeigen möchten, klicken Sie auf **Sonstige Berichte**.</span><span class="sxs-lookup"><span data-stu-id="20505-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="20505-134">Ausführliche Informationen zu den Best Practices Analyzer-Berichten und den identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer erstellt wurden, in lync Server 2013</A> und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert</A>wurden.</span><span class="sxs-lookup"><span data-stu-id="20505-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

