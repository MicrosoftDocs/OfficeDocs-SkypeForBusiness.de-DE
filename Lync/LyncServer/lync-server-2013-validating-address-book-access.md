---
title: 'Lync Server 2013: Überprüfen des Adressbuch Zugriffs'
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
ms.openlocfilehash: 0f18651cd75df62cf1d5f8c543d0e5c11361c7db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="66c02-102">Überprüfen des Adressbuch Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66c02-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66c02-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="66c02-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c02-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="66c02-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="66c02-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="66c02-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c02-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="66c02-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="66c02-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66c02-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c02-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="66c02-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="66c02-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="66c02-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="66c02-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsAddressBookService verfügt.</span><span class="sxs-lookup"><span data-stu-id="66c02-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="66c02-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="66c02-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="66c02-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66c02-112">Description</span></span>

<span data-ttu-id="66c02-113">Das Cmdlet Test-CsAddressBookService bietet Ihnen die Möglichkeit, zu überprüfen, ob ein Benutzer eine Verbindung mit dem Webdienst für den Adressbuch Download herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="66c02-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="66c02-114">Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookService eine Verbindung mit dem Adressbuch-Download-Webdienst im angegebenen Pool her und fordert den Speicherort der Adressbuchdateien an.</span><span class="sxs-lookup"><span data-stu-id="66c02-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="66c02-115">Wenn der Adressbuch-Download-Webdienst diesen Speicherort bereitstellt, wird der Test als erfolgreich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="66c02-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="66c02-116">Wenn die Anforderung abgelehnt wird, wird der Test als nicht erfolgreich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="66c02-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="66c02-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="66c02-117">Running the test</span></span>

<span data-ttu-id="66c02-118">Das Cmdlet Test-CsAddressBookService kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="66c02-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="66c02-119">Um diese Prüfung mit einem Testkonto auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Tests lync Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="66c02-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="66c02-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66c02-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="66c02-121">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="66c02-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="66c02-122">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn Sie Test-CsAddressBookService aufrufen:</span><span class="sxs-lookup"><span data-stu-id="66c02-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="66c02-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="66c02-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="66c02-124">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="66c02-124">Determining success or failure</span></span>

<span data-ttu-id="66c02-125">Wenn der angegebene Benutzer eine Verbindung mit dem Adressbuchdienst herstellen kann, wird die Ausgabe wie folgt zurückgegeben, wobei die Result-Eigenschaft als **Success**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="66c02-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="66c02-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="66c02-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="66c02-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66c02-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="66c02-128">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="66c02-128">Result : Success</span></span>

<span data-ttu-id="66c02-129">Wartezeit: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="66c02-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="66c02-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="66c02-130">Error :</span></span>

<span data-ttu-id="66c02-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="66c02-131">Diagnosis :</span></span>

<span data-ttu-id="66c02-132">Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="66c02-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="66c02-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="66c02-133">TargetUri :</span></span>

<span data-ttu-id="66c02-134">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66c02-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="66c02-135">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="66c02-135">Result : Failure</span></span>

<span data-ttu-id="66c02-136">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="66c02-136">Latency : 00:00:00</span></span>

<span data-ttu-id="66c02-137">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="66c02-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="66c02-138">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="66c02-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="66c02-139">existieren.</span><span class="sxs-lookup"><span data-stu-id="66c02-139">exist.</span></span>

<span data-ttu-id="66c02-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="66c02-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="66c02-141">Die obige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da der angegebene Benutzer (also der "Ziel-URI") entweder nicht vorhanden oder für lync Server nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="66c02-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="66c02-142">Sie können überprüfen, ob ein Benutzerkonto gültig ist, und sicherstellen, dass Sie die richtige SIP-Adresse angegeben haben, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="66c02-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="66c02-143">Get-CsUser-Identity "SIP:kenmyer@litwareinc.com" | SELECT-Objekt SipAddress, aktiviert</span><span class="sxs-lookup"><span data-stu-id="66c02-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="66c02-144">Wenn "Test-CsAddressBookService" fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, einschließlich des Verbose-Parameters:</span><span class="sxs-lookup"><span data-stu-id="66c02-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="66c02-145">Test-CsAddressBookService-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="66c02-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="66c02-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsAddressBookService eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, um die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="66c02-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="66c02-147">Beispielsweise zeigt diese Beispielausgabe, dass Test-CsAddressBookService zumindest in diesem Beispiel die Adressbuchdatei herunterladen konnte:</span><span class="sxs-lookup"><span data-stu-id="66c02-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="66c02-148">Senden der HTTP GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="66c02-148">Sending Http GET Request.</span></span>

<span data-ttu-id="66c02-149">Dateipfad =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="66c02-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="66c02-150">Nummer des Versuchs = 1</span><span class="sxs-lookup"><span data-stu-id="66c02-150">Attempt Number = 1</span></span>

<span data-ttu-id="66c02-151">Timeout (MS) = 60000</span><span class="sxs-lookup"><span data-stu-id="66c02-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="66c02-152">Die ABS-Datei wurde erfolgreich heruntergeladen.https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="66c02-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="66c02-153">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="66c02-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="66c02-154">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsAddressBookService möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="66c02-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="66c02-155">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="66c02-155">You specified an invalid user account.</span></span> <span data-ttu-id="66c02-156">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="66c02-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="66c02-157">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66c02-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="66c02-158">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="66c02-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="66c02-159">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="66c02-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66c02-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66c02-160">See Also</span></span>


[<span data-ttu-id="66c02-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="66c02-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

