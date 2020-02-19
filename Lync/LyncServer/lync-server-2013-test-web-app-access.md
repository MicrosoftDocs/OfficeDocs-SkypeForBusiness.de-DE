---
title: 'Lync Server 2013: Testen des webapp-Zugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d116adc6b3ece7faf1d6e85b2848b35bdf522f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="03e03-102">Testen des webapp-Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03e03-102">Test Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03e03-103">_**Letztes Änderungsstand des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="03e03-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03e03-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="03e03-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="03e03-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="03e03-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03e03-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="03e03-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="03e03-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="03e03-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03e03-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="03e03-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="03e03-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="03e03-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="03e03-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsWebApp verfügt.</span><span class="sxs-lookup"><span data-stu-id="03e03-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="03e03-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="03e03-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="03e03-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03e03-112">Description</span></span>

<span data-ttu-id="03e03-113">Das Cmdlet Test-CsWebApp überprüft, ob authentifizierte Benutzer lync Server Konferenzen mit der lync Web App teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="03e03-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="03e03-114">Wenn Sie das Cmdlet ausführen, kontaktiert Test-CsWebApp den Webdienst, um webtickets für die angegebenen Benutzer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="03e03-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="03e03-115">Diese Tickets fungieren effektiv als "Eintrittskarten" für die lync Server Konferenz.</span><span class="sxs-lookup"><span data-stu-id="03e03-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="03e03-116">Wenn die Tickets abgerufen werden können und die Benutzer authentifiziert werden können, wird Test-CsWebApp dann Kontakt lync Server und versuchen, separate Konferenzen für Chatnachrichten, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="03e03-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="03e03-117">Beachten Sie, dass mit Test-CsWebApp nur die APIs und Verbindungen überprüft werden, die zum Erstellen dieser Konferenzen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="03e03-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="03e03-118">Das Cmdlet soll sicherstellen, dass lync Web App zum Erstellen und beitreten von Konferenzen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="03e03-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="03e03-119">Es wird jedoch nicht tatsächlich erstellt und eine Konferenz durchführen.</span><span class="sxs-lookup"><span data-stu-id="03e03-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="03e03-120">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="03e03-120">Running the test</span></span>

<span data-ttu-id="03e03-121">Das Cmdlet Test-CsWebApp kann entweder mit einem vorkonfigurierten Test Konto oder mit den Konten von zwei Benutzern ausgeführt werden, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="03e03-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="03e03-122">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des getesteten lync Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="03e03-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="03e03-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="03e03-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="03e03-124">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="03e03-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="03e03-125">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsWebApp aufrufen:</span><span class="sxs-lookup"><span data-stu-id="03e03-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="03e03-126">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="03e03-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="03e03-127">Beachten Sie, dass Test-CsWebApp für die Verwendung in lync Server 2013 veraltet war.</span><span class="sxs-lookup"><span data-stu-id="03e03-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="03e03-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="03e03-128">Determining success or failure</span></span>

<span data-ttu-id="03e03-129">Wenn Test-CsWebApp die Benutzer zu ihren Konferenzen hinzufügen kann, gibt das Cmdlet das Test Ergebnis Success zurück:</span><span class="sxs-lookup"><span data-stu-id="03e03-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="03e03-130">Ziel-FQDN:</span><span class="sxs-lookup"><span data-stu-id="03e03-130">Target Fqdn :</span></span>

<span data-ttu-id="03e03-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="03e03-131">Result : Success</span></span>

<span data-ttu-id="03e03-132">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="03e03-132">Latency : 00:00:00</span></span>

<span data-ttu-id="03e03-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="03e03-133">Error Message :</span></span>

<span data-ttu-id="03e03-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="03e03-134">Diagnosis :</span></span>

<span data-ttu-id="03e03-135">Wenn die Benutzer nicht an den erforderlichen Konferenzen teilnehmen können, wird das Testergebnis als Fehler gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="03e03-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="03e03-136">In der Regel meldet Test-CsWebApp auch eine ausführliche Fehlermeldung und Diagnose zurück:</span><span class="sxs-lookup"><span data-stu-id="03e03-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="03e03-137">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="03e03-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="03e03-138">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="03e03-138">Result : Failure</span></span>

<span data-ttu-id="03e03-139">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="03e03-139">Latency : 00:00:00</span></span>

<span data-ttu-id="03e03-140">Fehlermeldung: Es wurde keine Antwort für den Webdienst "Ticket Service" empfangen.</span><span class="sxs-lookup"><span data-stu-id="03e03-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="03e03-141">Diagnose: die HTTP-Anforderung ist nicht autorisiert mit dem Client</span><span class="sxs-lookup"><span data-stu-id="03e03-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="03e03-142">Authentifizierungsschema ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="03e03-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="03e03-143">Die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="03e03-143">The authentication</span></span>

<span data-ttu-id="03e03-144">vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".</span><span class="sxs-lookup"><span data-stu-id="03e03-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="03e03-145">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="03e03-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="03e03-146">Zu Test-CsWebApp-Fehlern gehören normalerweise Benutzer Authentifizierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="03e03-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="03e03-147">Wenn Test-CsWebApp fehlschlägt, sollten Sie zunächst überprüfen, ob die angegebenen Benutzer über gültige Benutzerkonten verfügen und für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="03e03-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="03e03-148">Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="03e03-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="03e03-149">Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt. Sie sollten auch überprüfen, ob die Kennwörter, die Sie für das Cmdlet angegeben haben, gültig sind.</span><span class="sxs-lookup"><span data-stu-id="03e03-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

