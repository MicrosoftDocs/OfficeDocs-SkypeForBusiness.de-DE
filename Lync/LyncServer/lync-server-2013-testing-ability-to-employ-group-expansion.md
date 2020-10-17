---
title: 'Lync Server 2013: Testen der Fähigkeit zur Verwendung der Gruppenerweiterung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8c12d687d6c23c7c7bdc2bf2d8046038154c871
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520742"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="74ba8-102">Testen der Möglichkeit zur Verwendung der Gruppenerweiterung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ba8-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74ba8-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="74ba8-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ba8-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="74ba8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="74ba8-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="74ba8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ba8-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="74ba8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="74ba8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ba8-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="74ba8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="74ba8-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="74ba8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="74ba8-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsGroupExpansion-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="74ba8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="74ba8-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="74ba8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="74ba8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74ba8-112">Description</span></span>

<span data-ttu-id="74ba8-113">Mit dem Test-CsGroupExpansion-Cmdlet können Sie bestimmen, ob die Gruppenerweiterung in Ihrer Organisation funktioniert.</span><span class="sxs-lookup"><span data-stu-id="74ba8-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="74ba8-114">Wenn die Gruppenerweiterung aktiviert ist, konfigurieren Benutzer Verteilergruppen als Kontakt.</span><span class="sxs-lookup"><span data-stu-id="74ba8-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="74ba8-115">Das bedeutet, dass diese Benutzer dann dieselbe Sofortnachricht an alle Gruppenmitglieder senden können, indem Sie die Nachricht an die Gruppe anstatt an einzelne Mitglieder dieser Gruppe adressieren.</span><span class="sxs-lookup"><span data-stu-id="74ba8-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="74ba8-116">Mit Gruppenerweiterung können Sie mühelos alle Gruppenmitglieder und ihren aktuellen Status anzeigen.</span><span class="sxs-lookup"><span data-stu-id="74ba8-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="74ba8-117">Mit dem Test-CsGroupExpansion-Cmdlet geben Sie eine Active Directory Verteilergruppe mithilfe der e-Mail-Adresse der Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="74ba8-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="74ba8-118">Test-CsGroupExpansion verwendet dann die Gruppenerweiterung, um die Gruppenmitgliedschaft abzurufen und die abgerufene Liste mit der Mitgliedschaft der von Ihnen angegebenen Gruppen-e-Mail-Adresse zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="74ba8-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="74ba8-119">Stimmen die beiden Listen überein, funktioniert die Gruppenerweiterung ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="74ba8-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="74ba8-120">Beachten Sie, dass Sie die Gruppenerweiterung auf zwei Arten testen können: durch Testen des Diensts selbst oder durch Testen des zugeordneten Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="74ba8-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="74ba8-121">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="74ba8-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="74ba8-122">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="74ba8-122">Running the test</span></span>

<span data-ttu-id="74ba8-123">Das Test-CsGroupExpansion-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="74ba8-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="74ba8-124">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des getesteten lync Server Pools und die e-Mail-Adresse für eine gültige Verteilergruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="74ba8-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="74ba8-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74ba8-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="74ba8-126">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein lync Server Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="74ba8-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="74ba8-127">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn das System Test-CsGroupExpansion aufruft:</span><span class="sxs-lookup"><span data-stu-id="74ba8-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="74ba8-128">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="74ba8-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="74ba8-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="74ba8-129">Determining success or failure</span></span>

<span data-ttu-id="74ba8-130">Wenn der angegebene Benutzer die Gruppenerweiterung verwenden kann, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="74ba8-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="74ba8-131">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="74ba8-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="74ba8-132">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="74ba8-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="74ba8-133">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="74ba8-133">Result : Success</span></span>

<span data-ttu-id="74ba8-134">Wartezeit: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="74ba8-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="74ba8-135">Fehler</span><span class="sxs-lookup"><span data-stu-id="74ba8-135">Error :</span></span>

<span data-ttu-id="74ba8-136">Diagnose</span><span class="sxs-lookup"><span data-stu-id="74ba8-136">Diagnosis :</span></span>

<span data-ttu-id="74ba8-137">Wenn der angegebene Benutzer keine Gruppenerweiterung verwenden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Error und Diagnostic aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="74ba8-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="74ba8-138">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="74ba8-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="74ba8-139">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="74ba8-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="74ba8-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="74ba8-140">Result : Failure</span></span>

<span data-ttu-id="74ba8-141">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="74ba8-141">Latency : 00:00:00</span></span>

<span data-ttu-id="74ba8-142">Fehler</span><span class="sxs-lookup"><span data-stu-id="74ba8-142">Error :</span></span>

<span data-ttu-id="74ba8-143">Diagnose</span><span class="sxs-lookup"><span data-stu-id="74ba8-143">Diagnosis :</span></span>

<span data-ttu-id="74ba8-144">Test-CsGroupExpansion: der Endpunkt konnte sich nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="74ba8-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="74ba8-145">Lesen Sie den ErrorCode aus einem bestimmten Grund.</span><span class="sxs-lookup"><span data-stu-id="74ba8-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="74ba8-146">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da sich der angegebene Benutzer nicht bei lync Server registrieren konnte.</span><span class="sxs-lookup"><span data-stu-id="74ba8-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="74ba8-147">Dies tritt normalerweise auf, wenn das Testkonto nicht vorhanden ist oder für lync Server nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="74ba8-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="74ba8-148">Sie können sicherstellen, dass das Konto vorhanden ist, und bestimmen, ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="74ba8-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="74ba8-149">Wenn Test-CsGroupExpansion fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="74ba8-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="74ba8-150">Wenn der Verbose-Parameter enthalten ist Test-CsGroupExpansion gibt eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="74ba8-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="74ba8-151">Diese Ausgabe gibt beispielsweise an, dass die angegebene Verteilergruppe nicht gefunden werden konnte:</span><span class="sxs-lookup"><span data-stu-id="74ba8-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="74ba8-152">Das Abrufen von webtickets wird versucht.</span><span class="sxs-lookup"><span data-stu-id="74ba8-152">Trying to get web ticket.</span></span>

<span data-ttu-id="74ba8-153">Webdienst-URL: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="74ba8-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="74ba8-154">Verwenden von NTLM/Kerb-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="74ba8-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="74ba8-155">GetWebTicketActivity abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="74ba8-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="74ba8-156">"VerifyDistributionList"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="74ba8-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="74ba8-157">Der Antwort Status des dlx-Webdiensts lautet: NotFound.</span><span class="sxs-lookup"><span data-stu-id="74ba8-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="74ba8-158">"VerifyDistributionList"-Aktivität wurde in "0,2597923" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="74ba8-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="74ba8-159">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="74ba8-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="74ba8-160">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsGroupExpansion Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="74ba8-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="74ba8-161">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="74ba8-161">You specified an invalid user account.</span></span> <span data-ttu-id="74ba8-162">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="74ba8-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="74ba8-163">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="74ba8-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="74ba8-164">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="74ba8-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="74ba8-165">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="74ba8-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="74ba8-166">Die Gruppenerweiterung ist möglicherweise deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="74ba8-166">Group expansion might be disabled.</span></span> <span data-ttu-id="74ba8-167">Die Gruppenerweiterung kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="74ba8-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="74ba8-168">Wenn die Gruppenerweiterung deaktiviert wurde, tritt beim Test-CsGroupExpansion-Cmdlet ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="74ba8-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="74ba8-169">Verwenden Sie einen Befehl wie den folgenden, um festzustellen, ob die Gruppenerweiterung aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="74ba8-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

