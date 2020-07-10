---
title: Blockieren von eingehenden Anrufen in Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094681"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="72615-102">Eingehende Anrufe blockieren</span><span class="sxs-lookup"><span data-stu-id="72615-102">Block inbound calls</span></span>

<span data-ttu-id="72615-103">Direkte Routing-und Anrufpläne für Telefonsysteme unterstützen das Blockieren von eingehenden Anrufen über das öffentlich geschaltete Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="72615-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="72615-104">Dieses Feature ermöglicht es, eine globale Mandantenliste mit Zahlen Mustern zu definieren, damit die Rufnummernanzeige jedes eingehenden PSTN-Anrufs für den Mandanten anhand der Liste für eine Übereinstimmung überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="72615-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="72615-105">Wenn eine Übereinstimmung erfolgt, wird ein eingehender Anruf abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="72615-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="72615-106">Dieses Feature für eingehende Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf Mandantenebene.</span><span class="sxs-lookup"><span data-stu-id="72615-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="72615-107">Sie steht nicht für einzelne Benutzer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="72615-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="72615-108">Blockierte Anrufer können ein etwas anderes Verhalten erfahren, wenn Sie blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="72615-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="72615-109">Das Verhalten hängt davon ab, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden darf.</span><span class="sxs-lookup"><span data-stu-id="72615-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="72615-110">Zu den Beispielen kann eine Netzbetreiber Nachricht gehören, die besagt, dass der Anruf nicht wie gewählt durchgeführt werden kann, oder Sie können den Anruf einfach ablegen.</span><span class="sxs-lookup"><span data-stu-id="72615-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="72615-111">Anruf Blockierung von Administrator Steuerelementen und-Informationen</span><span class="sxs-lookup"><span data-stu-id="72615-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="72615-112">Administrator Steuerelemente für blockierende Nummern werden nur mithilfe von PowerShell bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="72615-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="72615-113">Zahlenblock Muster werden als reguläre Ausdrucksmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="72615-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="72615-114">Die Reihenfolge der Ausdrücke ist unwichtig – das erste Muster, das in der Liste übereinstimmt, bewirkt, dass der Anruf blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="72615-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="72615-115">Eine neue Nummer oder ein Muster, das in der Liste der blockierten Anrufer hinzugefügt oder entfernt wird, kann bis zu 24 Stunden dauern, bis das Muster aktiv wird.</span><span class="sxs-lookup"><span data-stu-id="72615-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="72615-116">PowerShell-Befehle zum Blockieren von Anrufen</span><span class="sxs-lookup"><span data-stu-id="72615-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="72615-117">Sie verwalten Zahlenmuster mithilfe der Cmdlets " **neu**", " **Abrufen** **", "CsInboundBlockedNumberPattern", "** **Entfernen**"  - **CsInboundBlockedNumberPattern** .</span><span class="sxs-lookup"><span data-stu-id="72615-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="72615-118">Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umzuschalten.</span><span class="sxs-lookup"><span data-stu-id="72615-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="72615-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Zahlenmuster zurück, die der Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, aktiviert (wahr/falsch) und Muster für jeden.</span><span class="sxs-lookup"><span data-stu-id="72615-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="72615-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) fügt der Mandantenliste ein blockiertes Zahlenmuster hinzu.</span><span class="sxs-lookup"><span data-stu-id="72615-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="72615-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.</span><span class="sxs-lookup"><span data-stu-id="72615-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="72615-122">Mit " [CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) " werden in der Mandantenliste mindestens ein Parameter eines blockierten Zahlen Musters geändert.</span><span class="sxs-lookup"><span data-stu-id="72615-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="72615-123">Das anzeigen und Aktivieren des gesamten Anruf Blockierungs Features wird über die Cmdlets **Get**, **Sets**  - **CsTenantBlockingCallingNumbers** verwaltet.</span><span class="sxs-lookup"><span data-stu-id="72615-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="72615-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die Liste der globalen blockierten Nummern einschließlich Enabled (wahr/falsch) zurück.</span><span class="sxs-lookup"><span data-stu-id="72615-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="72615-125">Es gibt eine einzelne globale Mandanten Richtlinie, die nicht manuell anders geändert werden kann, als das Feature ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="72615-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="72615-126">Mit " [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) " können Sie ändern, dass die globalen Mandanten blockierten Anrufe auf Mandantenebene ein-und ausgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="72615-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="72615-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="72615-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="72615-128">Blockieren einer Zahl</span><span class="sxs-lookup"><span data-stu-id="72615-128">Block a number</span></span>

