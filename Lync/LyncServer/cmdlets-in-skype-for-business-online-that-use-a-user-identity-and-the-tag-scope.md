---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden
description: Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Transponder Bereich verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545611"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="978af-103">Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="978af-103">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="978af-104">Die **Grant-CS-** Cmdlets (zum Zuweisen von Richtlinien zu Benutzern) erfordern zwei Bezeichner: eine Benutzeridentität (der Parameter Identity) und die Identität einer benutzerspezifischen Richtlinie (dem Parameter PolicyName).</span><span class="sxs-lookup"><span data-stu-id="978af-104">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="978af-105">Um beispielsweise die VoIP-Richtlinie "redmondvoicepolicy" dem Benutzer Ken Myers zuzuweisen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="978af-105">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="978af-106">Beim Zuweisen von Richtlinien zu Benutzern müssen zwei Punkte beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="978af-106">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="978af-107">Zunächst können nur benutzerspezifische Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="978af-107">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="978af-108">Sie können die globale Richtlinie keinem Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="978af-108">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="978af-109">Beispielsweise tritt bei diesem Befehl ein Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="978af-109">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="978af-110">Dieser Befehl schlägt fehl, da es nicht erforderlich ist, die globale Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="978af-110">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="978af-111">Wenn Sie einen Benutzer mithilfe der globalen Richtlinie verwalten möchten, achten Sie darauf, dass Sie diesem Benutzer keine Richtlinien auf Benutzerebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="978af-111">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="978af-112">Wenn einem Benutzer keine benutzerspezifische Richtlinie zugewiesen wurde, wird der Benutzer automatisch mithilfe der globalen Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="978af-112">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="978af-113">Was geschieht, wenn dem Benutzer zuvor eine benutzerspezifische Richtlinie zugewiesen wurde und Sie die Zuweisung dieser Richtlinie aufheben und stattdessen den Benutzer von der globalen Richtlinie verwalten lassen möchten?</span><span class="sxs-lookup"><span data-stu-id="978af-113">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="978af-114">In diesem Fall verwenden Sie zunächst die folgende Syntax, die die Zuweisung einer benutzerbasierten Richtlinie aufheben, indem Sie dem Benutzer eine NULL-Richtlinie gewährt:</span><span class="sxs-lookup"><span data-stu-id="978af-114">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="978af-115">Grant-CsVoicePolicy – Identity "Ken Myers" – Richtlinienname $NULL</span><span class="sxs-lookup"><span data-stu-id="978af-115">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="978af-116">Beachten Sie Zweitens, dass benutzerspezifische Richtlinien auf dem Tag-Bereich erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="978af-116">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="978af-117">Sie können **das Tagpräfix jedoch beim angeben** eines Richtlinien namens weglassen.</span><span class="sxs-lookup"><span data-stu-id="978af-117">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="978af-118">Diese beiden Befehle sind identisch:</span><span class="sxs-lookup"><span data-stu-id="978af-118">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="978af-119">Wenn Sie die Identitäten für alle Richtlinien auf Benutzerebene (oder zumindest alle benutzerspezifischen Richtlinien des angegebenen Typs, beispielsweise VoIP-Richtlinien) zurückgeben möchten, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="978af-119">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="978af-120">Die folgenden Cmdlets verwenden sowohl eine Benutzeridentität als auch den Tag-Bereich:</span><span class="sxs-lookup"><span data-stu-id="978af-120">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="978af-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="978af-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="978af-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="978af-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="978af-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="978af-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="978af-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="978af-127">See Also</span></span>


[<span data-ttu-id="978af-128">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="978af-128">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="978af-129">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="978af-129">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

