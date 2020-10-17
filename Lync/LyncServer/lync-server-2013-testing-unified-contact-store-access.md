---
title: 'Lync Server 2013: Testen des Zugriffs auf den einheitlichen Kontaktspeicher'
description: 'Lync Server 2013: Testen des Zugriffs auf den einheitlichen Kontaktspeicher.'
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
ms.openlocfilehash: 58238685133c51130c414e0d7a8cd761d0233f5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556081"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="72632-103">Testen des Zugriffs auf den einheitlichen Kontaktspeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72632-103">Testing Unified Contact Store access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72632-104">_**Letztes Änderungsstand des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="72632-104">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72632-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="72632-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="72632-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="72632-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72632-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="72632-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="72632-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72632-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72632-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="72632-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="72632-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="72632-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="72632-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsUnifiedContactStore</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="72632-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="72632-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="72632-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="72632-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72632-113">Description</span></span>

<span data-ttu-id="72632-114">Der in lync Server 2013 eingeführte einheitliche Kontaktspeicher bietet Administratoren die Möglichkeit, die Kontakte eines Benutzers in Microsoft Exchange Server 2013 anstatt in lync Server zu speichern.</span><span class="sxs-lookup"><span data-stu-id="72632-114">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="72632-115">Dadurch kann der Benutzer neben lync 2013 auf denselben Satz Kontakte in Outlook Web Access zugreifen.</span><span class="sxs-lookup"><span data-stu-id="72632-115">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="72632-116">(Oder Sie können Kontakte weiterhin in lync Server speichern.</span><span class="sxs-lookup"><span data-stu-id="72632-116">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="72632-117">In diesem Fall müssen die Benutzer zwei getrennte Kontaktsätze verwalten: eine für die Verwendung mit Outlook und Outlook Web Access und eine für die Verwendung mit lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="72632-117">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="72632-118">Sie können ermitteln, ob die Kontakte eines Benutzers in den einheitlichen Kontaktspeicher verschoben wurden, indem Sie das Cmdlet **Test-CsUnifiedContactStore** ausführen.</span><span class="sxs-lookup"><span data-stu-id="72632-118">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="72632-119">Das Cmdlet **Test-CsUnifiedContactStore** übernimmt das angegebene Benutzerkonto, stellt eine Verbindung mit dem einheitlichen Kontaktspeicher her und versucht, einen Kontakt für den Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="72632-119">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="72632-120">Wenn keine Kontakte abgerufen werden können, wird der Befehl zusammen mit der Meldung "keine Kontakte für den Benutzer empfangen" fehl.</span><span class="sxs-lookup"><span data-stu-id="72632-120">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="72632-121">Stellen Sie sicher, dass Kontakte für den Benutzer vorhanden sind.".</span><span class="sxs-lookup"><span data-stu-id="72632-121">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="72632-122">Beachten Sie, dass das **Test-CsUnifiedContactStore-** Cmdlet einen Fehler aufweist, wenn der Benutzer erfolgreich zum einheitlichen Kontaktspeicher migriert wurde, aber keine Kontakte in seiner Kontaktliste hat.</span><span class="sxs-lookup"><span data-stu-id="72632-122">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="72632-123">Der angegebene Benutzer muss mindestens über einen Kontakt verfügen, damit das Cmdlet **Test-CsUnifiedContactStore** erfolgreich abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="72632-123">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="72632-124">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="72632-124">Running the test</span></span>

<span data-ttu-id="72632-125">Die im folgenden Beispiel gezeigten Befehle bestimmen, ob Kontakte für den Benutzer litwareinc \\ kenmyer im einheitlichen Kontaktspeicher gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="72632-125">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="72632-126">Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Objekt der Befehlszeilen-Schnittstellen Anmeldeinformationen für den Benutzer litwareinc \\ kenmyer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72632-126">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="72632-127">Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Credentials-Objekt zu erstellen und sicherzustellen, dass das **Test-CsUnifiedContactStore-** Cmdlet seine Überprüfung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="72632-127">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="72632-128">Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des Benutzers litwareinc \\ kenmyer, um zu ermitteln, ob seine Kontakte im einheitlichen Kontaktspeicher gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="72632-128">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="72632-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="72632-129">Determining success or failure</span></span>

<span data-ttu-id="72632-130">Wenn der Zugriff auf den Kontaktspeicher ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="72632-130">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="72632-131">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72632-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72632-132">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="72632-132">Result : Success</span></span>

<span data-ttu-id="72632-133">Wartezeit: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="72632-133">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="72632-134">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="72632-134">Error Message :</span></span>

<span data-ttu-id="72632-135">Diagnose</span><span class="sxs-lookup"><span data-stu-id="72632-135">Diagnosis :</span></span>

<span data-ttu-id="72632-136">Wenn der Zugriff auf den Kontaktspeicher nicht ordnungsgemäß konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="72632-136">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="72632-137">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="72632-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="72632-138">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="72632-138">domain name (FQDN).</span></span> <span data-ttu-id="72632-139">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="72632-139">Using default Registrar port number.</span></span> <span data-ttu-id="72632-140">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="72632-140">Exception:</span></span>

<span data-ttu-id="72632-141">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="72632-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="72632-142">auf</span><span class="sxs-lookup"><span data-stu-id="72632-142">at</span></span>

<span data-ttu-id="72632-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="72632-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="72632-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="72632-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="72632-145">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72632-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72632-146">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="72632-146">Result : Failure</span></span>

<span data-ttu-id="72632-147">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="72632-147">Latency : 00:00:00</span></span>

<span data-ttu-id="72632-148">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="72632-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="72632-149">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="72632-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="72632-150">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="72632-150">established connection failed because connected host has</span></span>

<span data-ttu-id="72632-151">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="72632-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="72632-152">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="72632-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="72632-153">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="72632-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="72632-154">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="72632-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="72632-155">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="72632-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="72632-156">Diagnose</span><span class="sxs-lookup"><span data-stu-id="72632-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="72632-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="72632-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="72632-158">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsUnifiedContactStore** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="72632-158">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="72632-159">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="72632-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="72632-160">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72632-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="72632-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="72632-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="72632-162">Die Verbindung mit dem einheitlichen Kontaktspeicher ist fehlgeschlagen, und der Versuch, einen Kontakt für den Benutzer abzurufen, war nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="72632-162">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="72632-163">Möglicherweise treten Netzwerkverbindungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="72632-163">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72632-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72632-164">See Also</span></span>


[<span data-ttu-id="72632-165">New-csuserservicespolicy "</span><span class="sxs-lookup"><span data-stu-id="72632-165">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="72632-166">Gruppe-csuserservicespolicy "</span><span class="sxs-lookup"><span data-stu-id="72632-166">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