<span data-ttu-id="72615-129">In diesem Beispiel sind die Parameter **Enabled** und **Description** optional.</span><span class="sxs-lookup"><span data-stu-id="72615-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="72615-130">Beim Erstellen eines neuen Musters wird das Muster standardmäßig als aktiviert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="72615-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="72615-131">Die Beschreibung ist ein optionales Feld, in dem weitere Informationen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="72615-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="72615-132">Wir empfehlen, dass Sie einen aussagekräftigen Namen angeben, um einfach zu verstehen, warum das Muster hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="72615-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="72615-133">Wenn Sie Spam-Nummern einfach blockieren, sollten Sie die Regel genauso benennen wie das Zahlenmuster, das verglichen wird, und bei Bedarf zusätzliche Informationen in der Beschreibung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="72615-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="72615-134">Muster werden mit regulären Ausdrücken (Regex) verglichen.</span><span class="sxs-lookup"><span data-stu-id="72615-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="72615-135">Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="72615-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="72615-136">Zulassen einer Zahl</span><span class="sxs-lookup"><span data-stu-id="72615-136">Allow a number</span></span>

<span data-ttu-id="72615-137">In diesem Beispiel ist der Parameter **Identity** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72615-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="72615-138">Wenn die Identität unbekannt ist, verwenden Sie das Cmdlet **Get-CsInboundBlockedNumberPattern** , um zuerst das richtige Muster zu finden und die Identität zu notieren.</span><span class="sxs-lookup"><span data-stu-id="72615-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="72615-139">Führen Sie dann das Cmdlet **Remove-CsTenantBlockedNumberPattern** aus, und übergeben Sie den entsprechenden Identitätswert.</span><span class="sxs-lookup"><span data-stu-id="72615-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="72615-140">Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="72615-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="72615-141">Anzeigen aller Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="72615-141">View all number patterns</span></span>

<span data-ttu-id="72615-142">Wenn Sie dieses Cmdlet ausführen, wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben werden:</span><span class="sxs-lookup"><span data-stu-id="72615-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="72615-143">Verwenden Sie integrierte PowerShell-Filterfähigkeiten, um die zurückgegebenen Werte nach Bedarf zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="72615-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="72615-144">Hinzufügen von Zahlen Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="72615-144">Add number exceptions</span></span>

<span data-ttu-id="72615-145">Sie können Ausnahmen zu blockierten Zahlen Mustern hinzufügen, indem Sie die Cmdlets **New**, **Get**, **Sets**, **Remove**  - **CsTenantBlockNumberExceptionPattern** verwenden.</span><span class="sxs-lookup"><span data-stu-id="72615-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="72615-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) fügt der Mandantenliste ein Zahlen Ausnahme Muster hinzu.</span><span class="sxs-lookup"><span data-stu-id="72615-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="72615-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) gibt eine Liste aller Zahlen Ausnahme Muster zurück, die der Mandantenliste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="72615-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="72615-148">Mit " [CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) " werden mindestens ein Parameter in der Mandantenliste in ein Zahlen Ausnahme Muster geändert.</span><span class="sxs-lookup"><span data-stu-id="72615-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="72615-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) entfernt ein Zahlen Ausnahme Muster aus der Mandantenliste.</span><span class="sxs-lookup"><span data-stu-id="72615-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="72615-150">Beispiele</span><span class="sxs-lookup"><span data-stu-id="72615-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="72615-151">Hinzufügen einer Zahlen Ausnahme</span><span class="sxs-lookup"><span data-stu-id="72615-151">Add a number exception</span></span>

<span data-ttu-id="72615-152">In diesem Beispiel wird ein neues Zahlen Ausnahme Muster erstellt, das standardmäßig als aktiviert hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="72615-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="72615-153">Die Parameter **Enabled** und **Description** sind optional.</span><span class="sxs-lookup"><span data-stu-id="72615-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="72615-154">Alle Zahlen Ausnahmen anzeigen</span><span class="sxs-lookup"><span data-stu-id="72615-154">View all number exceptions</span></span>

