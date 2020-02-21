---
title: 'Lync Server 2013: Testen der Telefonnummer für eine VoIP-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22c801c7d08c3df663f69df07a6c73a5f17f858
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="61d07-102">Testen der Telefonnummer für eine VoIP-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61d07-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61d07-103">_**Letztes Änderungsstand des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="61d07-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61d07-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="61d07-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="61d07-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="61d07-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61d07-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="61d07-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="61d07-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61d07-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61d07-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="61d07-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="61d07-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="61d07-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="61d07-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsVoicePolicy verfügt.</span><span class="sxs-lookup"><span data-stu-id="61d07-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="61d07-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="61d07-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="61d07-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61d07-112">Description</span></span>

<span data-ttu-id="61d07-113">Die Fähigkeit von Enterprise-VoIP-Benutzern, ausgehende Anrufe über das Festnetz-Scharnier (Public Switched Telephone Network, PSTN) zu tätigen, besteht zu einem großen Teil aus drei Punkten:</span><span class="sxs-lookup"><span data-stu-id="61d07-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="61d07-114">Die dem Benutzer zugewiesene VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="61d07-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="61d07-115">Die VoIP-Routen, die zum Weiterleiten von Anrufen von lync Server an das PSTN-Netzwerk verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61d07-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="61d07-116">Die PSTN-Verwendung, eine lync Server Eigenschaft, die eine VoIP-Richtlinie mit einer VoIP-Route verbindet.</span><span class="sxs-lookup"><span data-stu-id="61d07-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="61d07-117">Die PSTN-Verwendung ist besonders wichtig: Sie ist die Eigenschaft, die eine VoIP-Richtlinie mit einer VoIP-Route verbindet.</span><span class="sxs-lookup"><span data-stu-id="61d07-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="61d07-118">(Eine VoIP-Richtlinie und eine VoIP-Route werden als verbunden bezeichnet, wenn Sie mindestens eine PSTN-Nutzung gemeinsam haben.) VoIP-Richtlinien können ohne Angabe einer PSTN-Verwendung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="61d07-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="61d07-119">In diesem Fall können Benutzer, denen diese Richtlinie zugewiesen wurde, keine ausgehenden Anrufe über das PSTN-Netzwerk tätigen.</span><span class="sxs-lookup"><span data-stu-id="61d07-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="61d07-120">Ebenso können VoIP-Routen, die nicht über mindestens eine festgelegte PSTN-Verwendung verfügen, keine Anrufe an das PSTN-Netzwerk weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="61d07-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="61d07-121">Das Cmdlet Test-CsVoicePolicy überprüft, ob eine bestimmte VoIP-Richtlinie über eine PSTN-Verwendung verfügt und dass die Nutzung von mindestens einer VoIP-Route gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="61d07-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="61d07-122">Wenn die Überprüfung durch Test-CsVoicePolicy erfolgreich ausgeführt wird, meldet das Cmdlet den Namen der ersten gültigen VoIP-Route, die gefunden wird, sowie den Namen der PSTN-Verwendung, die die Richtlinie mit der Route verbindet.</span><span class="sxs-lookup"><span data-stu-id="61d07-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="61d07-123">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="61d07-123">Running the test</span></span>

<span data-ttu-id="61d07-124">Zum Ausführen des Test-CsVoicePolicy-Cmdlets müssen Sie zunächst das Cmdlet Get-CsVoicePolicy verwenden, um eine Instanz der zu testenden VoIP-Richtlinie abzurufen. Diese Instanz muss anschließend an Test-CsVoicePolicy weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="61d07-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="61d07-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="61d07-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="61d07-126">Beachten Sie, dass dieser Befehl, der nicht get-CsVoicePolicy zum Abrufen einer VoIP-Richtlinieninstanz verwendet, fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="61d07-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="61d07-127">Wenn Sie alle VoIP-Richtlinien anhand einer bestimmten Telefonnummer überprüfen möchten, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="61d07-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="61d07-128">Beachten Sie, dass das TargetNumber mithilfe des E. 164-Formats angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="61d07-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="61d07-129">Test-CsVoicePolicy versucht nicht, Telefonnummern in das E. 164-Format zu normalisieren oder zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="61d07-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="61d07-130">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="61d07-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="61d07-131">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="61d07-131">Determining success or failure</span></span>

<span data-ttu-id="61d07-132">Wenn die VoIP-Richtlinie sowohl eine übereinstimmende VoIP-Route als auch eine entsprechende PSTN-Verwendung finden kann, werden sowohl die Route als auch die Nutzung auf dem Bildschirm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="61d07-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="61d07-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="61d07-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="61d07-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="61d07-134">\------------------ -------------</span></span>

<span data-ttu-id="61d07-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="61d07-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="61d07-136">Wenn entweder eine entsprechende VoIP-Route oder eine entsprechende PSTN-Verwendung nicht gefunden werden kann, werden leere Eigenschaftswerte auf dem Bildschirm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="61d07-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="61d07-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="61d07-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="61d07-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="61d07-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="61d07-139">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="61d07-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="61d07-140">Wenn mit Test-CsVoicePolicy keine Übereinstimmung zurückgegeben wird, kann dies bedeuten, dass die VoIP-Richtlinie nicht eine PSTN-Verwendung mit einer VoIP-Route teilt.</span><span class="sxs-lookup"><span data-stu-id="61d07-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="61d07-141">Verwenden Sie zum Überprüfen eines Cmdlets wie das folgende ein Cmdlet, um zu überprüfen, ob PSTN-Verwendungen der VoIP-Richtlinie zugewiesen sind:</span><span class="sxs-lookup"><span data-stu-id="61d07-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="61d07-142">Führen Sie als nächstes den folgenden Befehl aus, um festzustellen, welche PSTN-Verwendungen den einzelnen VoIP-Routen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="61d07-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="61d07-143">Wenn Übereinstimmungen angezeigt werden (wenn eine oder mehrere VoIP-Routen angezeigt werden, die mindestens eine PSTN-Verwendung mit Ihrer VoIP-Richtlinie aufweisen), sollten Sie das Cmdlet Test-CsVoiceRoute ausführen, um sicherzustellen, dass die VoIP-Route die angegebene Telefonnummer wählen kann.</span><span class="sxs-lookup"><span data-stu-id="61d07-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61d07-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61d07-144">See Also</span></span>


[<span data-ttu-id="61d07-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="61d07-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

