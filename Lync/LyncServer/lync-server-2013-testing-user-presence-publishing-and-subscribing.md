---
title: 'Lync Server 2013: Testen der Veröffentlichung und des Abonnierens von Benutzer Anwesenheit'
description: 'Lync Server 2013: Testen der Veröffentlichung von Benutzer Anwesenheit und abonnieren.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90913f270fbd034ca4d2ea7cf3b93c255fc95c66
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541851"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="27194-103">Testen der Veröffentlichung von Benutzer Anwesenheit und abonnieren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27194-103">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27194-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="27194-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27194-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="27194-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="27194-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="27194-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27194-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="27194-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="27194-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27194-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27194-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="27194-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="27194-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="27194-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="27194-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPresence-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="27194-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="27194-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="27194-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="27194-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27194-113">Description</span></span>

<span data-ttu-id="27194-114">Test-CsPresence wird verwendet, um zu bestimmen, ob ein paar von Testbenutzern sich bei lync Server anmelden und dann Anwesenheitsinformationen austauschen kann.</span><span class="sxs-lookup"><span data-stu-id="27194-114">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="27194-115">Hierzu meldet das Cmdlet die beiden Benutzer zunächst am System an.</span><span class="sxs-lookup"><span data-stu-id="27194-115">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="27194-116">Wenn beide erfolgreich angemeldet werden können, fordert der erste Testbenutzer Anwesenheitsinformationen vom zweiten Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="27194-116">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="27194-117">Der zweite Benutzer veröffentlicht diese Informationen, und mit Test-CsPresence wird geprüft, ob die Informationen erfolgreich an den ersten Benutzer übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="27194-117">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="27194-118">Nach dem Austausch von Anwesenheitsinformationen werden die beiden Testbenutzer dann von lync Server abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="27194-118">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="27194-119">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="27194-119">Running the test</span></span>

<span data-ttu-id="27194-120">Das Test-CsPresence-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="27194-120">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="27194-121">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="27194-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="27194-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="27194-122">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="27194-123">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="27194-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="27194-124">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsPresence aufrufen:</span><span class="sxs-lookup"><span data-stu-id="27194-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="27194-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="27194-125">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="27194-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="27194-126">Determining success or failure</span></span>

<span data-ttu-id="27194-127">Wenn die angegebenen Benutzeranwesenheitsinformationen austauschen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="27194-127">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="27194-128">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27194-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27194-129">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="27194-129">Result : Success</span></span>

<span data-ttu-id="27194-130">Wartezeit: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="27194-130">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="27194-131">Fehler</span><span class="sxs-lookup"><span data-stu-id="27194-131">Error :</span></span>

<span data-ttu-id="27194-132">Diagnose</span><span class="sxs-lookup"><span data-stu-id="27194-132">Diagnosis :</span></span>

<span data-ttu-id="27194-133">Wenn die beiden Benutzer keine Anwesenheitsinformationen austauschen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="27194-133">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="27194-134">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27194-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27194-135">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="27194-135">Result : Failure</span></span>

<span data-ttu-id="27194-136">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="27194-136">Latency : 00:00:00</span></span>

<span data-ttu-id="27194-137">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="27194-137">Error : 404, Not Found</span></span>

<span data-ttu-id="27194-138">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="27194-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="27194-139">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="27194-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="27194-140">existieren.</span><span class="sxs-lookup"><span data-stu-id="27194-140">exist.</span></span>

<span data-ttu-id="27194-141">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="27194-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="27194-142">In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, da mindestens eines der beiden Benutzerkonten ungültig ist: entweder ist das Konto nicht vorhanden oder es wurde nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="27194-142">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="27194-143">Sie können überprüfen, ob die Konten vorhanden sind, und bestimmen, ob Sie für lync Server aktiviert sind, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="27194-143">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="27194-144">Wenn Test-CsPresence fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="27194-144">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="27194-145">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPresence eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="27194-145">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="27194-146">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="27194-146">For example:</span></span>

<span data-ttu-id="27194-147">Registrierungs Anforderungs Treffer gegen unbekannt</span><span class="sxs-lookup"><span data-stu-id="27194-147">Registration Request hit against Unknown</span></span>

<span data-ttu-id="27194-148">"Registrierung"-Aktivität abgeschlossen in "0,0345791" Sek.</span><span class="sxs-lookup"><span data-stu-id="27194-148">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="27194-149">"SelfSubscribeActivity"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="27194-149">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="27194-150">"SelfSubscribeActivity"-Aktivität wurde in "0,0041174" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="27194-150">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="27194-151">"SubscribePresence"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="27194-151">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="27194-152">"SubscribePresence"-Aktivität wurde in "0,0038764" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="27194-152">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="27194-153">"PublishPresence"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="27194-153">'PublishPresence' activity started.</span></span>

<span data-ttu-id="27194-154">Eine Ausnahme "Anwesenheits Benachrichtigung wird nicht innerhalb von 25 Sekunden empfangen."</span><span class="sxs-lookup"><span data-stu-id="27194-154">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="27194-155">bereut Workflow "Microsoft. RTC. SyntheticTransactions. Workflows. STPresenceWorkflow-Ausführung" aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="27194-155">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="27194-156">Die Tatsache, dass die Anwesenheits Benachrichtigung nicht innerhalb von 25 Sekunden empfangen wurde, deutet möglicherweise darauf hin, dass Netzwerkprobleme das Austauschen von Informationen verhindern.</span><span class="sxs-lookup"><span data-stu-id="27194-156">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="27194-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="27194-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="27194-158">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsPresence Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="27194-158">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="27194-159">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="27194-159">You specified an incorrect user account.</span></span> <span data-ttu-id="27194-160">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="27194-160">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="27194-161">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="27194-161">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="27194-162">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="27194-162">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="27194-163">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27194-163">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

