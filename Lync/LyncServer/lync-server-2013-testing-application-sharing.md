---
title: 'Lync Server 2013: Testen der Anwendungsfreigabe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="5995f-102">Testen der Anwendungsfreigabe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5995f-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5995f-103">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="5995f-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5995f-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="5995f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5995f-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="5995f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5995f-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="5995f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5995f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5995f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5995f-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5995f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5995f-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="5995f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5995f-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsASConference-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="5995f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="5995f-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="5995f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5995f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5995f-112">Description</span></span>

<span data-ttu-id="5995f-113">Das Cmdlet **Test-CsASConference** überprüft, ob ein paar Testbenutzer an einer Onlinekonferenz teilnehmen können, die die Anwendungsfreigabe umfasst.</span><span class="sxs-lookup"><span data-stu-id="5995f-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="5995f-114">Dazu registriert das Cmdlet die beiden Benutzer mit lync Server 2013 und verwendet dann eines der Benutzerkonten, um eine neue Konferenz zu erstellen, die die Freigabe von Anwendungen umfasst.</span><span class="sxs-lookup"><span data-stu-id="5995f-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="5995f-115">Das Cmdlet überprüft dann, ob der zweite Benutzer an dieser Konferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="5995f-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5995f-116">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="5995f-116">Running the test</span></span>

<span data-ttu-id="5995f-117">Der in Beispiel 1 gezeigte Befehl überprüft, ob eine Anwendungsfreigabe Konferenz im Pool ATL-CS-001.litwareinc.com durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5995f-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5995f-118">Bei diesem Befehl wird davon ausgegangen, dass Sie ein paar Testbenutzer für den angegebenen Pool konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="5995f-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="5995f-119">Wenn keine solchen Testbenutzer vorhanden sind, wird der Befehl nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5995f-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="5995f-120">Beispiel 2 testet die Möglichkeit des Join-Startprogrammdiensts, an einer Konferenz zur Anwendungsfreigabe im Pool ATL-CS-001.litwareinc.com teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="5995f-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5995f-121">Beachten Sie, dass dieser Befehl nur den Dienst selbst testet; Sie benötigen keine mobilen Geräte, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5995f-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="5995f-122">Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines Paars von Benutzern\\("litwareinc Pilar\\und" litwareinc kenmyer), sich bei lync Server 2013 anzumelden und dann eine Konferenz zur Anwendungsfreigabe durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5995f-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="5995f-123">Dazu wird im ersten Befehl im Beispiel das Cmdlet Get-Credential verwendet, um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="5995f-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="5995f-124">(Da der Anmeldename, "litwareinc\\Pilar, als Parameter hinzugefügt wurde, erfordert das Dialogfeld Windows PowerShell-Anmeldeinformationen nur, dass der Administrator das Kennwort für das Pilar Ackerman-Konto eingegeben hat.) Das resultierende Anmeldeinformationsobjekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5995f-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="5995f-125">Der zweite Befehl führt dieselbe Aufgabe aus, wobei dieses Mal ein Anmeldeinformationsobjekt für das Ken Myers-Konto zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5995f-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="5995f-126">Wenn die Anmeldeinformationsobjekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Konferenz zur Anwendungsfreigabe durchführen können.</span><span class="sxs-lookup"><span data-stu-id="5995f-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="5995f-127">Um diese Aufgabe auszuführen, wird das Cmdlet **Test-CsASConference** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (der FQDN des registrierungspools); SenderSipAddress (die SIP-Adresse des ersten Testbenutzers); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für denselben Benutzer enthält); ReceiverSipAddress (die SIP-Adresse des anderen Testbenutzers); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).</span><span class="sxs-lookup"><span data-stu-id="5995f-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5995f-128">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="5995f-128">Determining success or failure</span></span>

<span data-ttu-id="5995f-129">Wenn die Anwendungsfreigabe ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="5995f-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5995f-130">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5995f-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5995f-131">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="5995f-131">Result : Success</span></span>

<span data-ttu-id="5995f-132">Latenz: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="5995f-132">Latency : 00:00:01</span></span>

<span data-ttu-id="5995f-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="5995f-133">Error Message :</span></span>

<span data-ttu-id="5995f-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="5995f-134">Diagnosis :</span></span>

<span data-ttu-id="5995f-135">Wenn die angegebenen Benutzer keine Anwendungen freigeben können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="5995f-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5995f-136">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5995f-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5995f-137">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="5995f-137">Result : Failure</span></span>

<span data-ttu-id="5995f-138">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5995f-138">Latency : 00:00:00</span></span>

<span data-ttu-id="5995f-139">Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="5995f-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5995f-140">hat nach einer bestimmten Zeit nicht richtig reagiert, oder</span><span class="sxs-lookup"><span data-stu-id="5995f-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5995f-141">Fehler beim Herstellen einer Verbindung, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="5995f-141">established connection failed because connected host has</span></span>

<span data-ttu-id="5995f-142">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5995f-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5995f-143">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="5995f-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5995f-144">die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert</span><span class="sxs-lookup"><span data-stu-id="5995f-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5995f-145">Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="5995f-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5995f-146">Fehler beim Antworten 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5995f-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5995f-147">Diagnose</span><span class="sxs-lookup"><span data-stu-id="5995f-147">Diagnosis :</span></span>

<span data-ttu-id="5995f-148">Die vorherige Ausgabe enthält beispielsweise die Notiz "die verbundene Partei hat nicht richtig reagiert", die in der Regel auf ein Problem mit dem Edgeserver hindeutet.</span><span class="sxs-lookup"><span data-stu-id="5995f-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5995f-149">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="5995f-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="5995f-150">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsASConference** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="5995f-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="5995f-151">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="5995f-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5995f-152">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="5995f-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5995f-153">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="5995f-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5995f-154">Dieser Befehl schlägt fehl, wenn den Testbenutzern eine konferenzrichtlinie zugewiesen wurde, die verhindert, dass Sie die Anwendungsfreigabe verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5995f-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="5995f-155">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5995f-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5995f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5995f-156">See Also</span></span>


[<span data-ttu-id="5995f-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="5995f-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="5995f-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="5995f-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

