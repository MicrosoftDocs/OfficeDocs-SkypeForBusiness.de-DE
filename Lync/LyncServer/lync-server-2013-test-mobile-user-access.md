---
title: 'Lync Server 2013: Testen des Zugriffs durch mobile Benutzer'
description: 'Lync Server 2013: Testen des Zugriffs durch mobile Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541871"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="62106-103">Testen des Zugriffs auf mobile Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62106-103">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62106-104">_**Letztes Änderungsstand des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="62106-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62106-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="62106-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="62106-106">Monatlich</span><span class="sxs-lookup"><span data-stu-id="62106-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62106-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="62106-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="62106-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62106-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62106-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="62106-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="62106-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="62106-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="62106-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsMcxConference-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="62106-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="62106-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="62106-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="62106-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62106-113">Description</span></span>

<span data-ttu-id="62106-114">Mit dem Mobilitätsdienst können Benutzer mobiler Geräte folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="62106-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="62106-115">Exchange-Sofortnachrichten und Anwesenheitsinformationen.</span><span class="sxs-lookup"><span data-stu-id="62106-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="62106-116">Speichern und Abrufen von Voicemail intern statt mit Ihrem drahtlosen Anbieter.</span><span class="sxs-lookup"><span data-stu-id="62106-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="62106-117">Nutzen Sie lync Server Funktionen wie "Anruf über Arbeit" und "Einwahlkonferenzen".</span><span class="sxs-lookup"><span data-stu-id="62106-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="62106-118">Das Test-CsMcxConference-Cmdlet bietet eine schnelle und einfache Möglichkeit zu überprüfen, ob Benutzer an lync Server Konferenzen teilnehmen können, indem Sie ein mobiles Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="62106-118">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="62106-119">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="62106-119">Running the test</span></span>

<span data-ttu-id="62106-120">Um diese Prüfung auszuführen, müssen Sie drei Windows PowerShell Credential-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="62106-120">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="62106-121">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsMcxConference aufrufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="62106-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="62106-122">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="62106-122">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="62106-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="62106-123">Determining success or failure</span></span>

<span data-ttu-id="62106-124">Wenn die Überprüfung erfolgreich verläuft, meldet Test-CsMcxConference ein Testergebnis von Success:</span><span class="sxs-lookup"><span data-stu-id="62106-124">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="62106-125">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="62106-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="62106-126">Ziel-URI: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="62106-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="62106-127">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="62106-127">Result : Success</span></span>

<span data-ttu-id="62106-128">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="62106-128">Latency : 00:00:00</span></span>

<span data-ttu-id="62106-129">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="62106-129">Error Message :</span></span>

<span data-ttu-id="62106-130">Diagnose</span><span class="sxs-lookup"><span data-stu-id="62106-130">Diagnosis :</span></span>

<span data-ttu-id="62106-131">Wenn die Überprüfung nicht erfolgreich war Test-CsMcxConference meldet ein Testergebnis eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="62106-131">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="62106-132">Dieses Testergebnis wird in der Regel von einer detaillierten Fehlermeldung und Diagnose begleitet.</span><span class="sxs-lookup"><span data-stu-id="62106-132">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="62106-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62106-133">For example:</span></span>

<span data-ttu-id="62106-134">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="62106-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="62106-135">Ziel-URI: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="62106-135">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="62106-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="62106-136">Result : Failure</span></span>

<span data-ttu-id="62106-137">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="62106-137">Latency : 00:00:00</span></span>

<span data-ttu-id="62106-138">Fehlermeldung: für Web-Ticket Dienst wurde keine Antwort empfangen.</span><span class="sxs-lookup"><span data-stu-id="62106-138">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="62106-139">Innere Ausnahme: die HHTP-Anforderung ist mit dem Client nicht autorisiert</span><span class="sxs-lookup"><span data-stu-id="62106-139">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="62106-140">Aushandlungs Schema ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="62106-140">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="62106-141">Der empfangene Authentifizierungsheader</span><span class="sxs-lookup"><span data-stu-id="62106-141">The authentication header received</span></span>

