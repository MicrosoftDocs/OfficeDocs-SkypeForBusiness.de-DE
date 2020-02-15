---
title: 'Lync Server 2013: Testen der Freigabe in Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0094c0b58281027f24d4cd902a4e0813c7e45f96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="3d7f8-102">Testen der Freigabe in Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d7f8-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d7f8-103">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d7f8-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d7f8-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="3d7f8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3d7f8-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="3d7f8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d7f8-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="3d7f8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3d7f8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d7f8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d7f8-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3d7f8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3d7f8-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3d7f8-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csdataconference "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="3d7f8-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="3d7f8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3d7f8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d7f8-112">Description</span></span>

<span data-ttu-id="3d7f8-113">In lync Server 2013 handelt es sich bei einer Datenkonferenz um eine Konferenz, in der kollaborative Aktivitäten wie Whiteboards oder Anmerkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="3d7f8-114">Mit dem Cmdlet **Test-csdataconference "** können Sie überprüfen, ob ein Benutzer Paar an einer Datenkonferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3d7f8-115">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="3d7f8-115">Running the test</span></span>

<span data-ttu-id="3d7f8-p103">Der Befehl in Beispiel 1 prüft, ob in Pool "atl-cs-001.litwareinc.com" eine Datenkonferenz stattfinden kann. Dieser Befehl setzt voraus, dass Sie ein Testbenutzerpaar für den angegebenen Pool konfiguriert haben. Wenn keine Testbenutzer vorhanden sind, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="3d7f8-119">Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (\\litwareinc Pilar und\\litwareinc kenmyer), sich bei lync Server 2013 anzumelden und dann eine Datenkonferenz durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="3d7f8-120">Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="3d7f8-121">(Da der Anmeldename litwareinc\\Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Pilar Ackerman-Konto angeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="3d7f8-122">Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="3d7f8-123">Wenn die Credential-Objekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Datenkonferenz durchführen können.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="3d7f8-124">Zur Ausführung dieser Aufgabe wird das Cmdlet **Test-csdataconference "** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); "Sendersipaddress" (die SIP-Adresse für den ersten Testbenutzer); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); "Receiversipaddress" (die SIP-Adresse für den anderen Testbenutzer); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).</span><span class="sxs-lookup"><span data-stu-id="3d7f8-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3d7f8-125">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="3d7f8-125">Determining success or failure</span></span>

<span data-ttu-id="3d7f8-126">Wenn die Datenkonferenz ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="3d7f8-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3d7f8-127">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d7f8-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d7f8-128">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="3d7f8-128">Result : Success</span></span>

<span data-ttu-id="3d7f8-129">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3d7f8-129">Latency : 00:00:00</span></span>

<span data-ttu-id="3d7f8-130">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="3d7f8-130">Error Message :</span></span>

<span data-ttu-id="3d7f8-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3d7f8-131">Diagnosis :</span></span>

<span data-ttu-id="3d7f8-132">Wenn die angegebenen Benutzer keine Datenfreigabe verwenden können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="3d7f8-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3d7f8-133">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d7f8-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d7f8-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="3d7f8-134">Result : Failure</span></span>

<span data-ttu-id="3d7f8-135">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3d7f8-135">Latency : 00:00:00</span></span>

<span data-ttu-id="3d7f8-136">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="3d7f8-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="3d7f8-137">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="3d7f8-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="3d7f8-138">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="3d7f8-138">established connection failed because connected host has</span></span>

<span data-ttu-id="3d7f8-139">Fehler bei der \[Antwort 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="3d7f8-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="3d7f8-140">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="3d7f8-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="3d7f8-141">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="3d7f8-142">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="3d7f8-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="3d7f8-143">Fehler beim Antworten</span><span class="sxs-lookup"><span data-stu-id="3d7f8-143">has failed to respond</span></span>

<span data-ttu-id="3d7f8-144">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="3d7f8-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="3d7f8-145">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3d7f8-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3d7f8-146">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="3d7f8-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="3d7f8-147">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csdataconference "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="3d7f8-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="3d7f8-148">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3d7f8-149">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3d7f8-150">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3d7f8-151">Die Möglichkeit zum Durchführen einer Datenkonferenz hängt von der konferenzrichtlinie ab, die dem Benutzer zugewiesen wurde, der die Konferenz organisiert hat (im Fall des **Test-csdataconference "-** Cmdlets, also des" Absenders ").</span><span class="sxs-lookup"><span data-stu-id="3d7f8-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="3d7f8-152">Wenn der Organisator keine kollaborativen Aktivitäten in seine Besprechung einschließen darf (Wenn beispielsweise die EnableDataCollaboration-Eigenschaft für die konferenzrichtlinie auf false festgelegt ist), tritt das **Test-csdataconference "-** Cmdlet nicht mehr auf.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="3d7f8-153">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

