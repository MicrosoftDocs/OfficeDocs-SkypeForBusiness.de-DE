---
title: 'Lync Server 2013: Testen des Replikat Diensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2784796d0eaca5d37aa841ee3db351a841c3c397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="dd4e5-102">Testen des Replikat Diensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd4e5-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd4e5-103">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="dd4e5-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd4e5-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="dd4e5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dd4e5-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="dd4e5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd4e5-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="dd4e5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dd4e5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd4e5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd4e5-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dd4e5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dd4e5-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dd4e5-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csreplica "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="dd4e5-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="dd4e5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dd4e5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd4e5-112">Description</span></span>

<span data-ttu-id="dd4e5-113">Das Cmdlet **Test-csreplica "** überprüft, ob der lync Server 2013 Replikat Dienst auf dem lokalen Computer aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="dd4e5-114">Das Cmdlet **Test-csreplica "** erfüllt folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="dd4e5-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="dd4e5-115">Überprüfen des Status des Replikations-Agents und der zentralisierten Protokollierungs-Agent-Dienste</span><span class="sxs-lookup"><span data-stu-id="dd4e5-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="dd4e5-116">Überprüfen, ob die erforderlichen Ports in der Windows-Firewall geöffnet wurden</span><span class="sxs-lookup"><span data-stu-id="dd4e5-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="dd4e5-117">sicherstellen, dass die erforderlichen Sicherheitsgruppen für Active Directory und lokale Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="dd4e5-118">Beachten Sie, dass dieses Cmdlet lokal ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="dd4e5-119">Das heißt, Sie muss auf demselben Computer ausgeführt werden, auf dem der Replikat Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="dd4e5-120">Es gibt keine Optionen zum Ausführen des **Test-csreplica "-** Cmdlets für einen Remoteserver.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dd4e5-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="dd4e5-121">Running the test</span></span>

<span data-ttu-id="dd4e5-122">Der in Beispiel 1 gezeigte Befehl testet den lync Server 2013 Replikat Dienst auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="dd4e5-123">In diesem Beispiel wird der Verbose-Parameter verwendet, um sicherzustellen, dass Informationen zum Test – einschließlich des eventuellen Fehlers oder des Erfolgs des Tests und des Standorts des Berichts, der durch den Test generiert wird – auf dem Bildschirm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="dd4e5-124">Beispiel 2 ist eine Variante des Befehls in Beispiel 1.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="dd4e5-125">In diesem Fall ist der Parameter Report enthalten, um einen Ordnerpfad und-Namen für den vom Test generierten Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="dd4e5-126">Wenn Sie keinen Berichtspfad angeben, erhält der Bericht einen automatisch generierten Namen, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="dd4e5-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="dd4e5-127">C:\\Benutzer\\Administrator. litwareinc\\APPDATA\\local\\Temp\\1\\Test-CS-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html</span><span class="sxs-lookup"><span data-stu-id="dd4e5-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dd4e5-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="dd4e5-128">Determining success or failure</span></span>

<span data-ttu-id="dd4e5-129">Abschnittstext hier einfügen.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-129">Insert section body here.</span></span>

