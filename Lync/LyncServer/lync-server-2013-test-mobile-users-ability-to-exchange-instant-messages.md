---
title: 'Lync Server 2013: Testen der Fähigkeit von mobilen Benutzern zum Austauschen von Chatnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5885ed34fd28f06b9a7d8c4f95abc29d3b5e147
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="26c7d-102">Testen der Fähigkeit von mobilen Benutzern zum Austauschen von Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26c7d-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26c7d-103">_**Letztes Änderungsstand des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="26c7d-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26c7d-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="26c7d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="26c7d-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="26c7d-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26c7d-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="26c7d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="26c7d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26c7d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26c7d-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="26c7d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="26c7d-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="26c7d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="26c7d-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsMcxP2PIM verfügt.</span><span class="sxs-lookup"><span data-stu-id="26c7d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="26c7d-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="26c7d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="26c7d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26c7d-112">Description</span></span>

<span data-ttu-id="26c7d-113">Mit dem Mobilitätsdienst können Benutzer mobiler Geräte folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="26c7d-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="26c7d-114">Exchange-Sofortnachrichten und Anwesenheitsinformationen.</span><span class="sxs-lookup"><span data-stu-id="26c7d-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="26c7d-115">Speichern und Abrufen von Voicemail intern statt mit Ihrem drahtlosen Anbieter.</span><span class="sxs-lookup"><span data-stu-id="26c7d-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="26c7d-116">Nutzen Sie lync Server Funktionen wie "Anruf über Arbeit" und "Einwahlkonferenzen".</span><span class="sxs-lookup"><span data-stu-id="26c7d-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="26c7d-117">Das Cmdlet Test-CsMxcP2PIM bietet eine schnelle und einfache Möglichkeit, um sicherzustellen, dass Benutzer den Mobilitätsdienst zum Austauschen von Sofortnachrichten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="26c7d-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="26c7d-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="26c7d-118">Running the test</span></span>

<span data-ttu-id="26c7d-119">Zum Ausführen dieses Tests müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="26c7d-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="26c7d-120">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsMcxP2PIM aufrufen:</span><span class="sxs-lookup"><span data-stu-id="26c7d-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="26c7d-121">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="26c7d-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="26c7d-122">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="26c7d-122">Determining success or failure</span></span>

<span data-ttu-id="26c7d-123">Wenn die beiden Testbenutzer Chatnachrichten mithilfe des mobilitätsdiensts austauschen können, gibt Test-CsMcxP2PIM Testergebnis Erfolg zurück:</span><span class="sxs-lookup"><span data-stu-id="26c7d-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="26c7d-124">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="26c7d-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="26c7d-125">Ziel-URI:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="26c7d-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="26c7d-126">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="26c7d-126">Result : Success</span></span>

<span data-ttu-id="26c7d-127">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="26c7d-127">Latency : 00:00:00</span></span>

<span data-ttu-id="26c7d-128">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="26c7d-128">Error Message :</span></span>

<span data-ttu-id="26c7d-129">Diagnose</span><span class="sxs-lookup"><span data-stu-id="26c7d-129">Diagnosis :</span></span>

<span data-ttu-id="26c7d-130">Wenn der Test fehlschlägt, wird das Ergebnis auf "Failure" festgelegt, und es wird eine ausführliche Fehlermeldung und Diagnose angezeigt:</span><span class="sxs-lookup"><span data-stu-id="26c7d-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="26c7d-131">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="26c7d-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="26c7d-132">Ziel-URI:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="26c7d-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="26c7d-133">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="26c7d-133">Result : Failure</span></span>

<span data-ttu-id="26c7d-134">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="26c7d-134">Latency : 00:00:00</span></span>

<span data-ttu-id="26c7d-135">Fehlermeldung: Es wurde keine Antwort für den WebTICKET Dienst empfangen.</span><span class="sxs-lookup"><span data-stu-id="26c7d-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="26c7d-136">Innere Ausnahme: die HHTP-Anforderung ist nicht autorisiert mit</span><span class="sxs-lookup"><span data-stu-id="26c7d-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="26c7d-137">Client-Aushandlungs Schema ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="26c7d-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="26c7d-138">Die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="26c7d-138">The authentication</span></span>

