---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Transponder Bereich verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727565"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="1cba4-102">Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Transponder Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="1cba4-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="1cba4-103">Für die **Grant-CS-** Cmdlets (für die Zuweisung von Richtlinien für Benutzer) sind zwei Bezeichner erforderlich: eine Benutzeridentität (der Parameter Identity) und die Identität einer Richtlinie pro Benutzer (dem Parameter PolicyName).</span><span class="sxs-lookup"><span data-stu-id="1cba4-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="1cba4-104">Um beispielsweise die VoIP-Richtlinie RedmondVoicePolicy dem Benutzer Ken Myers zuzuweisen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="1cba4-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="1cba4-105">Beim Zuweisen von Richtlinien zu Benutzern müssen zwei Punkte beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="1cba4-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="1cba4-106">Zunächst können nur Richtlinien für einzelne Benutzer zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1cba4-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="1cba4-107">Sie können die globale Richtlinie nicht einem Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1cba4-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="1cba4-108">Dieser Befehl schlägt beispielsweise fehl:</span><span class="sxs-lookup"><span data-stu-id="1cba4-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="1cba4-109">Dieser Befehl schlägt fehl, da die globale Richtlinie nicht zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="1cba4-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="1cba4-110">Wenn Sie einen Benutzer mithilfe der globalen Richtlinie verwalten möchten, stellen Sie sicher, dass Sie diesem Benutzer keine Richtlinie pro Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1cba4-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="1cba4-111">Wenn einem Benutzer keine benutzerspezifische Richtlinie zugewiesen wurde, wird der Benutzer automatisch mithilfe der globalen Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1cba4-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="1cba4-112">Was ist, wenn dem Benutzer zuvor eine Richtlinie pro Benutzer zugewiesen wurde und Sie die Zuweisung dieser Richtlinie aufheben und stattdessen den Benutzer von der globalen Richtlinie verwalten lassen möchten?</span><span class="sxs-lookup"><span data-stu-id="1cba4-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="1cba4-113">In diesem Fall verwenden Sie zunächst die folgende Syntax, die die Zuweisung einer Richtlinie für einzelne Benutzer aufheben, indem Sie diesem Benutzer eine NULL-Richtlinie gewährt:</span><span class="sxs-lookup"><span data-stu-id="1cba4-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="1cba4-114">Grant-CsVoicePolicy – Identity "Ken Myers" – Richtliniennamen $NULL</span><span class="sxs-lookup"><span data-stu-id="1cba4-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="1cba4-115">Beachten Sie Zweitens, dass Richtlinien für einzelne Benutzer im Bereich "Tag" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1cba4-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="1cba4-116">Sie können **das Tagpräfix jedoch bei der** Angabe eines Richtlinien namens weglassen.</span><span class="sxs-lookup"><span data-stu-id="1cba4-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="1cba4-117">Diese beiden Befehle sind identisch:</span><span class="sxs-lookup"><span data-stu-id="1cba4-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="1cba4-118">Wenn Sie die Identitäten für alle Richtlinien für einzelne Benutzer zurückgeben möchten (oder zumindest alle Richtlinien für einzelne Benutzer, beispielsweise VoIP-Richtlinien), verwenden Sie einen Befehl, der wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="1cba4-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="1cba4-119">Die folgenden Cmdlets verwenden eine Benutzeridentität und den Tag-Bereich:</span><span class="sxs-lookup"><span data-stu-id="1cba4-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="1cba4-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1cba4-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1cba4-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1cba4-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1cba4-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1cba4-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="1cba4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cba4-126">See Also</span></span>


[<span data-ttu-id="1cba4-127">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1cba4-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="1cba4-128">[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cba4-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

