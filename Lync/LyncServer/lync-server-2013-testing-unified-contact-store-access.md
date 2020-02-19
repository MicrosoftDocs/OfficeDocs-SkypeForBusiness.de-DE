---
title: 'Lync Server 2013: Testen des Zugriffs auf den einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6022d7651a99c2165961ed8cb8852048c10779ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="aa0d2-102">Testen des Zugriffs auf den einheitlichen Kontaktspeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa0d2-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0d2-103">_**Letztes Änderungsstand des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="aa0d2-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0d2-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="aa0d2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="aa0d2-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="aa0d2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0d2-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="aa0d2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="aa0d2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa0d2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0d2-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="aa0d2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="aa0d2-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="aa0d2-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsUnifiedContactStore</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="aa0d2-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="aa0d2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="aa0d2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa0d2-112">Description</span></span>

<span data-ttu-id="aa0d2-113">Der in lync Server 2013 eingeführte einheitliche Kontaktspeicher bietet Administratoren die Möglichkeit, die Kontakte eines Benutzers in Microsoft Exchange Server 2013 anstatt in lync Server zu speichern.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="aa0d2-114">Dadurch kann der Benutzer neben lync 2013 auf denselben Satz Kontakte in Outlook Web Access zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="aa0d2-115">(Oder Sie können Kontakte weiterhin in lync Server speichern.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="aa0d2-116">In diesem Fall müssen die Benutzer zwei getrennte Kontaktsätze verwalten: eine für die Verwendung mit Outlook und Outlook Web Access und eine für die Verwendung mit lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="aa0d2-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="aa0d2-117">Sie können ermitteln, ob die Kontakte eines Benutzers in den einheitlichen Kontaktspeicher verschoben wurden, indem Sie das Cmdlet **Test-CsUnifiedContactStore** ausführen.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="aa0d2-118">Das Cmdlet **Test-CsUnifiedContactStore** übernimmt das angegebene Benutzerkonto, stellt eine Verbindung mit dem einheitlichen Kontaktspeicher her und versucht, einen Kontakt für den Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="aa0d2-119">Wenn keine Kontakte abgerufen werden können, wird der Befehl zusammen mit der Meldung "keine Kontakte für den Benutzer empfangen" fehl.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="aa0d2-120">Stellen Sie sicher, dass Kontakte für den Benutzer vorhanden sind.".</span><span class="sxs-lookup"><span data-stu-id="aa0d2-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="aa0d2-121">Beachten Sie, dass das **Test-CsUnifiedContactStore-** Cmdlet einen Fehler aufweist, wenn der Benutzer erfolgreich zum einheitlichen Kontaktspeicher migriert wurde, aber keine Kontakte in seiner Kontaktliste hat.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="aa0d2-122">Der angegebene Benutzer muss mindestens über einen Kontakt verfügen, damit das Cmdlet **Test-CsUnifiedContactStore** erfolgreich abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="aa0d2-123">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="aa0d2-123">Running the test</span></span>

<span data-ttu-id="aa0d2-124">Die im folgenden Beispiel gezeigten Befehle bestimmen, ob Kontakte für den\\Benutzer litwareinc kenmyer im einheitlichen Kontaktspeicher gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="aa0d2-125">Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Objekt der Befehlszeilen-Schnittstellen Anmeldeinformationen für den Benutzer litwareinc\\kenmyer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="aa0d2-126">Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Credentials-Objekt zu erstellen und sicherzustellen, dass das **Test-CsUnifiedContactStore-** Cmdlet seine Überprüfung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="aa0d2-127">Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des\\Benutzers litwareinc kenmyer, um zu ermitteln, ob seine Kontakte im einheitlichen Kontaktspeicher gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="aa0d2-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="aa0d2-128">Determining success or failure</span></span>

<span data-ttu-id="aa0d2-129">Wenn der Zugriff auf den Kontaktspeicher ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="aa0d2-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="aa0d2-130">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aa0d2-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aa0d2-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="aa0d2-131">Result : Success</span></span>

<span data-ttu-id="aa0d2-132">Wartezeit: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="aa0d2-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="aa0d2-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="aa0d2-133">Error Message :</span></span>

<span data-ttu-id="aa0d2-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="aa0d2-134">Diagnosis :</span></span>

<span data-ttu-id="aa0d2-135">Wenn der Zugriff auf den Kontaktspeicher nicht ordnungsgemäß konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="aa0d2-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="aa0d2-136">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="aa0d2-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="aa0d2-137">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="aa0d2-137">domain name (FQDN).</span></span> <span data-ttu-id="aa0d2-138">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-138">Using default Registrar port number.</span></span> <span data-ttu-id="aa0d2-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="aa0d2-139">Exception:</span></span>

<span data-ttu-id="aa0d2-140">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="aa0d2-141">auf</span><span class="sxs-lookup"><span data-stu-id="aa0d2-141">at</span></span>

<span data-ttu-id="aa0d2-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="aa0d2-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="aa0d2-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="aa0d2-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="aa0d2-144">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aa0d2-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aa0d2-145">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="aa0d2-145">Result : Failure</span></span>

<span data-ttu-id="aa0d2-146">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="aa0d2-146">Latency : 00:00:00</span></span>

<span data-ttu-id="aa0d2-147">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="aa0d2-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="aa0d2-148">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="aa0d2-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="aa0d2-149">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="aa0d2-149">established connection failed because connected host has</span></span>

<span data-ttu-id="aa0d2-150">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="aa0d2-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="aa0d2-151">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="aa0d2-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="aa0d2-152">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="aa0d2-153">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="aa0d2-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="aa0d2-154">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="aa0d2-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="aa0d2-155">Diagnose</span><span class="sxs-lookup"><span data-stu-id="aa0d2-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="aa0d2-156">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="aa0d2-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="aa0d2-157">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsUnifiedContactStore** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="aa0d2-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="aa0d2-158">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="aa0d2-159">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="aa0d2-160">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="aa0d2-161">Die Verbindung mit dem einheitlichen Kontaktspeicher ist fehlgeschlagen, und der Versuch, einen Kontakt für den Benutzer abzurufen, war nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="aa0d2-162">Möglicherweise treten Netzwerkverbindungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="aa0d2-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa0d2-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa0d2-163">See Also</span></span>


[<span data-ttu-id="aa0d2-164">New-csuserservicespolicy "</span><span class="sxs-lookup"><span data-stu-id="aa0d2-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="aa0d2-165">Gruppe-csuserservicespolicy "</span><span class="sxs-lookup"><span data-stu-id="aa0d2-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

