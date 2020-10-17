---
title: 'Lync Server 2013: Testen von Exchange auf lync-Benachrichtigungen'
description: 'Lync Server 2013: Testen von Exchange auf lync-Benachrichtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf453bfdaab7e7b6bdaae8b67ac7759c0d55af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560621"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="c26f6-103">Testen von Exchange auf lync-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c26f6-103">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c26f6-104">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c26f6-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c26f6-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="c26f6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c26f6-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="c26f6-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c26f6-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="c26f6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c26f6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c26f6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c26f6-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c26f6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c26f6-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="c26f6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c26f6-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csexstoragenotification "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="c26f6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="c26f6-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="c26f6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c26f6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c26f6-113">Description</span></span>

<span data-ttu-id="c26f6-114">Das Cmdlet **Test-csexstoragenotification "** wird verwendet, um zu überprüfen, ob der Microsoft Exchange Server 2013-Benachrichtigungsdienst lync Server 2013 jederzeit benachrichtigen kann, wenn Aktualisierungen an der Kontaktliste eines Benutzers vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c26f6-114">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="c26f6-115">Dieses Cmdlet ist nur bei Verwendung des einheitlichen Kontaktspeichers gültig.</span><span class="sxs-lookup"><span data-stu-id="c26f6-115">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c26f6-116">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="c26f6-116">Running the test</span></span>

<span data-ttu-id="c26f6-117">Mit dem Befehl in Beispiel 1 wird überprüft, ob der lync Server Speicherdienst eine Verbindung mit dem Exchange Server-Post Fach Benachrichtigungsdienst für den Benutzer SIP:kenmyer@litwareinc.com herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="c26f6-117">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="c26f6-118">In diesem Beispiel wird "NetNamedPipe" als WCF-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c26f6-118">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c26f6-119">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="c26f6-119">Determining success or failure</span></span>

<span data-ttu-id="c26f6-120">Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert wurde:</span><span class="sxs-lookup"><span data-stu-id="c26f6-120">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="c26f6-121">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c26f6-121">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c26f6-122">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="c26f6-122">Result : Success</span></span>

<span data-ttu-id="c26f6-123">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c26f6-123">Latency : 00:00:00</span></span>

<span data-ttu-id="c26f6-124">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="c26f6-124">Error Message :</span></span>

<span data-ttu-id="c26f6-125">Diagnose</span><span class="sxs-lookup"><span data-stu-id="c26f6-125">Diagnosis :</span></span>

<span data-ttu-id="c26f6-126">Wenn der angegebene Benutzer keine Benachrichtigungen empfangen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="c26f6-126">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c26f6-127">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c26f6-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c26f6-128">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="c26f6-128">Result : Failure</span></span>

<span data-ttu-id="c26f6-129">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c26f6-129">Latency : 00:00:00</span></span>

<span data-ttu-id="c26f6-130">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="c26f6-130">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c26f6-131">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="c26f6-131">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c26f6-132">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="c26f6-132">established connection failed because connected host has</span></span>

<span data-ttu-id="c26f6-133">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c26f6-133">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c26f6-134">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="c26f6-134">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c26f6-135">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="c26f6-135">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c26f6-136">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="c26f6-136">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c26f6-137">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c26f6-137">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c26f6-138">Diagnose</span><span class="sxs-lookup"><span data-stu-id="c26f6-138">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c26f6-139">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="c26f6-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="c26f6-140">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csexstoragenotification "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="c26f6-140">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="c26f6-141">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="c26f6-141">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c26f6-142">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c26f6-142">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c26f6-143">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c26f6-143">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c26f6-144">Dieser Befehl schlägt fehl, wenn der Exchange Server falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c26f6-144">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c26f6-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c26f6-145">See Also</span></span>


[<span data-ttu-id="c26f6-146">Test-csexstorageconnectivity "</span><span class="sxs-lookup"><span data-stu-id="c26f6-146">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

