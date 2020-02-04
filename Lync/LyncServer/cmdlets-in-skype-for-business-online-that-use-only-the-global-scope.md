---
title: Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728105"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="7a1bc-102">Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="7a1bc-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="7a1bc-103">Eine Reihe von Skype for Business Online-Einstellungen steht nur im *globalen Bereich*zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="7a1bc-104">Das bedeutet, dass es eine einzelne Sammlung von Einstellungen gibt, die für alle Benutzer gelten, die diesem Mandanten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="7a1bc-105">(Jeder Mandant hat eine eigene eindeutige Sammlung globaler Einstellungen.) Wenn Sie Cmdlets verwenden, die auf den globalen Bereich beschränkt sind, ist der Parameter Identity optional.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="7a1bc-106">Wenn Sie beispielsweise die Einstellungen für die besprechungskonfiguration abrufen möchten, können Sie diesen Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="7a1bc-107">Alternativ können Sie den Parameter Identity weglassen und stattdessen diesen einfacheren Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="7a1bc-108">Da nur eine globale Sammlung von Einstellungen für die besprechungskonfiguration vorhanden ist, geben die beiden Befehle exakt dieselben Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="7a1bc-109">Der Parameter Identity kann auch bei Verwendung eines der Cmdlets für die **Satz-CS-** Cmdlets ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="7a1bc-110">Diese beiden Befehle sind identisch:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="7a1bc-111">Die beiden Befehle sind identisch, da Windows PowerShell standardmäßig die globale Sammlung ändert, wenn Sie den Parameter Identity nicht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="7a1bc-112">Die folgenden Cmdlets werden nur im globalen Bereich ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="7a1bc-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7a1bc-122">[Satz-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="7a1bc-123">Beachten Sie, dass es sich bei dem Cmdlet **Remove-CsVoicePolicy** um eine Anomalie handelt.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="7a1bc-124">Zunächst müssen Sie mit diesem Cmdlet den Parameter Identity einbeziehen:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="7a1bc-125">Zweitens löscht das Cmdlet **Remove-CsVoicePolicy** die globale VoIP-Richtlinie nicht tatsächlich; In Skype for Business Online ist es nicht möglich, globale Richtlinien oder Konfigurationseinstellungen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="7a1bc-126">Mit dem Cmdlet können Sie alle Eigenschaften in der globalen VoIP-Richtlinie auf ihre Standardwerte zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="7a1bc-127">Standardmäßig ist die AllowCallForwarding-Eigenschaft beispielsweise auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="7a1bc-128">AllowCallForwarding wurde jedoch möglicherweise geändert, wobei der Wert nun auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="7a1bc-129">Wenn Sie das Cmdlet **Remove-CsVoicePolicy** ausführen, wird die AllowCallForwarding-Eigenschaft auf den Standardwert zurückgesetzt: false.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="7a1bc-130">In der folgenden Tabelle ist dieses Szenario zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a1bc-131">AllowCallForwarding-Wert</span><span class="sxs-lookup"><span data-stu-id="7a1bc-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="7a1bc-132">Szenario</span><span class="sxs-lookup"><span data-stu-id="7a1bc-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a1bc-133">Falsch</span><span class="sxs-lookup"><span data-stu-id="7a1bc-133">False</span></span></p></td>
<td><p><span data-ttu-id="7a1bc-134">Standardwert</span><span class="sxs-lookup"><span data-stu-id="7a1bc-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a1bc-135">Wahr</span><span class="sxs-lookup"><span data-stu-id="7a1bc-135">True</span></span></p></td>
<td><p><span data-ttu-id="7a1bc-136">Nachdem die globale Richtlinie geändert wurde</span><span class="sxs-lookup"><span data-stu-id="7a1bc-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a1bc-137">Falsch</span><span class="sxs-lookup"><span data-stu-id="7a1bc-137">False</span></span></p></td>
<td><p><span data-ttu-id="7a1bc-138">Nachdem das Cmdlet " <strong>Remove-CsVoicePolicy</strong> " ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="7a1bc-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="7a1bc-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a1bc-139">See Also</span></span>


[<span data-ttu-id="7a1bc-140">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a1bc-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="7a1bc-141">[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7a1bc-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

