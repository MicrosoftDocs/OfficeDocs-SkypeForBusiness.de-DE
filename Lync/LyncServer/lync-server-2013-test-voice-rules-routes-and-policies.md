---
title: 'Lync Server 2013: Testen von VoIP-Regeln,-Routen und-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 689f591b416cdab6eb5d325a7dade2c54659d072
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42017886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="06a9f-102">Testen von VoIP-Regeln,-Routen und-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06a9f-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06a9f-103">_**Letztes Änderungsstand des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="06a9f-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06a9f-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="06a9f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="06a9f-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="06a9f-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a9f-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="06a9f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="06a9f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a9f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a9f-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06a9f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="06a9f-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="06a9f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="06a9f-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsVoiceUser verfügt.</span><span class="sxs-lookup"><span data-stu-id="06a9f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="06a9f-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="06a9f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="06a9f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06a9f-112">Description</span></span>

<span data-ttu-id="06a9f-113">Wenn ein Benutzer einen Anruf tätigt, richtet sich die Route, die der Anruf zum Erreichen seines Ziels benötigt, sowohl nach den Richtlinien als auch den Wählplänen, die diesem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="06a9f-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="06a9f-114">Wenn die SIP-Adresse und eine Telefonnummer eines Benutzers angegeben werden, überprüft das Cmdlet Test-CsVoiceUser, ob der betreffende Benutzer einen Anruf an diese Nummer abschließen kann.</span><span class="sxs-lookup"><span data-stu-id="06a9f-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="06a9f-115">Wenn der Test erfolgreich ist, gibt Test-CsVoiceUser Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="06a9f-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="06a9f-116">Die im E. 164-Format übersetzte Nummer (basierend auf den Wähleinstellungen des Benutzers)</span><span class="sxs-lookup"><span data-stu-id="06a9f-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="06a9f-117">Die Normalisierungsregel, die die Übersetzung bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="06a9f-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="06a9f-118">Die verwendete VoIP-Route (basierend auf der Routen Priorität);</span><span class="sxs-lookup"><span data-stu-id="06a9f-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="06a9f-119">Die Telefonverwendung, die die VoIP-Richtlinie des Benutzers mit der VoIP-Route verknüpft hat.</span><span class="sxs-lookup"><span data-stu-id="06a9f-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="06a9f-120">Mit Test-CsVoiceUser können Sie bestimmen, ob eine bestimmte Telefonnummer wie erwartet weitergeleitet und übersetzt wird und kann bei der Behandlung von anrufbezogenen Problemen behilflich sein, die von einzelnen Benutzern auftreten.</span><span class="sxs-lookup"><span data-stu-id="06a9f-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="06a9f-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="06a9f-121">Running the test</span></span>

<span data-ttu-id="06a9f-122">Wenn Sie das Cmdlet Test-CsVoiceUser ausführen, müssen Sie zwei Informationen angeben: die Nummer, die gewählt wird ("DialedNumber") und die Identität des zu testenden Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="06a9f-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="06a9f-123">Beispielsweise testet dieser Befehl die Fähigkeit des Benutzers, der über die SIP-Adresse SIP:kenmyer@litwareinc.com verfügt, um einen Anruf an die Telefonnummer + 1206555-1219 zu tätigen:</span><span class="sxs-lookup"><span data-stu-id="06a9f-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="06a9f-124">Die Telefonnummer sollte so formatiert sein, dass Sie von Ihrer Wahl ausgehen.</span><span class="sxs-lookup"><span data-stu-id="06a9f-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="06a9f-125">Wenn beispielsweise Benutzer normalerweise nicht die 1 wählen, bevor Sie einen Ferngesprächen tätigen, sollten Sie dieses Format verwenden:</span><span class="sxs-lookup"><span data-stu-id="06a9f-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="06a9f-126">In diesem Fall schlägt der Test natürlich fehl, wenn keine Normalisierungsregel vorhanden ist, mit der die Nummer 2065551219 korrekt in das von lync Server verwendete E. 164-Telefon Format übersetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06a9f-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="06a9f-127">Weitere Informationen finden Sie im Hilfethema New-CsVoiceNormalizationRule-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="06a9f-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="06a9f-128">Wenn Sie denselben Test für jedes Ihrer Benutzerkonten ausführen möchten, können Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="06a9f-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="06a9f-129">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="06a9f-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="06a9f-130">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="06a9f-130">Determining success or failure</span></span>

