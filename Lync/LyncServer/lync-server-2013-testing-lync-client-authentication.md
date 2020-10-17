---
title: 'Lync Server 2013: Testen der lync-Client Authentifizierung'
description: 'Lync Server 2013: Testen der lync-Client Authentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560581"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="d984f-103">Testen der lync-Client Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d984f-103">Testing Lync Client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d984f-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d984f-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d984f-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="d984f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d984f-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="d984f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d984f-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="d984f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d984f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d984f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d984f-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d984f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d984f-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="d984f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d984f-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsClientAuth-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="d984f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="d984f-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="d984f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d984f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d984f-113">Description</span></span>

<span data-ttu-id="d984f-114">Mit dem Test-CsClientAuth-Cmdlet können Sie bestimmen, ob sich ein Benutzer bei der lync Server mithilfe eines Clientzertifikats anmelden kann, indem Sie das Test-CsClientAuth-Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="d984f-114">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="d984f-115">Nach dem Aufruf von Test-CsClientAuth wird das Cmdlet mit dem Dienst für die Bereitstellung von Zertifikaten Kontakt aufnehmen und eine Kopie aller Clientzertifikate für den angegebenen Benutzer herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d984f-115">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="d984f-116">Wenn ein Clientzertifikat gefunden und heruntergeladen werden kann, versucht Test-CsClientAuth, sich mit diesem Zertifikat anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d984f-116">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="d984f-117">Wenn die Anmeldung erfolgreich ist, melden sich Test-CsClientAuth ab und melden, dass der Test erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d984f-117">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="d984f-118">Falls kein Zertifikat gefunden oder heruntergeladen werden kann oder wenn das Cmdlet sich mit dem Zertifikat nicht anmelden kann, meldet Test-CsClientAuth den Test als nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d984f-118">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d984f-119">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="d984f-119">Running the test</span></span>

<span data-ttu-id="d984f-120">Das Test-CsClientAuth-Cmdlet wird mithilfe des Kontos eines beliebigen Benutzers ausgeführt, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d984f-120">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="d984f-121">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="d984f-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="d984f-122">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn das System Test-CsClientAuth aufruft:</span><span class="sxs-lookup"><span data-stu-id="d984f-122">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d984f-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="d984f-123">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d984f-124">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="d984f-124">Determining success or failure</span></span>

<span data-ttu-id="d984f-125">Wenn sich der angegebene Benutzer bei lync Server mithilfe eines Clientzertifikats anmelden kann, erhalten Sie eine ähnliche Ausgabe wie diese, wobei die Result-Eigenschaft als Success markiert wird **:**</span><span class="sxs-lookup"><span data-stu-id="d984f-125">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d984f-126">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d984f-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d984f-127">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="d984f-127">Result : Success</span></span>

<span data-ttu-id="d984f-128">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="d984f-128">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="d984f-129">Fehler</span><span class="sxs-lookup"><span data-stu-id="d984f-129">Error :</span></span>

<span data-ttu-id="d984f-130">Diagnose</span><span class="sxs-lookup"><span data-stu-id="d984f-130">Diagnosis :</span></span>

<span data-ttu-id="d984f-131">Wenn sich der angegebene Benutzer nicht anmelden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Error und Diagnostic aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="d984f-131">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d984f-132">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d984f-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d984f-133">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="d984f-133">Result : Failure</span></span>

<span data-ttu-id="d984f-134">Wartezeit: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="d984f-134">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="d984f-135">Fehler: das CS-Zertifikat für den angegebenen Benutzer konnte nicht heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d984f-135">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="d984f-136">Prüfen Sie, ob</span><span class="sxs-lookup"><span data-stu-id="d984f-136">Check if</span></span>

<span data-ttu-id="d984f-137">der angegebene URI und die Anmeldeinformationen sind korrekt.</span><span class="sxs-lookup"><span data-stu-id="d984f-137">provided uri and credentials are correct.</span></span>

<span data-ttu-id="d984f-138">Diagnose</span><span class="sxs-lookup"><span data-stu-id="d984f-138">Diagnosis :</span></span>

<span data-ttu-id="d984f-139">Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da ein gültiges Clientzertifikat für den angegebenen Benutzer nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="d984f-139">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="d984f-140">Sie können eine Liste der für einen Benutzer ausgestellten Clientzertifikate zurückgeben, indem Sie einen Befehl wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="d984f-140">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="d984f-141">Wenn Test-CsClientAuth fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="d984f-141">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="d984f-142">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsClientAuth eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d984f-142">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d984f-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d984f-143">For example:</span></span>

<span data-ttu-id="d984f-144">Versuch, ein CS-Zertifikat für den Benutzer herunterzuladen: kenmyer@litwareinc.com-Endpunkt: Step-up</span><span class="sxs-lookup"><span data-stu-id="d984f-144">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="d984f-145">Webdienst-URL: https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="d984f-145">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="d984f-146">CS-Zertifikat konnte nicht aus dem Webdienst heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d984f-146">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="d984f-147">Kontroll</span><span class="sxs-lookup"><span data-stu-id="d984f-147">CHECK:</span></span>

<span data-ttu-id="d984f-148">\- Die Webdienst-URL ist gültig, und die Webdienste sind funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="d984f-148">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="d984f-149">\-Wenn \\ \\ Sie die PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d984f-149">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="d984f-150">\- Wenn Sie NTLM \\ -Kerberos-Authentifizierung verwenden, stellen Sie sicher, dass Sie gültige Anmeldeinformationen angegeben haben</span><span class="sxs-lookup"><span data-stu-id="d984f-150">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d984f-151">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="d984f-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="d984f-152">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsClientAuth Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="d984f-152">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="d984f-153">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="d984f-153">You specified a user account that was not valid.</span></span> <span data-ttu-id="d984f-154">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="d984f-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d984f-155">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d984f-155">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d984f-156">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="d984f-156">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d984f-157">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d984f-157">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d984f-158">Der Testbenutzer verfügt möglicherweise nicht über ein gültiges Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="d984f-158">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="d984f-159">Sie können Informationen zu den einem Benutzer zugewiesenen Clientzertifikaten mithilfe eines Befehls wie dem folgenden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="d984f-159">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

