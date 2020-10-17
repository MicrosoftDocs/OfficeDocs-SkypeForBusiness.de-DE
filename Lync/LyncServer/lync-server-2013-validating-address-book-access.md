---
title: 'Lync Server 2013: Überprüfen des Adressbuch Zugriffs'
description: 'Lync Server 2013: Überprüfen des Adressbuch Zugriffs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547241"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="a4378-103">Überprüfen des Adressbuch Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4378-103">Validating address book access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4378-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a4378-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4378-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="a4378-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a4378-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="a4378-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4378-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="a4378-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a4378-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4378-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4378-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a4378-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a4378-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="a4378-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a4378-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAddressBookService-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="a4378-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="a4378-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="a4378-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a4378-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4378-113">Description</span></span>

<span data-ttu-id="a4378-114">Mit dem Test-CsAddressBookService-Cmdlet können Sie überprüfen, ob ein Benutzer eine Verbindung mit dem Webdienst für den Adressbuch Download herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a4378-114">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="a4378-115">Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookService eine Verbindung mit dem Adressbuch-Download-Webdienst im angegebenen Pool her und fordert den Speicherort der Adressbuchdateien an.</span><span class="sxs-lookup"><span data-stu-id="a4378-115">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="a4378-116">Wenn der Adressbuch-Download-Webdienst diesen Speicherort bereitstellt, wird der Test als erfolgreich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="a4378-116">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="a4378-117">Wenn die Anforderung abgelehnt wird, wird der Test als nicht erfolgreich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="a4378-117">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a4378-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="a4378-118">Running the test</span></span>

<span data-ttu-id="a4378-119">Das Test-CsAddressBookService-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="a4378-119">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="a4378-120">Um diese Prüfung mit einem Testkonto auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Tests lync Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="a4378-120">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="a4378-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4378-121">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="a4378-122">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="a4378-122">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="a4378-123">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn Sie Test-CsAddressBookService aufrufen:</span><span class="sxs-lookup"><span data-stu-id="a4378-123">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a4378-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="a4378-124">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a4378-125">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="a4378-125">Determining success or failure</span></span>

<span data-ttu-id="a4378-126">Wenn der angegebene Benutzer eine Verbindung mit dem Adressbuchdienst herstellen kann, wird die Ausgabe wie folgt zurückgegeben, wobei die Result-Eigenschaft als **Success**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="a4378-126">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="a4378-127">TargetUri https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="a4378-127">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="a4378-128">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a4378-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a4378-129">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="a4378-129">Result : Success</span></span>

<span data-ttu-id="a4378-130">Wartezeit: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="a4378-130">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="a4378-131">Fehler</span><span class="sxs-lookup"><span data-stu-id="a4378-131">Error :</span></span>

<span data-ttu-id="a4378-132">Diagnose</span><span class="sxs-lookup"><span data-stu-id="a4378-132">Diagnosis :</span></span>

<span data-ttu-id="a4378-133">Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="a4378-133">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a4378-134">TargetUri</span><span class="sxs-lookup"><span data-stu-id="a4378-134">TargetUri :</span></span>

<span data-ttu-id="a4378-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a4378-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a4378-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="a4378-136">Result : Failure</span></span>

<span data-ttu-id="a4378-137">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a4378-137">Latency : 00:00:00</span></span>

<span data-ttu-id="a4378-138">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="a4378-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="a4378-139">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="a4378-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="a4378-140">existieren.</span><span class="sxs-lookup"><span data-stu-id="a4378-140">exist.</span></span>

<span data-ttu-id="a4378-141">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="a4378-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="a4378-142">Die obige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da der angegebene Benutzer (also der "Ziel-URI") entweder nicht vorhanden oder für lync Server nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="a4378-142">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="a4378-143">Sie können überprüfen, ob ein Benutzerkonto gültig ist, und sicherstellen, dass Sie die richtige SIP-Adresse angegeben haben, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="a4378-143">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="a4378-144">Get-CsUser-Identity "SIP:kenmyer@litwareinc.com" | Select-Object SipAddress, aktiviert</span><span class="sxs-lookup"><span data-stu-id="a4378-144">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="a4378-145">Wenn Test-CsAddressBookService fehlschlägt, möchten Sie den Test möglicherweise erneut ausführen, und zwar mit dem Verbose-Parameter:</span><span class="sxs-lookup"><span data-stu-id="a4378-145">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="a4378-146">Test-CsAddressBookService-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="a4378-146">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="a4378-147">Wenn der Verbose-Parameter enthalten ist Test-CsAddressBookService gibt eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Fähigkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a4378-147">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a4378-148">Beispielsweise zeigt diese Beispielausgabe, dass Test-CsAddressBookService zumindest in diesem Beispiel die Adressbuchdatei herunterladen konnte:</span><span class="sxs-lookup"><span data-stu-id="a4378-148">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="a4378-149">Senden der HTTP GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a4378-149">Sending Http GET Request.</span></span>

<span data-ttu-id="a4378-150">Dateipfad = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="a4378-150">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="a4378-151">Nummer des Versuchs = 1</span><span class="sxs-lookup"><span data-stu-id="a4378-151">Attempt Number = 1</span></span>

<span data-ttu-id="a4378-152">Timeout (MS) = 60000</span><span class="sxs-lookup"><span data-stu-id="a4378-152">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="a4378-153">Die ABS-Datei wurde erfolgreich heruntergeladen. https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="a4378-153">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a4378-154">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="a4378-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="a4378-155">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsAddressBookService Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="a4378-155">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="a4378-156">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="a4378-156">You specified an invalid user account.</span></span> <span data-ttu-id="a4378-157">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="a4378-157">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a4378-158">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4378-158">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="a4378-159">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="a4378-159">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a4378-160">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a4378-160">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4378-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4378-161">See Also</span></span>


[<span data-ttu-id="a4378-162">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="a4378-162">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