<span data-ttu-id="72615-155">In diesem Beispiel ist der Parameter **Identity** optional.</span><span class="sxs-lookup"><span data-stu-id="72615-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="72615-156">Wenn der Parameter **Identity** nicht angegeben ist, gibt dieses Cmdlet eine Liste aller für einen Mandanten eingegebenen Zahlen Ausnahme Muster zurück.</span><span class="sxs-lookup"><span data-stu-id="72615-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="72615-157">Ändern einer Zahlen Ausnahme</span><span class="sxs-lookup"><span data-stu-id="72615-157">Modify a number exception</span></span>

<span data-ttu-id="72615-158">In diesem Beispiel ist der Parameter **Identity** obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="72615-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="72615-159">Mit dem Cmdlet " **Satz-CsTenantBlockedNumberExceptionPattern** " können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmuster Identität ändern.</span><span class="sxs-lookup"><span data-stu-id="72615-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="72615-160">Entfernen einer Zahlen Ausnahme</span><span class="sxs-lookup"><span data-stu-id="72615-160">Remove a number exception</span></span>

<span data-ttu-id="72615-161">In diesem Beispiel ist der Parameter **Identity** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72615-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="72615-162">Mit diesem Cmdlet wird das angegebene Zahlenmuster aus der Mandantenliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="72615-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="72615-163">Wenn die Identität unbekannt ist, verwenden Sie das Cmdlet **Get-CsInboundBlockedNumberPattern** , um zuerst das richtige Muster zu finden und die Identität zu notieren.</span><span class="sxs-lookup"><span data-stu-id="72615-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="72615-164">Führen Sie dann das Cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** aus, und übergeben Sie den entsprechenden Identitätswert.</span><span class="sxs-lookup"><span data-stu-id="72615-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="72615-165">Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="72615-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="72615-166">Testen, ob eine Zahl blockiert ist</span><span class="sxs-lookup"><span data-stu-id="72615-166">Test whether a number is blocked</span></span>

<span data-ttu-id="72615-167">Verwenden Sie das Cmdlet **Test-CsInboundBlockedNumberPattern** , um zu überprüfen, ob eine Zahl im Mandanten blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="72615-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="72615-168">In diesem Beispiel **sind die Parameter** für die Telefonnummer und den **Mandanten** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72615-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="72615-169">Der **Parameter** "Telefonnummer" sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie + oder-sein.</span><span class="sxs-lookup"><span data-stu-id="72615-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="72615-170">In TRPS ist der **Mandanten Parameter** optional.</span><span class="sxs-lookup"><span data-stu-id="72615-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="72615-171">Der resultierende **isNumberBlocked** -Parameter gibt den Wert "true" zurück, wenn die Zahl im Mandanten blockiert ist, und false, wenn er nicht blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="72615-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="72615-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="72615-172">httpResponseCode</span></span>  |<span data-ttu-id="72615-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="72615-173">isNumberBlocked</span></span>   |<span data-ttu-id="72615-174">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="72615-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="72615-175">200</span><span class="sxs-lookup"><span data-stu-id="72615-175">200</span></span>    | <span data-ttu-id="72615-176">Wahr</span><span class="sxs-lookup"><span data-stu-id="72615-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="72615-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="72615-177">httpResponseCode</span></span>  |<span data-ttu-id="72615-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="72615-178">isNumberBlocked</span></span>   |<span data-ttu-id="72615-179">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="72615-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="72615-180">200</span><span class="sxs-lookup"><span data-stu-id="72615-180">200</span></span>    | <span data-ttu-id="72615-181">Falsch</span><span class="sxs-lookup"><span data-stu-id="72615-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="72615-182">Eine Notiz zu Regex</span><span class="sxs-lookup"><span data-stu-id="72615-182">A note about Regex</span></span>

<span data-ttu-id="72615-183">Wie bereits erwähnt, wird der Musterabgleich für das Blockieren von Aufrufen mithilfe von Regex ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72615-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="72615-184">Es stehen mehrere Tools online zur Verfügung, mit denen Sie eine Regex-Musterübereinstimmung überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="72615-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="72615-185">Wenn Sie mit Regex-Mustern nicht vertraut sind, sollten Sie sich etwas Zeit nehmen, um sich mit den Grundlagen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="72615-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="72615-186">Wenn Sie sicherstellen möchten, dass Sie die erwarteten Ergebnisse erzielen, verwenden Sie ein Tool zum Überprüfen von Musterübereinstimmungen, bevor Sie dem Mandanten neue blockierte Nummern Übereinstimmungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="72615-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
