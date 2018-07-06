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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205078"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="04a93-103">Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?</span><span class="sxs-lookup"><span data-stu-id="04a93-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="04a93-104">**Obwohl Sonderzeichen für das Erstellen von Teams Richtlinien mit PowerShell verwendet werden können, werden Sie bei der Verwaltung diese Richtlinien eingeschränkt werden.  Daher wird dringend empfohlen, dass die Richtliniennamen keine Sonderzeichen enthalten.**</span><span class="sxs-lookup"><span data-stu-id="04a93-104">**Although special characters can be used for creating Teams policies with PowerShell, you will be limited in managing these policies .  As such, we strongly recommend policy names do not include special characters.**</span></span>

<span data-ttu-id="04a93-105">Richtliniennamen, die Sie beim Erstellen von PowerShell für Besprechungen und Chatten in Teams haben Sonderzeichen wie @, #, $.</span><span class="sxs-lookup"><span data-stu-id="04a93-105">Policy names that you create using PowerShell for meetings and chat in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="04a93-106">Jedoch, wenn Sie die Richtlinie in der Microsoft-Teams und Skype für die Business-Verwaltungskonsole bearbeiten möchte, Sie kann nicht zu werden.</span><span class="sxs-lookup"><span data-stu-id="04a93-106">However, if you are wanting to edit the policy in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="04a93-107">Sie müssen die Windows PowerShell und die richtige Richtlinie-Cmdlet verwenden, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="04a93-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="04a93-108">Wenn Sie ein Gruppenrichtlinienobjekt mit Sonderzeichen haben und Sie Sonderzeichen entfernen, um die Richtlinie für die Business-Verwaltungskonsole in der Microsoft-Teams und Skype besser verwalten möchten, müssen Sie mit dem folgenden Verfahren.</span><span class="sxs-lookup"><span data-stu-id="04a93-108">If you have a policy object with special characters and you want to remove the special characters in order to better manage the policy in the Microsoft Teams and Skype for Business admin center, you will need to use the below procedure.</span></span> 

<span data-ttu-id="04a93-109">Hinweis: Das Verfahren formuliert wird hier als Beispiel eine Messaging-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="04a93-109">Note: The procedure articulated here uses the example of a Messaging policy.</span></span>  <span data-ttu-id="04a93-110">Das gleiche Verfahren würde von Subsituting die relevanten Cmdlets für eine andere Richtlinie (beispielsweise in Besprechungen) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04a93-110">The same process would be used for another policy type (Meetings for example) by subsituting the relevant cmdlets.</span></span> 

<span data-ttu-id="04a93-111">1) rufen Sie Get-CSMessagingPolicy-Identity < Old_policy_name > und erfasst die Ausgabe der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="04a93-111">1.) Call Get-CSMessagingPolicy -identity <old_policy_name> and capture the output of the policy.</span></span>
<span data-ttu-id="04a93-112">2) rufen Sie Set-CSMessagingPolicy-Identity < New_policy_name > zum Erstellen einer neuen Richtlinie mit der Konfiguration als die ursprüngliche Richtlinie, aber ohne Sonderzeichen im Namen.</span><span class="sxs-lookup"><span data-stu-id="04a93-112">2.) Call Set-CSMessagingPolicy -identity <new_policy_name> to create a new policy with the same configuration as the original policy but without any special characters in the name.</span></span>
<span data-ttu-id="04a93-113">3.) aufrufen Delete-CSMessagingPolicy-Identity < Old_policy_name >, um die Richtlinie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="04a93-113">3.) Call Delete-CSMessagingPolicy -identity <old_policy_name> to delete the policy.</span></span>  <span data-ttu-id="04a93-114">Wenn dieser Befehl erfolgreich ist, fertig sind, und Sie können Sie die neue Richtlinie mithilfe von PowerShell oder der Microsoft-Teams und Skype für Business Administrationscenter Benutzer zuweisen beginnen.</span><span class="sxs-lookup"><span data-stu-id="04a93-114">If this command succeeds, you're done and can begin to assign users to the new policy using either PowerShell or the Microsoft Teams and Skype for Business admin center.</span></span>
<span data-ttu-id="04a93-115">4.) Wenn der obige Befehl nicht erfolgreich ist, ist es, weil ein Benutzer die alte Richtlinie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="04a93-115">4.) If the above command does not succeed, it is because the old policy has been assigned to a user.</span></span>  <span data-ttu-id="04a93-116">Aufheben der Zuweisung von Run-Cmdlet zum Aufheben der Zuweisung der Richtlinie zu Benutzer, neue Richtlinie zuweisen und dann Dwlete erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="04a93-116">Run unassign cmdlet to unassign the policy from user, assign new policy, then run dwlete again.</span></span>


