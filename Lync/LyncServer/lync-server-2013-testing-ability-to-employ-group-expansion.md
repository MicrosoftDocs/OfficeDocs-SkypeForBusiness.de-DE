---
title: 'Lync Server 2013: Testen der Fähigkeit, Gruppen Erweiterungen zu verwenden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="a3dcb-102">Testen der Möglichkeit zur Verwendung der Gruppenerweiterung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3dcb-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3dcb-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a3dcb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3dcb-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="a3dcb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a3dcb-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="a3dcb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3dcb-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="a3dcb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a3dcb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3dcb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3dcb-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a3dcb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a3dcb-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a3dcb-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsGroupExpansion-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="a3dcb-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a3dcb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3dcb-112">Description</span></span>

<span data-ttu-id="a3dcb-113">Mit dem Cmdlet Test-CsGroupExpansion können Sie ermitteln, ob die Gruppenerweiterung in Ihrer Organisation funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="a3dcb-114">Wenn die Gruppenerweiterung aktiviert ist, konfigurieren Benutzer Verteilergruppen als Kontakt.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="a3dcb-115">Das bedeutet, dass diese Benutzer dann die gleiche Sofortnachricht an alle Gruppenmitglieder senden können, indem Sie die Nachricht an die Gruppe anstatt an einzelne Mitglieder dieser Gruppe adressieren.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="a3dcb-116">Mit der Gruppenerweiterung können Sie alle Gruppenmitglieder und deren aktuellen Status schnell und einfach anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="a3dcb-117">Mit dem Cmdlet Test-CsGroupExpansion geben Sie eine Active Directory-Verteilergruppe an, indem Sie die e-Mail-Adresse der Gruppe verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="a3dcb-118">Test-CsGroupExpansion verwendet dann die Gruppenerweiterung, um die Gruppenmitgliedschaft abzurufen, und vergleicht die abgerufene Liste mit der Mitgliedschaft der von Ihnen angegebenen Gruppen-e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="a3dcb-119">Wenn die beiden Listen übereinstimmen, funktioniert die Gruppenerweiterung ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="a3dcb-120">Beachten Sie, dass Sie die Gruppenerweiterung auf zwei Arten testen können: durch Testen des Diensts selbst oder durch Testen des zugehörigen Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="a3dcb-121">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="a3dcb-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a3dcb-122">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="a3dcb-122">Running the test</span></span>

<span data-ttu-id="a3dcb-123">Das Cmdlet "Test-CsGroupExpansion" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert war.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="a3dcb-124">Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools und die e-Mail-Adresse für eine gültige Verteilergruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="a3dcb-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="a3dcb-126">Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein lync Server-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="a3dcb-127">Sie müssen dann das Anmeldeinformationsobjekt und die SIP-Adresse einbeziehen, die dem Konto zugewiesen ist, wenn das System Test-CsGroupExpansion aufruft:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a3dcb-128">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="a3dcb-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a3dcb-129">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="a3dcb-129">Determining success or failure</span></span>

<span data-ttu-id="a3dcb-130">Wenn der angegebene Benutzer die Gruppenerweiterung verwenden kann, erhalten Sie eine ähnliche Ausgabe, wobei die Ergebniseigenschaft als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="a3dcb-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a3dcb-131">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a3dcb-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="a3dcb-132">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3dcb-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a3dcb-133">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="a3dcb-133">Result : Success</span></span>

<span data-ttu-id="a3dcb-134">Latenz: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="a3dcb-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="a3dcb-135">Fehler</span><span class="sxs-lookup"><span data-stu-id="a3dcb-135">Error :</span></span>

<span data-ttu-id="a3dcb-136">Diagnose</span><span class="sxs-lookup"><span data-stu-id="a3dcb-136">Diagnosis :</span></span>

<span data-ttu-id="a3dcb-137">Wenn der angegebene Benutzer keine Gruppenerweiterung verwenden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a3dcb-138">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a3dcb-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="a3dcb-139">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3dcb-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a3dcb-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="a3dcb-140">Result : Failure</span></span>

<span data-ttu-id="a3dcb-141">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a3dcb-141">Latency : 00:00:00</span></span>

<span data-ttu-id="a3dcb-142">Fehler</span><span class="sxs-lookup"><span data-stu-id="a3dcb-142">Error :</span></span>

<span data-ttu-id="a3dcb-143">Diagnose</span><span class="sxs-lookup"><span data-stu-id="a3dcb-143">Diagnosis :</span></span>

<span data-ttu-id="a3dcb-144">Test-CsGroupExpansion: der Endpunkt konnte nicht registriert werden.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="a3dcb-145">Lesen Sie den ErrorCode aus bestimmten Gründen.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="a3dcb-146">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer sich nicht bei lync Server registrieren konnte.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="a3dcb-147">Dies erfolgt in der Regel, wenn das Testkonto nicht vorhanden ist oder für lync Server nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="a3dcb-148">Sie können überprüfen, ob das Konto vorhanden ist, und ermitteln, ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="a3dcb-149">Wenn Test-CsGroupExpansion fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="a3dcb-150">Wenn der Verbose-Parameter enthalten ist, gibt CsGroupExpansion eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a3dcb-151">Diese Ausgabe gibt beispielsweise an, dass die angegebene Verteilergruppe nicht gefunden wurde:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="a3dcb-152">Sie versuchen, Web-Ticket zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-152">Trying to get web ticket.</span></span>

<span data-ttu-id="a3dcb-153">Webdienst-URL:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="a3dcb-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="a3dcb-154">Verwenden von NTLM/Kerb auth</span><span class="sxs-lookup"><span data-stu-id="a3dcb-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="a3dcb-155">GetWebTicketActivity abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="a3dcb-156">Die Aktivität "VerifyDistributionList" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="a3dcb-157">Der Antwort Status des dlx-Webdiensts lautet: NotFound.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="a3dcb-158">"VerifyDistributionList"-Aktivität wurde in "0,2597923" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a3dcb-159">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="a3dcb-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="a3dcb-160">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsGroupExpansion möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="a3dcb-161">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-161">You specified an invalid user account.</span></span> <span data-ttu-id="a3dcb-162">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a3dcb-163">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="a3dcb-164">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert war, führen Sie einen Befehl ähnlich der folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a3dcb-165">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="a3dcb-166">Die Gruppenerweiterung ist möglicherweise deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-166">Group expansion might be disabled.</span></span> <span data-ttu-id="a3dcb-167">Es ist möglich, die Gruppenerweiterung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="a3dcb-168">Wenn die Gruppenerweiterung deaktiviert wurde, schlägt das Cmdlet Test-CsGroupExpansion fehl.</span><span class="sxs-lookup"><span data-stu-id="a3dcb-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="a3dcb-169">Wenn Sie feststellen möchten, ob die Gruppenerweiterung aktiviert ist, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="a3dcb-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

