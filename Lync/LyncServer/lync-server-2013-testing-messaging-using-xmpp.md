---
title: 'Lync Server 2013: Testen von Messaging mit xmpp'
description: 'Lync Server 2013: Testen von Messaging mit xmpp.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556301"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="6acba-103">Testen von Messaging mithilfe von xmpp in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6acba-103">Testing messaging using XMPP in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6acba-104">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="6acba-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6acba-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="6acba-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6acba-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="6acba-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6acba-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="6acba-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6acba-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6acba-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6acba-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6acba-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6acba-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="6acba-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6acba-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csxmppim "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="6acba-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="6acba-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="6acba-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6acba-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6acba-113">Description</span></span>

<span data-ttu-id="6acba-114">Das Extensible Messaging and Presence-Protokoll (XMPP) ist ein Standardkommunikationsprotokoll (basierend auf XML), das zum Senden von Nachrichten über das Internet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6acba-114">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="6acba-115">XMPP wurde ursprünglich Jabber genannt und wird von verschiedenen Internet-Messaging-und Kommunikationsanwendungen wie Google Talk und Facebook-Chat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6acba-115">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="6acba-116">Das Cmdlet **Test-csxmppim "** überprüft, ob ein Benutzer Chatnachrichten mit einem Benutzer in einem XMPP-Netzwerk austauschen kann.</span><span class="sxs-lookup"><span data-stu-id="6acba-116">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="6acba-117">Beachten Sie, dass Sie für den Erfolg dieses Tests eine gültige SIP-Adresse für den XMPP-Benutzer haben müssen und dass sich diese SIP-Adresse in einem Netzwerk befinden muss, das als zulässiger XMPP-Partner konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="6acba-117">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6acba-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="6acba-118">Running the test</span></span>

<span data-ttu-id="6acba-119">Im folgenden Beispiel werden die Funktionen der XMPP-Sofortnachrichten für den Pool ATL-CS-001.litwareinc.com überprüft.</span><span class="sxs-lookup"><span data-stu-id="6acba-119">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="6acba-120">Dieser Befehl ist nur möglich, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6acba-120">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="6acba-121">Wenn dies der Fall ist, wird mit dem Befehl ermittelt, ob der erste Testbenutzer eine XMPP-Sofortnachricht an einen Benutzer senden kann, der über die SIP-Adresse adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6acba-121">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="6acba-122">Wenn Testbenutzer nicht definiert sind, tritt beim Ausführen des Befehls ein Fehler auf, da er nicht weiß, welcher Benutzer sich anmelden muss.</span><span class="sxs-lookup"><span data-stu-id="6acba-122">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="6acba-123">Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den UserSipAddress-Parameter und die Anmeldeinformationen des Benutzers angeben, den der Befehl beim Anmelden verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="6acba-123">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="6acba-124">Die im nächsten Beispiel gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers (litwareinc \\ Pilar), sich anzumelden, um eine XMPP-Sofortnachricht an den Benutzer adelaney@contoso.com zu senden.</span><span class="sxs-lookup"><span data-stu-id="6acba-124">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="6acba-125">Dazu wird im ersten Befehl des Beispiels das Get-Credential-Cmdlet verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="6acba-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="6acba-126">(Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur vom Administrator eingegeben werden, um das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6acba-126">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="6acba-127">Der zweite Befehl prüft dann, ob sich dieser Benutzer am Pool ATL-CS-001.litwareinc.com anmelden und die XMPP-Sofortnachricht senden kann.</span><span class="sxs-lookup"><span data-stu-id="6acba-127">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="6acba-128">Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-csxmppim "** zusammen mit vier Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); Empfänger (die SIP-Adresse des Benutzers, an den die Nachricht adressiert wird); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und UserSipAddress (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).</span><span class="sxs-lookup"><span data-stu-id="6acba-128">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6acba-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="6acba-129">Determining success or failure</span></span>

<span data-ttu-id="6acba-130">Wenn die XMPP-Sofortnachrichtenfunktion ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="6acba-130">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="6acba-131">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6acba-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6acba-132">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="6acba-132">Result : Success</span></span>

<span data-ttu-id="6acba-133">Wartezeit: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="6acba-133">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="6acba-134">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="6acba-134">Error Message :</span></span>

<span data-ttu-id="6acba-135">Diagnose</span><span class="sxs-lookup"><span data-stu-id="6acba-135">Diagnosis :</span></span>

<span data-ttu-id="6acba-136">Wenn die angegebenen Benutzer keine XMPP-Sofortnachrichten verwenden können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="6acba-136">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6acba-137">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="6acba-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="6acba-138">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="6acba-138">domain name (FQDN).</span></span> <span data-ttu-id="6acba-139">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="6acba-139">Using default Registrar port number.</span></span> <span data-ttu-id="6acba-140">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="6acba-140">Exception:</span></span>

<span data-ttu-id="6acba-141">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="6acba-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="6acba-142">auf</span><span class="sxs-lookup"><span data-stu-id="6acba-142">at</span></span>

<span data-ttu-id="6acba-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="6acba-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="6acba-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="6acba-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="6acba-145">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6acba-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6acba-146">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="6acba-146">Result : Failure</span></span>

<span data-ttu-id="6acba-147">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6acba-147">Latency : 00:00:00</span></span>

<span data-ttu-id="6acba-148">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="6acba-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="6acba-149">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="6acba-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="6acba-150">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="6acba-150">established connection failed because connected host has</span></span>

<span data-ttu-id="6acba-151">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="6acba-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="6acba-152">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="6acba-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="6acba-153">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="6acba-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="6acba-154">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="6acba-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="6acba-155">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="6acba-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="6acba-156">Diagnose</span><span class="sxs-lookup"><span data-stu-id="6acba-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6acba-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="6acba-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="6acba-158">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csxmppim "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="6acba-158">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="6acba-159">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="6acba-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="6acba-160">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6acba-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="6acba-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6acba-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="6acba-162">Dieser Befehl schlägt fehl, wenn die XMPP-Gateway-Konfiguration falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6acba-162">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6acba-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6acba-163">See Also</span></span>


[<span data-ttu-id="6acba-164">Gruppe-csxmppgatewayconfiguration "stehen</span><span class="sxs-lookup"><span data-stu-id="6acba-164">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

