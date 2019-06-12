---
title: 'Lync Server 2013: Testen des Zugriffs auf mobile Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda2ec2d02fe4189c8e34cf700f6f1fd07895ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="f40be-102">Testen des Zugriffs von mobilen Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f40be-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f40be-103">_**Letztes Änderungsdatum des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="f40be-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f40be-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="f40be-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f40be-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="f40be-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f40be-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="f40be-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f40be-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f40be-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f40be-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f40be-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f40be-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="f40be-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f40be-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsMcxConference-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="f40be-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="f40be-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="f40be-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f40be-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f40be-112">Description</span></span>

<span data-ttu-id="f40be-113">Mit dem Mobilitätsdienst können Benutzer mobiler Geräte wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="f40be-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="f40be-114">Tauschen Sie Sofortnachrichten und Anwesenheitsinformationen aus.</span><span class="sxs-lookup"><span data-stu-id="f40be-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="f40be-115">Speichern und Abrufen von Voicemail intern und nicht mit Ihrem WLAN-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="f40be-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="f40be-116">Nutzen Sie die Vorteile von lync-Server Funktionen wie Anruf über Arbeit und Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="f40be-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="f40be-117">Das Cmdlet Test-CsMcxConference bietet eine schnelle und einfache Möglichkeit, um zu überprüfen, ob Benutzer teilnehmen und an lync Server-Konferenzen teilnehmen können, indem Sie ein mobiles Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="f40be-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f40be-118">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="f40be-118">Running the test</span></span>

<span data-ttu-id="f40be-119">Zum Ausführen dieser Prüfung müssen Sie für jedes Konto drei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="f40be-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f40be-120">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsMcxConference aufrufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f40be-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="f40be-121">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="f40be-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f40be-122">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="f40be-122">Determining success or failure</span></span>

<span data-ttu-id="f40be-123">Wenn die Überprüfung erfolgreich ist, wird in Test-CsMcxConference ein Testergebnis von Success gemeldet:</span><span class="sxs-lookup"><span data-stu-id="f40be-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="f40be-124">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f40be-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f40be-125">Ziel-URI:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="f40be-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="f40be-126">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="f40be-126">Result : Success</span></span>

<span data-ttu-id="f40be-127">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f40be-127">Latency : 00:00:00</span></span>

<span data-ttu-id="f40be-128">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="f40be-128">Error Message :</span></span>

<span data-ttu-id="f40be-129">Diagnose</span><span class="sxs-lookup"><span data-stu-id="f40be-129">Diagnosis :</span></span>

<span data-ttu-id="f40be-130">Wenn die Überprüfung nicht erfolgreich ist, meldet CsMcxConference ein Testergebnis des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="f40be-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="f40be-131">Dieses Testergebnis wird in der Regel von einer detaillierten Fehlermeldung und Diagnose begleitet.</span><span class="sxs-lookup"><span data-stu-id="f40be-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="f40be-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f40be-132">For example:</span></span>

<span data-ttu-id="f40be-133">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f40be-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f40be-134">Ziel-URI:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="f40be-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="f40be-135">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="f40be-135">Result : Failure</span></span>

<span data-ttu-id="f40be-136">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f40be-136">Latency : 00:00:00</span></span>

<span data-ttu-id="f40be-137">Fehlermeldung: beim Web-Ticket-Service wurde keine Antwort empfangen.</span><span class="sxs-lookup"><span data-stu-id="f40be-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="f40be-138">Innere Ausnahme: die HHTP-Anforderung ist mit dem Client nicht autorisiert</span><span class="sxs-lookup"><span data-stu-id="f40be-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="f40be-139">Aushandlungs Schema "NTLM".</span><span class="sxs-lookup"><span data-stu-id="f40be-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="f40be-140">Der empfangene Authentifizierungsheader</span><span class="sxs-lookup"><span data-stu-id="f40be-140">The authentication header received</span></span>

