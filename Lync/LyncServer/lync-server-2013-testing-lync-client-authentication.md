---
title: 'Lync Server 2013: Testen der lync-Client Authentifizierung'
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
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="330a1-102">Testen der lync-Client Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330a1-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="330a1-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="330a1-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="330a1-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="330a1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="330a1-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="330a1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330a1-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="330a1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="330a1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="330a1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330a1-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="330a1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="330a1-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="330a1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="330a1-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsClientAuth-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="330a1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="330a1-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="330a1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="330a1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="330a1-112">Description</span></span>

<span data-ttu-id="330a1-113">Mit dem Cmdlet Test-CsClientAuth können Sie ermitteln, ob sich ein Benutzer mit einem Clientzertifikat am lync-Server anmelden kann, indem Sie das Cmdlet Test-CsClientAuth ausführen.</span><span class="sxs-lookup"><span data-stu-id="330a1-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="330a1-114">Nach dem Aufruf von Test-CsClientAuth wird das Cmdlet mit dem Dienst für die Zertifikatbereitstellung Kontakt aufnehmen und eine Kopie aller Clientzertifikate für den angegebenen Benutzer herunterladen.</span><span class="sxs-lookup"><span data-stu-id="330a1-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="330a1-115">Wenn ein Clientzertifikat gefunden und heruntergeladen werden kann, versucht Test-CsClientAuth, sich mit diesem Zertifikat anzumelden.</span><span class="sxs-lookup"><span data-stu-id="330a1-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="330a1-116">Wenn die Anmeldung erfolgreich ist, wird sich Test-CsClientAuth abmelden und melden, dass der Test erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="330a1-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="330a1-117">Wenn ein Zertifikat nicht gefunden oder heruntergeladen werden kann oder wenn sich das Cmdlet nicht mit diesem Zertifikat anmelden kann, meldet Test-CsClientAuth, dass der Test fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="330a1-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="330a1-118">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="330a1-118">Running the test</span></span>

<span data-ttu-id="330a1-119">Das Cmdlet Test-CsClientAuth wird mithilfe des Kontos eines beliebigen Benutzers ausgeführt, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="330a1-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="330a1-120">Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="330a1-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="330a1-121">Sie müssen dann das Anmeldeinformationsobjekt und die SIP-Adresse einbeziehen, die dem Konto zugewiesen ist, wenn das System Test-CsClientAuth aufruft:</span><span class="sxs-lookup"><span data-stu-id="330a1-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="330a1-122">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="330a1-122">For more information, see the Help documentation for the [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="330a1-123">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="330a1-123">Determining success or failure</span></span>

<span data-ttu-id="330a1-124">Wenn sich der angegebene Benutzer mit einem Clientzertifikat bei lync Server anmelden kann, wird die Ausgabe ähnlich wie diese angezeigt, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="330a1-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="330a1-125">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="330a1-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="330a1-126">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="330a1-126">Result : Success</span></span>

<span data-ttu-id="330a1-127">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="330a1-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="330a1-128">Fehler</span><span class="sxs-lookup"><span data-stu-id="330a1-128">Error :</span></span>

<span data-ttu-id="330a1-129">Diagnose</span><span class="sxs-lookup"><span data-stu-id="330a1-129">Diagnosis :</span></span>

<span data-ttu-id="330a1-130">Wenn der angegebene Benutzer sich nicht anmelden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="330a1-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="330a1-131">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="330a1-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="330a1-132">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="330a1-132">Result : Failure</span></span>

<span data-ttu-id="330a1-133">Latenz: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="330a1-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="330a1-134">Fehler: Es konnte kein CS-Zertifikat für den angegebenen Benutzer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="330a1-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="330a1-135">Überprüfen Sie, ob</span><span class="sxs-lookup"><span data-stu-id="330a1-135">Check if</span></span>

<span data-ttu-id="330a1-136">der angegebene URI und die Anmeldeinformationen sind richtig.</span><span class="sxs-lookup"><span data-stu-id="330a1-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="330a1-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="330a1-137">Diagnosis :</span></span>

<span data-ttu-id="330a1-138">In der vorherigen Ausgabe wird beispielsweise angegeben, dass der Test fehlgeschlagen ist, da für den angegebenen Benutzer kein gültiges Clientzertifikat gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="330a1-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="330a1-139">Sie können eine Liste der für einen Benutzer ausgestellten Clientzertifikate zurückgeben, indem Sie einen Befehl wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="330a1-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="330a1-140">Wenn Test-CsClientAuth fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="330a1-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="330a1-141">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsClientAuth eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="330a1-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="330a1-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="330a1-142">For example:</span></span>

<span data-ttu-id="330a1-143">Versuch, ein CS-Zertifikat für Benutzer herunterzuladen: kenmyer@litwareinc.com-Endpunkt: Schritt-Nr</span><span class="sxs-lookup"><span data-stu-id="330a1-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="330a1-144">Webdienst-URL:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="330a1-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="330a1-145">CS-Zertifikat konnte nicht vom Webdienst heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="330a1-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="330a1-146">Kontroll</span><span class="sxs-lookup"><span data-stu-id="330a1-146">CHECK:</span></span>

<span data-ttu-id="330a1-147">\-Die Webdienst-URL ist gültig, und die Webdienste funktionieren.</span><span class="sxs-lookup"><span data-stu-id="330a1-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="330a1-148">\-Wenn Sie die\\\\PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="330a1-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="330a1-149">\-Stellen Sie bei\\Verwendung der NTLM-Kerberos-Authentifizierung sicher, dass Sie gültige Anmeldeinformationen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="330a1-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="330a1-150">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="330a1-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="330a1-151">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsClientAuth möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="330a1-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="330a1-152">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="330a1-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="330a1-153">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="330a1-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="330a1-154">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="330a1-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="330a1-155">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="330a1-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="330a1-156">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="330a1-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="330a1-157">Der Testbenutzer verfügt möglicherweise nicht über ein gültiges Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="330a1-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="330a1-158">Sie können Informationen zu den einem Benutzer zugewiesenen Clientzertifikaten mithilfe eines Befehls zurückgeben, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="330a1-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

