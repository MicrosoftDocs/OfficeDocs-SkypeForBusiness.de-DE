---
title: 'Lync Server 2013: Testen der Telefonnummer für eine VoIP-Route'
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
ms.openlocfilehash: 3fccdcb5dfc0fe52c2c0dcf80f7f6a374e35a39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="f6a8e-102">Testen der Telefonnummer für eine VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6a8e-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6a8e-103">_**Letztes Änderungsstand des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="f6a8e-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6a8e-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="f6a8e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f6a8e-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="f6a8e-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6a8e-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="f6a8e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f6a8e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6a8e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6a8e-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f6a8e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f6a8e-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f6a8e-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsVoiceRoute verfügt.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="f6a8e-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f6a8e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6a8e-112">Description</span></span>

<span data-ttu-id="f6a8e-113">VoIP-Routen arbeiten zusammen mit VoIP-Richtlinien, um Enterprise-VoIP-Anrufe an das PSTN-Netzwerk weiterleiten zu können.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="f6a8e-114">Jede VoIP-Route enthält einen regulären Ausdruck (ein Nummernmuster), mit dem die Telefonnummern identifiziert werden, die über eine bestimmte VoIP-Route weitergeleitet werden: die Route kann alle Telefonnummern verarbeiten, die diesem regulären Ausdruck entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="f6a8e-115">Beispielsweise kann eine VoIP-Route einen regulären Ausdruck haben, der es ermöglicht, eine beliebige 10-stellige Zahl zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="f6a8e-116">Das bedeutet, dass die Route eine Telefonnummer wie die folgende verarbeiten kann:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="f6a8e-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="f6a8e-117">2065551219</span></span>

<span data-ttu-id="f6a8e-118">Die Route kann keine der folgenden zwei Zahlen verarbeiten, von denen keine 10 Ziffern enthält:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="f6a8e-119">5551219</span><span class="sxs-lookup"><span data-stu-id="f6a8e-119">5551219</span></span>

  - <span data-ttu-id="f6a8e-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="f6a8e-120">12065551219</span></span>

<span data-ttu-id="f6a8e-121">Das Cmdlet Test-CsVoiceRoute überprüft, ob eine bestimmte VoIP-Route eine angegebene Telefonnummer weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f6a8e-122">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="f6a8e-122">Running the test</span></span>

<span data-ttu-id="f6a8e-123">Die Überprüfung der Fähigkeit einer VoIP-Route zum Weiterleiten einer bestimmten Telefonnummer ist ein zweistufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="f6a8e-124">Zunächst müssen Sie das Cmdlet Get-CsVoiceRoute verwenden, um eine Instanz dieser VoIP-Route zurückzugeben, und anschließend müssen Sie das Test-CsVoiceRoute-Cmdlet verwenden, um zu überprüfen, ob diese Route die Zieltelefonnummer verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="f6a8e-125">Mit diesem Befehl wird beispielsweise überprüft, ob die RedmondVoiceRoute-VoIP-Route die Telefonnummer 2065551219 weiterleiten kann:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="f6a8e-126">Beachten Sie, dass die Telefonnummer so eingegeben werden sollte, wie Sie davon ausgehen, dass die Benutzer diese Nummer wählen.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="f6a8e-127">Wenn Sie beispielsweise nicht davon ausgehen, dass Benutzer beim wählen die Landes-und Ortsvorwahl einbeziehen möchten, verwenden Sie eine ähnliche Syntax wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="f6a8e-128">In diesem Fall hinterlässt die Ziel Nummer sowohl die Ländervorwahl als auch die Vorwahl.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="f6a8e-129">Verwenden Sie eine Syntax wie die folgende, um einen einzelnen Befehl zum Testen aller VoIP-Routen für eine angegebene Ziel Nummer zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="f6a8e-130">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f6a8e-131">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="f6a8e-131">Determining success or failure</span></span>

<span data-ttu-id="f6a8e-132">Wenn die VoIP-Route die Zieltelefonnummer weiterleiten kann, gibt das Cmdlet "Test-CsVoiceRoute" nur den Wert "true" zurück:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="f6a8e-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="f6a8e-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="f6a8e-134">Wahr</span><span class="sxs-lookup"><span data-stu-id="f6a8e-134">True</span></span>

<span data-ttu-id="f6a8e-135">Das bedeutet, dass die Route Nummern ähnlich wie die Zielrufnummer verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="f6a8e-136">Wenn die VoIP-Route die Ziel Nummer nicht verarbeiten kann, gibt Test-CsVoiceRoute den Wert false zurück:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="f6a8e-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="f6a8e-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="f6a8e-138">False</span><span class="sxs-lookup"><span data-stu-id="f6a8e-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f6a8e-139">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="f6a8e-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="f6a8e-140">Beim Testen von VoIP-Routen ist "Fehler" ein relativer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="f6a8e-141">In diesem Fall bedeutet dies nicht, dass die Route irgendwie "kaputt" ist, sondern bedeutet nur, dass die Zielrufnummer nicht von der Route verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="f6a8e-142">Dies kann daran liegen, dass die VoIP-Route falsch konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="f6a8e-143">Dies kann auch bedeuten, dass die Route nie mit diesem Muster Zahlen verarbeiten sollte.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="f6a8e-144">Wenn Sie beispielsweise keine Anrufe an andere Länder über eine bestimmte Route weiterleiten möchten, kann diese Route so konfiguriert werden, dass alle Telefonnummern abgelehnt werden, die eine Ländervorwahl enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="f6a8e-145">Wenn Test-CsVoiceRoute false zurückgibt, wenn Sie erwartet haben, dass true zurückgegeben wird, überprüfen Sie, ob Sie die Zielrufnummer richtig eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="f6a8e-146">Wenn Sie dies getan haben, verwenden Sie einen Befehl wie den folgenden, um die für die Route konfigurierte NumberPattern anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6a8e-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6a8e-147">See Also</span></span>


[<span data-ttu-id="f6a8e-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="f6a8e-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

