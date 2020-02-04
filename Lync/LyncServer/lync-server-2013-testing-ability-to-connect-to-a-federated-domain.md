---
title: 'Lync Server 2013: Testen der Möglichkeit zum Herstellen einer Verbindung mit einer Verbunddomäne'
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
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="af1da-102">Testen der Möglichkeit zum Herstellen einer Verbindung mit einer Verbunddomäne von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af1da-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af1da-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="af1da-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af1da-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="af1da-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="af1da-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="af1da-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af1da-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="af1da-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="af1da-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af1da-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af1da-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="af1da-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="af1da-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="af1da-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="af1da-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsFederatedPartner-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="af1da-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="af1da-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="af1da-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="af1da-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af1da-112">Description</span></span>

<span data-ttu-id="af1da-113">Test-CsFederatedPartner überprüft Ihre Möglichkeiten zum Herstellen einer Verbindung mit der Domäne eines Verbundpartners.</span><span class="sxs-lookup"><span data-stu-id="af1da-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="af1da-114">Um die Konnektivität zu einer Domäne zu überprüfen, muss diese Domäne in der Sammlung zulässiger (Verbund-) Domänen aufgelistet sein.</span><span class="sxs-lookup"><span data-stu-id="af1da-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="af1da-115">Mit diesem Befehl können Sie eine Liste der Domänen in der Liste der zulässigen Domänen abrufen:</span><span class="sxs-lookup"><span data-stu-id="af1da-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="af1da-116">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="af1da-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="af1da-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="af1da-117">Running the test</span></span>

<span data-ttu-id="af1da-118">Das Cmdlet Test-FederatedPartner erfordert zwei Informationen: den FQDN des Edge-Servers und den FQDN des Partner Partners.</span><span class="sxs-lookup"><span data-stu-id="af1da-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="af1da-119">Dieser Befehl testet beispielsweise die Möglichkeit zum Herstellen einer Verbindung mit dem Domänen contoso.com:</span><span class="sxs-lookup"><span data-stu-id="af1da-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="af1da-120">Mit diesem Befehl können Sie die Verbindungen zu allen Domänen testen, die sich derzeit in der Liste der zulässigen Domänen befinden:</span><span class="sxs-lookup"><span data-stu-id="af1da-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="af1da-121">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="af1da-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="af1da-122">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="af1da-122">Determining success or failure</span></span>

<span data-ttu-id="af1da-123">Wenn die angegebene Domäne kontaktiert werden kann, erhalten Sie eine ähnliche Ausgabe, wobei die Ergebniseigenschaft als erfolgreich markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="af1da-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="af1da-124">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="af1da-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="af1da-125">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="af1da-125">Result : Success</span></span>

<span data-ttu-id="af1da-126">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="af1da-126">Latency : 00:00:00</span></span>

<span data-ttu-id="af1da-127">Fehler</span><span class="sxs-lookup"><span data-stu-id="af1da-127">Error :</span></span>

<span data-ttu-id="af1da-128">Diagnose</span><span class="sxs-lookup"><span data-stu-id="af1da-128">Diagnosis :</span></span>

<span data-ttu-id="af1da-129">Wenn die angegebene Domäne nicht kontaktiert werden kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="af1da-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="af1da-130">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="af1da-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="af1da-131">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="af1da-131">Result : Failure</span></span>

<span data-ttu-id="af1da-132">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="af1da-132">Latency : 00:00:00</span></span>

<span data-ttu-id="af1da-133">Fehler: 504, Server Timeout</span><span class="sxs-lookup"><span data-stu-id="af1da-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="af1da-134">Diagnose: errorCode = 2, Quelle = ATL-CS-001. "litwareinc. com, Reason = siehe</span><span class="sxs-lookup"><span data-stu-id="af1da-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="af1da-135">Antwortcode und Ursachen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="af1da-135">response code and reason phrase.</span></span>

<span data-ttu-id="af1da-136">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="af1da-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="af1da-137">In der vorherigen Ausgabe wird beispielsweise angegeben, dass der Test aufgrund eines Servertimeout Fehlers fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="af1da-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="af1da-138">Dies weist in der Regel auf Netzwerkverbindungsprobleme oder Probleme beim Kontaktieren des Edge-Servers hin.</span><span class="sxs-lookup"><span data-stu-id="af1da-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="af1da-139">Wenn Test-CsFederatedPartner fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="af1da-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="af1da-140">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="af1da-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="af1da-141">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsFederatedPartner möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="af1da-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="af1da-142">Der Edgeserver steht möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="af1da-142">The Edge Server might not be available.</span></span> <span data-ttu-id="af1da-143">Mit diesem Befehl können Sie die FQDNs ihrer Edgeserver verwenden:</span><span class="sxs-lookup"><span data-stu-id="af1da-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="af1da-144">Anschließend können Sie die einzelnen Edgeserver anpingen, um zu überprüfen, ob Sie über das Netzwerk darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="af1da-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="af1da-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="af1da-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="af1da-146">Die angegebene Domäne ist in der Liste zugelassene Domänen möglicherweise nicht aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="af1da-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="af1da-147">Verwenden Sie diesen Befehl, um die Domänen zu überprüfen, die der Liste zugelassene Domänen hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="af1da-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="af1da-148">Wenn Sie eine Liste der Domänen sehen möchten, mit denen die Kommunikation von Benutzern blockiert wurde, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="af1da-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

