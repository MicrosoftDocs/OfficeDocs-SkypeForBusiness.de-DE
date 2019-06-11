---
title: 'Lync Server 2013: Testen der Sprachkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="a3eef-102">Testen der Sprachkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3eef-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3eef-103">_**Letztes Änderungsdatum des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a3eef-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3eef-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="a3eef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a3eef-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="a3eef-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3eef-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="a3eef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a3eef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3eef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3eef-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a3eef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a3eef-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="a3eef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a3eef-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceTestConfiguration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="a3eef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="a3eef-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="a3eef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a3eef-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3eef-112">Description</span></span>

<span data-ttu-id="a3eef-113">Lync Server umfasst mehrere Windows PowerShell-Cmdlets (wie Test-CsVoiceRoute und Test-CsVoicePolicy, Test-CsTrunkConfiguration), mit denen Sie überprüfen können, ob die einzelnen Teile Ihrer Enterprise-VoIP-Infrastruktur – VoIP-Routen, VoIP Richtlinien, SIP-Stämme, funktionieren wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="a3eef-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="a3eef-114">Während es bei Enterprise-VoIP wichtig ist, dass alle einzelnen Teile funktionieren: Es ist möglich, eine gültige VoIP-Route, eine gültige VoIP-Richtlinie und einen gültigen SIP-Stamm zu haben, aber die Benutzer können dennoch keine Telefonanrufe tätigen oder empfangen.</span><span class="sxs-lookup"><span data-stu-id="a3eef-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="a3eef-115">Aus diesem Grund bietet lync Server auch die Möglichkeit, Sprachtest Konfigurationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3eef-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="a3eef-116">Sprachtest Konfigurationen stellen allgemeine Enterprise-VoIP-Szenarien dar: Sie können beispielsweise eine VoIP-Route, eine VoIP-Richtlinie und einen Wählplan angeben und dann überprüfen, ob diese einzelnen Elemente in der Lage sind, zusammenzuarbeiten, um einen Telefondienst bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a3eef-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="a3eef-117">Darüber hinaus können Sie Ihre Erwartungen in einem bestimmten Szenario überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a3eef-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="a3eef-118">Angenommen, Sie gehen davon aus, dass die Kombination aus Wählplan A und VoIP-Richtlinie B dazu führen würde, dass Anrufe über die VoIP-Route C weitergeleitet werden. Sie können die sprach Route C als ExpectedRoute eingeben.</span><span class="sxs-lookup"><span data-stu-id="a3eef-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="a3eef-119">Wenn Sie den Test ausführen und die VoIP-Route C nicht verwendet wird, wird der Test als fehlerhaft markiert.</span><span class="sxs-lookup"><span data-stu-id="a3eef-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a3eef-120">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="a3eef-120">Running the test</span></span>

<span data-ttu-id="a3eef-121">Bevor Sie sprach Konfigurations Sammlungen mithilfe von Windows PowerShell testen, müssen Sie zuerst das Cmdlet Get-CsVoiceTestConfiguration verwenden, um eine Instanz dieser Konfigurationseinstellungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a3eef-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="a3eef-122">Diese Instanz muss dann an den Test-CsVoiceTestConfiguration umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a3eef-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="a3eef-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3eef-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="a3eef-124">Verwenden Sie stattdessen diesen Befehl, um alle Konfigurationseinstellungen für den Sprachtest gleichzeitig zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="a3eef-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="a3eef-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a3eef-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a3eef-126">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="a3eef-126">Determining success or failure</span></span>

<span data-ttu-id="a3eef-127">Das Cmdlet Test-CsVoiceTestConfiguration meldet, ob ein Test fehlgeschlagen oder erfolgreich war, und bietet zusätzliche Informationen zu jedem erfolgreichen Test, wie etwa die Übersetzungsregel, die VoIP-Route und die PSTN-Nutzung, die zum Ausführen der Aufgabe verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="a3eef-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="a3eef-128">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="a3eef-128">Result:             Success</span></span>

