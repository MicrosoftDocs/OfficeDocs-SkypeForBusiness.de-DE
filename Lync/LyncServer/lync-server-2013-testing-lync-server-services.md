---
title: 'Lync Server 2013: Testen von lync Server Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c5f39a636eb300f19cd42131fc42d2480bbf14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="eba05-102">Testen von lync Server Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eba05-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eba05-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="eba05-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eba05-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="eba05-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="eba05-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="eba05-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eba05-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="eba05-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="eba05-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eba05-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eba05-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="eba05-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="eba05-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="eba05-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="eba05-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsComputer verfügt.</span><span class="sxs-lookup"><span data-stu-id="eba05-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="eba05-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="eba05-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="eba05-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eba05-112">Description</span></span>

<span data-ttu-id="eba05-113">Mit Test-CsComputer wird der Status aller auf dem lokalen Computer ausgeführten lync Server 2013 Dienste überprüft.</span><span class="sxs-lookup"><span data-stu-id="eba05-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="eba05-114">(Test-CsComputer kann nur lokal ausgeführt werden, kann nicht von einer Remoteinstanz von Windows PowerShell ausgeführt werden.) Das Cmdlet prüft außerdem, ob die entsprechenden Firewall-Ports auf dem Computer geöffnet sind, und legt fest, ob die Active Directory Gruppen, die beim Installieren von lync Server 2013 erstellt wurden, zu den entsprechenden lokalen Gruppen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="eba05-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="eba05-115">Beispielsweise prüft Test-CsComputer, ob die Active Directory Gruppe RTCUniversalUserAdmins der Gruppe Administratoren hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="eba05-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="eba05-116">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="eba05-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="eba05-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="eba05-117">Running the test</span></span>

<span data-ttu-id="eba05-118">Das Cmdlet Test-CsComputer kann nur auf dem lokalen Computer ausgeführt werden, und Sie können Test-CsComputer nicht von einer Remoteinstanz von Windows PowerShell aus aufrufen.</span><span class="sxs-lookup"><span data-stu-id="eba05-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="eba05-119">Standardmäßig zeigt Test-CsComputer sehr wenig Ausgabe auf dem Bildschirm an, stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="eba05-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="eba05-120">Aus diesem Grund wird empfohlen, dass Sie den Verbose-Parameter und den Report-Parameter immer dann einbeziehen, wenn Sie Test-CsComputer ausführen.</span><span class="sxs-lookup"><span data-stu-id="eba05-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="eba05-121">Der Verbose-Parameter stellt eine etwas detailliertere Ausgabe auf dem Bildschirm bereit, während das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eba05-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="eba05-122">Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsComputer generierte HTML-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="eba05-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="eba05-123">Wenn Sie den Parameter "Report" nicht angeben, wird die HTML-Datei automatisch im Ordner "Users" gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-AD34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="eba05-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="eba05-124">Im folgenden Beispielbefehl wird Test-CsComputer ausgeführt, und die Ausgabe wird in einer Datei mit dem Namen\\C\\: Logs ComputerTest. html gespeichert:</span><span class="sxs-lookup"><span data-stu-id="eba05-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="eba05-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="eba05-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="eba05-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="eba05-126">Determining success or failure</span></span>

<span data-ttu-id="eba05-127">Aufgrund der Anzahl der Überprüfungs Prüfungen, die durchgeführt werden, meldet Test-CsComputer nicht wieder ein einfaches **Ja, der Test ist erfolgreich** oder **Nein, der Test ist fehlgeschlagen**.</span><span class="sxs-lookup"><span data-stu-id="eba05-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="eba05-128">Stattdessen müssen Sie die generierte HTML-Datei anzeigen, indem Sie Internet Explorer verwenden, um den Erfolg oder Misserfolg jedes Tests zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="eba05-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="eba05-129">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="eba05-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="eba05-130">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsComputer möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="eba05-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="eba05-131">Der Testcomputer ist möglicherweise nicht für die Verwendung mit lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eba05-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="eba05-132">Dies kann vorkommen, wenn sich die lync Server-Dienste oder-Server Rollen auf dem Computer geändert haben und das Cmdlet Enable-CsComputer nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="eba05-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="eba05-133">Führen Sie zum Beheben des Problems den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="eba05-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="eba05-134">Die Replikation ist auf dem Testcomputer möglicherweise nicht auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="eba05-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="eba05-135">Sie können den aktuellen Replikationsstatus für einen Computer überprüfen, indem Sie das Cmdlet Get-CsManagementStoreReplicationStatus ausführen:</span><span class="sxs-lookup"><span data-stu-id="eba05-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="eba05-136">Wenn der Replikationsstatus nicht auf dem neuesten Stand ist, können Sie die Replikation manuell erzwingen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="eba05-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="eba05-137">Möglicherweise muss die Topologie aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="eba05-137">The topology might have to be enabled.</span></span> <span data-ttu-id="eba05-138">Wenn Sie die lync Server Topologie ändern (Änderungen, die sich auf den lokalen Computer auswirken könnten), müssen Sie die neue Topologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eba05-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="eba05-139">Sie können die Topologie jederzeit aktivieren, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="eba05-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

