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
ms.openlocfilehash: e30d0b8c0e570605c8c6556d42224a205741a821
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503962"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="344de-102">Testen des Replikat Diensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="344de-102">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="344de-103">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="344de-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="344de-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="344de-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="344de-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="344de-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344de-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="344de-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="344de-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="344de-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344de-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="344de-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="344de-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="344de-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="344de-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csreplica "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="344de-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="344de-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="344de-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="344de-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="344de-112">Description</span></span>

<span data-ttu-id="344de-113">Das Cmdlet **Test-csreplica "** überprüft, ob der lync Server 2013 Replikat Dienst auf dem lokalen Computer aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="344de-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="344de-114">Das Cmdlet **Test-csreplica "** erfüllt folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="344de-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="344de-115">Überprüfen des Status des Replikations-Agents und der zentralisierten Protokollierungs-Agent-Dienste</span><span class="sxs-lookup"><span data-stu-id="344de-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="344de-116">Überprüfen, ob die erforderlichen Ports in der Windows-Firewall geöffnet wurden</span><span class="sxs-lookup"><span data-stu-id="344de-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="344de-117">sicherstellen, dass die erforderlichen Sicherheitsgruppen für Active Directory und lokale Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="344de-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="344de-118">Beachten Sie, dass dieses Cmdlet lokal ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="344de-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="344de-119">Das heißt, Sie muss auf demselben Computer ausgeführt werden, auf dem der Replikat Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="344de-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="344de-120">Es gibt keine Optionen zum Ausführen des **Test-csreplica "-** Cmdlets für einen Remoteserver.</span><span class="sxs-lookup"><span data-stu-id="344de-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="344de-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="344de-121">Running the test</span></span>

<span data-ttu-id="344de-122">Der in Beispiel 1 gezeigte Befehl testet den lync Server 2013 Replikat Dienst auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="344de-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="344de-123">In diesem Beispiel wird der Verbose-Parameter verwendet, um sicherzustellen, dass Informationen zum Test – einschließlich des eventuellen Fehlers oder des Erfolgs des Tests und des Standorts des Berichts, der durch den Test generiert wird – auf dem Bildschirm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="344de-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="344de-124">Beispiel 2 ist eine Variante des Befehls in Beispiel 1.</span><span class="sxs-lookup"><span data-stu-id="344de-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="344de-125">In diesem Fall ist der Parameter Report enthalten, um einen Ordnerpfad und-Namen für den vom Test generierten Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="344de-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="344de-126">Wenn Sie keinen Berichtspfad angeben, erhält der Bericht einen automatisch generierten Namen, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="344de-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="344de-127">C: \\ Benutzer \\ Administrator. litwareinc \\ AppData \\ lokale \\ Temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="344de-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="344de-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="344de-128">Determining success or failure</span></span>

<span data-ttu-id="344de-129">Abschnittstext hier einfügen.</span><span class="sxs-lookup"><span data-stu-id="344de-129">Insert section body here.</span></span>

<span data-ttu-id="344de-130">Ausführlich: Erstellen einer neuen Protokolldatei "C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="344de-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="344de-131">Ausführlich: Erstellen einer neuen Protokolldatei "C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="344de-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="344de-132">Verbose: die Verarbeitung von "Test-csreplica" "wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="344de-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="344de-133">Ausführlich: detaillierte Ergebnisse finden Sie unter "C: \\ Users \\ testing \\ AppData \\ local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="344de-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="344de-134">Ausführlich: Erstellen einer neuen Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="344de-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="344de-135">"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="344de-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="344de-136">d3bd0e4a083.xml ".</span><span class="sxs-lookup"><span data-stu-id="344de-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="344de-137">Ausführlich: Erstellen einer neuen Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="344de-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="344de-138">"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="344de-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="344de-139">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="344de-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="344de-140">Warnung: Test-CsReplica fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="344de-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="344de-141">Warnung: detaillierte Ergebnisse finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="344de-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="344de-142">"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="344de-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="344de-143">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="344de-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="344de-144">Test-CsReplica: Fehler bei Befehlsausführung: der angeforderte Registrierungszugriff ist nicht</span><span class="sxs-lookup"><span data-stu-id="344de-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="344de-145">erlaubt.</span><span class="sxs-lookup"><span data-stu-id="344de-145">allowed.</span></span>

<span data-ttu-id="344de-146">In der Reihe: 1 Char: 1</span><span class="sxs-lookup"><span data-stu-id="344de-146">At line:1 char:1</span></span>

<span data-ttu-id="344de-147">\+ Test-CsReplica-ausführlich</span><span class="sxs-lookup"><span data-stu-id="344de-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="344de-148">\+ CategoryInfo: InvalidOperation: (:) \[ Test-csreplica " \] , Sicherheit</span><span class="sxs-lookup"><span data-stu-id="344de-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="344de-149">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="344de-149">Exception</span></span>

<span data-ttu-id="344de-150">\+ FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="344de-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="344de-151">ment. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="344de-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="344de-152">PS C: \\ Testen von Benutzern \\\></span><span class="sxs-lookup"><span data-stu-id="344de-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="344de-153">PS C: \\ Benutzer \\ Testen \> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="344de-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="344de-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="344de-154">icrosoft.com"</span></span>

<span data-ttu-id="344de-155">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="344de-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="344de-156">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="344de-156">domain name (FQDN).</span></span> <span data-ttu-id="344de-157">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="344de-157">Using default Registrar port number.</span></span> <span data-ttu-id="344de-158">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="344de-158">Exception:</span></span>

<span data-ttu-id="344de-159">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="344de-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="344de-160">auf</span><span class="sxs-lookup"><span data-stu-id="344de-160">at</span></span>

<span data-ttu-id="344de-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="344de-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="344de-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="344de-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="344de-163">Test-CsUcwaConference: kein Testbenutzer zugewiesen</span><span class="sxs-lookup"><span data-stu-id="344de-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="344de-164">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="344de-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="344de-165">Überprüfen Sie die Konfiguration des Testbenutzers.</span><span class="sxs-lookup"><span data-stu-id="344de-165">Verify test user configuration.</span></span>

<span data-ttu-id="344de-166">In der Reihe: 1 Char: 1</span><span class="sxs-lookup"><span data-stu-id="344de-166">At line:1 char:1</span></span>

<span data-ttu-id="344de-167">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="344de-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="344de-168">\+ CategoryInfo: ResourceUnavailable: (:) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="344de-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="344de-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="344de-169">, InvalidOperationException</span></span>

<span data-ttu-id="344de-170">\+ FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. Synth</span><span class="sxs-lookup"><span data-stu-id="344de-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="344de-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="344de-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="344de-172">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="344de-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="344de-173">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csreplica "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="344de-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="344de-174">Möglicherweise liegt ein größeres Problem mit dem Replikations-Agent und den zentralisierten Protokollierungs-Agent-Diensten vor.</span><span class="sxs-lookup"><span data-stu-id="344de-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="344de-175">Die erforderlichen Ports sind möglicherweise nicht in der Windows-Firewall geöffnet.</span><span class="sxs-lookup"><span data-stu-id="344de-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="344de-176">Die erforderlichen Active Directory und lokale Computersicherheitsgruppen sind möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="344de-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

