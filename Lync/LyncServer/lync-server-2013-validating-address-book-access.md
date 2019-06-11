---
title: 'Lync Server 2013: Überprüfen des Zugriffs auf das Adressbuch'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="75996-102">Überprüfen des Adressbuch Zugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75996-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75996-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="75996-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75996-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="75996-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="75996-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="75996-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75996-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="75996-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="75996-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75996-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75996-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="75996-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="75996-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="75996-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="75996-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAddressBookService-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="75996-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="75996-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="75996-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="75996-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75996-112">Description</span></span>

<span data-ttu-id="75996-113">Das Cmdlet Test-CsAddressBookService bietet eine Möglichkeit, um zu überprüfen, ob ein Benutzer eine Verbindung mit dem Webdienst des Adressbuchs herunterladen kann.</span><span class="sxs-lookup"><span data-stu-id="75996-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="75996-114">Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookService eine Verbindung mit dem Download-Webdienst des Adressbuchs im angegebenen Pool her und fordert den Speicherort der Adressbuchdateien an.</span><span class="sxs-lookup"><span data-stu-id="75996-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="75996-115">Wenn das Adressbuch, das vom Webdienst heruntergeladen wird, diesen Speicherort bereitstellt, wird der Test als erfolgreich angesehen.</span><span class="sxs-lookup"><span data-stu-id="75996-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="75996-116">Wenn die Anforderung abgelehnt wird, wird der Test als Fehler gewertet.</span><span class="sxs-lookup"><span data-stu-id="75996-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="75996-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="75996-117">Running the test</span></span>

<span data-ttu-id="75996-118">Das Cmdlet "Test-CsAddressBookService" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="75996-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="75996-119">Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="75996-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="75996-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75996-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="75996-121">Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="75996-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="75996-122">Sie müssen das Anmeldeinformationsobjekt und die SIP-Adresse, die dem Konto zugewiesen ist, beim Aufrufen von Test-CsAddressBookService einfügen:</span><span class="sxs-lookup"><span data-stu-id="75996-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="75996-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="75996-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="75996-124">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="75996-124">Determining success or failure</span></span>

<span data-ttu-id="75996-125">Wenn der angegebene Benutzer in der Lage ist, eine Verbindung mit dem Adressbuchdienst herzustellen, erhalten Sie eine ähnliche Ausgabe wie diese, wobei die Eigenschaft Ergebnis als **erfolgreich**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="75996-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="75996-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="75996-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="75996-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="75996-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="75996-128">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="75996-128">Result : Success</span></span>

<span data-ttu-id="75996-129">Latenz: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="75996-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="75996-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="75996-130">Error :</span></span>

<span data-ttu-id="75996-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="75996-131">Diagnosis :</span></span>

<span data-ttu-id="75996-132">Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="75996-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="75996-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="75996-133">TargetUri :</span></span>

<span data-ttu-id="75996-134">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="75996-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="75996-135">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="75996-135">Result : Failure</span></span>

<span data-ttu-id="75996-136">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="75996-136">Latency : 00:00:00</span></span>

<span data-ttu-id="75996-137">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="75996-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="75996-138">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="75996-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="75996-139">existieren.</span><span class="sxs-lookup"><span data-stu-id="75996-139">exist.</span></span>

<span data-ttu-id="75996-140">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="75996-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="75996-141">In der vorhergehenden Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer (also der "Ziel-URI") entweder nicht vorhanden ist oder für lync Server nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="75996-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="75996-142">Sie können überprüfen, ob ein Benutzerkonto gültig ist, und sicherstellen, dass Sie die richtige SIP-Adresse angegeben haben, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="75996-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="75996-143">Get-CsUser-Identity "SIP:kenmyer@litwareinc.com" | Select-Object SipAddress, aktiviert</span><span class="sxs-lookup"><span data-stu-id="75996-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="75996-144">Wenn Test-CsAddressBookService fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="75996-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="75996-145">Test-CsAddressBookService-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="75996-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="75996-146">Wenn der Verbose-Parameter enthalten ist, gibt CsAddressBookService eine Schritt-für-Schritt-Konto für jede Aktion zurück, die beim Überprüfen der Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="75996-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="75996-147">Diese Beispielausgabe zeigt beispielsweise, dass Test-CsAddressBookService, zumindest in diesem Beispiel, die Adressbuchdatei herunterladen konnte:</span><span class="sxs-lookup"><span data-stu-id="75996-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="75996-148">Sendet eine HTTP GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="75996-148">Sending Http GET Request.</span></span>

<span data-ttu-id="75996-149">Dateipfad =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="75996-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="75996-150">Nummer des Versuchs = 1</span><span class="sxs-lookup"><span data-stu-id="75996-150">Attempt Number = 1</span></span>

<span data-ttu-id="75996-151">Timeout (MS) = 60000</span><span class="sxs-lookup"><span data-stu-id="75996-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="75996-152">Die ABS-Datei wurde erfolgreich heruntergeladenhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="75996-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="75996-153">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="75996-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="75996-154">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsAddressBookService möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="75996-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="75996-155">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="75996-155">You specified an invalid user account.</span></span> <span data-ttu-id="75996-156">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="75996-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="75996-157">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="75996-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="75996-158">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="75996-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="75996-159">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="75996-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75996-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75996-160">See Also</span></span>


[<span data-ttu-id="75996-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="75996-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

