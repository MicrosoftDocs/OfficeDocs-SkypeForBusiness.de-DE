---
title: 'Lync Server 2013: Testen des webapp-Zugriffs'
description: 'Lync Server 2013: Testen Sie den webapp-Zugriff.'
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
ms.openlocfilehash: fc3bbc8008df4fe47fc5a39571356383fe5a6035
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560831"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="fd672-103">Testen des webapp-Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd672-103">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd672-104">_**Letztes Änderungsstand des Themas:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="fd672-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd672-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="fd672-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fd672-106">Monatlich</span><span class="sxs-lookup"><span data-stu-id="fd672-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd672-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="fd672-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fd672-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd672-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd672-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fd672-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fd672-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="fd672-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fd672-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsWebApp-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="fd672-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="fd672-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="fd672-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fd672-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd672-113">Description</span></span>

<span data-ttu-id="fd672-114">Das Test-CsWebApp-Cmdlet überprüft, ob authentifizierte Benutzer lync Server Konferenzen mithilfe der lync Web App beitreten können.</span><span class="sxs-lookup"><span data-stu-id="fd672-114">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="fd672-115">Wenn Sie das Cmdlet ausführen, kontaktiert Test-CsWebApp den Webdienst, um webtickets für die angegebenen Benutzer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fd672-115">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="fd672-116">Diese Tickets fungieren effektiv als "Eintrittskarten" für die lync Server Konferenz.</span><span class="sxs-lookup"><span data-stu-id="fd672-116">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="fd672-117">Wenn die Tickets abgerufen werden können und die Benutzer authentifiziert werden können, kontaktieren Test-CsWebApp dann lync Server und versuchen, separate Konferenzen für Chatnachrichten, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fd672-117">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="fd672-118">Beachten Sie, dass Test-CsWebApp nur die APIs und Verbindungen überprüft, die zum Erstellen dieser Konferenzen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="fd672-118">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="fd672-119">Das Cmdlet soll sicherstellen, dass lync Web App zum Erstellen und beitreten von Konferenzen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd672-119">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="fd672-120">Es wird jedoch nicht tatsächlich erstellt und eine Konferenz durchführen.</span><span class="sxs-lookup"><span data-stu-id="fd672-120">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fd672-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="fd672-121">Running the test</span></span>

<span data-ttu-id="fd672-122">Das Test-CsWebApp-Cmdlet kann entweder mit vorkonfigurierten Testkonten oder mit den Konten von zwei Benutzern ausgeführt werden, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="fd672-122">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="fd672-123">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des getesteten lync Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="fd672-123">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="fd672-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fd672-124">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="fd672-125">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd672-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="fd672-126">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsWebApp aufrufen:</span><span class="sxs-lookup"><span data-stu-id="fd672-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="fd672-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="fd672-127">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="fd672-128">Beachten Sie, dass Test-CsWebApp für die Verwendung in lync Server 2013 veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="fd672-128">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fd672-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="fd672-129">Determining success or failure</span></span>

<span data-ttu-id="fd672-130">Wenn Test-CsWebApp die Benutzer zu ihren Konferenzen hinzufügen können, gibt das Cmdlet das Testergebnis Success zurück:</span><span class="sxs-lookup"><span data-stu-id="fd672-130">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="fd672-131">Ziel-FQDN:</span><span class="sxs-lookup"><span data-stu-id="fd672-131">Target Fqdn :</span></span>

<span data-ttu-id="fd672-132">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="fd672-132">Result : Success</span></span>

<span data-ttu-id="fd672-133">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fd672-133">Latency : 00:00:00</span></span>

<span data-ttu-id="fd672-134">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="fd672-134">Error Message :</span></span>

<span data-ttu-id="fd672-135">Diagnose</span><span class="sxs-lookup"><span data-stu-id="fd672-135">Diagnosis :</span></span>

<span data-ttu-id="fd672-136">Wenn die Benutzer nicht an den erforderlichen Konferenzen teilnehmen können, wird das Testergebnis als Fehler gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="fd672-136">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="fd672-137">Normalerweise werden Test-CsWebApp auch eine ausführliche Fehlermeldung und Diagnose zurückmelden:</span><span class="sxs-lookup"><span data-stu-id="fd672-137">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="fd672-138">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd672-138">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fd672-139">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="fd672-139">Result : Failure</span></span>

<span data-ttu-id="fd672-140">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fd672-140">Latency : 00:00:00</span></span>

<span data-ttu-id="fd672-141">Fehlermeldung: keine Antwort für Web-Ticket Dienst empfangen</span><span class="sxs-lookup"><span data-stu-id="fd672-141">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="fd672-142">Diagnose: die HTTP-Anforderung ist nicht autorisiert mit dem Client</span><span class="sxs-lookup"><span data-stu-id="fd672-142">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="fd672-143">Authentifizierungsschema ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="fd672-143">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="fd672-144">Die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fd672-144">The authentication</span></span>

<span data-ttu-id="fd672-145">vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".</span><span class="sxs-lookup"><span data-stu-id="fd672-145">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fd672-146">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="fd672-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="fd672-147">Test-CsWebApp Fehler beziehen sich in der Regel auf Benutzer Authentifizierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="fd672-147">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="fd672-148">Wenn Test-CsWebApp fehlschlägt, sollten Sie zunächst überprüfen, ob die angegebenen Benutzer über gültige Benutzerkonten verfügen und für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="fd672-148">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="fd672-149">Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="fd672-149">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="fd672-150">Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt. Sie sollten auch überprüfen, ob die Kennwörter, die Sie für das Cmdlet angegeben haben, gültig sind.</span><span class="sxs-lookup"><span data-stu-id="fd672-150">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

