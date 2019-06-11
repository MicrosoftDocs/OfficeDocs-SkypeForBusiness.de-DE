---
title: 'Lync Server 2013: Testen der Chat Fähigkeit zwischen zwei Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea824216c456e9f673a5383eab0b788933bf53d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="bcc4b-102">Testen der Chat Fähigkeit zwischen zwei Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcc4b-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcc4b-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bcc4b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcc4b-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="bcc4b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bcc4b-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="bcc4b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcc4b-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="bcc4b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bcc4b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcc4b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcc4b-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bcc4b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bcc4b-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bcc4b-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsIM-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="bcc4b-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bcc4b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcc4b-112">Description</span></span>

<span data-ttu-id="bcc4b-113">Das Cmdlet Test-CsIM überprüft, ob ein paar Testbenutzer Sofortnachrichten austauschen können.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="bcc4b-114">Wenn das Cmdlet Test-CsIM aufgerufen wird, versuchen Sie, sich bei einem Paar Testbenutzern mit lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="bcc4b-115">Wenn die beiden Anmeldungen erfolgreich sind, startet das Cmdlet dann eine Chatsitzung zwischen den beiden Testbenutzern.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="bcc4b-116">(Benutzer 1 lädt Benutzer 2 zu einer Chatsitzung ein, und Benutzer 2 nimmt die Einladung an.) Nachdem Sie überprüft haben, ob Nachrichten zwischen den beiden Benutzern ausgetauscht werden können, beendet Test-CsIM dann die Chatsitzung und protokolliert beide Benutzer vom System.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="bcc4b-117">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="bcc4b-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bcc4b-118">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="bcc4b-118">Running the Test</span></span>

<span data-ttu-id="bcc4b-119">Das Cmdlet "Test-CsIM" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="bcc4b-120">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="bcc4b-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="bcc4b-122">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="bcc4b-123">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsIM aufrufen:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="bcc4b-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="bcc4b-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bcc4b-125">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="bcc4b-125">Determining Success or Failure</span></span>

<span data-ttu-id="bcc4b-126">Wenn die beiden Benutzer eine Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="bcc4b-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bcc4b-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bcc4b-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bcc4b-128">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="bcc4b-128">Result : Success</span></span>

<span data-ttu-id="bcc4b-129">Latenz: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="bcc4b-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="bcc4b-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="bcc4b-130">Error :</span></span>

<span data-ttu-id="bcc4b-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="bcc4b-131">Diagnosis :</span></span>

<span data-ttu-id="bcc4b-132">Wenn die Testbenutzer die Sitzung nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bcc4b-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bcc4b-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bcc4b-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="bcc4b-134">Result : Failure</span></span>

<span data-ttu-id="bcc4b-135">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bcc4b-135">Latency : 00:00:00</span></span>

<span data-ttu-id="bcc4b-136">Fehler: 504, Server Timeout</span><span class="sxs-lookup"><span data-stu-id="bcc4b-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="bcc4b-137">Diagnose: errorCode = 2, Quelle = ATL-CS-001. "litwareinc. com, Reason = siehe</span><span class="sxs-lookup"><span data-stu-id="bcc4b-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="bcc4b-138">Antwortcode und Ursachen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-138">response code and reason phrase.</span></span>

<span data-ttu-id="bcc4b-139">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="bcc4b-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="bcc4b-140">Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="bcc4b-141">Sie können feststellen, ob eine SIP-Adresse gültig ist (und ob der Benutzer, der diese SIP-Adresse zugewiesen hat, für lync Server aktiviert wurde), indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="bcc4b-142">Wenn Test-CsIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="bcc4b-143">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der beiden Test Benutzer zur Teilnahme an einer Chatsitzung überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="bcc4b-144">Hier finden Sie beispielsweise eine Beispielausgabe, die auftritt, wenn eine falsche Gruppe von Benutzeranmeldeinformationen (in diesem Fall ein falsches Kennwort) für Test-CsIM bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="bcc4b-145">Registrierungsanfrage wird gesendet:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-145">Sending Registration request :</span></span>

<span data-ttu-id="bcc4b-146">Ziel-FQDN = ATL-CS-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bcc4b-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="bcc4b-147">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bcc4b-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="bcc4b-148">Registrar Port = 5061</span><span class="sxs-lookup"><span data-stu-id="bcc4b-148">Registrar Port = 5061</span></span>

<span data-ttu-id="bcc4b-149">Auth-Typ "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="bcc4b-150">Registrierungs Treffer für SIP/ATL-CS-001. "litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="bcc4b-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bcc4b-151">' Registrieren '-Aktivität abgeschlossen in ' 0,0601795 ' Sek.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="bcc4b-152">Eine Ausnahme "die Anmeldung wurde abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="bcc4b-153">Überprüfen Sie, ob die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="bcc4b-154">während des Workflows aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bcc4b-155">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="bcc4b-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="bcc4b-156">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsIM möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="bcc4b-157">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="bcc4b-158">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="bcc4b-159">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="bcc4b-160">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="bcc4b-161">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="bcc4b-162">Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="bcc4b-163">Mit lync Server können Sie das System so konfigurieren, dass Sofortnachrichten nicht verfügbar sind, wenn auf die Archivierungsdatenbank nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="bcc4b-164">Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="bcc4b-165">Wenn BlockOnArchiveFailure auf "true" festgelegt ist, sollten Sie ermitteln, ob die Archivierungsdatenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="bcc4b-166">Sie können die Speicherorte ihrer Archivierungsdatenbanken mithilfe des folgenden Befehls zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="bcc4b-167">Der Archivierungsserver steht möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-167">The Archiving server might not be available.</span></span> <span data-ttu-id="bcc4b-168">Mit diesem Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="bcc4b-169">Sie können dann den entsprechenden Server anpingen, um zu überprüfen, ob er verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="bcc4b-170">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bcc4b-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

