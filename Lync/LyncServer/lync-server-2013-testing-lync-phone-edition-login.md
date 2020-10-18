---
title: 'Lync Server 2013: Testen der Anmeldung von lync Phone Edition'
description: 'Lync Server 2013: Testen von lync Phone Edition Anmeldung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d21d65676c4f5e0f867c7d9556cdea50419be69b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575241"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="3d2fb-103">Testen von lync Phone Edition Anmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d2fb-103">Testing Lync Phone Edition login in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d2fb-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3d2fb-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d2fb-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="3d2fb-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3d2fb-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="3d2fb-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d2fb-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="3d2fb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3d2fb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d2fb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d2fb-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3d2fb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3d2fb-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3d2fb-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPhoneBootstrap-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="3d2fb-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3d2fb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d2fb-113">Description</span></span>

<span data-ttu-id="3d2fb-114">Mit dem Test-CsPhoneBootstrap-Cmdlet können Administratoren überprüfen, ob ein bestimmter Benutzer – unter Verwendung der ihm zugewiesenen Telefonnummer und PIN – sich von einem lync 2013 Phone Edition kompatiblen Gerät beim System anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-114">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="3d2fb-115">(Zum Ausführen des Tests ist tatsächlich kein Gerät erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="3d2fb-115">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="3d2fb-116">Damit Test-CsPhoneBootstrap den Test durchführen kann, muss der Registrierungsstellenpool, der das zu testende Benutzerkonto hostet, mit DHCP erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-116">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="3d2fb-117">Um zu ermitteln, ob eine Registrierungsstelle auf diese Weise erkannt werden kann, verwenden Sie das Cmdlet Get-CsRegistrarConfiguration, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-117">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="3d2fb-118">Wenn diese Eigenschaft auf false festgelegt ist, müssen Sie Set-CsRegistrarConfiguration verwenden, um den Eigenschaftswert auf true festzulegen und die Registrierungsstelle mithilfe von DHCP auffindbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-118">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="3d2fb-119">Dies kann auch mithilfe des Enterprise-DHCP-Servers und der Konfiguration der lync Server spezifischen Optionen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-119">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3d2fb-120">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="3d2fb-120">Running the test</span></span>

<span data-ttu-id="3d2fb-121">Zum Ausführen des Test-CsPhoneBootstrap-Cmdlets müssen Sie mindestens die Telefonnummer und die persönliche Identifikationsnummer (PIN) des Clients für einen gültigen lync Server Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-121">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="3d2fb-122">Beispielsweise testet dieser Befehl die Anmeldefähigkeit für den Benutzer mit der Telefonnummer 12065551219 und dem PIN 0712:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-122">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="3d2fb-123">Für eine umfassendere Überprüfung können Sie auch die SIP-Adresse des Benutzers einschließen.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-123">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="3d2fb-124">In diesem Fall müssen die Telefonnummer, die Client-PIN und die SIP-Adresse gültig sein, damit der Test erfolgreich ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-124">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="3d2fb-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-csphonebootstrap aus](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="3d2fb-125">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3d2fb-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="3d2fb-126">Determining success or failure</span></span>

<span data-ttu-id="3d2fb-127">Wenn der angegebene Benutzer eine Verbindung mit lync Server herstellen konnte, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="3d2fb-127">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3d2fb-128">TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="3d2fb-128">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="3d2fb-129">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="3d2fb-129">CertProvisioningService.svc</span></span>

<span data-ttu-id="3d2fb-130">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d2fb-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d2fb-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="3d2fb-131">Result : Success</span></span>

<span data-ttu-id="3d2fb-132">Wartezeit: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="3d2fb-132">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="3d2fb-133">Fehler</span><span class="sxs-lookup"><span data-stu-id="3d2fb-133">Error :</span></span>

<span data-ttu-id="3d2fb-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3d2fb-134">Diagnosis :</span></span>

<span data-ttu-id="3d2fb-135">Wenn der angegebene Benutzer keine Verbindung herstellen konnte, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-135">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3d2fb-136">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d2fb-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d2fb-137">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="3d2fb-137">Result : Failure</span></span>

<span data-ttu-id="3d2fb-138">Wartezeit: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="3d2fb-138">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="3d2fb-139">Fehler: Fehler – für Web-Ticket Dienst wurde keine Antwort empfangen.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-139">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="3d2fb-140">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3d2fb-140">Diagnosis :</span></span>

<span data-ttu-id="3d2fb-141">Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da der webticketdienst nicht antwortete.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-141">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="3d2fb-142">Dies kann auf ein Problem mit dem Dienst selbst oder auf die SIP-Adresse, Telefonnummer oder Client-Pin zurückzuführen sein, die an Test-csphonebootstrap aus übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-142">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="3d2fb-143">Sie können die SIP-Adresse und Telefonnummer des Benutzers überprüfen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-143">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="3d2fb-144">Sie können überprüfen, ob der Benutzer über eine gültige Pin verfügt, indem Sie einen Befehl wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-144">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="3d2fb-145">Wenn Test-CsPhoneBootstrap fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-145">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="3d2fb-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPhoneBootstrap eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-146">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="3d2fb-147">Hier ist beispielsweise ein Teil der Ausgabe für eine nicht erfolgreiche Anmeldung, eine Sitzung, in der eine falsche PIN enthalten war:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-147">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="3d2fb-148">Verwenden der PIN-Authentifizierung mit Telefon- \\ ext: 12065551219-PIN: 0712</span><span class="sxs-lookup"><span data-stu-id="3d2fb-148">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="3d2fb-149">Das Webdienst Ticket konnte nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-149">Could not get web ticket</span></span>

<span data-ttu-id="3d2fb-150">Kontroll</span><span class="sxs-lookup"><span data-stu-id="3d2fb-150">CHECK :</span></span>

<span data-ttu-id="3d2fb-151">\- Die Webdienst-URL ist gültig, und die Webdienste sind funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-151">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="3d2fb-152">\- Wenn \\ Sie die PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-152">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="3d2fb-153">\- Wenn Sie NTLM \\ -Kerberos-Authentifizierung verwenden, stellen Sie sicher, dass Sie gültige Anmeldeinformationen angegeben haben</span><span class="sxs-lookup"><span data-stu-id="3d2fb-153">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3d2fb-154">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="3d2fb-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="3d2fb-155">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsPhoneBootstrap Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-155">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="3d2fb-156">Möglicherweise haben Sie eine ungültige SIP-Adresse angegeben.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-156">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="3d2fb-157">Sie können überprüfen, ob eine SIP-Adresse korrekt ist, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-157">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3d2fb-158">Möglicherweise haben Sie eine ungültige PIN angegeben.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-158">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="3d2fb-159">Die PIN-Nummer des Benutzers kann zwar nicht abgerufen werden, aber Sie können überprüfen, ob der Benutzer mindestens über eine PIN-Nummer verfügt, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-159">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3d2fb-160">Möglicherweise haben Sie eine ungültige Telefonnummer angegeben.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-160">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="3d2fb-161">Sie können das Telefon eines Benutzers überprüfen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-161">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="3d2fb-162">Der registrierungsstellenpool ist nicht DHCP-fähig.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-162">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="3d2fb-163">Um zu ermitteln, ob Ihr registrierungsstellenpool für DHCP aktiviert ist, führen Sie das Get-CsRegistrarConfiguration-Cmdlet aus, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d2fb-163">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="3d2fb-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3d2fb-164">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

