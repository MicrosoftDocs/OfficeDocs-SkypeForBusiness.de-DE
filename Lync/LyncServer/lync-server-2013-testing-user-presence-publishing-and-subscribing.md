---
title: 'Lync Server 2013: Testen der Benutzer Anwesenheits Veröffentlichung und-Anmeldung'
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
ms.openlocfilehash: 4d506ed0115fd5346048ff8870763a7ffc888a69
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="bcf62-102">Testen der Veröffentlichung und des Abonnierens von Benutzeranwesenheitsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcf62-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcf62-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bcf62-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcf62-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="bcf62-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bcf62-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="bcf62-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcf62-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="bcf62-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bcf62-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcf62-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcf62-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bcf62-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bcf62-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="bcf62-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bcf62-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPresence-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="bcf62-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="bcf62-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="bcf62-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bcf62-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcf62-112">Description</span></span>

<span data-ttu-id="bcf62-113">Test-CsPresence wird verwendet, um zu ermitteln, ob ein paar Testbenutzer sich bei lync Server anmelden und dann Anwesenheitsinformationen austauschen können.</span><span class="sxs-lookup"><span data-stu-id="bcf62-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="bcf62-114">Dazu protokolliert das Cmdlet zunächst die beiden Benutzer am System.</span><span class="sxs-lookup"><span data-stu-id="bcf62-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="bcf62-115">Wenn beide Anmeldungen erfolgreich sind, werden Sie vom ersten Testbenutzer aufgefordert, Anwesenheitsinformationen des zweiten Benutzers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bcf62-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="bcf62-116">Der zweite Benutzer veröffentlicht diese Informationen, und Test-CsPresence überprüft, ob die Informationen erfolgreich an den ersten Benutzer übertragen wurden.</span><span class="sxs-lookup"><span data-stu-id="bcf62-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="bcf62-117">Nach dem Austausch von Anwesenheitsinformationen werden die beiden Testbenutzer dann von lync Server abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="bcf62-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bcf62-118">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="bcf62-118">Running the test</span></span>

<span data-ttu-id="bcf62-119">Das Cmdlet "Test-CsPresence" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="bcf62-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="bcf62-120">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="bcf62-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="bcf62-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bcf62-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="bcf62-122">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="bcf62-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="bcf62-123">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsPresence aufrufen:</span><span class="sxs-lookup"><span data-stu-id="bcf62-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="bcf62-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="bcf62-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bcf62-125">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="bcf62-125">Determining success or failure</span></span>

<span data-ttu-id="bcf62-126">Wenn die angegebenen Benutzeranwesenheitsinformationen austauschen können, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="bcf62-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bcf62-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bcf62-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bcf62-128">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="bcf62-128">Result : Success</span></span>

<span data-ttu-id="bcf62-129">Latenz: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="bcf62-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="bcf62-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="bcf62-130">Error :</span></span>

<span data-ttu-id="bcf62-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="bcf62-131">Diagnosis :</span></span>

<span data-ttu-id="bcf62-132">Wenn die beiden Benutzer keine Anwesenheitsinformationen austauschen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="bcf62-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bcf62-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bcf62-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bcf62-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="bcf62-134">Result : Failure</span></span>

<span data-ttu-id="bcf62-135">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bcf62-135">Latency : 00:00:00</span></span>

<span data-ttu-id="bcf62-136">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="bcf62-136">Error : 404, Not Found</span></span>

<span data-ttu-id="bcf62-137">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="bcf62-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="bcf62-138">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="bcf62-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="bcf62-139">existieren.</span><span class="sxs-lookup"><span data-stu-id="bcf62-139">exist.</span></span>

<span data-ttu-id="bcf62-140">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="bcf62-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="bcf62-141">In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, da mindestens eines der beiden Benutzerkonten ungültig ist: entweder ist das Konto nicht vorhanden, oder es wurde nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bcf62-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="bcf62-142">Sie können überprüfen, ob die Konten vorhanden sind, und ermitteln, ob Sie für lync Server aktiviert sind, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="bcf62-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="bcf62-143">Wenn Test-CsPresence fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="bcf62-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="bcf62-144">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPresence eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="bcf62-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="bcf62-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bcf62-145">For example:</span></span>

<span data-ttu-id="bcf62-146">Anmeldungsanfrage gegen unbekannt getroffen</span><span class="sxs-lookup"><span data-stu-id="bcf62-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="bcf62-147">' Registrieren '-Aktivität abgeschlossen in ' 0,0345791 ' Sek.</span><span class="sxs-lookup"><span data-stu-id="bcf62-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="bcf62-148">Die Aktivität "SelfSubscribeActivity" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="bcf62-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="bcf62-149">"SelfSubscribeActivity"-Aktivität wurde in "0,0041174" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bcf62-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="bcf62-150">Die Aktivität "SubscribePresence" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="bcf62-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="bcf62-151">"SubscribePresence"-Aktivität wurde in "0,0038764" Sek. abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bcf62-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="bcf62-152">Die Aktivität "PublishPresence" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="bcf62-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="bcf62-153">Die Anwesenheits Benachrichtigung einer Ausnahme wird nicht innerhalb von 25 Sekunden empfangen.</span><span class="sxs-lookup"><span data-stu-id="bcf62-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="bcf62-154">bereut-Workflow Microsoft. RTC. SyntheticTransactions. Workflows. STPresenceWorkflow-Ausführung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bcf62-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="bcf62-155">Die Tatsache, dass die Anwesenheits Benachrichtigung nicht innerhalb von 25 Sekunden empfangen wurde, kann darauf hindeuten, dass Netzwerkprobleme das Austauschen von Informationen verhindern.</span><span class="sxs-lookup"><span data-stu-id="bcf62-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bcf62-156">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="bcf62-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="bcf62-157">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsPresence möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="bcf62-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="bcf62-158">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="bcf62-158">You specified an incorrect user account.</span></span> <span data-ttu-id="bcf62-159">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="bcf62-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="bcf62-160">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bcf62-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="bcf62-161">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="bcf62-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="bcf62-162">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bcf62-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

