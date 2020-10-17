---
title: 'Lync Server 2013: Testen der Fähigkeit, eine Verbindung mit einer Verbunddomäne herzustellen'
description: 'Lync Server 2013: Testen der Fähigkeit, eine Verbindung mit einer Verbunddomäne herzustellen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560821"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="874de-103">Testen der Fähigkeit zum Herstellen einer Verbindung mit einer Verbunddomäne von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="874de-103">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="874de-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="874de-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="874de-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="874de-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="874de-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="874de-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="874de-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="874de-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="874de-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="874de-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="874de-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="874de-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="874de-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="874de-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="874de-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsFederatedPartner-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="874de-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="874de-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="874de-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="874de-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="874de-113">Description</span></span>

<span data-ttu-id="874de-114">Test-CsFederatedPartner überprüft die Fähigkeit, eine Verbindung mit der Domäne eines Verbundpartners herzustellen.</span><span class="sxs-lookup"><span data-stu-id="874de-114">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="874de-115">Um die Verbindung mit einer Domäne zu überprüfen, muss diese Domäne in der Auflistung zulässiger (Verbund-) Domänen aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="874de-115">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="874de-116">Mit dem folgenden Befehl können Sie eine Liste der Domänen in der Liste der zugelassenen Domänen abrufen:</span><span class="sxs-lookup"><span data-stu-id="874de-116">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="874de-117">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="874de-117">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="874de-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="874de-118">Running the test</span></span>

<span data-ttu-id="874de-119">Das Test-FederatedPartner-Cmdlet erfordert zwei Informationen: den FQDN des Edgeserver und den FQDN des Partnerverbund Partners.</span><span class="sxs-lookup"><span data-stu-id="874de-119">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="874de-120">Beispielsweise testet dieser Befehl die Möglichkeit, eine Verbindung mit der Domäne contoso.com herzustellen:</span><span class="sxs-lookup"><span data-stu-id="874de-120">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="874de-121">Mit diesem Befehl können Sie die Verbindungen zu allen Domänen testen, die sich derzeit in der Liste der zugelassenen Domänen befinden:</span><span class="sxs-lookup"><span data-stu-id="874de-121">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="874de-122">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="874de-122">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="874de-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="874de-123">Determining success or failure</span></span>

<span data-ttu-id="874de-124">Wenn Sie eine Verbindung mit der angegebenen Domäne aufnehmen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="874de-124">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="874de-125">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="874de-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="874de-126">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="874de-126">Result : Success</span></span>

<span data-ttu-id="874de-127">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="874de-127">Latency : 00:00:00</span></span>

<span data-ttu-id="874de-128">Fehler</span><span class="sxs-lookup"><span data-stu-id="874de-128">Error :</span></span>

<span data-ttu-id="874de-129">Diagnose</span><span class="sxs-lookup"><span data-stu-id="874de-129">Diagnosis :</span></span>

<span data-ttu-id="874de-130">Wenn die angegebene Domäne nicht kontaktiert werden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="874de-130">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="874de-131">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="874de-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="874de-132">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="874de-132">Result : Failure</span></span>

<span data-ttu-id="874de-133">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="874de-133">Latency : 00:00:00</span></span>

<span data-ttu-id="874de-134">Fehler: 504, Server Timeout</span><span class="sxs-lookup"><span data-stu-id="874de-134">Error : 504, Server time-out</span></span>

<span data-ttu-id="874de-135">Diagnose: errorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = siehe</span><span class="sxs-lookup"><span data-stu-id="874de-135">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="874de-136">Antwortcode und Grund Phrase.</span><span class="sxs-lookup"><span data-stu-id="874de-136">response code and reason phrase.</span></span>

<span data-ttu-id="874de-137">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="874de-137">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="874de-138">Die vorherige Ausgabe besagt beispielsweise, dass der Test aufgrund eines Servertimeout Fehlers fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="874de-138">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="874de-139">Dies deutet normalerweise auf Netzwerkverbindungsprobleme oder Probleme beim Kontakt mit dem Edgeserver hin.</span><span class="sxs-lookup"><span data-stu-id="874de-139">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="874de-140">Wenn Test-CsFederatedPartner fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="874de-140">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="874de-141">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="874de-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="874de-142">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsFederatedPartner Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="874de-142">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="874de-143">Die Edgeserver ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="874de-143">The Edge Server might not be available.</span></span> <span data-ttu-id="874de-144">Sie können die FQDNs ihrer Edgeserver mithilfe dieses Befehls ausführen:</span><span class="sxs-lookup"><span data-stu-id="874de-144">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="874de-145">Anschließend können Sie jeden Edgeserver anpingen, um sicherzustellen, dass der Zugriff über das Netzwerk möglich ist.</span><span class="sxs-lookup"><span data-stu-id="874de-145">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="874de-146">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="874de-146">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="874de-147">Die angegebene Domäne ist möglicherweise nicht in der Liste der zugelassenen Domänen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="874de-147">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="874de-148">Verwenden Sie den folgenden Befehl, um die Domänen zu überprüfen, die der Liste der zugelassenen Domänen hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="874de-148">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="874de-149">Wenn Sie eine Liste der Domänen anzeigen möchten, mit denen Benutzer die Kommunikation mit blockiert haben, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="874de-149">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

