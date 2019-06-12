---
title: 'Lync Server 2013: Testen der lync Phone Edition-Anmeldung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2cf0dae748cf82e83e86389abf55c55c8c70e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="3c748-102">Testen der lync Phone Edition-Anmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c748-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c748-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3c748-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c748-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="3c748-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3c748-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="3c748-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c748-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="3c748-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3c748-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c748-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c748-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3c748-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3c748-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="3c748-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3c748-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPhoneBootstrap-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="3c748-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="3c748-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="3c748-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3c748-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c748-112">Description</span></span>

<span data-ttu-id="3c748-113">Mit dem Cmdlet Test-CsPhoneBootstrap können Administratoren überprüfen, ob ein bestimmter Benutzer – unter Verwendung der ihm zugewiesenen Telefonnummer und der ihm zugewiesenen PIN – sich über ein lync 2013 Phone Edition-kompatibles Gerät am System anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="3c748-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="3c748-114">(Für die Ausführung des Tests ist eigentlich kein Gerät erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="3c748-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="3c748-115">Damit Test-CsPhoneBootstrap seine Prüfung durchführen kann, muss der Registrierungspool, der das getestete Benutzerkonto hostet, mithilfe von DHCP auffindbar sein.</span><span class="sxs-lookup"><span data-stu-id="3c748-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="3c748-116">Um zu ermitteln, ob eine Registrierungsstelle auf diese Weise auffindbar ist, verwenden Sie das Cmdlet Get-CsRegistrarConfiguration, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3c748-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="3c748-117">Wenn diese Eigenschaft auf "false" festgelegt ist, müssen Sie "CsRegistrarConfiguration" verwenden, um den Eigenschaftswert auf "true" festzulegen und die Registrierungsstelle mithilfe von DHCP auffindbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="3c748-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="3c748-118">Dies kann auch über den Enterprise-DHCP-Server und die Konfiguration der lync Server-spezifischen Optionen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3c748-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3c748-119">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="3c748-119">Running the test</span></span>

<span data-ttu-id="3c748-120">Damit Sie das Cmdlet Test-CsPhoneBootstrap ausführen können, müssen Sie mindestens die Telefonnummer und die persönliche Identifikationsnummer (PIN) des Clients für einen gültigen lync Server-Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="3c748-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="3c748-121">Dieser Befehl testet beispielsweise die Anmeldefähigkeit des Benutzers, der die Telefonnummer 12065551219 und die PIN 0712 hat:</span><span class="sxs-lookup"><span data-stu-id="3c748-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="3c748-122">Für eine umfassendere Überprüfung können Sie auch die SIP-Adresse des Benutzers angeben.</span><span class="sxs-lookup"><span data-stu-id="3c748-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="3c748-123">In diesem Fall müssen die Telefonnummer, die Client-PIN und die SIP-Adresse gültig sein, damit der Test erfolgreich ist:</span><span class="sxs-lookup"><span data-stu-id="3c748-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="3c748-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="3c748-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3c748-125">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="3c748-125">Determining success or failure</span></span>

<span data-ttu-id="3c748-126">Wenn der angegebene Benutzer eine Verbindung mit lync Server herstellen konnte, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als erfolgreich markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="3c748-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3c748-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="3c748-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="3c748-128">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="3c748-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="3c748-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c748-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3c748-130">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="3c748-130">Result : Success</span></span>

<span data-ttu-id="3c748-131">Latenz: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="3c748-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="3c748-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="3c748-132">Error :</span></span>

<span data-ttu-id="3c748-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3c748-133">Diagnosis :</span></span>

<span data-ttu-id="3c748-134">Wenn der angegebene Benutzer keine Verbindung herstellen konnte, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="3c748-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3c748-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c748-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3c748-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="3c748-136">Result : Failure</span></span>

<span data-ttu-id="3c748-137">Latenz: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="3c748-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="3c748-138">Fehler: Fehler – es wurde keine Antwort für den Web-Ticket-Dienst empfangen.</span><span class="sxs-lookup"><span data-stu-id="3c748-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="3c748-139">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3c748-139">Diagnosis :</span></span>

<span data-ttu-id="3c748-140">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, weil der Web-Ticket Dienst nicht reagiert hat.</span><span class="sxs-lookup"><span data-stu-id="3c748-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="3c748-141">Dies kann auf ein Problem mit dem Dienst selbst zurückzuführen sein, oder es kann daran liegen, dass die SIP-Adresse, die Telefonnummer oder die Client-PIN an Test-CsPhoneBootstrap übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3c748-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="3c748-142">Sie können die SIP-Adresse und Telefonnummer des Benutzers mithilfe eines Befehls wie den folgenden überprüfen:</span><span class="sxs-lookup"><span data-stu-id="3c748-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="3c748-143">Und Sie können überprüfen, ob der Benutzer über eine gültige Pin verfügt, indem Sie einen Befehl wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c748-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="3c748-144">Wenn Test-CsPhoneBootstrap fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="3c748-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="3c748-145">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPhoneBootstrap eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="3c748-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="3c748-146">Hier sehen Sie beispielsweise einen Teil der Ausgabe für eine erfolglose Anmeldung, eine Sitzung, in der eine falsche PIN enthalten war:</span><span class="sxs-lookup"><span data-stu-id="3c748-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="3c748-147">Verwenden der PIN-Authentifizierung\\mit Telefon extern: 12065551219-PIN: 0712</span><span class="sxs-lookup"><span data-stu-id="3c748-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="3c748-148">Web-Ticket konnte nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="3c748-148">Could not get web ticket</span></span>

<span data-ttu-id="3c748-149">Kontroll</span><span class="sxs-lookup"><span data-stu-id="3c748-149">CHECK :</span></span>

<span data-ttu-id="3c748-150">\-Die Webdienst-URL ist gültig, und die Webdienste funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3c748-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="3c748-151">\-Wenn Sie die\\PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="3c748-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="3c748-152">\-Stellen Sie bei\\Verwendung der NTLM-Kerberos-Authentifizierung sicher, dass Sie gültige Anmeldeinformationen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="3c748-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3c748-153">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="3c748-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="3c748-154">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsPhoneBootstrap möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="3c748-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="3c748-155">Möglicherweise haben Sie eine ungültige SIP-Adresse angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c748-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="3c748-156">Sie können überprüfen, ob eine SIP-Adresse richtig ist, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c748-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3c748-157">Möglicherweise haben Sie eine ungültige PIN angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c748-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="3c748-158">Obwohl Sie die PIN-Nummer des Benutzers nicht abrufen können, können Sie überprüfen, ob der Benutzer mindestens über eine PIN-Nummer verfügt, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c748-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3c748-159">Möglicherweise haben Sie eine ungültige Telefonnummer angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c748-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="3c748-160">Sie können das Telefon eines Benutzers überprüfen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c748-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="3c748-161">Der Registrierungspool ist nicht DHCP-fähig.</span><span class="sxs-lookup"><span data-stu-id="3c748-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="3c748-162">Wenn Sie feststellen möchten, ob Ihr Registrierungspool für DHCP aktiviert ist, führen Sie das Cmdlet "Get-CsRegistrarConfiguration" aus, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3c748-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="3c748-163">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3c748-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

