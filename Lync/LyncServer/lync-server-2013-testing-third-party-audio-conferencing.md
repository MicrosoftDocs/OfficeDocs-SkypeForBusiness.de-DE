---
title: 'Lync Server 2013: Testen von Drittanbieter-Audiokonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2897e085ea35e17d65719874ecf103ed7f1475d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="3fd98-102">Testen von Drittanbieter-Audiokonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fd98-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fd98-103">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3fd98-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fd98-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="3fd98-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3fd98-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="3fd98-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fd98-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="3fd98-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3fd98-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fd98-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fd98-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3fd98-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3fd98-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="3fd98-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3fd98-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsAudioConferencingProvider verfügt.</span><span class="sxs-lookup"><span data-stu-id="3fd98-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="3fd98-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="3fd98-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3fd98-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fd98-112">Description</span></span>

<span data-ttu-id="3fd98-p102">Bei einem Audiokonferenzanbieter handelt es sich um ein Drittanbieterunternehmen, das Konferenzdienste für Organisationen bereitstellt. Audiokonferenzanbieter bieten Benutzern u. a. die Möglichkeit, von außerhalb eines Standorts und ohne Verbindung mit dem Unternehmensnetzwerk oder dem Internet am Audioteil einer Konferenz oder Besprechung teilzunehmen. Audiokonferenzanbieter stellen oft hochwertige Dienstleistungen wie Simultanübersetzung, Transkription und operatorgestützte Livekonferenzen bereit.</span><span class="sxs-lookup"><span data-stu-id="3fd98-p102">An audio conferencing provider is a third-party company that provides organizations with conferencing services. Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting. Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="3fd98-116">Das Cmdlet **Test-CsAudioConferencingProvider** wird verwendet, um zu überprüfen, ob ein Benutzer in der Lage ist, eine Verbindung mit seinem Audiokonferenz-Anbieter herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3fd98-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="3fd98-117">Beachten Sie, dass dieses Cmdlet auf zwei Arten ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fd98-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="3fd98-118">Viele Administratoren verwenden die Cmdlets vom Typ "CsHealthMonitoringConfiguration", um für jeden Registrierungsstellenpool Testbenutzer einzurichten.</span><span class="sxs-lookup"><span data-stu-id="3fd98-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="3fd98-119">Bei diesen Testbenutzern handelt es sich um ein Paar von Benutzerkonten, das für synthetische Transaktionen vorkonfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="3fd98-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="3fd98-120">(In der Regel handelt es sich um Testkonten und nicht um Konten, die tatsächlichen Benutzern angehören.) Wenn Testbenutzer für einen Pool konfiguriert sind, können Administratoren das **Test-CsAudioConferencingProvider-** Cmdlet für diesen Pool ausführen, ohne die Identität (und die Anmeldeinformationen für) des an dem Test beteiligten Benutzerkontos angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3fd98-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="3fd98-121">Alternativ können Administratoren das Cmdlet **Test-CsAudioConferencingProvider** mit einem tatsächlichen Benutzerkonto ausführen.</span><span class="sxs-lookup"><span data-stu-id="3fd98-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="3fd98-122">Denken Sie beim Ausführen der Tests mit einem tatsächlichen Benutzerkonto daran, dass Sie den Anmeldenamen und das Kennwort jedes Benutzers angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="3fd98-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3fd98-123">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="3fd98-123">Running the test</span></span>