<span data-ttu-id="26c7d-139">vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".</span><span class="sxs-lookup"><span data-stu-id="26c7d-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="26c7d-140">Innere Ausnahme: der Remoteserver hat einen Fehler zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="26c7d-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="26c7d-141">(401) nicht autorisiert.</span><span class="sxs-lookup"><span data-stu-id="26c7d-141">(401) Unauthorized.</span></span>

<span data-ttu-id="26c7d-142">Diagnose</span><span class="sxs-lookup"><span data-stu-id="26c7d-142">Diagnosis :</span></span>

<span data-ttu-id="26c7d-143">Innere Diagnose: X-MS-Server-Fqdb: ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="26c7d-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="26c7d-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="26c7d-144">001.litwareinc.com</span></span>

<span data-ttu-id="26c7d-145">Cache-Control: privat</span><span class="sxs-lookup"><span data-stu-id="26c7d-145">Cache-Control : private</span></span>

<span data-ttu-id="26c7d-146">Content-Type: Text/HTML; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="26c7d-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="26c7d-147">Server: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="26c7d-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="26c7d-148">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="26c7d-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="26c7d-149">X-powered by: ASP.net</span><span class="sxs-lookup"><span data-stu-id="26c7d-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="26c7d-150">X-Content-Type-Optionen: nosniff</span><span class="sxs-lookup"><span data-stu-id="26c7d-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="26c7d-151">Date: Mi, 28 May 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="26c7d-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="26c7d-152">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="26c7d-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="26c7d-153">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="26c7d-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="26c7d-154">Wenn Test-CsMcxP2PIM fehlschlägt, sollte der erste Schritt sein, um zu überprüfen, ob der Mobilitätsdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26c7d-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="26c7d-155">Dies kann mithilfe eines Webbrowsers erfolgen, um sicherzustellen, dass auf die Mobilitätsdienst-URL für Ihren lync Server-Pool zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="26c7d-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="26c7d-156">Mit diesem Befehl wird beispielsweise die URL für die ATL-CS-001.litwareinc.com des Pools überprüft:</span><span class="sxs-lookup"><span data-stu-id="26c7d-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="26c7d-157">Wenn der Mobilitätsdienst scheinbar ausgeführt wird, stellen Sie sicher, dass Ihre beiden Testbenutzer über gültige lync Server Konten verfügen.</span><span class="sxs-lookup"><span data-stu-id="26c7d-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="26c7d-158">Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="26c7d-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="26c7d-159">Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="26c7d-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="26c7d-160">Sie sollten auch sicherstellen, dass der Benutzer für Mobilität aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="26c7d-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="26c7d-161">Ermitteln Sie dazu zunächst die Mobilitätsrichtlinie, die dem Konto zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="26c7d-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="26c7d-162">Nachdem Sie den Richtliniennamen kennen, verwenden Sie das Cmdlet Get-CsMobilityPolicy, um zu überprüfen, ob die betreffende Richtlinie (beispielsweise RedmondMobilityPolicy) die EnableMobility-Eigenschaft auf true festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="26c7d-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="26c7d-163">Wenn Sie eine Fehlermeldung mit Authentifizierungs Headern erhalten, bedeutet dies häufig, dass Sie kein gültiges Benutzerkonto angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="26c7d-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="26c7d-164">Überprüfen Sie den Benutzernamen und das Kennwort, und führen Sie den Test erneut aus.</span><span class="sxs-lookup"><span data-stu-id="26c7d-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="26c7d-165">Wenn Sie davon überzeugt sind, dass das Benutzerkonto gültig ist, verwenden Sie das Cmdlet Get-CsWebServiceConfiguration, und überprüfen Sie den Wert der UseWindowsAuth-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="26c7d-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="26c7d-166">Dadurch erfahren Sie, welche Authentifizierungsmethoden in Ihrer Organisation aktiviert sind. Weitere Tipps zur Problembehandlung für den Mobilitätsdienst finden Sie im Blogbeitrag [Troubleshooting External lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="26c7d-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

