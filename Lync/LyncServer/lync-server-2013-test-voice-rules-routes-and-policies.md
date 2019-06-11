---
title: 'Lync Server 2013: Testen von VoIP-Regeln,-Routen und-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="12b1a-102">Testen von VoIP-Regeln,-Routen und-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12b1a-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12b1a-103">_**Letztes Änderungsdatum des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="12b1a-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12b1a-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="12b1a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="12b1a-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="12b1a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b1a-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="12b1a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="12b1a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12b1a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b1a-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="12b1a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="12b1a-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="12b1a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="12b1a-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceUser-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="12b1a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="12b1a-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="12b1a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="12b1a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12b1a-112">Description</span></span>

<span data-ttu-id="12b1a-113">Wenn ein Benutzer einen Telefonanruf tätigt, hängt die Route, die der Anruf zum Erreichen seines Ziels benötigt, von den Richtlinien und den Wählplänen ab, die diesem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="12b1a-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="12b1a-114">Angesichts der SIP-Adresse und einer Telefonnummer eines Benutzers überprüft das Cmdlet Test-CsVoiceUser, ob der betreffende Benutzer einen Anruf an diese Nummer durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="12b1a-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="12b1a-115">Wenn der Test erfolgreich ist, gibt Test-CsVoiceUser Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="12b1a-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="12b1a-116">Die im E. 164-Format übersetzte Zahl (basierend auf dem Wählplan des Benutzers)</span><span class="sxs-lookup"><span data-stu-id="12b1a-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="12b1a-117">Die Normalisierungsregel, die die Übersetzung bereitgestellt hat</span><span class="sxs-lookup"><span data-stu-id="12b1a-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="12b1a-118">Die verwendete VoIP-Route (basierend auf der Routen Priorität);</span><span class="sxs-lookup"><span data-stu-id="12b1a-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="12b1a-119">Die Telefonverwendung, die die VoIP-Richtlinie des Benutzers mit der VoIP-Route verknüpft hat.</span><span class="sxs-lookup"><span data-stu-id="12b1a-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="12b1a-120">Mit Test-CsVoiceUser können Sie feststellen, ob eine bestimmte Telefonnummer wie erwartet weitergeleitet und übersetzt wird, und Sie können bei der Behandlung von Problemen mit dem Anruf helfen, die von einzelnen Benutzern erlebt werden.</span><span class="sxs-lookup"><span data-stu-id="12b1a-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="12b1a-121">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="12b1a-121">Running the test</span></span>

<span data-ttu-id="12b1a-122">Wenn Sie das Cmdlet Test-CsVoiceUser ausführen, müssen Sie zwei Informationen angeben: die Nummer, die gewählt wird (DialedNumber), und die Identität des zu testenden Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="12b1a-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="12b1a-123">Dieser Befehl testet beispielsweise die Fähigkeit des Benutzers, der die SIP-Adresse SIP:kenmyer@litwareinc.com, um einen Anruf an die Telefonnummer + 1206555-1219 zu führen:</span><span class="sxs-lookup"><span data-stu-id="12b1a-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="12b1a-124">Die Telefonnummer sollte so formatiert sein, wie Sie Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="12b1a-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="12b1a-125">Wenn Benutzer beispielsweise in der Regel nicht die 1 wählen, bevor Sie einen Ferngespräch führen, sollten Sie folgendes Format verwenden:</span><span class="sxs-lookup"><span data-stu-id="12b1a-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="12b1a-126">In diesem Fall schlägt der Test natürlich fehl, wenn keine Normalisierungsregel vorhanden ist, mit der die Zahl 2065551219 ordnungsgemäß in das von lync Server verwendete E. 164-Telefon Format übersetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="12b1a-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="12b1a-127">Weitere Informationen finden Sie im Hilfethema Cmdlet New-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="12b1a-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="12b1a-128">Wenn Sie denselben Test für alle Benutzerkonten ausführen möchten, können Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="12b1a-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="12b1a-129">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="12b1a-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="12b1a-130">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="12b1a-130">Determining success or failure</span></span>

<span data-ttu-id="12b1a-131">Wenn der Test erfolgreich abgeschlossen wurde (das heißt, wenn der Benutzer einen Anruf mit der angegebenen Nummer führen kann), werden in der Ausgabe Informationen wie die übersetzte Telefonnummer und die übereinstimmende Normalisierungsregel sowie die VoIP-Route angezeigt:</span><span class="sxs-lookup"><span data-stu-id="12b1a-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="12b1a-132">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="12b1a-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="12b1a-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="12b1a-133"></span></span>

