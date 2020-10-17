---
title: 'Lync Server 2013: Testen der Dienstaktivierung und der Gruppen Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e29cafcfac7a74e43617841a174653f6072c5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530522"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="0de20-102">Testen von Dienstaktivierung und Gruppen Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0de20-102">Testing service activation and group permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0de20-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0de20-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0de20-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="0de20-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0de20-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="0de20-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de20-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="0de20-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0de20-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0de20-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de20-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0de20-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0de20-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="0de20-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0de20-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsTopology-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="0de20-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="0de20-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="0de20-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0de20-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0de20-112">Description</span></span>

<span data-ttu-id="0de20-113">Mit dem Test-CsTopology-Cmdlet können Sie überprüfen, ob lync Server 2013 auf globaler Ebene ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0de20-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="0de20-114">Standardmäßig prüft das Cmdlet die gesamte lync Server Infrastruktur, überprüft, ob die erforderlichen Dienste aktiv sind und dass die entsprechenden Berechtigungen für diese Dienste und für die universellen Sicherheitsgruppen festgelegt sind, die bei der Installation von lync Server erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0de20-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="0de20-115">Zusätzlich zur Überprüfung der Gültigkeit der lync Server Installation können Sie mit Test-CsTopology auch die Gültigkeit eines bestimmten Diensts überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0de20-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="0de20-116">Mit dem folgenden Befehl wird beispielsweise der Zustand des A/V-Konferenzserver im Pool ATL-CS-001.litwareinc.com überprüft:</span><span class="sxs-lookup"><span data-stu-id="0de20-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0de20-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="0de20-117">Running the test</span></span>

<span data-ttu-id="0de20-118">Standardmäßig zeigt Test-CsTopology nur sehr wenig Ausgabe auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="0de20-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="0de20-119">Stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0de20-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="0de20-120">Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsTopology generierte HTML-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="0de20-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="0de20-121">Wenn Sie den Parameter "Report" nicht angeben, wird die HTML-Datei automatisch im Ordner "Users" gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="0de20-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="0de20-122">Der folgende Beispielbefehl führt Test-CsTopology aus und speichert die Ausgabe in einer Datei mit dem Namen C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="0de20-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="0de20-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="0de20-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0de20-124">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="0de20-124">Determining success or failure</span></span>

<span data-ttu-id="0de20-125">Im Gegensatz zu den meisten Test-Cmdlets meldet Test-CsTopology den Erfolg oder Misserfolg zurück.</span><span class="sxs-lookup"><span data-stu-id="0de20-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="0de20-126">Dies ist teilweise auf die große Anzahl von Überprüfungs Prüfungen zurückzuführen, die das Cmdlet jedes Mal vornehmen muss, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0de20-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="0de20-127">Stattdessen werden Daten in einem HTML-Bericht gespeichert, der dann mithilfe von Internet Explorer angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0de20-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0de20-128">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="0de20-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="0de20-129">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsTopology Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="0de20-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="0de20-130">Die Replikation ist auf dem Testcomputer möglicherweise nicht auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="0de20-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="0de20-131">Sie können den aktuellen Replikationsstatus für einen Computer überprüfen, indem Sie das Get-CsManagementStoreReplicationStatus-Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="0de20-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="0de20-132">Wenn der Replikationsstatus nicht auf dem neuesten Stand ist, können Sie die Replikation manuell erzwingen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="0de20-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="0de20-133">Möglicherweise muss die Topologie aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0de20-133">The topology might have to be enabled.</span></span> <span data-ttu-id="0de20-134">Wenn Sie die lync Server Topologie ändern (Änderungen, die sich auf den lokalen Computer auswirken könnten), müssen Sie die neue Topologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0de20-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="0de20-135">Sie können die Topologie jederzeit aktivieren, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="0de20-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

