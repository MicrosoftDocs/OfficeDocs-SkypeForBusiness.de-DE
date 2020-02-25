---
title: Blockieren von eingehenden Anrufen in Skype for Business Online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266064"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="53aad-102">Eingehende Anrufe blockieren</span><span class="sxs-lookup"><span data-stu-id="53aad-102">Block inbound calls</span></span>

<span data-ttu-id="53aad-103">Skype for Business Online-Anrufpläne unterstützen nun die Blockierung von eingehenden Anrufen aus dem öffentlich geschalteten Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="53aad-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="53aad-104">Dieses Feature ermöglicht es, eine globale Mandantenliste mit Zahlen Mustern zu definieren, damit die Rufnummernanzeige jedes eingehenden PSTN-Anrufs für den Mandanten anhand der Liste für eine Übereinstimmung überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="53aad-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="53aad-105">Wenn eine Übereinstimmung erfolgt, wird ein eingehender Anruf abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="53aad-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="53aad-106">Dieses Feature für eingehende Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf Mandantenebene.</span><span class="sxs-lookup"><span data-stu-id="53aad-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="53aad-107">Sie steht nicht für einzelne Benutzer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="53aad-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="53aad-108">Dieses Feature steht noch nicht für die direkte Weiterleitung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="53aad-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="53aad-109">Blockierte Anrufer können ein etwas anderes Verhalten erfahren, wenn Sie blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="53aad-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="53aad-110">Das Verhalten hängt davon ab, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden darf.</span><span class="sxs-lookup"><span data-stu-id="53aad-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="53aad-111">Zu den Beispielen kann eine Netzbetreiber Nachricht gehören, die besagt, dass der Anruf nicht wie gewählt durchgeführt werden kann, oder Sie können den Anruf einfach ablegen.</span><span class="sxs-lookup"><span data-stu-id="53aad-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="53aad-112">Anruf Blockierung von Administrator Steuerelementen und-Informationen</span><span class="sxs-lookup"><span data-stu-id="53aad-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="53aad-113">Administrator Steuerelemente für blockierende Nummern werden nur mithilfe von PowerShell bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="53aad-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="53aad-114">Zahlenblock Muster werden als reguläre Ausdrucksmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="53aad-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="53aad-115">Die Reihenfolge der Ausdrücke ist unwichtig – das erste Muster, das in der Liste übereinstimmt, bewirkt, dass der Anruf blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="53aad-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="53aad-116">Eine neue Nummer oder ein Muster, das in der Liste der blockierten Anrufer hinzugefügt oder entfernt wird, kann bis zu 24 Stunden dauern, bis das Muster aktiv wird.</span><span class="sxs-lookup"><span data-stu-id="53aad-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="53aad-117">PowerShell-Befehle zum Blockieren von Anrufen</span><span class="sxs-lookup"><span data-stu-id="53aad-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="53aad-118">Zahlen ```CsInboundBlockedNumberPattern``` Muster werden über die Befehle ```New``` ```Get``` ```Set```,, und ```Remove```verwaltet.</span><span class="sxs-lookup"><span data-stu-id="53aad-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="53aad-119">Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umzuschalten.</span><span class="sxs-lookup"><span data-stu-id="53aad-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="53aad-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Zahlenmuster zurück, die der Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, aktiviert (wahr/falsch) und Muster für jeden.</span><span class="sxs-lookup"><span data-stu-id="53aad-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="53aad-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) fügt der Mandantenliste ein blockiertes Zahlenmuster hinzu.</span><span class="sxs-lookup"><span data-stu-id="53aad-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="53aad-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.</span><span class="sxs-lookup"><span data-stu-id="53aad-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="53aad-123">Mit " [CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) " werden in der Mandantenliste mindestens ein Parameter eines blockierten Zahlen Musters geändert.</span><span class="sxs-lookup"><span data-stu-id="53aad-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="53aad-124">Das anzeigen und Aktivieren des gesamten Anruf Blockierungs Features wird über ```CsTenantBlockingCallingNumbers``` die ```Get``` Befehle ```Set```und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="53aad-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="53aad-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die Liste der globalen blockierten Nummern einschließlich Enabled (wahr/falsch) zurück.</span><span class="sxs-lookup"><span data-stu-id="53aad-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="53aad-126">Es gibt eine einzelne globale Mandanten Richtlinie, die nicht manuell anders geändert werden kann, als das Feature ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="53aad-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="53aad-127">Mit " [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) " können Sie ändern, dass die globalen Mandanten blockierten Anrufe auf Mandantenebene ein-und ausgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="53aad-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="53aad-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="53aad-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="53aad-129">Blockieren einer Zahl</span><span class="sxs-lookup"><span data-stu-id="53aad-129">Block a number</span></span>

