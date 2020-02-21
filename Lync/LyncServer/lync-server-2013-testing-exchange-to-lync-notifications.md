---
title: 'Lync Server 2013: Testen von Exchange auf lync-Benachrichtigungen'
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
ms.openlocfilehash: d186a41c8997f7e05a9bc9be93b44ff7b675b907
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="53baa-102">Testen von Exchange auf lync-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53baa-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53baa-103">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="53baa-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53baa-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="53baa-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="53baa-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="53baa-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53baa-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="53baa-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="53baa-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53baa-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53baa-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="53baa-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="53baa-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="53baa-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="53baa-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csexstoragenotification "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="53baa-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="53baa-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="53baa-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="53baa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53baa-112">Description</span></span>

<span data-ttu-id="53baa-113">Das Cmdlet **Test-csexstoragenotification "** wird verwendet, um zu überprüfen, ob der Microsoft Exchange Server 2013-Benachrichtigungsdienst lync Server 2013 jederzeit benachrichtigen kann, wenn Aktualisierungen an der Kontaktliste eines Benutzers vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="53baa-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="53baa-114">Dieses Cmdlet ist nur bei Verwendung des einheitlichen Kontaktspeichers gültig.</span><span class="sxs-lookup"><span data-stu-id="53baa-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="53baa-115">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="53baa-115">Running the test</span></span>

<span data-ttu-id="53baa-116">Mit dem Befehl in Beispiel 1 wird überprüft, ob der lync Server Speicherdienst eine Verbindung mit dem Exchange Server-Post Fach Benachrichtigungsdienst für den Benutzer SIP:kenmyer@litwareinc.com herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="53baa-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="53baa-117">In diesem Beispiel wird "NetNamedPipe" als WCF-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="53baa-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="53baa-118">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="53baa-118">Determining success or failure</span></span>

<span data-ttu-id="53baa-119">Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert wurde:</span><span class="sxs-lookup"><span data-stu-id="53baa-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="53baa-120">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="53baa-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="53baa-121">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="53baa-121">Result : Success</span></span>

<span data-ttu-id="53baa-122">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="53baa-122">Latency : 00:00:00</span></span>

<span data-ttu-id="53baa-123">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="53baa-123">Error Message :</span></span>

<span data-ttu-id="53baa-124">Diagnose</span><span class="sxs-lookup"><span data-stu-id="53baa-124">Diagnosis :</span></span>

<span data-ttu-id="53baa-125">Wenn der angegebene Benutzer keine Benachrichtigungen empfangen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="53baa-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="53baa-126">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="53baa-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="53baa-127">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="53baa-127">Result : Failure</span></span>

<span data-ttu-id="53baa-128">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="53baa-128">Latency : 00:00:00</span></span>

<span data-ttu-id="53baa-129">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="53baa-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="53baa-130">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="53baa-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="53baa-131">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="53baa-131">established connection failed because connected host has</span></span>

<span data-ttu-id="53baa-132">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="53baa-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="53baa-133">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="53baa-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="53baa-134">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="53baa-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="53baa-135">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="53baa-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="53baa-136">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="53baa-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="53baa-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="53baa-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="53baa-138">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="53baa-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="53baa-139">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csexstoragenotification "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="53baa-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="53baa-140">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="53baa-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="53baa-141">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53baa-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="53baa-142">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="53baa-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="53baa-143">Dieser Befehl schlägt fehl, wenn der Exchange Server falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="53baa-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53baa-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53baa-144">See Also</span></span>


[<span data-ttu-id="53baa-145">Test-csexstorageconnectivity "</span><span class="sxs-lookup"><span data-stu-id="53baa-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