<span data-ttu-id="3fd98-124">In Beispiel 1 wird überprüft, ob ein für den Pool ATL-CS-001.litwareinc.com definierter Testbenutzer in der Lage ist, eine Verbindung mit seinem Audiokonferenz-Anbieter herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3fd98-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="3fd98-125">Für diesen Befehl muss mindestens ein Testbenutzer für den Pool definiert sein.</span><span class="sxs-lookup"><span data-stu-id="3fd98-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="3fd98-126">Wenn keine Testbenutzer für ATL-CS-001.litwareinc.com definiert wurden, tritt beim Befehl ein Fehler auf. Das liegt daran, dass das **Test-CsAudioConferencingProvider-** Cmdlet nicht weiß, welcher Benutzer im Test verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fd98-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="3fd98-127">Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den UserSipAddress-Parameter und die Anmeldeinformationen des Benutzerkontos einschließen, das der Befehl bei der Überprüfung der Verbindung mit einem Anbieter für Audiokonferenzen verwenden sollte.</span><span class="sxs-lookup"><span data-stu-id="3fd98-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="3fd98-128">Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers (\\litwareinc kenmyer), eine Verbindung mit seinem Anbieter für Audiokonferenzen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3fd98-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="3fd98-129">Dazu wird im ersten Befehl des Beispiels das Cmdlet Get-Credential verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Ken Myers enthält.</span><span class="sxs-lookup"><span data-stu-id="3fd98-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="3fd98-130">(Da der Anmeldename litwareinc\\kenmyer als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Ken Myers-Konto angeben.) Das resultierende Credentials-Objekt wird in einer Variablen namens $Credential gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3fd98-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="3fd98-131">Der zweite Befehl prüft anschließend, ob dieser Benutzer eine Verbindung mit dem Audiokonferenzanbieter herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="3fd98-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="3fd98-132">Zur Ausführung dieser Aufgabe wird das Cmdlet Test-CsAudioConferencingProvider zusammen mit drei Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Ken Myers enthält); und UserSipAddress (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).</span><span class="sxs-lookup"><span data-stu-id="3fd98-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3fd98-133">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="3fd98-133">Determining success or failure</span></span>

<span data-ttu-id="3fd98-134">Wenn der Anbieter für Audiokonferenzen ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="3fd98-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3fd98-135">Ziel-FQDN: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3fd98-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="3fd98-136">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="3fd98-136">Result : Success</span></span>

<span data-ttu-id="3fd98-137">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3fd98-137">Latency : 00:00:00</span></span>

<span data-ttu-id="3fd98-138">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="3fd98-138">Error Message :</span></span>

<span data-ttu-id="3fd98-139">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3fd98-139">Diagnosis :</span></span>

<span data-ttu-id="3fd98-140">Wenn sich der angegebene Benutzer nicht anmelden oder abmelden kann, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="3fd98-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3fd98-141">Ziel-FQDN: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3fd98-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="3fd98-142">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="3fd98-142">Result : Failure</span></span>

<span data-ttu-id="3fd98-143">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3fd98-143">Latency : 00:00:00</span></span>

<span data-ttu-id="3fd98-144">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="3fd98-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="3fd98-145">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="3fd98-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="3fd98-146">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="3fd98-146">established connection failed because connected host has</span></span>

<span data-ttu-id="3fd98-147">Fehler bei der \[Antwort 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="3fd98-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="3fd98-148">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="3fd98-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="3fd98-149">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="3fd98-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="3fd98-150">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="3fd98-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="3fd98-151">Fehler beim Antworten</span><span class="sxs-lookup"><span data-stu-id="3fd98-151">has failed to respond</span></span>

<span data-ttu-id="3fd98-152">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="3fd98-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="3fd98-153">Diagnose</span><span class="sxs-lookup"><span data-stu-id="3fd98-153">Diagnosis :</span></span>

<span data-ttu-id="3fd98-154">Die vorherige Ausgabe enthält beispielsweise den Hinweis "der verbundene Teilnehmer hat nicht ordnungsgemäß reagiert", der in der Regel ein Problem mit dem Edgeserver angibt.</span><span class="sxs-lookup"><span data-stu-id="3fd98-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3fd98-155">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="3fd98-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="3fd98-156">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsAudioConferencingProvider** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="3fd98-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="3fd98-157">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="3fd98-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3fd98-158">Wie im vorherigen Beispiel gezeigt, müssen die optionalen Parameter ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="3fd98-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3fd98-159">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3fd98-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3fd98-160">Beachten Sie, dass der Test fehlschlägt, wenn der Benutzer, der mit dem Cmdlet **Test-CsAudioConferencingProvider** beschäftigt ist, keinem Anbieter für Audiokonferenzen zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="3fd98-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="3fd98-161">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3fd98-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

