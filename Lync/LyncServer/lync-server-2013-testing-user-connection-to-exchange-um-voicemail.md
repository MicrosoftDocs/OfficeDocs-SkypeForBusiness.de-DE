---
title: 'Lync Server 2013: Testen der Benutzerverbindung mit Exchange um Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa3ad3f51d1342ac99d3c58be66931ba0770bf6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="379cd-102">Testen der Benutzerverbindung mit Exchange um Voicemail in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="379cd-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="379cd-103">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="379cd-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="379cd-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="379cd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="379cd-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="379cd-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379cd-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="379cd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="379cd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="379cd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379cd-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="379cd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="379cd-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="379cd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="379cd-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csexumvoicemail "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="379cd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="379cd-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="379cd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="379cd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="379cd-112">Description</span></span>

<span data-ttu-id="379cd-113">Mit dem Cmdlet **Test-csexumvoicemail "** können Administratoren überprüfen, ob ein Benutzer auf den Microsoft Exchange Server 2013 Unified Messaging-Dienst zugreifen und diese verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="379cd-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="379cd-114">Hierzu stellt das Cmdlet eine Verbindung mit dem Unified Messaging-Dienst her und hinterlässt eine Voicemail im angegebenen Postfach.</span><span class="sxs-lookup"><span data-stu-id="379cd-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="379cd-115">Dies kann eine vom System bereitgestellte Voicemail sein, oder es kann eine benutzerdefinierte sein. WAV-Datei, die Sie selbst aufgezeichnet haben.</span><span class="sxs-lookup"><span data-stu-id="379cd-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="379cd-116">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="379cd-116">Running the test</span></span>

<span data-ttu-id="379cd-117">Im folgenden Beispiel wird die Exchange Unified Messaging-voicemailverbindung für den Pool ATL-CS-001.litwareinc.com getestet.</span><span class="sxs-lookup"><span data-stu-id="379cd-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="379cd-118">Dieser Befehl ist nur möglich, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="379cd-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="379cd-119">Wenn dies der Fall ist, wird mit dem Befehl ermittelt, ob der erste Testbenutzer Unified Messaging-Voicemail verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="379cd-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="379cd-120">Wenn Testbenutzer nicht für den Pool konfiguriert wurden, tritt beim Ausführen des Befehls ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="379cd-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="379cd-121">Die im nächsten Beispiel gezeigten Befehle testen die Exchange Unified Messaging-Voicemail-Konnektivität für\\den Benutzer litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="379cd-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="379cd-122">Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Objekt der Befehlszeilen-Schnittstellen Anmeldeinformationen für den Benutzer litwareinc\\kenmyer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="379cd-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="379cd-123">Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Credentials-Objekt zu erstellen und sicherzustellen, dass das **Test-csexumvoicemail "-** Cmdlet seine Überprüfung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="379cd-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="379cd-124">Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des\\Benutzers litwareinc kenmyer, um zu bestimmen, ob dieser Benutzer eine Verbindung mit der Exchange Unified Messaging-Voicemail herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="379cd-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="379cd-125">Der Befehl im nächsten Beispiel ist eine Variation des Befehls in Beispiel 1 dargestellt; in diesem Fall ist der OutLoggerVariable-Parameter enthalten, um ein detailliertes Protokoll aller Schritte zu generieren, die von der **Test-csexumvoicemail "** ausgeführt werden, um den Erfolg oder Misserfolg jedes dieser Schritte cmdletand.</span><span class="sxs-lookup"><span data-stu-id="379cd-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="379cd-126">Hierzu wird der Parameter OutLoggerVariable neben dem Parameterwert ExumText hinzugefügt. Dadurch werden ausführliche Protokollierungsinformationen in einer Variablen namens $ExumTest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="379cd-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="379cd-127">Im letzten Befehl im Beispiel wird die ToXml ()-Methode verwendet, um die Protokollinformationen in das XML-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="379cd-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="379cd-128">Diese XML-Daten werden dann mithilfe des Cmdlets Out-File in\\eine\\Datei mit dem Namen C: Logs VoicemailTest. XML geschrieben.</span><span class="sxs-lookup"><span data-stu-id="379cd-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="379cd-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="379cd-129">Determining success or failure</span></span>

<span data-ttu-id="379cd-130">Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert wurde:</span><span class="sxs-lookup"><span data-stu-id="379cd-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="379cd-131">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="379cd-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="379cd-132">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="379cd-132">Result : Success</span></span>

<span data-ttu-id="379cd-133">Wartezeit: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="379cd-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="379cd-134">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="379cd-134">Error Message :</span></span>

<span data-ttu-id="379cd-135">Diagnose</span><span class="sxs-lookup"><span data-stu-id="379cd-135">Diagnosis :</span></span>

<span data-ttu-id="379cd-136">Wenn der angegebene Benutzer keine Verbindung mit der Voicemail herstellen kann, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="379cd-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="379cd-137">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="379cd-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="379cd-138">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="379cd-138">domain name (FQDN).</span></span> <span data-ttu-id="379cd-139">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="379cd-139">Using default Registrar port number.</span></span> <span data-ttu-id="379cd-140">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="379cd-140">Exception:</span></span>

<span data-ttu-id="379cd-141">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="379cd-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="379cd-142">auf</span><span class="sxs-lookup"><span data-stu-id="379cd-142">at</span></span>

<span data-ttu-id="379cd-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="379cd-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="379cd-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="379cd-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="379cd-145">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="379cd-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="379cd-146">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="379cd-146">Result : Failure</span></span>

<span data-ttu-id="379cd-147">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="379cd-147">Latency : 00:00:00</span></span>

<span data-ttu-id="379cd-148">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="379cd-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="379cd-149">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="379cd-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="379cd-150">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="379cd-150">established connection failed because connected host has</span></span>

<span data-ttu-id="379cd-151">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="379cd-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="379cd-152">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="379cd-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="379cd-153">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="379cd-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="379cd-154">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="379cd-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="379cd-155">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="379cd-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="379cd-156">Diagnose</span><span class="sxs-lookup"><span data-stu-id="379cd-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="379cd-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="379cd-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="379cd-158">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csexumvoicemail "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="379cd-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="379cd-159">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="379cd-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="379cd-160">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="379cd-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="379cd-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="379cd-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="379cd-162">Dieser Befehl schlägt fehl, wenn der Exchange Server falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="379cd-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="379cd-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="379cd-163">See Also</span></span>


[<span data-ttu-id="379cd-164">Test-csexumconnectivity "</span><span class="sxs-lookup"><span data-stu-id="379cd-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

