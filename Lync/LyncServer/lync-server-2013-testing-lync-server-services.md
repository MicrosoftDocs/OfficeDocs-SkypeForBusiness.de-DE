---
title: 'Lync Server 2013: Testen der lync Server-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="ab0bf-102">Testen der lync Server-Dienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab0bf-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab0bf-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ab0bf-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab0bf-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="ab0bf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ab0bf-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="ab0bf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0bf-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="ab0bf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ab0bf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab0bf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0bf-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ab0bf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ab0bf-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ab0bf-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsComputer-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="ab0bf-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ab0bf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab0bf-112">Description</span></span>

<span data-ttu-id="ab0bf-113">Test-CsComputer überprüft den Status aller lync Server 2013-Dienste, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="ab0bf-114">(Test-CsComputer kann nur lokal ausgeführt werden, kann nicht von einer Remoteinstanz von Windows PowerShell ausgeführt werden.) Das Cmdlet überprüft auch, ob die entsprechenden Firewall-Ports auf dem Computer geöffnet sind, und bestimmt, ob die Active Directory-Gruppen, die bei der Installation von lync Server 2013 erstellt wurden, den entsprechenden lokalen Gruppen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="ab0bf-115">Beispielsweise überprüft Test-CsComputer, ob die Active Directory-Gruppe RTCUniversalUserAdmins der Gruppe Administratoren hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="ab0bf-116">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="ab0bf-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ab0bf-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="ab0bf-117">Running the test</span></span>

<span data-ttu-id="ab0bf-118">Das Cmdlet "Test-CsComputer" kann nur auf dem lokalen Computer ausgeführt werden, Sie können Test-CsComputer nicht aus einer Remoteinstanz von Windows PowerShell aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="ab0bf-119">Standardmäßig werden in Test-CsComputer nur sehr wenige Ausgaben auf dem Bildschirm angezeigt, stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="ab0bf-120">Aus diesem Grund empfehlen wir, dass Sie den Verbose-Parameter und den Berichtsparameter jederzeit einfügen, wenn Sie Test-CsComputer ausführen.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="ab0bf-121">Der Verbose-Parameter bietet eine etwas detailliertere Ausgabe auf dem Bildschirm, während das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="ab0bf-122">Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsComputer generierte HTML-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="ab0bf-123">Wenn Sie den Berichtsparameter nicht angeben, wird die HTML-Datei automatisch in Ihrem Benutzerordner gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-AD34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="ab0bf-124">Der folgende Beispielbefehl führt Test-CsComputer aus und speichert die Ausgabe in einer Datei mit dem Namen C\\:\\Logs ComputerTest. html:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="ab0bf-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="ab0bf-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ab0bf-126">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="ab0bf-126">Determining success or failure</span></span>

<span data-ttu-id="ab0bf-127">Aufgrund der Anzahl der Überprüfungs Prüfungen, die durchgeführt werden, wird in Test-CsComputer kein einfaches ja zurückgemeldet, **der Test war erfolgreich** oder **Nein, der Test ist fehlgeschlagen**.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="ab0bf-128">Stattdessen müssen Sie die generierte HTML-Datei anzeigen, indem Sie Internet Explorer verwenden, um den Erfolg oder Misserfolg jedes Tests zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ab0bf-129">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="ab0bf-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="ab0bf-130">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsComputer möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="ab0bf-131">Der Testcomputer ist möglicherweise nicht für die Verwendung mit lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="ab0bf-132">Dies kann auftreten, wenn sich die lync Server-Dienste oder Serverrollen auf dem Computer geändert haben und das Cmdlet Enable-CsComputer nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="ab0bf-133">Führen Sie den folgenden Befehl aus, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="ab0bf-134">Die Replikation ist auf dem Testcomputer möglicherweise nicht auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="ab0bf-135">Sie können den aktuellen Replikationsstatus für einen Computer überprüfen, indem Sie das Cmdlet "Get-CsManagementStoreReplicationStatus" ausführen:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="ab0bf-136">Wenn der Replikationsstatus nicht auf dem neuesten Stand ist, können Sie die Replikation manuell erzwingen, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="ab0bf-137">Möglicherweise muss die Topologie aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-137">The topology might have to be enabled.</span></span> <span data-ttu-id="ab0bf-138">Wenn Sie die lync Server-Topologie ändern (Änderungen, die sich auf den lokalen Computer auswirken könnten), müssen Sie die neue Topologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ab0bf-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="ab0bf-139">Sie können die Topologie jederzeit aktivieren, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ab0bf-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