<span data-ttu-id="53aad-130">In diesem Beispiel sind die ```-Enabled``` Parameter ```-Description``` und optional:</span><span class="sxs-lookup"><span data-stu-id="53aad-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="53aad-131">Beim Erstellen eines neuen Musters wird das Muster standardmäßig als aktiviert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="53aad-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="53aad-132">Die Beschreibung ist ein optionales Feld, in dem weitere Informationen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="53aad-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="53aad-133">Wir empfehlen, dass Sie einen aussagekräftigen Namen angeben, um einfach zu verstehen, warum das Muster hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="53aad-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="53aad-134">Wenn Sie Spam-Nummern einfach blockieren, sollten Sie die Regel genauso benennen wie das Zahlenmuster, das verglichen wird, und bei Bedarf zusätzliche Informationen in der Beschreibung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53aad-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="53aad-135">Muster werden mit regulären Ausdrücken (Regex) verglichen.</span><span class="sxs-lookup"><span data-stu-id="53aad-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="53aad-136">Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="53aad-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="53aad-137">Zulassen einer Zahl</span><span class="sxs-lookup"><span data-stu-id="53aad-137">Allow a number</span></span>

<span data-ttu-id="53aad-138">In diesem Beispiel ist der ```-Identity``` Parameter erforderlich:</span><span class="sxs-lookup"><span data-stu-id="53aad-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="53aad-139">Wenn die Identität nicht bekannt ist, suchen ```Get-CsInboundBlockedNumberPattern``` Sie mithilfe des Cmdlets zuerst das richtige Muster, und notieren Sie sich die Identität.</span><span class="sxs-lookup"><span data-stu-id="53aad-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="53aad-140">Führen Sie dann das ```Remove-CsTenantBlockedNumberPattern``` Cmdlet aus, und übergeben Sie den entsprechenden Identitätswert.</span><span class="sxs-lookup"><span data-stu-id="53aad-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="53aad-141">Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="53aad-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="53aad-142">Anzeigen aller Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="53aad-142">View all number patterns</span></span>

<span data-ttu-id="53aad-143">Wenn Sie dieses Cmdlet ausführen, wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben werden:</span><span class="sxs-lookup"><span data-stu-id="53aad-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="53aad-144">Verwenden Sie integrierte PowerShell-Filterfähigkeiten, um die zurückgegebenen Werte nach Bedarf zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="53aad-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="53aad-145">Hinzufügen von Zahlen Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="53aad-145">Add number exceptions</span></span>

<span data-ttu-id="53aad-146">Sie können mithilfe der ```CsTenantBlockNumberExceptionPattern``` Befehle ```New``` ```Get``` ```Set```,,, und ```Remove```die Ausnahmen für blockierte Zahlenmuster hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53aad-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="53aad-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) fügt der Mandantenliste ein Zahlen Ausnahme Muster hinzu.</span><span class="sxs-lookup"><span data-stu-id="53aad-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="53aad-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) gibt eine Liste aller Zahlen Ausnahme Muster zurück, die der Mandantenliste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="53aad-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="53aad-149">Mit " [CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) " werden mindestens ein Parameter in der Mandantenliste in ein Zahlen Ausnahme Muster geändert.</span><span class="sxs-lookup"><span data-stu-id="53aad-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="53aad-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) entfernt ein Zahlen Ausnahme Muster aus der Mandantenliste.</span><span class="sxs-lookup"><span data-stu-id="53aad-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="53aad-151">Beispiele</span><span class="sxs-lookup"><span data-stu-id="53aad-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="53aad-152">Hinzufügen einer Zahlen Ausnahme</span><span class="sxs-lookup"><span data-stu-id="53aad-152">Add a number exception</span></span>

<span data-ttu-id="53aad-153">In diesem Beispiel wird ein neues Zahlen Ausnahme Muster erstellt, das standardmäßig als aktiviert hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="53aad-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="53aad-154">Die ```-Enabled``` Parameter ```-Description``` und sind optional.</span><span class="sxs-lookup"><span data-stu-id="53aad-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="53aad-155">Alle Zahlen Ausnahmen anzeigen</span><span class="sxs-lookup"><span data-stu-id="53aad-155">View all number exceptions</span></span>

<span data-ttu-id="53aad-156">In diesem Beispiel ist der Parameter-Identity optional.</span><span class="sxs-lookup"><span data-stu-id="53aad-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="53aad-157">Wenn der ```-Identity``` Parameter nicht angegeben wird, gibt dieses Cmdlet eine Liste aller für einen Mandanten eingegebenen Zahlen Ausnahme Muster zurück.</span><span class="sxs-lookup"><span data-stu-id="53aad-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="53aad-158">Ändern einer Zahlen Ausnahme</span><span class="sxs-lookup"><span data-stu-id="53aad-158">Modify a number exception</span></span>

