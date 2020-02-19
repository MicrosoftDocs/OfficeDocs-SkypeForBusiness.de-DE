---
title: 'Lync Server 2013: Testen der Veröffentlichung und des Abonnierens von Benutzer Anwesenheit'
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
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="55086-102">Testen der Veröffentlichung von Benutzer Anwesenheit und abonnieren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55086-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55086-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="55086-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55086-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="55086-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="55086-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="55086-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55086-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="55086-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="55086-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55086-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55086-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="55086-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="55086-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="55086-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="55086-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsPresence verfügt.</span><span class="sxs-lookup"><span data-stu-id="55086-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="55086-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="55086-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="55086-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55086-112">Description</span></span>

<span data-ttu-id="55086-113">Test-CsPresence wird verwendet, um zu bestimmen, ob ein paar von Testbenutzern sich bei lync Server anmelden und dann Anwesenheitsinformationen austauschen kann.</span><span class="sxs-lookup"><span data-stu-id="55086-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="55086-114">Hierzu meldet das Cmdlet die beiden Benutzer zunächst am System an.</span><span class="sxs-lookup"><span data-stu-id="55086-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="55086-115">Wenn beide erfolgreich angemeldet werden können, fordert der erste Testbenutzer Anwesenheitsinformationen vom zweiten Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="55086-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="55086-116">Der zweite Benutzer veröffentlicht diese Informationen, und mit Test-CsPresence wird geprüft, ob die Informationen erfolgreich an den ersten Benutzer übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="55086-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="55086-117">Nach dem Austausch von Anwesenheitsinformationen werden die beiden Testbenutzer dann von lync Server abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="55086-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="55086-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="55086-118">Running the test</span></span>

<span data-ttu-id="55086-119">Das Cmdlet Test-CsPresence kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="55086-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="55086-120">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="55086-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="55086-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="55086-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="55086-122">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="55086-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="55086-123">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsPresence aufrufen:</span><span class="sxs-lookup"><span data-stu-id="55086-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="55086-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="55086-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="55086-125">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="55086-125">Determining success or failure</span></span>

<span data-ttu-id="55086-126">Wenn die angegebenen Benutzeranwesenheitsinformationen austauschen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="55086-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="55086-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55086-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="55086-128">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="55086-128">Result : Success</span></span>

<span data-ttu-id="55086-129">Wartezeit: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="55086-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="55086-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="55086-130">Error :</span></span>

<span data-ttu-id="55086-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="55086-131">Diagnosis :</span></span>

<span data-ttu-id="55086-132">Wenn die beiden Benutzer keine Anwesenheitsinformationen austauschen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="55086-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="55086-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55086-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="55086-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="55086-134">Result : Failure</span></span>

<span data-ttu-id="55086-135">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55086-135">Latency : 00:00:00</span></span>

<span data-ttu-id="55086-136">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="55086-136">Error : 404, Not Found</span></span>

<span data-ttu-id="55086-137">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="55086-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="55086-138">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="55086-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="55086-139">existieren.</span><span class="sxs-lookup"><span data-stu-id="55086-139">exist.</span></span>

<span data-ttu-id="55086-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="55086-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="55086-141">In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, da mindestens eines der beiden Benutzerkonten ungültig ist: entweder ist das Konto nicht vorhanden oder es wurde nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="55086-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="55086-142">Sie können überprüfen, ob die Konten vorhanden sind, und bestimmen, ob Sie für lync Server aktiviert sind, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="55086-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="55086-143">Wenn Test-CsPresence fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="55086-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="55086-144">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPresence eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="55086-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="55086-145">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="55086-145">For example:</span></span>

<span data-ttu-id="55086-146">Registrierungs Anforderungs Treffer gegen unbekannt</span><span class="sxs-lookup"><span data-stu-id="55086-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="55086-147">"Registrierung"-Aktivität abgeschlossen in "0,0345791" Sek.</span><span class="sxs-lookup"><span data-stu-id="55086-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="55086-148">"SelfSubscribeActivity"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="55086-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="55086-149">"SelfSubscribeActivity"-Aktivität wurde in "0,0041174" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="55086-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="55086-150">"SubscribePresence"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="55086-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="55086-151">"SubscribePresence"-Aktivität wurde in "0,0038764" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="55086-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="55086-152">"PublishPresence"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="55086-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="55086-153">Eine Ausnahme "Anwesenheits Benachrichtigung wird nicht innerhalb von 25 Sekunden empfangen."</span><span class="sxs-lookup"><span data-stu-id="55086-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="55086-154">bereut Workflow "Microsoft. RTC. SyntheticTransactions. Workflows. STPresenceWorkflow-Ausführung" aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="55086-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="55086-155">Die Tatsache, dass die Anwesenheits Benachrichtigung nicht innerhalb von 25 Sekunden empfangen wurde, deutet möglicherweise darauf hin, dass Netzwerkprobleme das Austauschen von Informationen verhindern.</span><span class="sxs-lookup"><span data-stu-id="55086-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="55086-156">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="55086-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="55086-157">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsPresence möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="55086-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="55086-158">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="55086-158">You specified an incorrect user account.</span></span> <span data-ttu-id="55086-159">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="55086-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="55086-160">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="55086-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="55086-161">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="55086-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="55086-162">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="55086-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

