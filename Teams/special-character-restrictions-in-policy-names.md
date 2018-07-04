---
title: Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Finden Sie unter welche Probleme mit Sonderzeichen im Namen von Richtlinien und was Sie tun können sind, um es zu beheben.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192164"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="a4948-103">Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?</span><span class="sxs-lookup"><span data-stu-id="a4948-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="a4948-104">**Obwohl Sie Sonderzeichen in die Namen der Richtlinien, den, die Sie in Teams erstellt haben verwenden können, wird dringend empfohlen, dass Sie nicht.**</span><span class="sxs-lookup"><span data-stu-id="a4948-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="a4948-105">Richtliniennamen, die Sie für Besprechungen, Chat und Prescense erstellen, und andere Aspekte in Teams können Sonderzeichen wie @, #, $.</span><span class="sxs-lookup"><span data-stu-id="a4948-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="a4948-106">Jedoch, wenn Sie den Namen in der Microsoft-Teams und Skype für Business Administrationscenter ändern möchte, Sie kann nicht zu werden.</span><span class="sxs-lookup"><span data-stu-id="a4948-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="a4948-107">Sie müssen die Windows PowerShell und die richtige Richtlinie-Cmdlet verwenden, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a4948-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="a4948-108">Wenn Sie eine besprechungsrichtlinie mit Sonderzeichen haben, und ändern Sie den Namen oder entfernen Sonderzeichen aus dem Namen soll, müssen Sie beispielsweise das Cmdlet Set-CsMeetingPolicy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4948-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="a4948-109">Es folgt eine Liste der Richtlinie-Cmdlets, die Sie hierzu müssen:</span><span class="sxs-lookup"><span data-stu-id="a4948-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="a4948-110">Set-CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a4948-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="a4948-111">Set-CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="a4948-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="a4948-112">Set-\*</span><span class="sxs-lookup"><span data-stu-id="a4948-112">Set-\*</span></span>