<span data-ttu-id="a3eef-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="a3eef-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="a3eef-130">MatchingRule: Description =; Muster = ^ (\\d{4}) $; Übersetzung = +\\1 d; Name = Test; IsInternalExtension = falsch</span><span class="sxs-lookup"><span data-stu-id="a3eef-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="a3eef-131">FirstMatchingRoute: Website: Redmond</span><span class="sxs-lookup"><span data-stu-id="a3eef-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="a3eef-132">MatchingUsage: lokal</span><span class="sxs-lookup"><span data-stu-id="a3eef-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="a3eef-133">Wenn der Test fehlschlägt, wird das Ergebnis als Fehler gemeldet:</span><span class="sxs-lookup"><span data-stu-id="a3eef-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="a3eef-134">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="a3eef-134">Result:             Fail</span></span>

<span data-ttu-id="a3eef-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="a3eef-135">TranslatedNumber:</span></span>   

<span data-ttu-id="a3eef-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="a3eef-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="a3eef-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="a3eef-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a3eef-138">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="a3eef-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="a3eef-139">Da die Tests für die Sprachtest Konfiguration verschiedene Elemente – einschließlich VoIP-Richtlinien, Wählpläne, VoIP-Routen usw. – testen, gibt es verschiedene Faktoren, die zu einem fehlgeschlagenen Test führen können.</span><span class="sxs-lookup"><span data-stu-id="a3eef-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="a3eef-140">Wenn ein Test fehlschlägt, sollte der erste Schritt darin liegen, die Konfigurationseinstellungen mithilfe des Cmdlets Get-CsVoiceTestConfiguration selbst zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="a3eef-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="a3eef-141">Wenn die Einstellungen anscheinend richtig konfiguriert sind, führen Sie den Test erneut aus, während Sie den Verbose-Parameter einbeziehen:</span><span class="sxs-lookup"><span data-stu-id="a3eef-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="a3eef-142">Der Verbose-Parameter stellt eine Schritt-für-Schritt-Konto für jede Aktion bereit, die von Test-CsVoiceTestConfiguration ausgeführt wird, wie in diesem Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a3eef-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="a3eef-143">Ausführlich: Wähleinstellungen werden geladen: "Global"</span><span class="sxs-lookup"><span data-stu-id="a3eef-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="a3eef-144">Verbose: Laden der VoIP-Richtlinie: "redmonddialplan" "</span><span class="sxs-lookup"><span data-stu-id="a3eef-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="a3eef-145">Dieses Schritt-für-Schritt-Konto bietet möglicherweise einen nützlichen Anhaltspunkt dafür, wo der Test tatsächlich fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="a3eef-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="a3eef-146">Wenn dies nicht der Fall ist, können Sie dann andere Windows PowerShell-Cmdlets verwenden (beispielsweise Test-CsVoicePolicy) und mit der Überprüfung der einzelnen Komponenten, die in den Einstellungen für die sprach Test Konfiguration enthalten sind, methodisch beginnen.</span><span class="sxs-lookup"><span data-stu-id="a3eef-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="a3eef-147">Beachten Sie außerdem, dass es möglich ist, dass ein Test einen Anruf weiterleiten kann und dennoch als Fehler gekennzeichnet ist. Dies kann auftreten, wenn Sie Werte für ExpectedRoute, ExpectedTranslatedNumber und ExpectedUsage eingeben und diese Erwartungen nicht erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="a3eef-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="a3eef-148">Nehmen wir beispielsweise an, dass Sie die VoIP-Route C als Ihre erwartete VoIP-Route eingeben, der Test aber den Anruf tatsächlich mit der VoIP-Route D abgeschlossen hat. In diesem Fall wird der Test als fehlerhaft markiert, weil die erwartete VoIP-Route nicht verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a3eef-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="a3eef-149">Wenn ein Test fehlschlägt, entfernen Sie möglicherweise die Werte für ExpectedRoute, ExpectedTranslatedNumber und ExpectedUsage, und führen Sie dann den Test erneut aus.</span><span class="sxs-lookup"><span data-stu-id="a3eef-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="a3eef-150">Damit können Sie feststellen, ob es sich um einen Fehler handelt, weil der Anruf nicht abgeschlossen werden konnte, oder weil Sie eine Aufgabe erwarten, die Sie tatsächlich erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="a3eef-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3eef-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3eef-151">See Also</span></span>


[<span data-ttu-id="a3eef-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3eef-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

