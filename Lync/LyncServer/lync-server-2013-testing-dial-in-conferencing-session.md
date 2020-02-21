---
title: 'Lync Server 2013: Testen der Einwahlkonferenz Sitzung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94999d2f3ce69308e38da1b261a4b0d96a2ef5cd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="e0a46-102">Testen der Einwahlkonferenz Sitzung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0a46-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0a46-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e0a46-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0a46-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="e0a46-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e0a46-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="e0a46-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0a46-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="e0a46-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e0a46-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0a46-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0a46-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e0a46-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e0a46-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="e0a46-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e0a46-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsDialInConferencing verfügt.</span><span class="sxs-lookup"><span data-stu-id="e0a46-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="e0a46-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="e0a46-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e0a46-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a46-112">Description</span></span>

<span data-ttu-id="e0a46-113">Das Cmdlet Test-CsDialInConferencing überprüft, ob ein Benutzer an einer Einwahlkonferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="e0a46-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="e0a46-114">Test-CsDialInConferencing funktioniert, indem versucht wird, einen Testbenutzer auf dem System zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="e0a46-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="e0a46-115">Wenn die Anmeldung erfolgreich verläuft, verwendet das Cmdlet dann die Anmeldeinformationen und Berechtigungen des Benutzers, um alle verfügbaren Zugriffsnummern für Einwahlkonferenzen zu testen.</span><span class="sxs-lookup"><span data-stu-id="e0a46-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="e0a46-116">Der Erfolg oder Misserfolg der einzelnen Einwahl Versuche wird notiert, dann wird der Testbenutzer von lync Server abgemeldet. Test-CsDialInConferencing nur überprüft, ob die entsprechenden Verbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e0a46-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="e0a46-117">Das Cmdlet tätigt keine echten Anrufe und erstellt keine Einwahlkonferenzen, an denen andere Benutzer teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="e0a46-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e0a46-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="e0a46-118">Running the test</span></span>

<span data-ttu-id="e0a46-119">Das Cmdlet Test-CsDialInConferencing kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e0a46-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="e0a46-120">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0a46-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e0a46-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e0a46-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="e0a46-122">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="e0a46-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="e0a46-123">Anschließend müssen Sie das Credentials-Objekt und die SIP-Adresse des Kontos zum aufrufenden Test-CsDialInConferencing hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e0a46-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e0a46-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="e0a46-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e0a46-125">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="e0a46-125">Determining success or failure</span></span>

<span data-ttu-id="e0a46-126">Wenn sich der angegebene Benutzer bei lync Server anmelden und dann eine Verbindung mit einer der verfügbaren Zugriffsnummern für Einwahlkonferenzen herstellen kann, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als "Success" markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="e0a46-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e0a46-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e0a46-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e0a46-128">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="e0a46-128">Result : Success</span></span>

<span data-ttu-id="e0a46-129">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="e0a46-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="e0a46-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="e0a46-130">Error :</span></span>

<span data-ttu-id="e0a46-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e0a46-131">Diagnosis :</span></span>

<span data-ttu-id="e0a46-132">Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="e0a46-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e0a46-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e0a46-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e0a46-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="e0a46-134">Result : Failure</span></span>

<span data-ttu-id="e0a46-135">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e0a46-135">Latency : 00:00:00</span></span>

<span data-ttu-id="e0a46-136">Fehler: das Anmelden wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="e0a46-136">Error : The log on was denied.</span></span> <span data-ttu-id="e0a46-137">Stellen Sie sicher, dass die richtigen Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="e0a46-137">Check that the proper credentials are</span></span>

<span data-ttu-id="e0a46-138">verwendet wird und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e0a46-138">being used and the account is active.</span></span>

<span data-ttu-id="e0a46-139">Innere Ausnahme: NegotiateSecurityAssociation fehlgeschlagen, Fehler:-</span><span class="sxs-lookup"><span data-stu-id="e0a46-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="e0a46-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="e0a46-140">2146893044</span></span>

<span data-ttu-id="e0a46-141">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e0a46-141">Diagnosis :</span></span>

<span data-ttu-id="e0a46-142">Die vorherige Ausgabe gibt an, dass dem Testbenutzer der Zugriff auf lync Server selbst verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="e0a46-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="e0a46-143">Dies bedeutet normalerweise, dass die an Test-CsDialInConferencing übergebenen Benutzeranmeldeinformationen ungültig waren.</span><span class="sxs-lookup"><span data-stu-id="e0a46-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="e0a46-144">Sie sollten wiederum das Windows PowerShell Credentials-Objekt neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e0a46-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="e0a46-145">Obwohl Sie das Kennwort für das Benutzerkonto abrufen können, können Sie die SIP-Adresse überprüfen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="e0a46-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e0a46-146">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="e0a46-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="e0a46-147">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsDialInConferencing möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="e0a46-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="e0a46-148">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="e0a46-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="e0a46-149">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="e0a46-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e0a46-150">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e0a46-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e0a46-151">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="e0a46-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e0a46-152">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e0a46-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="e0a46-153">Möglicherweise verfügen Sie über eine falsche Zugriffsnummer für Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="e0a46-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="e0a46-154">Sie können die aktuell konfigurierte Liste der Zugriffsnummern für Einwahlkonferenzen mithilfe dieses Befehls zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="e0a46-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

