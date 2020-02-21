---
title: 'Lync Server 2013: Testen des anonymen webapp-Zugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98878c2e0d0e50c385448dceec5df5643e92aa53
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="10fea-102">Testen des anonymen webapp-Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10fea-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10fea-103">_**Letztes Änderungsstand des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="10fea-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10fea-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="10fea-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="10fea-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="10fea-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10fea-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="10fea-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="10fea-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10fea-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10fea-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10fea-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="10fea-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="10fea-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="10fea-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsWebAppAnonymous verfügt.</span><span class="sxs-lookup"><span data-stu-id="10fea-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="10fea-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="10fea-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="10fea-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10fea-112">Description</span></span>

<span data-ttu-id="10fea-113">Das Cmdlet Test-CsWebAppAnonymous überprüft, ob ein anonymer Benutzer mithilfe der lync Web App lync Server Konferenzen beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="10fea-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="10fea-114">Wenn Sie das Cmdlet ausführen, kontaktiert Test-CsWebAppAnonymous den Webdienst, um ein WebTICKET für den anonymen Benutzer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="10fea-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="10fea-115">Wenn es dem Cmdlet gelingt, dieses Ticket zu erhalten, wird Test-CsWebAppAnonymous dann mit lync Server Kontakt aufnehmen und versuchen, separate Konferenzen für Sofortnachrichten, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="10fea-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="10fea-116">Beachten Sie, dass mit Test-CsWebAppAnonymous nur die APIs und Verbindungen überprüft werden, die zum Erstellen dieser Konferenzen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="10fea-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="10fea-117">Das Cmdlet erstellt und führt keine Konferenzen tatsächlich aus.</span><span class="sxs-lookup"><span data-stu-id="10fea-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="10fea-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="10fea-118">Running the test</span></span>

<span data-ttu-id="10fea-119">Das Cmdlet Test-CsWebAppAnonymous kann entweder mit einem vorkonfigurierten Test Konto oder mit den Konten von zwei Benutzern ausgeführt werden, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="10fea-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="10fea-120">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des getesteten lync Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="10fea-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="10fea-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="10fea-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="10fea-122">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server-Verwaltungsshell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="10fea-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="10fea-123">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsWebAppAnonymous aufrufen:</span><span class="sxs-lookup"><span data-stu-id="10fea-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="10fea-124">Weitere Informationen finden Sie im Hilfethema zum Cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="10fea-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="10fea-125">Beachten Sie, dass Test-CsWebAppAnonymous für die Verwendung in lync Server 2013 veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="10fea-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="10fea-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="10fea-126">Determining success or failure</span></span>

<span data-ttu-id="10fea-127">Wenn Test-CsWebAppAnonymous den anonymen Benutzer zu seinen Konferenzen hinzufügen kann, gibt das Cmdlet das Test Ergebnis Success zurück:</span><span class="sxs-lookup"><span data-stu-id="10fea-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="10fea-128">Ziel-FQDN:</span><span class="sxs-lookup"><span data-stu-id="10fea-128">Target Fqdn :</span></span>

<span data-ttu-id="10fea-129">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="10fea-129">Result : Success</span></span>

<span data-ttu-id="10fea-130">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="10fea-130">Latency : 00:00:00</span></span>

<span data-ttu-id="10fea-131">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="10fea-131">Error Message :</span></span>

<span data-ttu-id="10fea-132">Diagnose</span><span class="sxs-lookup"><span data-stu-id="10fea-132">Diagnosis :</span></span>

<span data-ttu-id="10fea-133">Wenn der anonyme Benutzer nicht an den erforderlichen Konferenzen teilnehmen kann, wird das Testergebnis als Fehler markiert.</span><span class="sxs-lookup"><span data-stu-id="10fea-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="10fea-134">In der Regel meldet Test-CsWebAppAnonymous auch eine ausführliche Fehlermeldung und Diagnose zurück:</span><span class="sxs-lookup"><span data-stu-id="10fea-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="10fea-135">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="10fea-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="10fea-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="10fea-136">Result : Failure</span></span>

<span data-ttu-id="10fea-137">Wartezeit: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="10fea-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="10fea-138">Fehlermeldung: Es wurde keine Antwort für den Webdienst "Ticket Service" empfangen.</span><span class="sxs-lookup"><span data-stu-id="10fea-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="10fea-139">Diagnose: die HTTP-Anforderung ist nicht autorisiert mit dem Client</span><span class="sxs-lookup"><span data-stu-id="10fea-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="10fea-140">Authentifizierungsschema ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="10fea-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="10fea-141">Die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10fea-141">The authentication</span></span>

<span data-ttu-id="10fea-142">vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".</span><span class="sxs-lookup"><span data-stu-id="10fea-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="10fea-143">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="10fea-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="10fea-144">Fehler der Test-CsWebAppAnonymous drehen sich normalerweise um Benutzer Authentifizierungsfehler: Sie müssen den Test mit einem gültigen Benutzerkonto ausführen, obwohl das Cmdlet die Möglichkeit eines anonymen Benutzers prüft, eine Verbindung mit lync Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="10fea-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="10fea-145">Wenn Test-CsWebAppAnonymous fehlschlägt, sollten Sie überprüfen, ob der angegebene Benutzer über ein gültiges lync Server Benutzerkonto verfügt.</span><span class="sxs-lookup"><span data-stu-id="10fea-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="10fea-146">Sie können lync Server Kontoinformationen abrufen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="10fea-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="10fea-147">Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="10fea-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="10fea-148">Sie sollten auch überprüfen, ob das Kennwort, das Sie beim Ausführen des Cmdlets angegeben haben, ein gültiges Kennwort ist.</span><span class="sxs-lookup"><span data-stu-id="10fea-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="10fea-149">Konfigurationsprobleme mit Office-webapps Server können auch dazu führen, dass Test-CsWebAppAnonymous fehlschlägt; Dies wird häufig der Fall sein, wenn Sie die folgende Diagnose erhalten:</span><span class="sxs-lookup"><span data-stu-id="10fea-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="10fea-150">Die HTTP-Anforderung ist nicht autorisiert mit dem Clientauthentifizierungsschema "NTLM".</span><span class="sxs-lookup"><span data-stu-id="10fea-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="10fea-151">Der vom Server empfangene Authentifizierungsheader lautete "aushandeln, NTLM".</span><span class="sxs-lookup"><span data-stu-id="10fea-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="10fea-152">Weitere Informationen zum Diagnostizieren und Beheben von Problemen mit Office-webapps-Servern finden Sie im Blog Post [Office-webapps Server 2013-Computer werden immer als](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)fehlerhaft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="10fea-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