<span data-ttu-id="dd4e5-130">Ausführlich: Erstellen einer neuen Protokolldatei "C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\Test-csreplica"-3cb066b3-dd23-411a-8932-99f01c0f940c. xml ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="dd4e5-131">Ausführlich: Erstellen einer neuen Protokolldatei "C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\Test-csreplica"-3cb066b3-dd23-411a-8932-99f01c0f940c. xml ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="dd4e5-132">Verbose: die Verarbeitung von "Test-csreplica" "wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="dd4e5-133">Ausführlich: detaillierte Ergebnisse finden Sie unter "C\\: Users\\testing\\APPDATA\\local\\Temp\\Test-csreplica"-3cb066b3-dd23-411a-8932-99f01c0f940c. xml ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="dd4e5-134">Ausführlich: Erstellen einer neuen Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="dd4e5-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="dd4e5-135">"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="dd4e5-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="dd4e5-136">d3bd0e4a083. xml ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="dd4e5-137">Ausführlich: Erstellen einer neuen Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="dd4e5-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="dd4e5-138">"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="dd4e5-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="dd4e5-139">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="dd4e5-140">Warnung: Fehler bei Test-csreplica ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="dd4e5-141">Warnung: detaillierte Ergebnisse finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="dd4e5-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="dd4e5-142">"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="dd4e5-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="dd4e5-143">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="dd4e5-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="dd4e5-144">Test-csreplica ": Fehler bei Befehlsausführung: der angeforderte Registrierungszugriff ist nicht</span><span class="sxs-lookup"><span data-stu-id="dd4e5-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="dd4e5-145">erlaubt.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-145">allowed.</span></span>

<span data-ttu-id="dd4e5-146">In der Reihe: 1 Char: 1</span><span class="sxs-lookup"><span data-stu-id="dd4e5-146">At line:1 char:1</span></span>

<span data-ttu-id="dd4e5-147">\+Test-csreplica "-Verbose</span><span class="sxs-lookup"><span data-stu-id="dd4e5-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="dd4e5-148">\+CategoryInfo: InvalidOperation: (:) \[Test-csreplica "\], Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dd4e5-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="dd4e5-149">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="dd4e5-149">Exception</span></span>

<span data-ttu-id="dd4e5-150">\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="dd4e5-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="dd4e5-151">ment. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="dd4e5-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="dd4e5-152">PS C:\\testen\\von Benutzern\></span><span class="sxs-lookup"><span data-stu-id="dd4e5-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="dd4e5-153">PS C:\\Benutzer\\testen\> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="dd4e5-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="dd4e5-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="dd4e5-154">icrosoft.com"</span></span>

<span data-ttu-id="dd4e5-155">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="dd4e5-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="dd4e5-156">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="dd4e5-156">domain name (FQDN).</span></span> <span data-ttu-id="dd4e5-157">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-157">Using default Registrar port number.</span></span> <span data-ttu-id="dd4e5-158">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="dd4e5-158">Exception:</span></span>

<span data-ttu-id="dd4e5-159">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="dd4e5-160">auf</span><span class="sxs-lookup"><span data-stu-id="dd4e5-160">at</span></span>

<span data-ttu-id="dd4e5-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="dd4e5-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="dd4e5-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="dd4e5-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="dd4e5-163">Test-CsUcwaConference: Es ist kein Testbenutzer zugewiesen</span><span class="sxs-lookup"><span data-stu-id="dd4e5-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="dd4e5-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="dd4e5-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="dd4e5-165">Überprüfen Sie die Konfiguration des Testbenutzers.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-165">Verify test user configuration.</span></span>

<span data-ttu-id="dd4e5-166">In der Reihe: 1 Char: 1</span><span class="sxs-lookup"><span data-stu-id="dd4e5-166">At line:1 char:1</span></span>

<span data-ttu-id="dd4e5-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="dd4e5-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="dd4e5-168">\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="dd4e5-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="dd4e5-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="dd4e5-169">, InvalidOperationException</span></span>

<span data-ttu-id="dd4e5-170">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. Synth</span><span class="sxs-lookup"><span data-stu-id="dd4e5-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="dd4e5-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="dd4e5-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dd4e5-172">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="dd4e5-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="dd4e5-173">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csreplica "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="dd4e5-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="dd4e5-174">Möglicherweise liegt ein größeres Problem mit dem Replikations-Agent und den zentralisierten Protokollierungs-Agent-Diensten vor.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="dd4e5-175">Die erforderlichen Ports sind möglicherweise nicht in der Windows-Firewall geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="dd4e5-176">Die erforderlichen Active Directory und lokale Computersicherheitsgruppen sind möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dd4e5-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