<span data-ttu-id="53aad-159">In diesem Beispiel ist der Parameter-Identity obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="53aad-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="53aad-160">Mit ```Set-CsTenantBlockedNumberExceptionPattern``` dem Cmdlet können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmuster Identität ändern.</span><span class="sxs-lookup"><span data-stu-id="53aad-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="53aad-161">Entfernen einer Zahlen Ausnahme</span><span class="sxs-lookup"><span data-stu-id="53aad-161">Remove a number exception</span></span>

<span data-ttu-id="53aad-162">In diesem Beispiel ist der ```-Identity``` Parameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="53aad-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="53aad-163">Mit diesem Cmdlet wird das angegebene Zahlenmuster aus der Mandantenliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="53aad-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="53aad-164">Wenn die Identität nicht bekannt ist, suchen ```Get-CsInboundBlockedNumberPattern``` Sie mithilfe des Cmdlets zuerst das richtige Muster, und notieren Sie sich die Identität.</span><span class="sxs-lookup"><span data-stu-id="53aad-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="53aad-165">Führen Sie dann das ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet aus, und übergeben Sie den entsprechenden Identitätswert.</span><span class="sxs-lookup"><span data-stu-id="53aad-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="53aad-166">Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="53aad-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="53aad-167">Testen, ob eine Zahl blockiert ist</span><span class="sxs-lookup"><span data-stu-id="53aad-167">Test whether a number is blocked</span></span>

<span data-ttu-id="53aad-168">Verwenden Sie ```Test-CsInboundBlockedNumberPattern``` das Cmdlet, um zu überprüfen, ob eine Zahl im Mandanten blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="53aad-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="53aad-169">In diesem Beispiel sind die ```-Phonenumber``` Parameter ```-Tenant``` und erforderlich.</span><span class="sxs-lookup"><span data-stu-id="53aad-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="53aad-170">Der ```-PhoneNumber``` Parameter sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie + oder-sein.</span><span class="sxs-lookup"><span data-stu-id="53aad-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="53aad-171">In TRPS ist das ```-Tenant parameter``` optional.</span><span class="sxs-lookup"><span data-stu-id="53aad-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="53aad-172">Der resultierende ```isNumberBlocked``` Parameter gibt den Wert true zurück, wenn die Zahl im Mandanten blockiert ist, und false, wenn er nicht blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="53aad-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="53aad-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="53aad-173">httpResponseCode</span></span>  |<span data-ttu-id="53aad-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="53aad-174">isNumberBlocked</span></span>   |<span data-ttu-id="53aad-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="53aad-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="53aad-176">200</span><span class="sxs-lookup"><span data-stu-id="53aad-176">200</span></span>    | <span data-ttu-id="53aad-177">Wahr</span><span class="sxs-lookup"><span data-stu-id="53aad-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="53aad-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="53aad-178">httpResponseCode</span></span>  |<span data-ttu-id="53aad-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="53aad-179">isNumberBlocked</span></span>   |<span data-ttu-id="53aad-180">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="53aad-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="53aad-181">200</span><span class="sxs-lookup"><span data-stu-id="53aad-181">200</span></span>    | <span data-ttu-id="53aad-182">Falsch</span><span class="sxs-lookup"><span data-stu-id="53aad-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="53aad-183">Eine Notiz zu Regex</span><span class="sxs-lookup"><span data-stu-id="53aad-183">A note about Regex</span></span>

<span data-ttu-id="53aad-184">Wie bereits erwähnt, wird der Musterabgleich für das Blockieren von Aufrufen mithilfe von Regex ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53aad-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="53aad-185">Es stehen mehrere Tools online zur Verfügung, mit denen Sie eine Regex-Musterübereinstimmung überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="53aad-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="53aad-186">Wenn Sie mit Regex-Mustern nicht vertraut sind, sollten Sie sich etwas Zeit nehmen, um sich mit den Grundlagen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="53aad-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="53aad-187">Wenn Sie sicherstellen möchten, dass Sie die erwarteten Ergebnisse erzielen, verwenden Sie ein Tool zum Überprüfen von Musterübereinstimmungen, bevor Sie dem Mandanten neue blockierte Nummern Übereinstimmungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53aad-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="53aad-188">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="53aad-188">Related topics</span></span>

- [<span data-ttu-id="53aad-189">Einrichten Ihres Computers zum Verwalten von Skype for Business Online mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53aad-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