<span data-ttu-id="06a9f-131">Wenn der Test erfolgreich abgeschlossen wurde (also, wenn der Benutzer einen Anruf für die angegebene Nummer tätigen kann), werden in der Ausgabe Informationen wie die übersetzte Telefonnummer und die passende Normalisierungsregel und VoIP-Route angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06a9f-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="06a9f-132">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="06a9f-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="06a9f-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="06a9f-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="06a9f-134">\+12065551219 Descripti...    LocalRoute lokal</span><span class="sxs-lookup"><span data-stu-id="06a9f-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="06a9f-135">Aufgrund der Einschränkungen des Windows PowerShell Bildschirms werden mindestens einige zurückgegebene Informationen (insbesondere die vollständige Beschreibung der übereinstimmenden Normalisierungsregel) möglicherweise nicht auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06a9f-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="06a9f-136">Wenn Sie nur am Erfolg oder Misserfolg des Tests interessiert sind, ist dies möglicherweise nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="06a9f-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="06a9f-137">Wenn Sie die vollständigen Details der zurückgegebenen Daten sehen möchten, übergeben Sie die Ausgabe an das Cmdlet Format-List, wenn Sie den Test ausführen:</span><span class="sxs-lookup"><span data-stu-id="06a9f-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="06a9f-138">Dadurch wird die Ausgabe in einem Leser freundlicheren Format angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06a9f-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="06a9f-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="06a9f-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="06a9f-140">MatchingRule: Description =; Muster = ^ (\\d{11}) $; Übersetzung = + $1;</span><span class="sxs-lookup"><span data-stu-id="06a9f-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="06a9f-141">Name = Prefix all; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="06a9f-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="06a9f-142">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="06a9f-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="06a9f-143">MatchingUsage: lokal</span><span class="sxs-lookup"><span data-stu-id="06a9f-143">MatchingUsage : Local</span></span>

<span data-ttu-id="06a9f-144">Wenn der Test fehlschlägt, gibt Test-CsVoiceUser eine leere Gruppe von Eigenschaftswerten zurück:</span><span class="sxs-lookup"><span data-stu-id="06a9f-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="06a9f-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="06a9f-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="06a9f-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="06a9f-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="06a9f-147">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="06a9f-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="06a9f-148">Es gibt eine Reihe von Gründen, aus denen das Test-CsVoiceUser-Cmdlet möglicherweise fehlschlägt: Es ist möglicherweise keine Normalisierungsregel vorhanden, mit der die bereitgestellte Telefonnummer übersetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06a9f-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="06a9f-149">Es kann Probleme mit der VoIP-Route geben.</span><span class="sxs-lookup"><span data-stu-id="06a9f-149">There could be problems with the voice route.</span></span> <span data-ttu-id="06a9f-150">Es kann ein Konfigurationsproblem mit den Wähleinstellungen geben, die dem betreffenden Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="06a9f-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="06a9f-151">Aus diesem Grund sollten Sie den Verbose-Parameter einschließen, wenn Sie das Cmdlet Test-CsVoiceUser ausführen:</span><span class="sxs-lookup"><span data-stu-id="06a9f-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="06a9f-152">Wenn das Verbose-Cmdlet enthalten ist, gibt Test-CsVoiceUser ein detailliertes Konto aller Schritte aus, die bei der Durchführung der Überprüfungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="06a9f-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="06a9f-153">Beispielsweise können Sie die folgenden Schritte wie folgt sehen:</span><span class="sxs-lookup"><span data-stu-id="06a9f-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="06a9f-154">Ausführlich: Suchen von Benutzern mit der Identität "SIP:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="06a9f-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="06a9f-155">Ausführlich: Wähleinstellungen werden geladen: "" redmonddialplan ""</span><span class="sxs-lookup"><span data-stu-id="06a9f-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="06a9f-156">Diese zusätzlichen Informationen können Hinweise auf die Schritte liefern, die Sie ausführen können, um die Ursache des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="06a9f-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="06a9f-157">Die hier gezeigte ausführliche Ausgabe gibt beispielsweise an, dass der getestete Benutzer dem Wählplan "redmonddialplan" zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="06a9f-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="06a9f-158">Wenn der Test fehlgeschlagen ist, besteht ein logischer nächster Schritt darin, zu überprüfen, ob die angegebene Telefonnummer von "redmonddialplan" übersetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06a9f-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06a9f-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06a9f-159">See Also</span></span>


[<span data-ttu-id="06a9f-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="06a9f-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

