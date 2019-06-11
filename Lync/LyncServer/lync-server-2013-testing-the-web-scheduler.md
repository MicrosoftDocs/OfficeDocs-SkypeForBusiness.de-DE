---
title: 'Lync Server 2013: Testen des Web Scheduler'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="82751-102">Testen des Web Scheduler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82751-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82751-103">_**Letztes Änderungsdatum des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="82751-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82751-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="82751-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="82751-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="82751-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="82751-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="82751-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82751-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82751-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="82751-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="82751-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="82751-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="82751-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsWebScheduler-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="82751-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="82751-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="82751-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="82751-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82751-112">Description</span></span>

<span data-ttu-id="82751-113">Mit dem Cmdlet **Test-CsWebScheduler** können Sie ermitteln, ob ein bestimmter Benutzer eine Besprechung mit dem Web Scheduler planen kann.</span><span class="sxs-lookup"><span data-stu-id="82751-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="82751-114">Der Web Scheduler ermöglicht es Benutzern, die Outlook nicht ausführen, Onlinebesprechungen zu planen.</span><span class="sxs-lookup"><span data-stu-id="82751-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="82751-115">Diese neue Funktion (mit der Funktionalität des Web Scheduler-Tools, die im Microsoft lync Server 2010 Resource Kit enthalten war) bietet Benutzern unter anderem die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="82751-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="82751-116">Planen einer neuen Onlinebesprechung</span><span class="sxs-lookup"><span data-stu-id="82751-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="82751-117">Listen Sie alle Besprechungen auf, die er geplant hat.</span><span class="sxs-lookup"><span data-stu-id="82751-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="82751-118">Anzeigen/Ändern einer vorhandenen Besprechung</span><span class="sxs-lookup"><span data-stu-id="82751-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="82751-119">Löschen einer vorhandenen Besprechung</span><span class="sxs-lookup"><span data-stu-id="82751-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="82751-120">Senden einer e-Mail-Einladung an Besprechungsteilnehmer mithilfe eines vorkonfigurierten SMTP-e-Mail-Servers.</span><span class="sxs-lookup"><span data-stu-id="82751-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="82751-121">Teilnehmen an einer vorhandenen Konferenz</span><span class="sxs-lookup"><span data-stu-id="82751-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="82751-122">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="82751-122">Running the test</span></span>

<span data-ttu-id="82751-123">Im folgenden Beispiel wird der Web Scheduler für den Pool ATL-CS-001.litwareinc.com überprüft.</span><span class="sxs-lookup"><span data-stu-id="82751-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="82751-124">Dieser Befehl funktioniert nur, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind.</span><span class="sxs-lookup"><span data-stu-id="82751-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="82751-125">Wenn ja, bestimmt der Befehl, ob der erste Testbenutzer eine Onlinebesprechung mit dem Web Scheduler planen kann.</span><span class="sxs-lookup"><span data-stu-id="82751-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="82751-126">Wenn Testbenutzer nicht definiert sind, schlägt der Befehl fehl, da er nicht weiß, zu welchem Benutzer Sie sich anmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="82751-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="82751-127">Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den "usersipaddress"-Parameter und die Anmeldeinformationen des Benutzers einbeziehen, den der Befehl bei der Anmeldung verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="82751-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="82751-128">Die im nächsten Beispiel gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers ("litwareinc\\kenmeyer), eine Onlinebesprechung mit dem Web Scheduler zu planen.</span><span class="sxs-lookup"><span data-stu-id="82751-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="82751-129">Dazu verwendet der erste Befehl im Beispiel das Cmdlet " **Get-Credential** ", um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Ken Meyer enthält.</span><span class="sxs-lookup"><span data-stu-id="82751-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="82751-130">(Da der Anmeldename "litwareinc\\kenmeyer als Parameter enthalten ist, erfordert das Windows PowerShell-Dialogfeld Anmeldeinformationen nur den Administrator, das Kennwort für das Ken Meyer-Konto einzugeben.) Das resultierende Anmeldeinformationsobjekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="82751-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="82751-131">Der zweite Befehl überprüft dann, ob dieser Benutzer sich beim Pool ATL-CS-001.litwareinc.com anmelden und eine Onlinebesprechung planen kann.</span><span class="sxs-lookup"><span data-stu-id="82751-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="82751-132">Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-CsWebScheduler** zusammen mit drei Parametern aufgerufen: TargetFqdn (dem FQDN des registrierungspools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und "usersipaddress" (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).</span><span class="sxs-lookup"><span data-stu-id="82751-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="82751-133">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="82751-133">Determining success or failure</span></span>

<span data-ttu-id="82751-134">Wenn der Web Scheduler richtig konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="82751-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="82751-135">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="82751-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="82751-136">Ziel-URI: https://-ATL-CS-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="82751-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="82751-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="82751-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="82751-138">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="82751-138">Result : Success</span></span>

<span data-ttu-id="82751-139">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="82751-139">Latency : 00:00:00</span></span>

<span data-ttu-id="82751-140">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="82751-140">Error Message :</span></span>

<span data-ttu-id="82751-141">Diagnose</span><span class="sxs-lookup"><span data-stu-id="82751-141">Diagnosis :</span></span>

<span data-ttu-id="82751-142">Wenn der Web Scheduler nicht richtig konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="82751-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="82751-143">Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="82751-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="82751-144">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="82751-144">domain name (FQDN).</span></span> <span data-ttu-id="82751-145">Verwenden der standardmäßigen Registrierungs Portnummer</span><span class="sxs-lookup"><span data-stu-id="82751-145">Using default Registrar port number.</span></span> <span data-ttu-id="82751-146">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="82751-146">Exception:</span></span>

<span data-ttu-id="82751-147">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="82751-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="82751-148">am</span><span class="sxs-lookup"><span data-stu-id="82751-148">at</span></span>

<span data-ttu-id="82751-149">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="82751-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="82751-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="82751-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="82751-151">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="82751-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="82751-152">Ziel-URI:</span><span class="sxs-lookup"><span data-stu-id="82751-152">Target Uri :</span></span>

<span data-ttu-id="82751-153">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="82751-153">Result : Failure</span></span>

<span data-ttu-id="82751-154">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="82751-154">Latency : 00:00:00</span></span>

<span data-ttu-id="82751-155">Fehlermeldung: Es wurde kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="82751-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="82751-156">Diagnose</span><span class="sxs-lookup"><span data-stu-id="82751-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="82751-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="82751-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="82751-158">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsWebScheduler** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="82751-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="82751-159">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="82751-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="82751-160">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="82751-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="82751-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="82751-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="82751-162">Dieser Befehl schlägt fehl, wenn der Web Scheduler falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="82751-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82751-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82751-163">See Also</span></span>


[<span data-ttu-id="82751-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="82751-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

