---
title: 'Lync Server 2013: Überprüfen der Adressbuch-Webabfrage'
description: 'Lync Server 2013: Überprüfen der Adressbuch-Webabfrage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547251"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="1a338-103">Überprüfen der Adressbuch-Webabfrage in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a338-103">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a338-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1a338-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a338-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="1a338-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1a338-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="1a338-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a338-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="1a338-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1a338-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a338-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a338-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1a338-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1a338-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="1a338-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1a338-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAddressBookWebQuery-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="1a338-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="1a338-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="1a338-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1a338-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a338-113">Description</span></span>

<span data-ttu-id="1a338-114">Mit dem Test-CsAddressBookWebQuery-Cmdlet können Administratoren überprüfen, ob Benutzer mithilfe der Adressbuch-Webabfragedienst nach einem bestimmten Kontakt suchen.</span><span class="sxs-lookup"><span data-stu-id="1a338-114">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="1a338-115">Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookWebQuery zunächst eine Verbindung mit dem webticketdienst her, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a338-115">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="1a338-116">Wenn die Authentifizierung erfolgreich ist, stellt das Cmdlet eine Verbindung mit dem Adressbuch-Webabfragedienst her und sucht nach dem angegebenen Kontakt.</span><span class="sxs-lookup"><span data-stu-id="1a338-116">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="1a338-117">Wird der Kontakt gefunden, versucht das Cmdlet, diese Informationen an den lokalen Computer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1a338-117">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="1a338-118">Der Test wird nur dann als erfolgreich markiert, wenn alle diese Schritte ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="1a338-118">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="1a338-119">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="1a338-119">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1a338-120">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="1a338-120">Running the test</span></span>

<span data-ttu-id="1a338-121">Das Test-CsAddressBookWebQuery-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a338-121">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="1a338-122">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools und die SIP-Adresse des Benutzers angeben, der als Ziel der Suche fungiert.</span><span class="sxs-lookup"><span data-stu-id="1a338-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="1a338-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1a338-123">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="1a338-124">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie ein Windows PowerShell Credentials-Objekt erstellen, das einen gültigen Benutzernamen und ein gültiges Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="1a338-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="1a338-125">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse einschließen, wenn der Code Test-CsAddressBookWebQuery aufruft:</span><span class="sxs-lookup"><span data-stu-id="1a338-125">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="1a338-126">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="1a338-126">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1a338-127">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="1a338-127">Determining success or failure</span></span>

<span data-ttu-id="1a338-128">Wenn der angegebene Benutzer eine Verbindung mit dem Adressbuchdienst herstellen und die Zielbenutzer Adresse abrufen kann, wird die Ausgabe wie folgt zurückgegeben, wobei die Ergebniseigenschaft als "Success" markiert ist:</span><span class="sxs-lookup"><span data-stu-id="1a338-128">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="1a338-129">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="1a338-129">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="1a338-130">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1a338-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1a338-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="1a338-131">Result : Success</span></span>

<span data-ttu-id="1a338-132">Wartezeit: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="1a338-132">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="1a338-133">Fehler</span><span class="sxs-lookup"><span data-stu-id="1a338-133">Error :</span></span>

<span data-ttu-id="1a338-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="1a338-134">Diagnosis :</span></span>

<span data-ttu-id="1a338-135">Wenn der angegebene Benutzer keine Verbindung herstellen kann oder die Zielbenutzer Adresse nicht abgerufen werden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="1a338-135">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1a338-136">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="1a338-136">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="1a338-137">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1a338-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1a338-138">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="1a338-138">Result : Failure</span></span>

<span data-ttu-id="1a338-139">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1a338-139">Latency : 00:00:00</span></span>

<span data-ttu-id="1a338-140">Fehler: die Webdienstanforderung für das Adressbuch ist mit dem Antwortcode fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="1a338-140">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="1a338-141">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="1a338-141">NoEntryFound.</span></span>

<span data-ttu-id="1a338-142">Diagnose</span><span class="sxs-lookup"><span data-stu-id="1a338-142">Diagnosis :</span></span>

<span data-ttu-id="1a338-143">Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da der Zielbenutzer nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="1a338-143">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="1a338-144">Sie können bestimmen, ob eine gültige SIP-Adresse an Test-CsAddressBookWebQuery übergeben wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="1a338-144">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="1a338-145">Wenn Test-CsAddressBookWebQuery fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="1a338-145">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="1a338-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsAddressBookWebQuery eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während die Möglichkeit des angegebenen Benutzers, sich bei lync Server anzumelden, überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="1a338-146">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="1a338-147">Diese Ausgabe gibt beispielsweise an, dass Test-CsAddressBookWebQuery eine Verbindung mit dem Adressbuchdienst herstellen konnte, die Ziel-SIP-Adresse konnte jedoch nicht gefunden werden:</span><span class="sxs-lookup"><span data-stu-id="1a338-147">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="1a338-148">"QueryAddressBookWebService"-Aktivität wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="1a338-148">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="1a338-149">Adressbuch-Webabfrage Dienst wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1a338-149">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="1a338-150">ABWS-URL =</span><span class="sxs-lookup"><span data-stu-id="1a338-150">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="1a338-151">Adressbuch-Abfrage Ausnahme: Fehler bei der Adressbuch-Webdienstanforderung mit Antwortcode NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="1a338-151">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1a338-152">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="1a338-152">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="1a338-153">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsAddressBookWebQuery Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="1a338-153">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="1a338-154">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a338-154">You specified an invalid user account.</span></span> <span data-ttu-id="1a338-155">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="1a338-155">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1a338-156">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1a338-156">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="1a338-157">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="1a338-157">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="1a338-158">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a338-158">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="1a338-159">Der Zielbenutzer ist möglicherweise nicht im Adressbuch.</span><span class="sxs-lookup"><span data-stu-id="1a338-159">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="1a338-160">Das Adressbuch wurde möglicherweise nicht vollständig aktualisiert und repliziert.</span><span class="sxs-lookup"><span data-stu-id="1a338-160">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="1a338-161">Sie können eine Aktualisierung aller Adressbuchserver in Ihrer Organisation erzwingen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1a338-161">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

