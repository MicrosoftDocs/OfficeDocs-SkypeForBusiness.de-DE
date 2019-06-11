---
title: 'Lync Server 2013: Testen des PSTN-Anruf Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faa6bfe178397ab474c1bcd8edc21107faff8dc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="42adf-102">Testen des PSTN-Anruf Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42adf-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42adf-103">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="42adf-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42adf-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="42adf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="42adf-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="42adf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42adf-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="42adf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="42adf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42adf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42adf-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="42adf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="42adf-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="42adf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="42adf-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsInterTrunkRouting-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="42adf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="42adf-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="42adf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="42adf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42adf-112">Description</span></span>

<span data-ttu-id="42adf-113">Das Cmdlet **Test-CsInterTrunkRouting** überprüft, ob Anrufe von einem SIP an einen anderen weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="42adf-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="42adf-114">Dazu erhält das Cmdlet eine Telefonnummer und eine trunk-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="42adf-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="42adf-115">In **Test-CsInterTrunkRouting** werden dann übereinstimmende Routen und übereinstimmende PSTN-Verwendungen für die angegebene Nummer zurückgemeldet.</span><span class="sxs-lookup"><span data-stu-id="42adf-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="42adf-116">Beachten Sie, dass Anrufe nur zwischen Trunks geroutet werden können, wenn die Trunks ein Zahlenmuster aufweisen, das der angegebenen Telefonnummer entspricht, und nur, wenn die Trunks mindestens eine PSTN-Nutzung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="42adf-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="42adf-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="42adf-117">Running the test</span></span>

<span data-ttu-id="42adf-118">Die folgenden Befehle geben die übereinstimmenden Routen und die übereinstimmenden Telefonverwendungen zurück, mit denen Benutzer die Telefonnummer 1-206-555-1219 mit den trunk-Konfigurationseinstellungen für die Website "Redmond" anrufen können.</span><span class="sxs-lookup"><span data-stu-id="42adf-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="42adf-119">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="42adf-119">Determining success or failure</span></span>

<span data-ttu-id="42adf-120">Wenn Anrufe von einem SIP an einen anderen weitergeleitet werden können, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="42adf-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="42adf-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="42adf-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="42adf-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="42adf-122"></span></span>

<span data-ttu-id="42adf-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="42adf-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="42adf-124">Wenn der Test nicht erfolgreich war, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="42adf-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="42adf-125">Test-CsInterTrunkRouting: die Argument Transformation für Parameter kann nicht verarbeitet werden</span><span class="sxs-lookup"><span data-stu-id="42adf-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="42adf-126">'TrunkConfiguration'.</span><span class="sxs-lookup"><span data-stu-id="42adf-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="42adf-127">Ungültiger TrunkConfigurationsetting (Parameter).</span><span class="sxs-lookup"><span data-stu-id="42adf-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="42adf-128">Angeben eines</span><span class="sxs-lookup"><span data-stu-id="42adf-128">Specify a</span></span>

<span data-ttu-id="42adf-129">gültige Einstellung (Parameter), und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="42adf-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="42adf-130">Zeile: 1 Zeichen: 79</span><span class="sxs-lookup"><span data-stu-id="42adf-130">At line:1 char:79</span></span>

<span data-ttu-id="42adf-131">\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="42adf-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="42adf-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="42adf-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="42adf-133">\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par</span><span class="sxs-lookup"><span data-stu-id="42adf-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="42adf-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="42adf-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="42adf-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="42adf-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="42adf-136">TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="42adf-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="42adf-137">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="42adf-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="42adf-138">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsInterTrunkRouting** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="42adf-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="42adf-139">Sie haben ungültige Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="42adf-139">You specified invalid parameters.</span></span> <span data-ttu-id="42adf-140">Der trunk ist möglicherweise noch nicht richtig konfiguriert, und die angegebene Ziel Nummer ist möglicherweise falsch oder ungültig.</span><span class="sxs-lookup"><span data-stu-id="42adf-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42adf-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42adf-141">See Also</span></span>


[<span data-ttu-id="42adf-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="42adf-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="42adf-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="42adf-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