<span data-ttu-id="f40be-141">vom Server war "Negotiate".</span><span class="sxs-lookup"><span data-stu-id="f40be-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="f40be-142">Innere Ausnahme: der Remoteserver hat einen Fehler zurückgegeben: (401)</span><span class="sxs-lookup"><span data-stu-id="f40be-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="f40be-143">Unbefugte.</span><span class="sxs-lookup"><span data-stu-id="f40be-143">Unauthorized.</span></span>

<span data-ttu-id="f40be-144">Diagnose</span><span class="sxs-lookup"><span data-stu-id="f40be-144">Diagnosis :</span></span>

<span data-ttu-id="f40be-145">Innere Diagnose: X-MS-Server-Fqdb: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f40be-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f40be-146">Cache-Control: privat</span><span class="sxs-lookup"><span data-stu-id="f40be-146">Cache-Control : private</span></span>

<span data-ttu-id="f40be-147">Content-Type: Text/HTML; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f40be-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="f40be-148">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="f40be-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="f40be-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="f40be-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="f40be-150">X-powered-by: ASP.net</span><span class="sxs-lookup"><span data-stu-id="f40be-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="f40be-151">X-Content-Type-Optionen: nosniff</span><span class="sxs-lookup"><span data-stu-id="f40be-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="f40be-152">Datum: Wed, 28 May 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="f40be-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="f40be-153">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="f40be-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f40be-154">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="f40be-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="f40be-155">Wenn Test-CsMcxConference fehlschlägt, sollten Sie zunächst überprüfen, ob der Mobilitätsdienst ausgeführt wird und zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f40be-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="f40be-156">Dies kann mithilfe eines Webbrowsers erfolgen, um zu überprüfen, ob auf die Mobilitätsdienst-URL für Ihren lync Server-Pool zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f40be-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="f40be-157">Mit diesem Befehl wird beispielsweise die URL für den Pool ATL-CS-001.litwareinc.com überprüft:</span><span class="sxs-lookup"><span data-stu-id="f40be-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="f40be-158">Wenn Sie auf den Mobilitätsdienst zugreifen können, sollten Sie sicherstellen, dass die Testbenutzer über gültige lync Server-Konten verfügen.</span><span class="sxs-lookup"><span data-stu-id="f40be-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="f40be-159">Sie können Kontoinformationen abrufen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="f40be-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="f40be-160">Wenn die Enabled-Eigenschaft nicht gleich true ist oder der Befehl fehlschlägt, bedeutet dies, dass der Benutzer kein gültiges lync Server-Konto hat. Sie sollten auch sicherstellen, dass jedes Benutzerkonto für Mobilität aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f40be-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="f40be-161">Ermitteln Sie dazu zunächst die Mobilitätsrichtlinie, die dem Konto zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="f40be-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="f40be-162">Nachdem Sie den Richtliniennamen kennen, verwenden Sie das Cmdlet Get-CsMobilityPolicy, um zu überprüfen, ob die fragliche Richtlinie (beispielsweise RedmondMobilityPolicy) die EnableMobility-Eigenschaft auf true festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="f40be-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="f40be-163">Wenn Sie beim Ausführen von Test-CsMcxConference eine Fehlermeldung "Authentifizierungsheader" erhalten, die häufig bedeutet, dass Sie kein gültiges Benutzerkonto angegeben haben, überprüfen Sie den Benutzernamen und das Kennwort, und versuchen Sie dann erneut, den Test zu testen.</span><span class="sxs-lookup"><span data-stu-id="f40be-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="f40be-164">Wenn Sie davon überzeugt sind, dass das Benutzerkonto gültig ist, verwenden Sie das Cmdlet Get-CsWebServiceConfiguration, und überprüfen Sie den Wert der UseWindowsAuth-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f40be-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="f40be-165">Damit erfahren Sie, welche Authentifizierungsmethoden in Ihrer Organisation aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f40be-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="f40be-166">Weitere Tipps zur Problembehandlung beim Mobilitätsdienst finden Sie im Blogbeitrag zur [Problembehandlung von externen lync-Mobilitäts Verbindungsproblemen Schritt-für-Schritt](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="f40be-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

