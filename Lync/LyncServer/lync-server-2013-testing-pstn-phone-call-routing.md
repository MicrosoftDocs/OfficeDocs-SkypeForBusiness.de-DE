---
title: 'Lync Server 2013: Testen des Routings von PSTN-Telefon anrufen'
description: 'Lync Server 2013: Testen der Routingfunktion für PSTN-Telefonanrufe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556271"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="35ef4-103">Testen der PSTN-Anrufweiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ef4-103">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ef4-104">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="35ef4-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35ef4-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="35ef4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="35ef4-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="35ef4-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35ef4-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="35ef4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="35ef4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35ef4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35ef4-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35ef4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="35ef4-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="35ef4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="35ef4-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csintertrunkrouting "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="35ef4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="35ef4-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="35ef4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="35ef4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35ef4-113">Description</span></span>

<span data-ttu-id="35ef4-114">Das Cmdlet **Test-csintertrunkrouting "** überprüft, ob Anrufe von einem SIP an einen anderen weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="35ef4-114">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="35ef4-115">Hierzu erhält das Cmdlet eine Telefonnummer und eine trunkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="35ef4-115">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="35ef4-116">In **Test-csintertrunkrouting "** werden dann übereinstimmende Routen und übereinstimmende PSTN-Verwendungen für die angegebene Nummer zurückgemeldet.</span><span class="sxs-lookup"><span data-stu-id="35ef4-116">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="35ef4-117">Beachten Sie, dass Anrufe nur dann zwischen Trunks geroutet werden können, wenn die Trunks über ein Nummernmuster verfügen, das mit der angegebenen Telefonnummer übereinstimmt, und nur dann, wenn die Trunks mindestens eine PSTN-Nutzung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="35ef4-117">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="35ef4-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="35ef4-118">Running the test</span></span>

<span data-ttu-id="35ef4-119">Die unten gezeigten Befehle geben die übereinstimmenden Routen und übereinstimmenden Telefonverwendungen zurück, mit denen Benutzer die Telefonnummer 1-206-555-1219 mithilfe der trunkkonfigurationseinstellungen für den Standort "Redmond" anrufen können.</span><span class="sxs-lookup"><span data-stu-id="35ef4-119">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="35ef4-120">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="35ef4-120">Determining success or failure</span></span>

<span data-ttu-id="35ef4-121">Wenn Anrufe von einem SIP an einen anderen weitergeleitet werden können, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="35ef4-121">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="35ef4-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="35ef4-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="35ef4-123">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="35ef4-123">\------------------ ------------- --------------</span></span>

<span data-ttu-id="35ef4-124">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="35ef4-124">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="35ef4-125">Wenn der Test nicht erfolgreich war, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="35ef4-125">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="35ef4-126">Test-CsInterTrunkRouting: Argument Transformation für Parameter kann nicht verarbeitet werden</span><span class="sxs-lookup"><span data-stu-id="35ef4-126">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="35ef4-127">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="35ef4-127">'TrunkConfiguration'.</span></span> <span data-ttu-id="35ef4-128">Ungültiger TrunkConfigurationsetting (-Parameter).</span><span class="sxs-lookup"><span data-stu-id="35ef4-128">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="35ef4-129">Geben Sie einen</span><span class="sxs-lookup"><span data-stu-id="35ef4-129">Specify a</span></span>

<span data-ttu-id="35ef4-130">gültige Einstellung (Parameter), und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="35ef4-130">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="35ef4-131">In der Reihe: 1 Char: 79</span><span class="sxs-lookup"><span data-stu-id="35ef4-131">At line:1 char:79</span></span>

<span data-ttu-id="35ef4-132">\+ Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="35ef4-132">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="35ef4-133">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="35ef4-133">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="35ef4-134">\+ CategoryInfo: InvalidData: (:) \[ Test-csintertrunkrouting " \] , par</span><span class="sxs-lookup"><span data-stu-id="35ef4-134">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="35ef4-135">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="35ef4-135">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="35ef4-136">\+ FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="35ef4-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="35ef4-137">TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="35ef4-137">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="35ef4-138">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="35ef4-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="35ef4-139">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csintertrunkrouting "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="35ef4-139">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="35ef4-140">Sie haben ungültige Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="35ef4-140">You specified invalid parameters.</span></span> <span data-ttu-id="35ef4-141">Der trunk ist möglicherweise noch nicht ordnungsgemäß konfiguriert, und die angegebene Ziel Nummer ist möglicherweise falsch oder ungültig.</span><span class="sxs-lookup"><span data-stu-id="35ef4-141">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35ef4-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35ef4-142">See Also</span></span>


[<span data-ttu-id="35ef4-143">Get-cstrunk "</span><span class="sxs-lookup"><span data-stu-id="35ef4-143">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="35ef4-144">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="35ef4-144">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

