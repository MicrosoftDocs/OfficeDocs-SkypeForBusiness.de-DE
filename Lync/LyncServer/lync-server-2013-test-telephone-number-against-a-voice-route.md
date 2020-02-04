---
title: 'Lync Server 2013: Testen einer Telefonnummer mit einer VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d4105b54c7d5b745efddeeb961960c402aaa349
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="6fc20-102">Testen einer Telefonnummer für eine VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fc20-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fc20-103">_**Letztes Änderungsdatum des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="6fc20-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fc20-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="6fc20-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6fc20-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="6fc20-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fc20-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="6fc20-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6fc20-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fc20-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fc20-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6fc20-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6fc20-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="6fc20-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6fc20-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceRoute-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="6fc20-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="6fc20-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="6fc20-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6fc20-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fc20-112">Description</span></span>

<span data-ttu-id="6fc20-113">VoIP-Routen arbeiten zusammen mit VoIP-Richtlinien, um Enterprise-Sprachanrufe an das PSTN-Netzwerk weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="6fc20-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="6fc20-114">Jede VoIP-Route enthält einen regulären Ausdruck (ein Zahlenmuster), der die Telefonnummern identifiziert, die über eine bestimmte VoIP-Route weitergeleitet werden: die Route kann alle Telefonnummern behandeln, die diesem regulären Ausdruck entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6fc20-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="6fc20-115">Beispielsweise kann eine VoIP-Route einen regulären Ausdruck aufweisen, der es ermöglicht, eine beliebige 10-stellige Zahl zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6fc20-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="6fc20-116">Das bedeutet, dass die Route eine Telefonnummer wie die folgende behandeln kann:</span><span class="sxs-lookup"><span data-stu-id="6fc20-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="6fc20-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="6fc20-117">2065551219</span></span>

<span data-ttu-id="6fc20-118">Die Route kann keine der beiden folgenden Zahlen behandeln, von denen keine 10 Ziffern umfasst:</span><span class="sxs-lookup"><span data-stu-id="6fc20-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="6fc20-119">5551219</span><span class="sxs-lookup"><span data-stu-id="6fc20-119">5551219</span></span>

  - <span data-ttu-id="6fc20-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="6fc20-120">12065551219</span></span>

<span data-ttu-id="6fc20-121">Das Cmdlet Test-CsVoiceRoute überprüft, ob eine bestimmte VoIP-Route eine bestimmte Telefonnummer weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="6fc20-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6fc20-122">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="6fc20-122">Running the test</span></span>

<span data-ttu-id="6fc20-123">Die Überprüfung, ob eine VoIP-Route eine bestimmte Telefonnummer weiterleiten kann, ist ein zweistufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="6fc20-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="6fc20-124">Zunächst müssen Sie das Cmdlet Get-CsVoiceRoute verwenden, um eine Instanz dieser VoIP-Route zurückzugeben, und dann müssen Sie das Test-CsVoiceRoute-Cmdlet verwenden, um die Fähigkeit dieser Route zur Behandlung der Zieltelefonnummer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6fc20-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="6fc20-125">Mit diesem Befehl wird beispielsweise überprüft, ob die RedmondVoiceRoute-VoIP-Route die Telefonnummer 2065551219 weiterleiten kann:</span><span class="sxs-lookup"><span data-stu-id="6fc20-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="6fc20-126">Beachten Sie, dass die Telefonnummer so eingegeben werden sollte, wie Sie erwarten, dass die Benutzer diese Nummer wählen.</span><span class="sxs-lookup"><span data-stu-id="6fc20-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="6fc20-127">Wenn Sie beispielsweise nicht davon ausgehen, dass Benutzer beim wählen die Landes-und Ortsvorwahl einbeziehen, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="6fc20-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="6fc20-128">In diesem Fall hinterlässt die Ziel Nummer sowohl die Landesvorwahl als auch die Ortsvorwahl.</span><span class="sxs-lookup"><span data-stu-id="6fc20-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="6fc20-129">Wenn Sie mit einem einzelnen Befehl alle VoIP-Routen für eine angegebene Zielrufnummer testen möchten, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="6fc20-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="6fc20-130">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="6fc20-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6fc20-131">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="6fc20-131">Determining success or failure</span></span>

<span data-ttu-id="6fc20-132">Wenn die VoIP-Route die Zieltelefonnummer weiterleiten kann, gibt das Cmdlet "Test-CsVoiceRoute" nur den Wert "true" zurück:</span><span class="sxs-lookup"><span data-stu-id="6fc20-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="6fc20-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="6fc20-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="6fc20-134">Wahr</span><span class="sxs-lookup"><span data-stu-id="6fc20-134">True</span></span>

<span data-ttu-id="6fc20-135">Das bedeutet, dass die Route Zahlen ähnlich wie die Ziel Nummer verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6fc20-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="6fc20-136">Wenn die VoIP-Route die Ziel Nummer nicht verarbeiten kann, gibt Test-CsVoiceRoute den Wert false zurück:</span><span class="sxs-lookup"><span data-stu-id="6fc20-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="6fc20-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="6fc20-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="6fc20-138">Falsch</span><span class="sxs-lookup"><span data-stu-id="6fc20-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6fc20-139">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="6fc20-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="6fc20-140">Beim Testen von VoIP-Routen ist "Fehler" ein relativer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6fc20-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="6fc20-141">In diesem Fall bedeutet dies nicht, dass die Route irgendwie "kaputt" ist, sondern bedeutet nur, dass die Route die Ziel Nummer nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6fc20-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="6fc20-142">Dies kann daran liegen, dass die VoIP-Route falsch konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="6fc20-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="6fc20-143">Es könnte auch bedeuten, dass die Route nie dazu bestimmt war, Zahlen unter Verwendung dieses Musters zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6fc20-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="6fc20-144">Wenn Sie beispielsweise keine Anrufe an andere Länder über eine bestimmte Route weiterleiten möchten, kann die Route so konfiguriert werden, dass alle Telefonnummern, die eine Landesvorwahl enthalten, abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="6fc20-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="6fc20-145">Wenn Test-CsVoiceRoute false zurückgibt, wenn Sie erwartet haben, dass true zurückgegeben wird, überprüfen Sie, ob Sie die Ziel Nummer korrekt eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6fc20-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="6fc20-146">Wenn ja, verwenden Sie einen ähnlichen Befehl, um die für die Route konfigurierte NumberPattern anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="6fc20-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fc20-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fc20-147">See Also</span></span>


[<span data-ttu-id="6fc20-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="6fc20-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

