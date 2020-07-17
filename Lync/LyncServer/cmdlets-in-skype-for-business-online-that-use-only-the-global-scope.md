---
title: Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755097"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="843b4-102">Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="843b4-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="843b4-103">Eine Reihe von Skype for Business Online Einstellungen sind nur auf *globaler*Ebene verfügbar.</span><span class="sxs-lookup"><span data-stu-id="843b4-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="843b4-104">Dies bedeutet, dass es eine einzelne Auflistung von Einstellungen gibt, die für alle Benutzer gilt, die diesem Mandanten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="843b4-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="843b4-105">(Jeder Mandant verfügt über eine eigene eindeutige Auflistung globaler Einstellungen.) Wenn Sie Cmdlets verwenden, die auf den globalen Bereich beschränkt sind, ist der Parameter Identity optional.</span><span class="sxs-lookup"><span data-stu-id="843b4-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="843b4-106">Wenn Sie beispielsweise Besprechungs Konfigurationseinstellungen abrufen möchten, können Sie diesen Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="843b4-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="843b4-107">Alternativ können Sie den Parameter Identity weglassen und stattdessen diesen einfacheren Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="843b4-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="843b4-108">Da nur eine globale Auflistung von Besprechungs Konfigurationseinstellungen vorhanden ist, geben die beiden Befehle exakt dieselben Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="843b4-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="843b4-109">Der Parameter Identity kann auch ausgelassen werden, wenn eines der Cmdlets der **Gruppe-cs** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="843b4-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="843b4-110">Diese beiden Befehle sind identisch:</span><span class="sxs-lookup"><span data-stu-id="843b4-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="843b4-111">Die beiden Befehle sind identisch, da Windows PowerShell standardmäßig die globale Auflistung ändert, wenn Sie den Parameter Identity nicht einschließen.</span><span class="sxs-lookup"><span data-stu-id="843b4-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="843b4-112">Die folgenden Cmdlets funktionieren nur auf globaler Ebene:</span><span class="sxs-lookup"><span data-stu-id="843b4-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="843b4-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-121">[Gruppe-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="843b4-122">[Gruppe-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="843b4-123">Beachten Sie, dass das Cmdlet **Remove-CsVoicePolicy** so etwas wie eine Anomalie ist.</span><span class="sxs-lookup"><span data-stu-id="843b4-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="843b4-124">Für dieses Cmdlet müssen Sie zunächst den Parameter Identity einschließen:</span><span class="sxs-lookup"><span data-stu-id="843b4-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="843b4-125">Zweitens löscht das Cmdlet **Remove-CsVoicePolicy** die globale VoIP-Richtlinie nicht tatsächlich; In Skype for Business Online können globale Richtlinien oder Konfigurationseinstellungen nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="843b4-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="843b4-126">Das Cmdlet macht es möglich, dass Sie alle Eigenschaften in der globalen VoIP-Richtlinie auf ihre Standardwerte zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="843b4-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="843b4-127">Beispielsweise ist die AllowCallForwarding-Eigenschaft standardmäßig auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="843b4-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="843b4-128">AllowCallForwarding wurde jedoch möglicherweise geändert, wobei der Wert nun auf true festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="843b4-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="843b4-129">Wenn Sie das Cmdlet **Remove-CsVoicePolicy** ausführen, wird die AllowCallForwarding-Eigenschaft auf den Standardwert zurückgesetzt: false.</span><span class="sxs-lookup"><span data-stu-id="843b4-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="843b4-130">In der folgenden Tabelle wird dieses Szenario zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="843b4-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="843b4-131">AllowCallForwarding-Wert</span><span class="sxs-lookup"><span data-stu-id="843b4-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="843b4-132">Szenario</span><span class="sxs-lookup"><span data-stu-id="843b4-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="843b4-133">Falsch</span><span class="sxs-lookup"><span data-stu-id="843b4-133">False</span></span></p></td>
<td><p><span data-ttu-id="843b4-134">Standardwert</span><span class="sxs-lookup"><span data-stu-id="843b4-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="843b4-135">Wahr</span><span class="sxs-lookup"><span data-stu-id="843b4-135">True</span></span></p></td>
<td><p><span data-ttu-id="843b4-136">Nachdem die globale Richtlinie geändert wurde</span><span class="sxs-lookup"><span data-stu-id="843b4-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="843b4-137">Falsch</span><span class="sxs-lookup"><span data-stu-id="843b4-137">False</span></span></p></td>
<td><p><span data-ttu-id="843b4-138">Nach dem Ausführen des Cmdlets " <strong>Remove-CsVoicePolicy</strong> "</span><span class="sxs-lookup"><span data-stu-id="843b4-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="843b4-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="843b4-139">See Also</span></span>


[<span data-ttu-id="843b4-140">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="843b4-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="843b4-141">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="843b4-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

