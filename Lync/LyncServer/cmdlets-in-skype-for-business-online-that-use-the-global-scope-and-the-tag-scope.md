---
title: Cmdlets in Skype for Business Online, die den globalen Bereich und den Transponder Bereich verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51327b98be69f92736c1c8523c97b4de6463273b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="b9cb6-102">Cmdlets in Skype for Business Online, die den globalen Bereich und den Transponder Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="b9cb6-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="b9cb6-103">In Skype for Business Online können Richtlinien entweder im *globalen Bereich* oder auf dem *Transponder Bereich* (oder *pro Benutzerbereich*) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="b9cb6-104">Wenn Sie die **Get-CS-** Cmdlets verwenden, müssen Sie keinen Bereich oder keine Identität angeben.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="b9cb6-105">Wenn Sie eines dieser Cmdlets ohne Parameter aufrufen, werden alle relevanten Elemente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="b9cb6-106">Dieser Befehl gibt beispielsweise Informationen zu allen ihren Richtlinien für den externen Zugriff zurück:</span><span class="sxs-lookup"><span data-stu-id="b9cb6-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="b9cb6-107">Sie müssen nur den Parameter Identity oder den Filter-Parameter einbeziehen, wenn Sie die zurückgegebenen Daten einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="b9cb6-108">Wenn Sie beispielsweise nur die globale Richtlinie zurückgeben möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="b9cb6-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="b9cb6-109">Verwenden Sie den folgenden Befehl, um eine benutzerspezifische Richtlinie mit der Identität "RedmondAccessPolicy" zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="b9cb6-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="b9cb6-110">Wenn Sie auf eine Richtlinie pro Benutzer verweisen, <STRONG></STRONG> ist das Tagpräfix optional.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="b9cb6-111">Diese Syntax, die das Präfix enthält, ist ebenfalls gültig:</span><span class="sxs-lookup"><span data-stu-id="b9cb6-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="b9cb6-112">Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="b9cb6-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="b9cb6-113">Verwenden Sie diesen Befehl, um alle Richtlinien mit Ausnahme der globalen Richtlinien (also alle pro-Benutzer-Richtlinien) zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="b9cb6-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="b9cb6-114">Die folgenden Cmdlets arbeiten sowohl für den globalen Bereich als auch für den Bereich pro Benutzer (Tag):</span><span class="sxs-lookup"><span data-stu-id="b9cb6-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="b9cb6-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b9cb6-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b9cb6-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b9cb6-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b9cb6-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b9cb6-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b9cb6-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="b9cb6-122">Trotz des Namens sind die Wählpläne in der Regel Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="b9cb6-123">Der Begriff <EM>Wählplan</EM> wird anstelle von Wähl Richtlinien verwendet, um die Terminologie beizubehalten, die in früheren Versionen von lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9cb6-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="b9cb6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9cb6-124">See Also</span></span>


[<span data-ttu-id="b9cb6-125">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b9cb6-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="b9cb6-126">[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b9cb6-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

