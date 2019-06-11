---
title: 'Lync Server 2013: Testen des Wählplans'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="9d578-102">Testen des Wählplans in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d578-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d578-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9d578-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d578-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="9d578-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9d578-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="9d578-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d578-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="9d578-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9d578-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d578-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d578-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9d578-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9d578-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="9d578-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9d578-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsDialPlan-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="9d578-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="9d578-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="9d578-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9d578-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d578-112">Description</span></span>

<span data-ttu-id="9d578-113">Mit dem Cmdlet Test-CsDialPlan können Sie die Ergebnisse der Anwendung eines Wählplans auf eine bestimmte Telefonnummer sehen.</span><span class="sxs-lookup"><span data-stu-id="9d578-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="9d578-114">Wählpläne liefern Informationen, wie beispielsweise die Anwendung von Normalisierungsregeln, die erforderlich sind, damit Enterprise-VoIP-Benutzer Telefonanrufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="9d578-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="9d578-115">Mit einer gewählten Nummer und einem Wählplan wird mit diesem Cmdlet überprüft, welche Normalisierungsregel innerhalb des Wählplans angewendet wird und welche übersetzte Nummer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d578-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="9d578-116">Sie können dieses Cmdlet verwenden, um Probleme bei der Übersetzung von Zahlen zu beheben oder um zu überprüfen, wie Regeln für bestimmte Zahlen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d578-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9d578-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="9d578-117">Running the test</span></span>

<span data-ttu-id="9d578-118">Das Cmdlet Test-CsDialPlan erfordert zwei Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="9d578-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="9d578-119">Zunächst müssen Sie eine Instanz des Wählplans abrufen, der getestet wird. Dies kann mit dem Cmdlet Get-CsDialPlan erfolgen.</span><span class="sxs-lookup"><span data-stu-id="9d578-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="9d578-120">Als nächstes müssen Sie die Telefonnummer angeben, die normalisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d578-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="9d578-121">Das für die Telefonnummer verwendete Format sollte mit der Nummer übereinstimmen, die von einem Benutzer gewählt/eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9d578-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="9d578-122">Mit diesem Befehl wird beispielsweise eine Instanz des Wählplans, redmonddialplan ", abgerufen, und es wird überprüft, ob die Telefonnummer 12065551219 normalisiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="9d578-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="9d578-123">Wenn Sie über eine Normalisierungsregel verfügen, die die Landesvorwahl (in diesem Beispiel 1) und die Ortsvorwahl (206) automatisch hinzufügt, sollten Sie die Telefonnummer 5551219 wie folgt überprüfen:</span><span class="sxs-lookup"><span data-stu-id="9d578-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="9d578-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="9d578-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9d578-125">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="9d578-125">Determining success or failure</span></span>

<span data-ttu-id="9d578-126">Test-CsDialPlan unterscheidet sich von vielen der lync Server Test-Cmdlets, da Sie nur indirekt angibt, ob ein Test erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="9d578-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="9d578-127">Bei Verwendung von Test-CsDialPlan erhalten Sie keine ähnliche Ausgabe wie diese, wobei das Ergebnis deutlich gekennzeichnet ist:</span><span class="sxs-lookup"><span data-stu-id="9d578-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="9d578-128">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9d578-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9d578-129">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="9d578-129">Result : Success</span></span>

<span data-ttu-id="9d578-130">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="9d578-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="9d578-131">Fehler</span><span class="sxs-lookup"><span data-stu-id="9d578-131">Error :</span></span>

<span data-ttu-id="9d578-132">Diagnose</span><span class="sxs-lookup"><span data-stu-id="9d578-132">Diagnosis :</span></span>

<span data-ttu-id="9d578-133">Wenn Test-CsDialPlan erfolgreich ist, erhalten Sie stattdessen Informationen zur Normalisierungsregel, die die angegebene Telefonnummer erfolgreich übersetzen und verwenden konnte:</span><span class="sxs-lookup"><span data-stu-id="9d578-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="9d578-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="9d578-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="9d578-135">MatchingRule: Description =; Muster = ^ (\\d (11)) $; Übersetzung = + $1;</span><span class="sxs-lookup"><span data-stu-id="9d578-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="9d578-136">Name = Präfix alle; IsInternalExtension = falsch</span><span class="sxs-lookup"><span data-stu-id="9d578-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="9d578-137">Wenn Test-CsDialPlan fehlschlägt (das heißt, wenn der Wählplan nicht über eine Normalisierungsregel verfügt, die die angegebene Telefonnummer übersetzen kann), erhalten Sie einfach die "leere" Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9d578-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="9d578-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="9d578-138">TranslatedNumber :</span></span>

<span data-ttu-id="9d578-139">MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9d578-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9d578-140">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="9d578-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="9d578-141">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsDialPlan möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="9d578-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="9d578-142">Möglicherweise haben Sie bei der Angabe der Telefonnummer ein falsches Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d578-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="9d578-143">Zu den Wählplänen gehören Normalisierungsregeln, mit denen lync Server die von einem Benutzer gewählten oder eingegebenen Telefonnummern übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="9d578-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="9d578-144">Daher sollten ihre Wähleinstellungen die Normalisierungsregeln aufweisen, die den Zahlen entsprechen, die Benutzer wahrscheinlich wählen.</span><span class="sxs-lookup"><span data-stu-id="9d578-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="9d578-145">Wenn Benutzer beispielsweise die Landesvorwahl, Ortsvorwahl und dann die Telefonnummer selbst wählen, bedeutet dies, dass Ihr Wählplan über eine Normalisierungsregel zur Behandlung von Telefonnummern wie diesen verfügt:</span><span class="sxs-lookup"><span data-stu-id="9d578-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="9d578-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="9d578-146">12065551219</span></span>
    
    <span data-ttu-id="9d578-147">Wenn Sie jedoch eine falsche Telefonnummer eingeben (beispielsweise, indem Sie die letzte Ziffer verlassen), schlägt die Test-CsDialPlan fehl.</span><span class="sxs-lookup"><span data-stu-id="9d578-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="9d578-148">Das liegt nicht daran, dass die Wähleinstellungen fehlerhaft sind, sondern weil Sie eine Telefonnummer eingegeben haben, als nicht interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9d578-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

