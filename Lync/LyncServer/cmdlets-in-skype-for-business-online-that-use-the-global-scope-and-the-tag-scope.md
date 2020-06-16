---
title: Cmdlets in Skype for Business Online, die den globalen Bereich und den Tag-Bereich verwenden
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755075"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="d87ee-102">Cmdlets in Skype for Business Online, die den globalen Bereich und den Tag-Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="d87ee-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="d87ee-103">In Skype for Business Online können Richtlinien entweder auf *globaler Ebene* oder auf dem *Tag-Bereich* (oder auf *Benutzerebene*) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d87ee-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="d87ee-104">Wenn Sie die Cmdlets " **Get-CS** " verwenden, müssen Sie keinen Bereich oder eine Identität angeben.</span><span class="sxs-lookup"><span data-stu-id="d87ee-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="d87ee-105">Wenn Sie eines dieser Cmdlets ohne Parameter aufrufen, werden alle relevanten Elemente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d87ee-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="d87ee-106">Mit diesem Befehl werden beispielsweise Informationen zu allen Richtlinien für den externen Zugriff zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="d87ee-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="d87ee-107">Sie müssen nur den Parameter Identity oder den Parameter Filter einschließen, wenn Sie die zurückgegebenen Daten einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="d87ee-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="d87ee-108">Um beispielsweise nur die globale Richtlinie zurückzugeben, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="d87ee-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="d87ee-109">Verwenden Sie den folgenden Befehl, um eine benutzerspezifische Richtlinie mit der Identität "RedmondAccessPolicy" zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="d87ee-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="d87ee-110">Beim Verweisen auf eine benutzerspezifische Richt <STRONG>Linie ist das Tagpräfix optional</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d87ee-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="d87ee-111">Diese Syntax, die das Präfix enthält, ist ebenfalls gültig:</span><span class="sxs-lookup"><span data-stu-id="d87ee-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="d87ee-112">Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="d87ee-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="d87ee-113">Verwenden Sie diesen Befehl, um alle Richtlinien mit Ausnahme der globalen Richtlinien (also aller benutzerspezifischen Richtlinien) zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="d87ee-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="d87ee-114">Die folgenden Cmdlets funktionieren sowohl für den globalen Bereich als auch für den pro-Benutzer-(Tag-) Bereich:</span><span class="sxs-lookup"><span data-stu-id="d87ee-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="d87ee-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d87ee-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d87ee-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d87ee-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d87ee-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d87ee-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d87ee-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="d87ee-122">Trotz des Namens sind Wählpläne funktional gesehen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="d87ee-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="d87ee-123">Der Begriff <EM>Wähl</EM> Einstellungen wird anstelle von, beispielsweise Wähl Richtlinie, verwendet, um die Terminologie beizubehalten, die in früheren Versionen von lync Server verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d87ee-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="d87ee-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d87ee-124">See Also</span></span>


[<span data-ttu-id="d87ee-125">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d87ee-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="d87ee-126">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d87ee-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

