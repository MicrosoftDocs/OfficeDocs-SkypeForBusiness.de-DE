---
title: 'Lync Server 2013: Testen des webplaners'
description: 'Lync Server 2013: Testen des webplaners.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556151"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="7a10c-103">Testen des webplaners in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a10c-103">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a10c-104">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="7a10c-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a10c-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="7a10c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7a10c-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="7a10c-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a10c-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="7a10c-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7a10c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a10c-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a10c-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7a10c-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7a10c-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="7a10c-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7a10c-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-cswebscheduler "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="7a10c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="7a10c-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="7a10c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7a10c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a10c-113">Description</span></span>

<span data-ttu-id="7a10c-114">Mit dem Cmdlet **Test-cswebscheduler "** können Sie bestimmen, ob ein bestimmter Benutzer eine Besprechung mithilfe des webplaners planen kann.</span><span class="sxs-lookup"><span data-stu-id="7a10c-114">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="7a10c-115">Mit dem Webplaner können Benutzer, die Outlook nicht starten, Onlinebesprechungen planen.</span><span class="sxs-lookup"><span data-stu-id="7a10c-115">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="7a10c-116">Dieses neue Feature (das die im Microsoft lync Server 2010 Resource Kit enthaltene Funktionalität des Webplaner-Tools enthält) ermöglicht es den Benutzern unter anderem, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="7a10c-116">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="7a10c-117">Planen einer neuen Onlinebesprechung</span><span class="sxs-lookup"><span data-stu-id="7a10c-117">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="7a10c-118">Auflisten aller vom Benutzer geplanten Besprechungen</span><span class="sxs-lookup"><span data-stu-id="7a10c-118">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="7a10c-119">Anzeigen/Ändern einer vorhandenen Besprechung</span><span class="sxs-lookup"><span data-stu-id="7a10c-119">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="7a10c-120">Löschen einer vorhandenen Besprechung</span><span class="sxs-lookup"><span data-stu-id="7a10c-120">Delete an existing meeting.</span></span>

  - <span data-ttu-id="7a10c-121">Senden einer E-Mail-Einladung an Besprechungsteilnehmer mit einem vorkonfigurierten SMTP-Mailserver.</span><span class="sxs-lookup"><span data-stu-id="7a10c-121">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="7a10c-122">Teilnehmen an einer vorhandenen Konferenz</span><span class="sxs-lookup"><span data-stu-id="7a10c-122">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7a10c-123">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="7a10c-123">Running the test</span></span>

<span data-ttu-id="7a10c-124">Im folgenden Beispiel wird der Webplaner für die Pool-ATL-CS-001.litwareinc.com überprüft.</span><span class="sxs-lookup"><span data-stu-id="7a10c-124">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7a10c-125">Dieser Befehl ist nur möglich, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7a10c-125">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7a10c-126">Wenn dies der Fall ist, wird mit dem Befehl ermittelt, ob der erste Testbenutzer eine Onlinebesprechung mithilfe des webplaners planen kann.</span><span class="sxs-lookup"><span data-stu-id="7a10c-126">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="7a10c-127">Wenn Testbenutzer nicht definiert sind, tritt beim Ausführen des Befehls ein Fehler auf, da er nicht weiß, welcher Benutzer sich anmelden muss.</span><span class="sxs-lookup"><span data-stu-id="7a10c-127">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="7a10c-128">Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den UserSipAddress-Parameter und die Anmeldeinformationen des Benutzers einschließen, der vom Befehl beim Anmelden verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7a10c-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="7a10c-129">Die im nächsten Beispiel gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers (litwareinc \\ kenmeyer), eine Onlinebesprechung mithilfe des webplaners zu planen.</span><span class="sxs-lookup"><span data-stu-id="7a10c-129">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="7a10c-130">Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Ken Meyer enthält.</span><span class="sxs-lookup"><span data-stu-id="7a10c-130">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="7a10c-131">(Da der Anmeldename litwareinc \\ kenmeyer als Parameter enthalten ist, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Ken Meyer-Konto angeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7a10c-131">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="7a10c-132">Der zweite Befehl prüft dann, ob sich dieser Benutzer am Pool ATL-CS-001.litwareinc.com anmelden und eine Onlinebesprechung planen kann.</span><span class="sxs-lookup"><span data-stu-id="7a10c-132">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="7a10c-133">Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-cswebscheduler "** zusammen mit drei Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und UserSipAddress (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).</span><span class="sxs-lookup"><span data-stu-id="7a10c-133">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7a10c-134">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="7a10c-134">Determining success or failure</span></span>

<span data-ttu-id="7a10c-135">Wenn der Webplaner ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="7a10c-135">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="7a10c-136">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7a10c-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7a10c-137">Ziel-URI: https://ATL-CS-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7a10c-137">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="7a10c-138">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="7a10c-138">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="7a10c-139">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="7a10c-139">Result : Success</span></span>

<span data-ttu-id="7a10c-140">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7a10c-140">Latency : 00:00:00</span></span>

<span data-ttu-id="7a10c-141">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="7a10c-141">Error Message :</span></span>

<span data-ttu-id="7a10c-142">Diagnose</span><span class="sxs-lookup"><span data-stu-id="7a10c-142">Diagnosis :</span></span>

<span data-ttu-id="7a10c-143">Wenn der Webplaner nicht ordnungsgemäß konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="7a10c-143">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7a10c-144">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="7a10c-144">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="7a10c-145">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="7a10c-145">domain name (FQDN).</span></span> <span data-ttu-id="7a10c-146">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="7a10c-146">Using default Registrar port number.</span></span> <span data-ttu-id="7a10c-147">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="7a10c-147">Exception:</span></span>

<span data-ttu-id="7a10c-148">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="7a10c-148">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="7a10c-149">auf</span><span class="sxs-lookup"><span data-stu-id="7a10c-149">at</span></span>

<span data-ttu-id="7a10c-150">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="7a10c-150">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="7a10c-151">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="7a10c-151">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="7a10c-152">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7a10c-152">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7a10c-153">Ziel-URI:</span><span class="sxs-lookup"><span data-stu-id="7a10c-153">Target Uri :</span></span>

<span data-ttu-id="7a10c-154">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="7a10c-154">Result : Failure</span></span>

<span data-ttu-id="7a10c-155">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7a10c-155">Latency : 00:00:00</span></span>

<span data-ttu-id="7a10c-156">Fehlermeldung: kein übereinstimmendes Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="7a10c-156">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="7a10c-157">Diagnose</span><span class="sxs-lookup"><span data-stu-id="7a10c-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7a10c-158">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="7a10c-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="7a10c-159">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von cswebscheduler "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="7a10c-159">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="7a10c-160">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="7a10c-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="7a10c-161">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a10c-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="7a10c-162">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7a10c-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="7a10c-163">Dieser Befehl schlägt fehl, wenn der Webplaner falsch konfiguriert oder noch nicht bereitgestellt ist.</span><span class="sxs-lookup"><span data-stu-id="7a10c-163">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a10c-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a10c-164">See Also</span></span>


[<span data-ttu-id="7a10c-165">Gruppe-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="7a10c-165">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

