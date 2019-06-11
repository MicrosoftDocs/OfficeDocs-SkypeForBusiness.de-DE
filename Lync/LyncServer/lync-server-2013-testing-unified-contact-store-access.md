---
title: 'Lync Server 2013: Testen des Zugriffs auf den einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="a7546-102">Testen des Zugriffs auf den einheitlichen Kontaktspeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7546-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7546-103">_**Letztes Änderungsdatum des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a7546-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7546-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="a7546-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a7546-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="a7546-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7546-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="a7546-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a7546-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7546-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7546-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a7546-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a7546-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="a7546-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a7546-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsUnifiedContactStore-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="a7546-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="a7546-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="a7546-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a7546-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7546-112">Description</span></span>

<span data-ttu-id="a7546-113">Der in lync Server 2013 eingeführte Unified Contact Store bietet Administratoren die Möglichkeit, die Kontakte eines Benutzers in Microsoft Exchange Server 2013 statt in lync Server zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a7546-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="a7546-114">Auf diese Weise kann der Benutzer zusätzlich zu lync 2013 auf denselben Satz Kontakte in Outlook Web Access zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a7546-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="a7546-115">(Oder Sie können Kontakte weiterhin in lync Server speichern.</span><span class="sxs-lookup"><span data-stu-id="a7546-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="a7546-116">In diesem Fall müssen Benutzer zwei getrennte Gruppen von Kontakten verwalten: eine für die Verwendung mit Outlook und Outlook Web Access und eine für die Verwendung mit lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="a7546-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="a7546-117">Sie können feststellen, ob die Kontakte eines Benutzers in den Unified Contact Store verschoben wurden, indem Sie das Cmdlet **Test-CsUnifiedContactStore** ausführen.</span><span class="sxs-lookup"><span data-stu-id="a7546-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="a7546-118">Das Cmdlet **Test-CsUnifiedContactStore** übernimmt das angegebene Benutzerkonto, stellt eine Verbindung mit dem Unified Contact Store her und versucht, einen Kontakt für den Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a7546-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="a7546-119">Wenn keine Kontakte abgerufen werden können, schlägt der Befehl zusammen mit der Meldung "Es wurden keine Kontakte für den Benutzer empfangen.</span><span class="sxs-lookup"><span data-stu-id="a7546-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="a7546-120">Überprüfen Sie, ob Kontakte für den Benutzer vorhanden sind. "</span><span class="sxs-lookup"><span data-stu-id="a7546-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="a7546-121">Beachten Sie, dass das Cmdlet **Test-CsUnifiedContactStore** fehlschlägt, wenn der Benutzer erfolgreich zum Unified Contact Store migriert wurde, aber keine Kontakte in seiner Kontaktliste hat.</span><span class="sxs-lookup"><span data-stu-id="a7546-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="a7546-122">Der angegebene Benutzer muss mindestens über einen Kontakt verfügen, damit das Cmdlet **Test-CsUnifiedContactStore** erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7546-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a7546-123">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="a7546-123">Running the test</span></span>

<span data-ttu-id="a7546-124">Die im folgenden Beispiel gezeigten Befehle legen fest, ob Kontakte für\\die Benutzer "litwareinc-kenmyer im Unified Contact Store gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="a7546-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="a7546-125">Dazu wird im ersten Befehl im Beispiel das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilenschnittstellen-Anmeldeinformationsobjekt für den Benutzer "litwareinc\\kenmyer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7546-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="a7546-126">Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Anmeldeinformationsobjekt zu erstellen und sicherzustellen, dass das **Test-CsUnifiedContactStore-** Cmdlet seine Überprüfung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="a7546-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="a7546-127">Der zweite Befehl im Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des Benutzers\\"litwareinc kenmyer, um zu ermitteln, ob seine Kontakte im Unified Contact Store zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="a7546-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a7546-128">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="a7546-128">Determining success or failure</span></span>

<span data-ttu-id="a7546-129">Wenn der Zugriff auf den Kontaktspeicher ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="a7546-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a7546-130">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a7546-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a7546-131">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="a7546-131">Result : Success</span></span>

<span data-ttu-id="a7546-132">Latenz: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="a7546-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="a7546-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="a7546-133">Error Message :</span></span>

<span data-ttu-id="a7546-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="a7546-134">Diagnosis :</span></span>

<span data-ttu-id="a7546-135">Wenn der Zugriff auf den Kontaktspeicher nicht richtig konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="a7546-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a7546-136">Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="a7546-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a7546-137">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a7546-137">domain name (FQDN).</span></span> <span data-ttu-id="a7546-138">Verwenden der standardmäßigen Registrierungs Portnummer</span><span class="sxs-lookup"><span data-stu-id="a7546-138">Using default Registrar port number.</span></span> <span data-ttu-id="a7546-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="a7546-139">Exception:</span></span>

<span data-ttu-id="a7546-140">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="a7546-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a7546-141">am</span><span class="sxs-lookup"><span data-stu-id="a7546-141">at</span></span>

<span data-ttu-id="a7546-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="a7546-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a7546-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="a7546-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a7546-144">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a7546-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a7546-145">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="a7546-145">Result : Failure</span></span>

<span data-ttu-id="a7546-146">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a7546-146">Latency : 00:00:00</span></span>

<span data-ttu-id="a7546-147">Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="a7546-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="a7546-148">hat nach einer bestimmten Zeit nicht richtig reagiert, oder</span><span class="sxs-lookup"><span data-stu-id="a7546-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="a7546-149">Fehler beim Herstellen einer Verbindung, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="a7546-149">established connection failed because connected host has</span></span>

<span data-ttu-id="a7546-150">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="a7546-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a7546-151">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="a7546-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="a7546-152">die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert</span><span class="sxs-lookup"><span data-stu-id="a7546-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="a7546-153">Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="a7546-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="a7546-154">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="a7546-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a7546-155">Diagnose</span><span class="sxs-lookup"><span data-stu-id="a7546-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a7546-156">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="a7546-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="a7546-157">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsUnifiedContactStore** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="a7546-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="a7546-158">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="a7546-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a7546-159">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="a7546-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a7546-160">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a7546-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a7546-161">Fehler beim Herstellen einer Verbindung mit dem Unified Contact Store, und der Versuch, einen Kontakt für den Benutzer abzurufen, war nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="a7546-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="a7546-162">Möglicherweise gibt es Probleme mit der Netzwerkverbindung.</span><span class="sxs-lookup"><span data-stu-id="a7546-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7546-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7546-163">See Also</span></span>


[<span data-ttu-id="a7546-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="a7546-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="a7546-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="a7546-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