<span data-ttu-id="62106-142">auf dem Server war "aushandeln".</span><span class="sxs-lookup"><span data-stu-id="62106-142">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="62106-143">Innere Ausnahme: der Remoteserver hat einen Fehler zurückgegeben: (401)</span><span class="sxs-lookup"><span data-stu-id="62106-143">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="62106-144">Unbefugte.</span><span class="sxs-lookup"><span data-stu-id="62106-144">Unauthorized.</span></span>

<span data-ttu-id="62106-145">Diagnose</span><span class="sxs-lookup"><span data-stu-id="62106-145">Diagnosis :</span></span>

<span data-ttu-id="62106-146">Innere Diagnose: X-MS-Server-Fqdb: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="62106-146">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="62106-147">Cache-Control: privat</span><span class="sxs-lookup"><span data-stu-id="62106-147">Cache-Control : private</span></span>

<span data-ttu-id="62106-148">Content-Type: Text/HTML; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="62106-148">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="62106-149">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="62106-149">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="62106-150">WWW-Authenticate: aushandeln, NTLM</span><span class="sxs-lookup"><span data-stu-id="62106-150">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="62106-151">X-powered by: ASP.net</span><span class="sxs-lookup"><span data-stu-id="62106-151">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="62106-152">X-Content-Type-Optionen: nosniff</span><span class="sxs-lookup"><span data-stu-id="62106-152">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="62106-153">Date: Mi, 28 May 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="62106-153">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="62106-154">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="62106-154">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="62106-155">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="62106-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="62106-156">Wenn Test-CsMcxConference fehlschlägt, sollten Sie zunächst überprüfen, ob der Mobilitätsdienst ausgeführt wird und auf den zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="62106-156">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="62106-157">Dies kann mithilfe eines Webbrowsers erfolgen, um sicherzustellen, dass auf die Mobilitätsdienst-URL für Ihren lync Server-Pool zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="62106-157">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="62106-158">Mit diesem Befehl wird beispielsweise die URL für die ATL-CS-001.litwareinc.com des Pools überprüft:</span><span class="sxs-lookup"><span data-stu-id="62106-158">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="62106-159">Wenn Sie auf den Mobilitätsdienst zugreifen können, sollten Sie sicherstellen, dass Ihre Testbenutzer über gültige lync Server Konten verfügen.</span><span class="sxs-lookup"><span data-stu-id="62106-159">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="62106-160">Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="62106-160">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="62106-161">Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt. Sie sollten auch sicherstellen, dass jedes Benutzerkonto für Mobility aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="62106-161">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="62106-162">Ermitteln Sie dazu zunächst die Mobilitätsrichtlinie, die dem Konto zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="62106-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="62106-163">Nachdem Sie den Richtliniennamen kennen, verwenden Sie das Get-CsMobilityPolicy-Cmdlet, um zu überprüfen, ob die fragliche Richtlinie (beispielsweise RedmondMobilityPolicy) die EnableMobility-Eigenschaft auf true festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="62106-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="62106-164">Wenn Sie eine Fehlermeldung "Authentifizierungsheader" erhalten, wenn Sie Test-CsMcxConference ausführen, die häufig bedeutet, dass Sie kein gültiges Benutzerkonto angegeben haben, überprüfen Sie den Benutzernamen und das Kennwort, und testen Sie den Test erneut.</span><span class="sxs-lookup"><span data-stu-id="62106-164">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="62106-165">Wenn Sie davon überzeugt sind, dass das Benutzerkonto gültig ist, verwenden Sie das Get-CsWebServiceConfiguration-Cmdlet, und überprüfen Sie den Wert der UseWindowsAuth-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="62106-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="62106-166">Dadurch erfahren Sie, welche Authentifizierungsmethoden in Ihrer Organisation aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="62106-166">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="62106-167">Weitere Tipps zur Problembehandlung für den Mobilitätsdienst finden Sie im Blogbeitrag [Troubleshooting External lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="62106-167">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

