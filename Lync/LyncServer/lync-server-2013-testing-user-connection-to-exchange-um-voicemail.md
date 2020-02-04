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
ms.openlocfilehash: c533781fedc3bf3d6266bae80e5c59cacbec4874
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="806b5-102">Testen der Benutzerverbindung mit Exchange um Voicemail in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="806b5-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="806b5-103">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="806b5-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="806b5-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="806b5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="806b5-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="806b5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806b5-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="806b5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="806b5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="806b5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806b5-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="806b5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="806b5-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="806b5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="806b5-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsExUMVoiceMail-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="806b5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="806b5-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="806b5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="806b5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="806b5-112">Description</span></span>

<span data-ttu-id="806b5-113">Mit dem Cmdlet **Test-CsExUMVoiceMail** können Administratoren überprüfen, ob ein Benutzer auf den Microsoft Exchange Server 2013 Unified Messaging-Dienst zugreifen und ihn verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="806b5-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="806b5-114">Zu diesem Zweck stellt das Cmdlet eine Verbindung mit dem Unified Messaging-Dienst her und verlässt eine Voicemail im angegebenen Postfach.</span><span class="sxs-lookup"><span data-stu-id="806b5-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="806b5-115">Dies kann eine vom System bereitgestellte Voicemail sein, oder es kann sich um eine benutzerdefinierte Nachricht handeln. WAV-Datei, die Sie selbst aufgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="806b5-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="806b5-116">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="806b5-116">Running the test</span></span>

<span data-ttu-id="806b5-117">Im folgenden Beispiel wird die Exchange Unified Messaging-Voicemail-Konnektivität für den Pool ATL-CS-001.litwareinc.com getestet.</span><span class="sxs-lookup"><span data-stu-id="806b5-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="806b5-118">Dieser Befehl funktioniert nur, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="806b5-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="806b5-119">Wenn ja, bestimmt der Befehl, ob der erste Testbenutzer Unified Messaging-Voicemail verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="806b5-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="806b5-120">Wenn Testbenutzer nicht für den Pool konfiguriert wurden, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="806b5-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="806b5-121">Die im nächsten Beispiel gezeigten Befehle testen die Exchange Unified Messaging-Voicemail-Konnektivität für\\den Benutzer "litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="806b5-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="806b5-122">Dazu wird im ersten Befehl im Beispiel das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilenschnittstellen-Anmeldeinformationsobjekt für den Benutzer "litwareinc\\kenmyer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="806b5-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="806b5-123">Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Anmeldeinformationsobjekt zu erstellen und sicherzustellen, dass das **Test-CsExUMVoiceMail-** Cmdlet seine Überprüfung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="806b5-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="806b5-124">Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des\\Benutzers "litwareinc kenmyer, um zu ermitteln, ob dieser Benutzer eine Verbindung mit der Exchange Unified Messaging-Voicemail herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="806b5-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="806b5-125">Der im nächsten Beispiel angezeigte Befehl ist eine Variation des Befehls, die in Beispiel 1 gezeigt wird. in diesem Fall ist der OutLoggerVariable-Parameter enthalten, um ein detailliertes Protokoll aller Schritte zu generieren, die vom **Test-CsExUMVoiceMail** cmdletand den Erfolg oder Misserfolg jedes dieser Schritte durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="806b5-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="806b5-126">Dazu wird der OutLoggerVariable-Parameter neben dem Parameterwert ExumText hinzugefügt. Dies bewirkt, dass detaillierte Protokollierungsinformationen in einer Variablen mit dem Namen $ExumTest gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="806b5-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="806b5-127">Im letzten Befehl im Beispiel wird die ToXml ()-Methode verwendet, um die Protokollinformationen in das XML-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="806b5-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="806b5-128">Diese XML-Daten werden dann mit dem Cmdlet "Out-File"\\in\\eine Datei mit dem Namen C: Logs VoicemailTest. XML geschrieben.</span><span class="sxs-lookup"><span data-stu-id="806b5-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="806b5-129">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="806b5-129">Determining success or failure</span></span>

<span data-ttu-id="806b5-130">Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="806b5-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="806b5-131">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="806b5-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="806b5-132">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="806b5-132">Result : Success</span></span>

<span data-ttu-id="806b5-133">Latenz: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="806b5-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="806b5-134">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="806b5-134">Error Message :</span></span>

<span data-ttu-id="806b5-135">Diagnose</span><span class="sxs-lookup"><span data-stu-id="806b5-135">Diagnosis :</span></span>

<span data-ttu-id="806b5-136">Wenn der angegebene Benutzer keine Verbindung mit Voicemail herstellen kann, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="806b5-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="806b5-137">Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="806b5-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="806b5-138">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="806b5-138">domain name (FQDN).</span></span> <span data-ttu-id="806b5-139">Verwenden der standardmäßigen Registrierungs Portnummer</span><span class="sxs-lookup"><span data-stu-id="806b5-139">Using default Registrar port number.</span></span> <span data-ttu-id="806b5-140">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="806b5-140">Exception:</span></span>

<span data-ttu-id="806b5-141">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="806b5-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="806b5-142">am</span><span class="sxs-lookup"><span data-stu-id="806b5-142">at</span></span>

<span data-ttu-id="806b5-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="806b5-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="806b5-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="806b5-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="806b5-145">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="806b5-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="806b5-146">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="806b5-146">Result : Failure</span></span>

<span data-ttu-id="806b5-147">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="806b5-147">Latency : 00:00:00</span></span>

<span data-ttu-id="806b5-148">Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="806b5-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="806b5-149">hat nach einer bestimmten Zeit nicht richtig reagiert, oder</span><span class="sxs-lookup"><span data-stu-id="806b5-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="806b5-150">Fehler beim Herstellen einer Verbindung, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="806b5-150">established connection failed because connected host has</span></span>

<span data-ttu-id="806b5-151">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="806b5-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="806b5-152">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="806b5-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="806b5-153">die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert</span><span class="sxs-lookup"><span data-stu-id="806b5-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="806b5-154">Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="806b5-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="806b5-155">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="806b5-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="806b5-156">Diagnose</span><span class="sxs-lookup"><span data-stu-id="806b5-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="806b5-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="806b5-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="806b5-158">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsExUMVoiceMail** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="806b5-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="806b5-159">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="806b5-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="806b5-160">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="806b5-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="806b5-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="806b5-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="806b5-162">Dieser Befehl schlägt fehl, wenn der Exchange-Server falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="806b5-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="806b5-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="806b5-163">See Also</span></span>


[<span data-ttu-id="806b5-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="806b5-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

