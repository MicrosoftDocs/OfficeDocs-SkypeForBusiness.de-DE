---
title: 'Lync Server 2013: Testen der Wähleinstellungen'
description: 'Lync Server 2013: Testen der Wähleinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef2e3fce9d1fbbb0186b1b7aef608834145d3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556171"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="ebb70-103">Testen der Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebb70-103">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebb70-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ebb70-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebb70-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="ebb70-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ebb70-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="ebb70-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebb70-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="ebb70-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ebb70-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebb70-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebb70-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ebb70-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ebb70-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="ebb70-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ebb70-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsDialPlan-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="ebb70-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="ebb70-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="ebb70-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ebb70-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebb70-113">Description</span></span>

<span data-ttu-id="ebb70-114">Mit dem Test-CsDialPlan-Cmdlet können Sie die Ergebnisse der Anwendung einer Wähleinstellungen auf eine bestimmte Telefonnummer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ebb70-114">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="ebb70-115">Wählpläne bieten Informationen, beispielsweise zum Anwenden von Normalisierungsregeln, die erforderlich sind, um Enterprise-VoIP-Benutzern das tätigen von Telefon anrufen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ebb70-115">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="ebb70-116">Bei einer gewählten Nummer und einem Wählplan überprüft dieses Cmdlet, welche Normalisierungsregel innerhalb des Wählplans angewendet wird und welche übersetzte Nummer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebb70-116">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="ebb70-117">Sie können dieses Cmdlet verwenden, um Probleme bei der Übersetzung von Nummern zu beheben oder um zu überprüfen, wie Regeln für bestimmte Nummern angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebb70-117">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ebb70-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="ebb70-118">Running the test</span></span>

<span data-ttu-id="ebb70-119">Das Test-CsDialPlan-Cmdlet erfordert zwei Schritte.</span><span class="sxs-lookup"><span data-stu-id="ebb70-119">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="ebb70-120">Zunächst müssen Sie eine Instanz der zu testenden Wähleinstellungen abrufen. Dies kann mithilfe des Get-CsDialPlan-Cmdlets erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ebb70-120">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="ebb70-121">Zweitens müssen Sie die Telefonnummer angeben, die normalisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ebb70-121">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="ebb70-122">Das für die Telefonnummer verwendete Format sollte mit der Nummer übereinstimmen, die von einem Benutzer gewählt/eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ebb70-122">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="ebb70-123">Mit diesem Befehl wird beispielsweise eine Instanz des Wählplans, "redmonddialplan", abgerufen, und es wird überprüft, ob die Telefonnummer 12065551219 normalisiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="ebb70-123">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="ebb70-124">Wenn Sie eine Normalisierungsregel haben, die den Landescode automatisch hinzufügt (in diesem Beispiel 1) und die Vorwahl (206), können Sie die Telefonnummer 5551219 wie folgt überprüfen:</span><span class="sxs-lookup"><span data-stu-id="ebb70-124">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="ebb70-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="ebb70-125">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ebb70-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="ebb70-126">Determining success or failure</span></span>

<span data-ttu-id="ebb70-127">Test-CsDialPlan unterscheidet sich von vielen der lync Server Test-Cmdlets, da Sie nur indirekt angibt, ob ein Test erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="ebb70-127">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="ebb70-128">Wenn Sie Test-CsDialPlan verwenden, erhalten Sie keine ähnliche Ausgabe wie diese, sodass das Ergebnis eindeutig gekennzeichnet ist:</span><span class="sxs-lookup"><span data-stu-id="ebb70-128">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="ebb70-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ebb70-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ebb70-130">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="ebb70-130">Result : Success</span></span>

<span data-ttu-id="ebb70-131">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="ebb70-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="ebb70-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="ebb70-132">Error :</span></span>

<span data-ttu-id="ebb70-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="ebb70-133">Diagnosis :</span></span>

<span data-ttu-id="ebb70-134">Wenn Test-CsDialPlan erfolgreich ist, erhalten Sie stattdessen Informationen zur Normalisierungsregel, mit der die angegebene Telefonnummer erfolgreich übersetzt und verwendet werden konnte:</span><span class="sxs-lookup"><span data-stu-id="ebb70-134">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="ebb70-135">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="ebb70-135">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="ebb70-136">MatchingRule: Description =; Pattern = ^ ( \\ d (11)) $; Übersetzung = + $1;</span><span class="sxs-lookup"><span data-stu-id="ebb70-136">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="ebb70-137">Name = alle Präfixe; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="ebb70-137">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="ebb70-138">Wenn Test-CsDialPlan fehlschlägt (das heißt, wenn der Wählplan keine Normalisierungsregel aufweist, die die angegebene Telefonnummer übersetzen kann), erhalten Sie nur die "leere" Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ebb70-138">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="ebb70-139">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="ebb70-139">TranslatedNumber :</span></span>

<span data-ttu-id="ebb70-140">MatchingRule</span><span class="sxs-lookup"><span data-stu-id="ebb70-140">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ebb70-141">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="ebb70-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="ebb70-142">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsDialPlan Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="ebb70-142">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="ebb70-143">Bei der Angabe der Telefonnummer haben Sie möglicherweise ein falsches Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebb70-143">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="ebb70-144">Zu den Wählplänen gehören Normalisierungsregeln, mit denen lync Server die von einem Benutzer gewählten oder eingegebenen Telefonnummern übersetzen können.</span><span class="sxs-lookup"><span data-stu-id="ebb70-144">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="ebb70-145">Daher sollten ihre Wähleinstellungen Normalisierungsregeln aufweisen, die mit den Nummern übereinstimmen, die Benutzer wahrscheinlich wählen müssen.</span><span class="sxs-lookup"><span data-stu-id="ebb70-145">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="ebb70-146">Wenn Benutzer beispielsweise die Ländervorwahl, die Vorwahl und dann die Telefonnummer selbst wählen, bedeutet dies, dass Ihr Wählplan über eine Normalisierungsregel zur Behandlung von Telefonnummern verfügt:</span><span class="sxs-lookup"><span data-stu-id="ebb70-146">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="ebb70-147">12065551219</span><span class="sxs-lookup"><span data-stu-id="ebb70-147">12065551219</span></span>
    
    <span data-ttu-id="ebb70-148">Wenn Sie jedoch eine falsche Telefonnummer eingeben (beispielsweise die letzte Ziffer weglassen), tritt bei Test-CsDialPlan ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="ebb70-148">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="ebb70-149">Dies liegt nicht daran, dass die Wähleinstellungen fehlerhaft sind, sondern weil Sie eine Telefonnummer eingegeben haben, die nicht interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebb70-149">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

