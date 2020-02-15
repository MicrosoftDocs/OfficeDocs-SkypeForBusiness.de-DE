---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden
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
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001440"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="a9cf0-102">Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="a9cf0-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="a9cf0-103">Die **Grant-CS-** Cmdlets (zum Zuweisen von Richtlinien zu Benutzern) erfordern zwei Bezeichner: eine Benutzeridentität (der Parameter Identity) und die Identität einer benutzerspezifischen Richtlinie (dem Parameter PolicyName).</span><span class="sxs-lookup"><span data-stu-id="a9cf0-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="a9cf0-104">Um beispielsweise die VoIP-Richtlinie "redmondvoicepolicy" dem Benutzer Ken Myers zuzuweisen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="a9cf0-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="a9cf0-105">Beim Zuweisen von Richtlinien zu Benutzern müssen zwei Punkte beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="a9cf0-106">Zunächst können nur benutzerspezifische Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="a9cf0-107">Sie können die globale Richtlinie keinem Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="a9cf0-108">Beispielsweise tritt bei diesem Befehl ein Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="a9cf0-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="a9cf0-109">Dieser Befehl schlägt fehl, da es nicht erforderlich ist, die globale Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="a9cf0-110">Wenn Sie einen Benutzer mithilfe der globalen Richtlinie verwalten möchten, achten Sie darauf, dass Sie diesem Benutzer keine Richtlinien auf Benutzerebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="a9cf0-111">Wenn einem Benutzer keine benutzerspezifische Richtlinie zugewiesen wurde, wird der Benutzer automatisch mithilfe der globalen Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="a9cf0-112">Was geschieht, wenn dem Benutzer zuvor eine benutzerspezifische Richtlinie zugewiesen wurde und Sie die Zuweisung dieser Richtlinie aufheben und stattdessen den Benutzer von der globalen Richtlinie verwalten lassen möchten?</span><span class="sxs-lookup"><span data-stu-id="a9cf0-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="a9cf0-113">In diesem Fall verwenden Sie zunächst die folgende Syntax, die die Zuweisung einer benutzerbasierten Richtlinie aufheben, indem Sie dem Benutzer eine NULL-Richtlinie gewährt:</span><span class="sxs-lookup"><span data-stu-id="a9cf0-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="a9cf0-114">Grant-CsVoicePolicy – Identity "Ken Myers" – Richtlinienname $NULL</span><span class="sxs-lookup"><span data-stu-id="a9cf0-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="a9cf0-115">Beachten Sie Zweitens, dass benutzerspezifische Richtlinien auf dem Tag-Bereich erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="a9cf0-116">Sie können **das Tagpräfix jedoch beim angeben** eines Richtlinien namens weglassen.</span><span class="sxs-lookup"><span data-stu-id="a9cf0-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="a9cf0-117">Diese beiden Befehle sind identisch:</span><span class="sxs-lookup"><span data-stu-id="a9cf0-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="a9cf0-118">Wenn Sie die Identitäten für alle Richtlinien auf Benutzerebene (oder zumindest alle benutzerspezifischen Richtlinien des angegebenen Typs, beispielsweise VoIP-Richtlinien) zurückgeben möchten, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="a9cf0-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="a9cf0-119">Die folgenden Cmdlets verwenden sowohl eine Benutzeridentität als auch den Tag-Bereich:</span><span class="sxs-lookup"><span data-stu-id="a9cf0-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="a9cf0-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a9cf0-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a9cf0-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a9cf0-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a9cf0-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a9cf0-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="a9cf0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9cf0-126">See Also</span></span>


[<span data-ttu-id="a9cf0-127">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a9cf0-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a9cf0-128">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a9cf0-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