<span data-ttu-id="12b1a-134">\+12065551219...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="12b1a-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="12b1a-135">Aufgrund der Einschränkungen des Windows PowerShell-Bildschirms werden mindestens einige zurückgegebene Informationen (insbesondere die vollständige Beschreibung der übereinstimmenden Normalisierungsregel) möglicherweise nicht auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12b1a-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="12b1a-136">Wenn Sie nur an dem Erfolg oder Misserfolg des Tests interessiert sind, ist dies möglicherweise nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="12b1a-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="12b1a-137">Wenn Sie die vollständigen Details der zurückgegebenen Daten anzeigen möchten, leiten Sie die Ausgabe an das Cmdlet Format-List weiter, wenn Sie den Test ausführen:</span><span class="sxs-lookup"><span data-stu-id="12b1a-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="12b1a-138">Dadurch wird die Ausgabe in einem Leser freundlicheren Format angezeigt:</span><span class="sxs-lookup"><span data-stu-id="12b1a-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="12b1a-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="12b1a-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="12b1a-140">MatchingRule: Description =; Muster = ^ (\\d{11}) $; Übersetzung = + $1;</span><span class="sxs-lookup"><span data-stu-id="12b1a-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="12b1a-141">Name = Präfix alle; IsInternalExtension = falsch</span><span class="sxs-lookup"><span data-stu-id="12b1a-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="12b1a-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="12b1a-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="12b1a-143">MatchingUsage: lokal</span><span class="sxs-lookup"><span data-stu-id="12b1a-143">MatchingUsage : Local</span></span>

<span data-ttu-id="12b1a-144">Wenn der Test fehlschlägt, gibt Test-CsVoiceUser einen leeren Satz von Eigenschaftswerten zurück:</span><span class="sxs-lookup"><span data-stu-id="12b1a-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="12b1a-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="12b1a-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="12b1a-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="12b1a-146"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="12b1a-147">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="12b1a-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="12b1a-148">Es gibt eine Reihe von Gründen, warum das Cmdlet Test-CsVoiceUser möglicherweise fehlschlägt: Es gibt möglicherweise keine Normalisierungsregel, die die angegebene Telefonnummer übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="12b1a-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="12b1a-149">Es können Probleme mit der VoIP-Route auftreten.</span><span class="sxs-lookup"><span data-stu-id="12b1a-149">There could be problems with the voice route.</span></span> <span data-ttu-id="12b1a-150">Es könnte ein Konfigurationsproblem mit dem Wählplan geben, der dem betreffenden Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="12b1a-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="12b1a-151">Aus diesem Grund sollten Sie den Verbose-Parameter einbeziehen, wenn Sie das Cmdlet Test-CsVoiceUser ausführen:</span><span class="sxs-lookup"><span data-stu-id="12b1a-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="12b1a-152">Wenn das Cmdlet "Verbose" enthalten ist, gibt Test-CsVoiceUser eine detaillierte Übersicht über alle Schritte, die bei der Durchführung der Überprüfungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="12b1a-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="12b1a-153">So können Sie beispielsweise die folgenden Schritte sehen:</span><span class="sxs-lookup"><span data-stu-id="12b1a-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="12b1a-154">Ausführlich: Suchen des Benutzers mit der Identität "SIP:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="12b1a-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="12b1a-155">Ausführlich: Wähleinstellungen werden geladen: "redmonddialplan" "</span><span class="sxs-lookup"><span data-stu-id="12b1a-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="12b1a-156">Diese zusätzlichen Informationen können Hinweise auf die Schritte liefern, die Sie ausführen können, um die Ursache des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="12b1a-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="12b1a-157">Die hier gezeigte ausführliche Ausgabe zeigt beispielsweise an, dass dem getesteten Benutzer der Wählplan redmonddialplan "zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="12b1a-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="12b1a-158">Wenn der Test fehlgeschlagen ist, besteht ein logischer nächster Schritt darin, zu überprüfen, ob redmonddialplan "die angegebene Telefonnummer übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="12b1a-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12b1a-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12b1a-159">See Also</span></span>


[<span data-ttu-id="12b1a-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="12b1a-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

