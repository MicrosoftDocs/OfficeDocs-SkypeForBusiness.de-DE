---
title: 'Lync Server 2013: Testen der Sitzung für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcc6d9277f7333989c59b812ed76087b9b6ca9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="4b836-102">Testen der Einwahlkonferenz Sitzung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b836-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b836-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4b836-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b836-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="4b836-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4b836-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="4b836-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b836-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="4b836-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4b836-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b836-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b836-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4b836-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4b836-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="4b836-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4b836-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsDialInConferencing-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="4b836-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="4b836-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="4b836-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4b836-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b836-112">Description</span></span>

<span data-ttu-id="4b836-113">Das Cmdlet Test-CsDialInConferencing überprüft, ob ein Benutzer an einer Einwahlkonferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="4b836-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="4b836-114">Test-CsDialInConferencing funktioniert, indem Sie versuchen, einen Testbenutzer auf dem System zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="4b836-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="4b836-115">Wenn die Anmeldung erfolgreich ausgeführt wird, verwendet das Cmdlet dann die Anmeldeinformationen und Berechtigungen des Benutzers, um alle verfügbaren Zugriffsnummern für Einwahlkonferenzen zu testen.</span><span class="sxs-lookup"><span data-stu-id="4b836-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="4b836-116">Der Erfolg oder Misserfolg jedes Einwahlversuchs wird festgestellt, dann wird der Testbenutzer von lync Server abgemeldet. Test-CsDialInConferencing überprüft nur, ob die entsprechenden Verbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="4b836-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="4b836-117">Das Cmdlet führt tatsächlich keine Telefonanrufe durch oder erstellt keine Einwahlkonferenzen, an denen andere Benutzer teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="4b836-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4b836-118">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="4b836-118">Running the test</span></span>

<span data-ttu-id="4b836-119">Das Cmdlet "Test-CsDialInConferencing" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4b836-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="4b836-120">Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="4b836-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="4b836-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4b836-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="4b836-122">Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="4b836-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="4b836-123">Sie müssen dann das Credentials-Objekt und die SIP-Adresse des Kontos mit dem aufrufenden Test-CsDialInConferencing einfügen:</span><span class="sxs-lookup"><span data-stu-id="4b836-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="4b836-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="4b836-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4b836-125">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="4b836-125">Determining success or failure</span></span>

<span data-ttu-id="4b836-126">Wenn sich der angegebene Benutzer bei lync Server anmelden und dann eine Verbindung mit einer der verfügbaren Zugriffsnummern für Einwahlkonferenzen herstellen kann, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="4b836-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="4b836-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b836-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4b836-128">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="4b836-128">Result : Success</span></span>

<span data-ttu-id="4b836-129">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="4b836-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="4b836-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="4b836-130">Error :</span></span>

<span data-ttu-id="4b836-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="4b836-131">Diagnosis :</span></span>

<span data-ttu-id="4b836-132">Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="4b836-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4b836-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b836-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4b836-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="4b836-134">Result : Failure</span></span>

<span data-ttu-id="4b836-135">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4b836-135">Latency : 00:00:00</span></span>

<span data-ttu-id="4b836-136">Fehler: die Anmeldung wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="4b836-136">Error : The log on was denied.</span></span> <span data-ttu-id="4b836-137">Überprüfen Sie, ob die richtigen Anmeldeinformationen sind.</span><span class="sxs-lookup"><span data-stu-id="4b836-137">Check that the proper credentials are</span></span>

<span data-ttu-id="4b836-138">verwendet wird und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="4b836-138">being used and the account is active.</span></span>

<span data-ttu-id="4b836-139">Innere Ausnahme: NegotiateSecurityAssociation ist fehlgeschlagen, Fehler:-</span><span class="sxs-lookup"><span data-stu-id="4b836-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="4b836-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="4b836-140">2146893044</span></span>

<span data-ttu-id="4b836-141">Diagnose</span><span class="sxs-lookup"><span data-stu-id="4b836-141">Diagnosis :</span></span>

<span data-ttu-id="4b836-142">Die vorherige Ausgabe zeigt an, dass dem Testbenutzer der Zugriff auf lync Server selbst verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="4b836-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="4b836-143">Dies bedeutet in der Regel, dass die an Test-CsDialInConferencing übergebenen Benutzeranmeldeinformationen ungültig waren.</span><span class="sxs-lookup"><span data-stu-id="4b836-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="4b836-144">Sie sollten wiederum das Windows PowerShell-Anmeldeinformationsobjekt erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b836-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="4b836-145">Obwohl Sie das Kennwort für das Benutzerkonto abrufen können, können Sie die SIP-Adresse überprüfen, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="4b836-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4b836-146">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="4b836-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="4b836-147">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsDialInConferencing möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="4b836-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="4b836-148">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="4b836-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="4b836-149">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="4b836-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="4b836-150">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4b836-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="4b836-151">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="4b836-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="4b836-152">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4b836-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="4b836-153">Möglicherweise verfügen Sie über eine falsche Zugriffsnummer für Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="4b836-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="4b836-154">Sie können die aktuell konfigurierte Liste der Zugriffsnummern für Einwahlkonferenzen mithilfe des folgenden Befehls zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="4b836-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

