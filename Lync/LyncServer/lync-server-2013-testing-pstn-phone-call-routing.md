---
title: 'Lync Server 2013: Testen des Routings von PSTN-Telefon anrufen'
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
ms.openlocfilehash: 8b831aef01d80a0d68a0eea06f429502026b7ccb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="aa99f-102">Testen der PSTN-Anrufweiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa99f-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa99f-103">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="aa99f-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa99f-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="aa99f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="aa99f-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="aa99f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa99f-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="aa99f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="aa99f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa99f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa99f-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="aa99f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="aa99f-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="aa99f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="aa99f-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csintertrunkrouting "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="aa99f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="aa99f-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="aa99f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="aa99f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa99f-112">Description</span></span>

<span data-ttu-id="aa99f-113">Das Cmdlet **Test-csintertrunkrouting "** überprüft, ob Anrufe von einem SIP an einen anderen weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="aa99f-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="aa99f-114">Hierzu erhält das Cmdlet eine Telefonnummer und eine trunkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="aa99f-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="aa99f-115">In **Test-csintertrunkrouting "** werden dann übereinstimmende Routen und übereinstimmende PSTN-Verwendungen für die angegebene Nummer zurückgemeldet.</span><span class="sxs-lookup"><span data-stu-id="aa99f-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="aa99f-116">Beachten Sie, dass Anrufe nur dann zwischen Trunks geroutet werden können, wenn die Trunks über ein Nummernmuster verfügen, das mit der angegebenen Telefonnummer übereinstimmt, und nur dann, wenn die Trunks mindestens eine PSTN-Nutzung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="aa99f-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="aa99f-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="aa99f-117">Running the test</span></span>

<span data-ttu-id="aa99f-118">Die unten gezeigten Befehle geben die übereinstimmenden Routen und übereinstimmenden Telefonverwendungen zurück, mit denen Benutzer die Telefonnummer 1-206-555-1219 mithilfe der trunkkonfigurationseinstellungen für den Standort "Redmond" anrufen können.</span><span class="sxs-lookup"><span data-stu-id="aa99f-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="aa99f-119">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="aa99f-119">Determining success or failure</span></span>

<span data-ttu-id="aa99f-120">Wenn Anrufe von einem SIP an einen anderen weitergeleitet werden können, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="aa99f-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="aa99f-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="aa99f-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="aa99f-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="aa99f-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="aa99f-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="aa99f-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="aa99f-124">Wenn der Test nicht erfolgreich war, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="aa99f-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="aa99f-125">Test-csintertrunkrouting ": Argument Transformation für Parameter kann nicht verarbeitet werden</span><span class="sxs-lookup"><span data-stu-id="aa99f-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="aa99f-126">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="aa99f-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="aa99f-127">Ungültiger TrunkConfigurationsetting (-Parameter).</span><span class="sxs-lookup"><span data-stu-id="aa99f-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="aa99f-128">Geben Sie einen</span><span class="sxs-lookup"><span data-stu-id="aa99f-128">Specify a</span></span>

<span data-ttu-id="aa99f-129">gültige Einstellung (Parameter), und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="aa99f-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="aa99f-130">In der Reihe: 1 Char: 79</span><span class="sxs-lookup"><span data-stu-id="aa99f-130">At line:1 char:79</span></span>

<span data-ttu-id="aa99f-131">\+Test-csintertrunkrouting "-TargetNumber" Tel: + 12065551219 "</span><span class="sxs-lookup"><span data-stu-id="aa99f-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="aa99f-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="aa99f-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="aa99f-133">\+CategoryInfo: InvalidData: (:) \[Test-csintertrunkrouting "\], par</span><span class="sxs-lookup"><span data-stu-id="aa99f-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="aa99f-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="aa99f-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="aa99f-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="aa99f-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="aa99f-136">TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="aa99f-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="aa99f-137">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="aa99f-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="aa99f-138">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csintertrunkrouting "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="aa99f-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="aa99f-139">Sie haben ungültige Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="aa99f-139">You specified invalid parameters.</span></span> <span data-ttu-id="aa99f-140">Der trunk ist möglicherweise noch nicht ordnungsgemäß konfiguriert, und die angegebene Ziel Nummer ist möglicherweise falsch oder ungültig.</span><span class="sxs-lookup"><span data-stu-id="aa99f-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa99f-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa99f-141">See Also</span></span>


[<span data-ttu-id="aa99f-142">Get-cstrunk "</span><span class="sxs-lookup"><span data-stu-id="aa99f-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="aa99f-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa99f-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

