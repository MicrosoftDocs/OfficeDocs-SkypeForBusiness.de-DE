---
title: 'Lync Server 2013: Testen von Messaging mit xmpp'
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
ms.openlocfilehash: 61eb53c5c2f3cfe74087599535541cfb8286ab55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="666d2-102">Testen von Messaging mithilfe von xmpp in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="666d2-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="666d2-103">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="666d2-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="666d2-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="666d2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="666d2-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="666d2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="666d2-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="666d2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="666d2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="666d2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="666d2-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="666d2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="666d2-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="666d2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="666d2-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csxmppim "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="666d2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="666d2-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="666d2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="666d2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="666d2-112">Description</span></span>

<span data-ttu-id="666d2-113">Das Extensible Messaging and Presence-Protokoll (XMPP) ist ein Standardkommunikationsprotokoll (basierend auf XML), das zum Senden von Nachrichten über das Internet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="666d2-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="666d2-114">XMPP wurde ursprünglich Jabber genannt und wird von verschiedenen Internet-Messaging-und Kommunikationsanwendungen wie Google Talk und Facebook-Chat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="666d2-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="666d2-115">Das Cmdlet **Test-csxmppim "** überprüft, ob ein Benutzer Chatnachrichten mit einem Benutzer in einem XMPP-Netzwerk austauschen kann.</span><span class="sxs-lookup"><span data-stu-id="666d2-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="666d2-116">Beachten Sie, dass Sie für den Erfolg dieses Tests eine gültige SIP-Adresse für den XMPP-Benutzer haben müssen und dass sich diese SIP-Adresse in einem Netzwerk befinden muss, das als zulässiger XMPP-Partner konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="666d2-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="666d2-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="666d2-117">Running the test</span></span>

<span data-ttu-id="666d2-118">Im folgenden Beispiel werden die Funktionen der XMPP-Sofortnachrichten für den Pool ATL-CS-001.litwareinc.com überprüft.</span><span class="sxs-lookup"><span data-stu-id="666d2-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="666d2-119">Dieser Befehl ist nur möglich, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind.</span><span class="sxs-lookup"><span data-stu-id="666d2-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="666d2-120">Wenn dies der Fall ist, wird mit dem Befehl ermittelt, ob der erste Testbenutzer eine XMPP-Sofortnachricht an einen Benutzer senden kann, der über die SIP-Adresse adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="666d2-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="666d2-121">Wenn Testbenutzer nicht definiert sind, tritt beim Ausführen des Befehls ein Fehler auf, da er nicht weiß, welcher Benutzer sich anmelden muss.</span><span class="sxs-lookup"><span data-stu-id="666d2-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="666d2-122">Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den UserSipAddress-Parameter und die Anmeldeinformationen des Benutzers angeben, den der Befehl beim Anmelden verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="666d2-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="666d2-123">Die im nächsten Beispiel gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers (litwareinc\\Pilar), sich anzumelden, um eine XMPP-Sofortnachricht an den Benutzer adelaney@contoso.com zu senden.</span><span class="sxs-lookup"><span data-stu-id="666d2-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="666d2-124">Dazu wird im ersten Befehl des Beispiels das Cmdlet Get-Credential verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="666d2-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="666d2-125">(Da der Anmeldename litwareinc\\Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur vom Administrator eingegeben werden, um das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="666d2-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="666d2-126">Der zweite Befehl prüft dann, ob sich dieser Benutzer am Pool ATL-CS-001.litwareinc.com anmelden und die XMPP-Sofortnachricht senden kann.</span><span class="sxs-lookup"><span data-stu-id="666d2-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="666d2-127">Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-csxmppim "** zusammen mit vier Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); Empfänger (die SIP-Adresse des Benutzers, an den die Nachricht adressiert wird); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und UserSipAddress (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).</span><span class="sxs-lookup"><span data-stu-id="666d2-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="666d2-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="666d2-128">Determining success or failure</span></span>

<span data-ttu-id="666d2-129">Wenn die XMPP-Sofortnachrichtenfunktion ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="666d2-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="666d2-130">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666d2-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="666d2-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="666d2-131">Result : Success</span></span>

<span data-ttu-id="666d2-132">Wartezeit: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="666d2-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="666d2-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="666d2-133">Error Message :</span></span>

<span data-ttu-id="666d2-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="666d2-134">Diagnosis :</span></span>

<span data-ttu-id="666d2-135">Wenn die angegebenen Benutzer keine XMPP-Sofortnachrichten verwenden können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="666d2-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="666d2-136">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="666d2-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="666d2-137">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="666d2-137">domain name (FQDN).</span></span> <span data-ttu-id="666d2-138">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="666d2-138">Using default Registrar port number.</span></span> <span data-ttu-id="666d2-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="666d2-139">Exception:</span></span>

<span data-ttu-id="666d2-140">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="666d2-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="666d2-141">auf</span><span class="sxs-lookup"><span data-stu-id="666d2-141">at</span></span>

<span data-ttu-id="666d2-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="666d2-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="666d2-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="666d2-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="666d2-144">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666d2-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="666d2-145">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="666d2-145">Result : Failure</span></span>

<span data-ttu-id="666d2-146">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="666d2-146">Latency : 00:00:00</span></span>

<span data-ttu-id="666d2-147">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="666d2-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="666d2-148">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="666d2-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="666d2-149">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="666d2-149">established connection failed because connected host has</span></span>

<span data-ttu-id="666d2-150">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="666d2-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="666d2-151">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="666d2-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="666d2-152">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="666d2-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="666d2-153">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="666d2-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="666d2-154">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="666d2-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="666d2-155">Diagnose</span><span class="sxs-lookup"><span data-stu-id="666d2-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="666d2-156">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="666d2-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="666d2-157">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csxmppim "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="666d2-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="666d2-158">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="666d2-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="666d2-159">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="666d2-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="666d2-160">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="666d2-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="666d2-161">Dieser Befehl schlägt fehl, wenn die XMPP-Gateway-Konfiguration falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="666d2-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="666d2-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="666d2-162">See Also</span></span>


[<span data-ttu-id="666d2-163">Gruppe-csxmppgatewayconfiguration "stehen</span><span class="sxs-lookup"><span data-stu-id="666d2-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

