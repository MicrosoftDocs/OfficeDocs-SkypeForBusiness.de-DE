---
title: Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informieren Sie sich über die verschiedenen Möglichkeiten, wie Sie Ihren Benutzern in Microsoft Teams Richtlinien zuweisen können.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: c7522bc4bffeafeef4d194f5e4ad24ec9648a91a
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021753"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="ec872-103">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec872-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ec872-104">**Beachten Sie die folgenden Informationen zu einem der in diesem Artikel beschriebenen Features: Richtlinienzuweisung zu Gruppen**:</span><span class="sxs-lookup"><span data-stu-id="ec872-104">**Note the following about one of the features discussed in this article, policy assignment to groups**:</span></span> 
> - <span data-ttu-id="ec872-105">[Die Richtlinienzuweisung zu Gruppen, die das Microsoft Teams Admin Center verwenden](#using-the-microsoft-teams-admin-center-3), wurde noch nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="ec872-105">[Policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="ec872-106">Es wurde angekündigt, und es wird bald kommen.</span><span class="sxs-lookup"><span data-stu-id="ec872-106">It's been announced, and it's coming soon.</span></span> 
> - <span data-ttu-id="ec872-107">[Die Richtlinienzuweisung zu Gruppen mit PowerShell](#using-powershell-3)steht derzeit nur in der privaten Vorschau zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ec872-107">[Policy assignment to groups using PowerShell](#using-powershell-3), is currently only available in private preview.</span></span> <span data-ttu-id="ec872-108">Die Cmdlets für dieses Feature befinden sich im Public Preview-Modul von Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec872-108">The cmdlets for this feature are in the Teams PowerShell public preview module.</span></span>
>
> <span data-ttu-id="ec872-109">Wenn Sie den Veröffentlichungsstatus dieser Funktion auf dem neuesten Stand halten möchten, lesen Sie die [Roadmap für Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="ec872-109">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="ec872-110">Als Administrator verwenden Sie Richtlinien, um die Teamfunktionen zu steuern, die Benutzern in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="ec872-110">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="ec872-111">So gibt es beispielsweise Anruf Richtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.</span><span class="sxs-lookup"><span data-stu-id="ec872-111">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="ec872-112">Organisationen verfügen über unterschiedliche Arten von Benutzern mit eindeutigen Anforderungen und benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, damit Sie die Richtlinieneinstellungen basierend auf den Anforderungen an unterschiedliche Benutzergruppen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="ec872-112">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="ec872-113">Um das Verwalten von Richtlinien in Ihrer Organisation zu vereinfachen, bietet Teams verschiedene Möglichkeiten, Richtlinien für Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-113">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="ec872-114">Sie können Benutzern eine Richtlinie entweder einzeln oder im Maßstab über eine Batch Zuordnung oder einer Gruppe, der die Benutzer angehören, direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-114">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="ec872-115">Sie können auch Richtlinien Pakete verwenden, um Benutzern in Ihrer Organisation, die über ähnliche Rollen verfügen, eine vordefinierte Sammlung von Richtlinien zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-115">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="ec872-116">Die von Ihnen ausgewählte Option richtet sich nach der Anzahl der Richtlinien, die Sie verwalten, und der Anzahl der Benutzer, denen Sie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-116">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="ec872-117">Wenn Sie die globalen Standardrichtlinien (org-Wide) so festlegen, dass Sie auf die größte Anzahl von Benutzern in Ihrer Organisation angewendet werden, müssen Sie nur solchen Benutzern Richtlinien zuweisen, für die spezielle Richtlinien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ec872-117">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="ec872-118">In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie Benutzern Richtlinien zuweisen können, sowie die empfohlenen Szenarien für die Verwendung von was.</span><span class="sxs-lookup"><span data-stu-id="ec872-118">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="ec872-119">Welche Richtlinie hat Vorrang?</span><span class="sxs-lookup"><span data-stu-id="ec872-119">Which policy takes precedence?</span></span>

<span data-ttu-id="ec872-120">Ein Benutzer verfügt über eine gültige Richtlinie für die einzelnen Richtlinientypen.</span><span class="sxs-lookup"><span data-stu-id="ec872-120">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="ec872-121">Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer direkt eine Richtlinie zugewiesen wird, und er ist auch ein Mitglied einer oder mehrerer Gruppen, denen eine Richtlinie desselben Typs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-121">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="ec872-122">Welche Richtlinie hat in diesen Szenarien Vorrang?</span><span class="sxs-lookup"><span data-stu-id="ec872-122">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="ec872-123">Die effektive Richtlinie eines Benutzers wird wie folgt gemäß den Regeln für die Rangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ec872-123">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="ec872-124">Wenn einem Benutzer direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batch Zuordnung), hat diese Richtlinie Vorrang.</span><span class="sxs-lookup"><span data-stu-id="ec872-124">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="ec872-125">Im folgenden Beispiel ist die effektive Richtlinie des Benutzers die Lincoln Square-Besprechungsrichtlinie, die dem Benutzer direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-125">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="ec872-127">Wenn einem Benutzer keine Richtlinie eines bestimmten Typs direkt zugewiesen wird, hat die der Gruppe zugewiesene Richtlinie Vorrang.</span><span class="sxs-lookup"><span data-stu-id="ec872-127">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="ec872-128">Wenn ein Benutzer ein Mitglied mehrerer Gruppen ist, hat die Richtlinie, die die höchste [Gruppen Zuordnungs Rangfolge](#group-assignment-ranking) für den angegebenen Richtlinientyp aufweist, Vorrang.</span><span class="sxs-lookup"><span data-stu-id="ec872-128">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="ec872-129">In diesem Beispiel ist die effektive Richtlinie des Benutzers die Exec Teams-und HD-Richtlinie, die die höchste Zuordnungs Rangfolge relativ zu anderen Gruppen aufweist, in der der Benutzer Mitglied ist und dem auch eine Richtlinie desselben Richtlinientyps zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-129">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramm, das zeigt, wie eine von Group geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

<span data-ttu-id="ec872-131">Wenn einem Benutzer keine Richtlinie direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, erhält der Benutzer die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="ec872-131">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="ec872-132">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ec872-132">Here's an example.</span></span>

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat](media/assign-policies-example-global.png)

<span data-ttu-id="ec872-134">Weitere Informationen finden Sie unter [Prioritätsregeln](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="ec872-134">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="ec872-135">Methoden zum Zuweisen von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ec872-135">Ways to assign policies</span></span>

<span data-ttu-id="ec872-136">Im folgenden finden Sie eine Übersicht über die Methoden zum Zuweisen von Richtlinien zu Benutzern sowie zu den empfohlenen Szenarien für die einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ec872-136">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="ec872-137">Klicken Sie auf die Links, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ec872-137">Click the links to learn more.</span></span>

<span data-ttu-id="ec872-138">Bevor Sie einzelnen Benutzern oder Gruppen Richtlinien zuweisen, müssen Sie zunächst [die globalen (organisationsweiten Standard-) Richtlinien festlegen](#set-the-global-policies) , damit Sie auf die größte Anzahl von Benutzern in Ihrer Organisation angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec872-138">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="ec872-139">Nachdem die globalen Richtlinien festgesetzt sind, müssen Sie nur solchen Benutzern Richtlinien zuweisen, für die spezielle Richtlinien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ec872-139">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="ec872-140">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="ec872-140">Do this</span></span>  |<span data-ttu-id="ec872-141">Wenn...</span><span class="sxs-lookup"><span data-stu-id="ec872-141">If...</span></span>  | <span data-ttu-id="ec872-142">Verwenden von...</span><span class="sxs-lookup"><span data-stu-id="ec872-142">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="ec872-143">Zuweisen einer Richtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec872-143">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="ec872-144">Sie sind neu bei Microsoft Teams und haben gerade erst begonnen, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-144">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="ec872-145">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im Skype for Business Online PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="ec872-145">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="ec872-146">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="ec872-146">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="ec872-147">Sie müssen bestimmten Gruppen von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-147">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="ec872-148">Weisen Sie beispielsweise Lehrern in Ihrer Bildungseinrichtung das Richtlinienpaket Education (Teacher) zu, um Ihnen den vollständigen Zugriff auf Chats, Anrufe und Besprechungen sowie das Richtlinienpaket Education (Secondary School Student) für sekundäre Schüler zu gewähren, um bestimmte Funktionen wie private Anrufe zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="ec872-148">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="ec872-149">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="ec872-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="ec872-150">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="ec872-150">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="ec872-151">Sie müssen einem umfangreichen Satz von Benutzern Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-151">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="ec872-152">So möchten Sie beispielsweise Hunderten oder tausenden Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-152">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="ec872-153">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="ec872-153">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="ec872-154">[Zuweisen einer Richtlinie zu einer Gruppe](#assign-a-policy-to-a-group) (in der Vorschau/in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="ec872-154">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview/coming soon)</span></span>|<span data-ttu-id="ec872-155">Sie müssen Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-155">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="ec872-156">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Organisationseinheit eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-156">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="ec872-157">Das Microsoft Teams Admin Center (in Kürze verfügbar) oder PowerShell-Cmdlets im Teams PowerShell-Modul (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="ec872-157">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module (in preview)</span></span>|
| [<span data-ttu-id="ec872-158">Zuweisen eines Richtlinienpakets zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="ec872-158">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="ec872-159">Sie müssen einem Batch von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-159">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="ec872-160">Weisen Sie beispielsweise das Richtlinienpaket Education (Teacher) allen Lehrern in ihrer Schule mithilfe der Batch Zuweisung zu, damit Sie Vollzugriff auf Chats, Anrufe und Besprechungen erhalten und das Richtlinienpaket Education (Secondary School Student) einem Batch von sekundären Kursteilnehmern zuweisen können, um bestimmte Funktionen wie private Anrufe zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="ec872-160">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="ec872-161">PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="ec872-161">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="ec872-162">Zuweisen eines Richtlinienpakets zu einer Gruppe (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="ec872-162">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="ec872-163">Globale Richtlinien einrichten</span><span class="sxs-lookup"><span data-stu-id="ec872-163">Set the global policies</span></span>

<span data-ttu-id="ec872-164">Führen Sie die folgenden Schritte aus, um die globalen (org-weiten Standardrichtlinien) für die einzelnen Richtlinientypen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ec872-164">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ec872-165">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="ec872-165">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ec872-166">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zur Seite Richtlinie für den Richtlinientyp, den Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ec872-166">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="ec872-167">Beispielsweise **Teams**  >  **Teams**, Richtlinien für **Besprechungs**  >  **Besprechungen**, **Nachrichtenrichtlinien**oder **VoIP**-  >  **Anruf Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="ec872-167">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="ec872-168">Wählen Sie die **globale (org-Wide Standard)-** Richtlinie aus, um die aktuellen Einstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec872-168">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="ec872-169">Aktualisieren Sie die Richtlinie nach Bedarf, und wählen Sie dann über **nehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-169">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ec872-170">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec872-170">Using PowerShell</span></span>

<span data-ttu-id="ec872-171">Verwenden Sie den globalen Bezeichner, um die globalen Richtlinien mithilfe von PowerShell einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ec872-171">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="ec872-172">Überprüfen Sie zunächst die aktuelle globale Richtlinie, um festzustellen, welche Einstellung Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ec872-172">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="ec872-173">Aktualisieren Sie als nächstes die globale Richtlinie nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ec872-173">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="ec872-174">Sie müssen nur Werte für die Einstellungen angeben, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ec872-174">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="ec872-175">Zuweisen einer Richtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec872-175">Assign a policy to individual users</span></span>

<span data-ttu-id="ec872-176">Führen Sie die folgenden Schritte aus, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-176">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ec872-177">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="ec872-177">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="ec872-178">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="ec872-178">To assign a policy to a user:</span></span>

1. <span data-ttu-id="ec872-179">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="ec872-179">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="ec872-180">Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ec872-180">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="ec872-181">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="ec872-181">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="ec872-182">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ec872-182">Or, you can also do the following:</span></span>

1. <span data-ttu-id="ec872-183">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zur Seite Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ec872-183">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="ec872-184">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links neben dem Richtliniennamen klicken.</span><span class="sxs-lookup"><span data-stu-id="ec872-184">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="ec872-185">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-185">Select **Manage users**.</span></span>
4. <span data-ttu-id="ec872-186">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ec872-186">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="ec872-187">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.</span><span class="sxs-lookup"><span data-stu-id="ec872-187">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="ec872-188">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie über **nehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-188">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ec872-189">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec872-189">Using PowerShell</span></span>

<span data-ttu-id="ec872-190">Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Verwalten.</span><span class="sxs-lookup"><span data-stu-id="ec872-190">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="ec872-191">Verwenden Sie das ```Grant-``` Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-191">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="ec872-192">Verwenden Sie beispielsweise das ```Grant-CsTeamsMeetingPolicy``` Cmdlet, um Benutzern eine Teams-Besprechungsrichtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-192">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="ec872-193">Diese Cmdlets sind Bestandteil des Skype for Business Online PowerShell-Moduls und werden im [Skype for Business-Cmdlet Reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="ec872-193">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="ec872-194">Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366) herunter, und installieren Sie es (falls noch nicht geschehen), und führen Sie dann die folgenden Schritte aus, um eine Verbindung mit Skype for Business Online herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ec872-194">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="ec872-195">In diesem Beispiel weisen wir eine Teams-Besprechungsrichtlinie mit dem Namen "Student-Besprechungsrichtlinie" einem Benutzer mit dem Namen "Sie" zu.</span><span class="sxs-lookup"><span data-stu-id="ec872-195">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="ec872-196">Weitere Informationen finden Sie unter [Verwalten von Richtlinien über PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="ec872-196">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="ec872-197">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="ec872-197">Assign a policy package</span></span>

<span data-ttu-id="ec872-198">Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die über die gleichen oder ähnlichen Rollen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="ec872-198">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="ec872-199">Jedes Richtlinienpaket ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ec872-199">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="ec872-200">Einige Beispiele für Richtlinien Pakete sind das Paket "Education (Teacher)" und "Healthcare (Clinical Worker)".</span><span class="sxs-lookup"><span data-stu-id="ec872-200">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="ec872-201">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen jeder Richtlinie im Paket anpassen, um die Anforderungen der Benutzer zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ec872-201">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="ec872-202">Weitere Informationen zu Richtlinien Paketen, einschließlich Schritt-für-Schritt-Anleitungen zum Zuweisen und Verwalten dieser Pakete, finden Sie unter [Verwalten von Richtlinien Paketen in Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="ec872-202">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="ec872-203">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="ec872-203">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ec872-204">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="ec872-204">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="ec872-205">So weisen Sie Benutzern eine Richtlinie in Massen zu:</span><span class="sxs-lookup"><span data-stu-id="ec872-205">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="ec872-206">Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center die Option **Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-206">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="ec872-207">Suchen Sie nach den Benutzern, denen Sie die Richtlinie zuweisen möchten, oder Filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec872-207">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="ec872-208">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-208">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="ec872-209">Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="ec872-209">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="ec872-210">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="ec872-210">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="ec872-211">Wenn Sie den Status Ihrer Richtlinienzuweisung anzeigen möchten, klicken Sie in dem Banner, das oben auf der Seite " **Benutzer** " angezeigt wird, nachdem Sie auf über **nehmen** klicken, um Ihre Richtlinien Aufgabe zu übermitteln, auf **Aktivitätsprotokoll**.</span><span class="sxs-lookup"><span data-stu-id="ec872-211">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="ec872-212">Oder klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Dashboard**, und klicken Sie dann unter **Aktivitätsprotokoll**auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ec872-212">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="ec872-213">Das Aktivitätsprotokoll zeigt Richtlinienzuweisungen für Stapel von mehr als 20 Benutzern über das Microsoft Teams Admin Center der letzten 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="ec872-213">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="ec872-214">Weitere Informationen finden Sie unter [Anzeigen der Richtlinienzuweisungen im Aktivitätsprotokoll](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="ec872-214">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ec872-215">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec872-215">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="ec872-216">Derzeit steht die Zuweisung von Batch Richtlinien mit PowerShell nicht für alle Teams-Richtlinientypen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ec872-216">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="ec872-217">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .</span><span class="sxs-lookup"><span data-stu-id="ec872-217">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="ec872-218">Mit der Batch Richtlinienzuweisung können Sie eine Richtlinie für große Benutzergruppen gleichzeitig zuweisen, ohne ein Skript verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ec872-218">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="ec872-219">Sie verwenden das ```New-CsBatchPolicyAssignmentOperation``` Cmdlet, um einen Benutzer Batch und die Richtlinie, die Sie zuweisen möchten, zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ec872-219">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="ec872-220">Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.</span><span class="sxs-lookup"><span data-stu-id="ec872-220">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="ec872-221">Anschließend können Sie das ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet verwenden, um den Fortschritt und den Status der Aufgaben in einem Batch zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ec872-221">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="ec872-222">Sie können Benutzer anhand der Objekt-ID oder der SIP-Adresse (Session Initiation Protocol) angeben.</span><span class="sxs-lookup"><span data-stu-id="ec872-222">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="ec872-223">Beachten Sie, dass die SIP-Adresse eines Benutzers häufig denselben Wert wie der Benutzerprinzipal Name (User Principal Name, UPN) oder die e-Mail-Adresse hat, dies ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec872-223">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="ec872-224">Wenn ein Benutzer über seinen UPN oder seine e-Mail-Adresse angegeben wird, dieser aber einen anderen Wert als seine SIP-Adresse hat, schlägt die Richtlinienzuweisung für den Benutzer fehl.</span><span class="sxs-lookup"><span data-stu-id="ec872-224">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="ec872-225">Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate aus dem Batch entfernt, bevor die Verarbeitung und der Status nur für die eindeutigen Benutzer bereitgestellt wird, die im Batch verbleiben.</span><span class="sxs-lookup"><span data-stu-id="ec872-225">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="ec872-226">Ein Batch kann bis zu 5.000-Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec872-226">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="ec872-227">Um optimale Ergebnisse zu erzielen, sollten Sie nicht mehr als ein paar Batches gleichzeitig einreichen.</span><span class="sxs-lookup"><span data-stu-id="ec872-227">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="ec872-228">Lassen Sie die Verarbeitung von Batches durchführen, bevor Sie weitere Stapel senden.</span><span class="sxs-lookup"><span data-stu-id="ec872-228">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="ec872-229">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="ec872-229">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="ec872-230">Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams)zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ec872-230">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="ec872-231">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="ec872-231">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="ec872-232">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ec872-232">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="ec872-233">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ec872-233">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="ec872-234">Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul (optional)</span><span class="sxs-lookup"><span data-stu-id="ec872-234">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="ec872-235">Möglicherweise möchten Sie auch [das Azure AD PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (falls noch nicht geschehen) herunterladen und installieren und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.</span><span class="sxs-lookup"><span data-stu-id="ec872-235">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="ec872-236">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ec872-236">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="ec872-237">Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung zu Teams verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="ec872-237">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="ec872-238">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="ec872-238">Assign a policy to a batch of users</span></span>

<span data-ttu-id="ec872-239">In diesem Beispiel verwenden wir das ```New-CsBatchPolicyAssignmentOperation``` Cmdlet, um eine APP-Setup Richtlinie mit dem Namen "HR-App-Setup Richtlinie" einem Batch von Benutzern zuzuweisen, die in der Datei "Users_ids. Text" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ec872-239">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="ec872-240">In diesem Beispiel stellen wir eine Verbindung mit Azure AD her, um eine Sammlung von Benutzern abzurufen, und weisen dann eine Messagingrichtlinie mit dem Namen "New Hire Messaging Policy" einem Batch von Benutzern zu, der mithilfe der SIP-Adresse angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ec872-240">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="ec872-241">Weitere Informationen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="ec872-241">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="ec872-242">Abrufen des Status einer Stapelverarbeitungs Zuordnung</span><span class="sxs-lookup"><span data-stu-id="ec872-242">Get the status of a batch assignment</span></span>

<span data-ttu-id="ec872-243">Führen Sie die folgenden Schritte aus, um den Status einer Stapelverarbeitungs Zuweisung abzurufen, wobei Vorgangskennung die Vorgangs-ID ist, die vom ```New-CsBatchPolicyAssignmentOperation``` Cmdlet für einen bestimmten Batch zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ec872-243">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="ec872-244">Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehlern zu erhalten, die in der Eigenschaft enthalten sind ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="ec872-244">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="ec872-245">Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="ec872-245">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="ec872-246">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="ec872-246">Assign a policy to a group</span></span>

<span data-ttu-id="ec872-247">Mit der Richtlinienzuweisung zu Gruppen können Sie einer Gruppe von Benutzern eine Richtlinie zuweisen, beispielsweise eine Sicherheitsgruppe oder eine Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="ec872-247">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="ec872-248">Die Richtlinienzuweisung wird nach Rangfolgeregeln an Mitglieder der Gruppe weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="ec872-248">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="ec872-249">Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ec872-249">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="ec872-250">Die Richtlinienzuweisung zu Gruppen wird für Gruppen von bis zu 50.000-Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.</span><span class="sxs-lookup"><span data-stu-id="ec872-250">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="ec872-251">Wenn Sie die Richtlinie zuweisen, wird Sie sofort der Gruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ec872-251">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="ec872-252">Beachten Sie jedoch, dass die Verteilung der Richtlinienzuweisung an Mitglieder der Gruppe als Hintergrundvorgang ausgeführt wird und je nach Größe der Gruppe einige Zeit in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="ec872-252">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="ec872-253">Das gleiche gilt, wenn eine Richtlinie aus einer Gruppe nicht zugewiesen wird oder wenn Mitglieder einer Gruppe hinzugefügt oder aus ihr entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ec872-253">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="ec872-254">Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen</span><span class="sxs-lookup"><span data-stu-id="ec872-254">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="ec872-255">Bevor Sie beginnen, ist es wichtig, die Rangfolge von Prioritätsregeln und die Rangfolge von Gruppenaufgaben zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="ec872-255">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="ec872-256">Rangfolgeregeln</span><span class="sxs-lookup"><span data-stu-id="ec872-256">Precedence rules</span></span>

<span data-ttu-id="ec872-257">Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers entsprechend den folgenden Bedingungen bestimmt:</span><span class="sxs-lookup"><span data-stu-id="ec872-257">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="ec872-258">Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor jeder anderen Richtlinie desselben Typs, die einer Gruppe zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-258">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="ec872-259">Anders ausgedrückt: Wenn einem Benutzer eine Richtlinie eines bestimmten Typs direkt zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs aus einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ec872-259">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="ec872-260">Dies bedeutet auch, dass Sie diese Richtlinie vom Benutzer entfernen müssen, bevor Sie eine Richtlinie desselben Typs aus einer Gruppe erben können, wenn ein Benutzer über eine Richtlinie eines bestimmten Typs verfügt, der Ihnen direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ec872-260">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="ec872-261">Wenn einem Benutzer nicht direkt eine Richtlinie zugewiesen wurde und es sich um ein Mitglied von zwei oder mehr Gruppen handelt und für jede Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenaufgabe, die die höchste Rangfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="ec872-261">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="ec872-262">Wenn ein Benutzer nicht Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ec872-262">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="ec872-263">Die effektive Richtlinie eines Benutzers wird entsprechend diesen Regeln aktualisiert, wenn ein Benutzer zu einer Gruppe hinzugefügt oder daraus entfernt wird, der eine Richtlinie zugewiesen ist, eine Richtlinie von einer Gruppe nicht zugewiesen wird oder eine Richtlinie entfernt wird, die dem Benutzer direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-263">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="ec872-264">Gruppen Zuordnungs Rangfolge</span><span class="sxs-lookup"><span data-stu-id="ec872-264">Group assignment ranking</span></span>
 
<span data-ttu-id="ec872-265">Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuordnung an.</span><span class="sxs-lookup"><span data-stu-id="ec872-265">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="ec872-266">Damit wird ermittelt, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer ein Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-266">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="ec872-267">Die Rangfolge der Gruppenzuweisungen ist relativ zu anderen Gruppenzuordnungen desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="ec872-267">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="ec872-268">Wenn Sie beispielsweise zwei Gruppen eine Anrufrichtlinie zuweisen, legen Sie die Rangfolge einer Zuordnung auf 1 und die andere auf 2, wobei 1 die höchste Rangliste ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-268">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="ec872-269">Die Gruppen Zuordnungs Rangfolge gibt an, welche Gruppenmitgliedschaft wichtiger oder relevanter als andere Gruppenmitgliedschaften im Hinblick auf die Vererbung ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-269">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="ec872-270">Angenommen, Sie verfügen über zwei Gruppen, Store-Mitarbeiter und Store-Manager.</span><span class="sxs-lookup"><span data-stu-id="ec872-270">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="ec872-271">Beiden Gruppen wird eine Anrufrichtlinie für Teams zugewiesen, und Sie können die Anruf Richtlinien für die Mitarbeiter und die Geschäftsmanager anrufen.</span><span class="sxs-lookup"><span data-stu-id="ec872-271">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="ec872-272">Bei einem Store Manager, der sich in beiden Gruppen befindet, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter, sodass die Anrufrichtlinie, die der Gruppe Store Managers zugewiesen ist, eine höhere Rangfolge aufweisen sollte.</span><span class="sxs-lookup"><span data-stu-id="ec872-272">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="ec872-273">Gruppe</span><span class="sxs-lookup"><span data-stu-id="ec872-273">Group</span></span> |<span data-ttu-id="ec872-274">Anruf Richtlinienname für Teams</span><span class="sxs-lookup"><span data-stu-id="ec872-274">Teams calling policy name</span></span>  |<span data-ttu-id="ec872-275">Rang</span><span class="sxs-lookup"><span data-stu-id="ec872-275">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="ec872-276">Store-Manager</span><span class="sxs-lookup"><span data-stu-id="ec872-276">Store Managers</span></span>   |<span data-ttu-id="ec872-277">Anruf Richtlinien für Store-Manager</span><span class="sxs-lookup"><span data-stu-id="ec872-277">Store Managers Calling Policy</span></span>         |<span data-ttu-id="ec872-278">1</span><span class="sxs-lookup"><span data-stu-id="ec872-278">1</span></span>|
|<span data-ttu-id="ec872-279">Speichern von Mitarbeitern</span><span class="sxs-lookup"><span data-stu-id="ec872-279">Store Employees</span></span>    |<span data-ttu-id="ec872-280">Speichern von Mitarbeiter Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ec872-280">Store Employees Calling Policy</span></span>      |<span data-ttu-id="ec872-281">2</span><span class="sxs-lookup"><span data-stu-id="ec872-281">2</span></span>|

<span data-ttu-id="ec872-282">Wenn Sie kein Ranking angeben, erhält die Richtlinienzuweisung die niedrigste Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="ec872-282">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ec872-283">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="ec872-283">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="ec872-284">**Dieses Feature wurde noch nicht veröffentlicht. Es wurde angekündigt, und es wird bald kommen.**</span><span class="sxs-lookup"><span data-stu-id="ec872-284">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="ec872-285">Derzeit steht die Richtlinienzuweisung für Gruppen, die das Microsoft Teams Admin Center verwenden, nur für die Anrufrichtlinie für Teams, die Besprechungsrichtlinie für Teams und die Messagingrichtlinie für Teams zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ec872-285">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="ec872-286">Verwenden Sie für andere Richtlinientypen PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec872-286">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="ec872-287">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zur Seite "Richtlinientyp".</span><span class="sxs-lookup"><span data-stu-id="ec872-287">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="ec872-288">Wechseln Sie beispielsweise zu **Meetings**den  >  **Besprechungsrichtlinien**für Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="ec872-288">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="ec872-289">Wählen Sie die Registerkarte **Gruppenrichtlinien Zuweisung** aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-289">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="ec872-290">Wählen Sie **Gruppe hinzufügen**aus, und führen Sie dann im Bereich **Richtlinie zu Gruppe zuweisen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ec872-290">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="ec872-291">Suchen Sie nach der Gruppe, der Sie die Richtlinie zuweisen möchten, und fügen Sie Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec872-291">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="ec872-292">Setzen Sie die Rangfolge für die Gruppenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="ec872-292">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="ec872-293">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec872-293">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="ec872-294">Wählen Sie über **nehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-294">Select **Apply**.</span></span>

<span data-ttu-id="ec872-295">Wenn Sie eine Gruppenrichtlinien Zuordnung entfernen möchten, wählen Sie auf der Registerkarte **Gruppenrichtlinien Zuweisung** auf der Seite Richtlinie die Gruppenzuordnung aus, und wählen Sie dann **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="ec872-295">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="ec872-296">Wenn Sie die Rangfolge einer Gruppenaufgabe ändern möchten, müssen Sie zuerst die Gruppenrichtlinien Zuweisung entfernen.</span><span class="sxs-lookup"><span data-stu-id="ec872-296">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="ec872-297">Führen Sie dann die obigen Schritte aus, um die Richtlinie einer Gruppe zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-297">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ec872-298">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec872-298">Using PowerShell</span></span>

<span data-ttu-id="ec872-299">**Dieses Feature steht derzeit nur in der privaten Vorschau zur Verfügung. Die Cmdlets für dieses Feature befinden sich im Public Preview-Modul von Teams PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="ec872-299">**This feature is currently only available in private preview. The cmdlets for this feature are in the Teams PowerShell public preview module.**</span></span>

> [!NOTE]
> <span data-ttu-id="ec872-300">Derzeit steht die Richtlinienzuweisung zu Gruppen mit PowerShell nicht für alle Teamrichtlinien Typen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ec872-300">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="ec872-301">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="ec872-301">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="ec872-302">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="ec872-302">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="ec872-303">Diese Cmdlets sind Teil des Public Preview-Moduls von Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec872-303">These cmdlets are part of the Teams PowerShell public preview module.</span></span> <span data-ttu-id="ec872-304">Schritt-für-Schritt-Anleitungen finden Sie unter [Installieren von Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="ec872-304">For step-by-step guidance, read [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="ec872-305">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="ec872-305">Assign a policy to a group</span></span>

<span data-ttu-id="ec872-306">Sie verwenden das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe eine Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-306">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="ec872-307">Sie können eine Gruppe mithilfe der Objekt-ID, der SIP-Adresse oder der e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="ec872-307">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="ec872-308">In diesem Beispiel verwenden wir das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe mit einer Zuordnungs Rangfolge von 1 eine Teams-Besprechungsrichtlinie mit dem Namen "Einzelhandels Manager-Besprechungsrichtlinie" zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-308">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="ec872-309">Weitere Informationen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="ec872-309">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="ec872-310">Abrufen von Richtlinienzuweisungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="ec872-310">Get policy assignments for a group</span></span>

<span data-ttu-id="ec872-311">Verwenden Sie das ```Get-CsGroupPolicyAssignment``` Cmdlet, um alle Richtlinien abzurufen, die einer Gruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ec872-311">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="ec872-312">Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn die SIP-Adresse oder e-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ec872-312">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="ec872-313">In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ec872-313">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="ec872-314">In diesem Beispiel geben wir alle Gruppen zurück, denen eine Teams-Besprechungsrichtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-314">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="ec872-315">Weitere Informationen finden Sie unter [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="ec872-315">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="ec872-316">Entfernen einer Richtlinie aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="ec872-316">Remove a policy from a group</span></span>

<span data-ttu-id="ec872-317">Verwenden Sie das ```Remove-CsGroupPolicyAssignment``` Cmdlet, um eine Richtlinie aus einer Gruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ec872-317">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="ec872-318">Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und die eine niedrigere Rangfolge aufweisen, aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ec872-318">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="ec872-319">Wenn Sie beispielsweise eine Richtlinie entfernen, die eine Rangfolge von 2 aufweist, werden Richtlinien mit einer Rangfolge von 3 und 4 aktualisiert, um Ihre neue Rangfolge wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="ec872-319">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="ec872-320">In den beiden folgenden Tabellen wird dieses Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec872-320">The following two tables show this example.</span></span>

<span data-ttu-id="ec872-321">Nachfolgend finden Sie eine Liste der Richtlinienzuweisungen und Prioritäten für eine Team-Besprechungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="ec872-321">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="ec872-322">Gruppenname</span><span class="sxs-lookup"><span data-stu-id="ec872-322">Group name</span></span>  |<span data-ttu-id="ec872-323">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="ec872-323">Policy name</span></span>  |<span data-ttu-id="ec872-324">Rang</span><span class="sxs-lookup"><span data-stu-id="ec872-324">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ec872-325">Vertrieb</span><span class="sxs-lookup"><span data-stu-id="ec872-325">Sales</span></span>    |<span data-ttu-id="ec872-326">Vertriebsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ec872-326">Sales policy</span></span>       | <span data-ttu-id="ec872-327">1</span><span class="sxs-lookup"><span data-stu-id="ec872-327">1</span></span>        |
|<span data-ttu-id="ec872-328">Region West</span><span class="sxs-lookup"><span data-stu-id="ec872-328">West Region</span></span>     |<span data-ttu-id="ec872-329">West Regions-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ec872-329">West Region policy</span></span>         |<span data-ttu-id="ec872-330">2</span><span class="sxs-lookup"><span data-stu-id="ec872-330">2</span></span>         |
|<span data-ttu-id="ec872-331">Division</span><span class="sxs-lookup"><span data-stu-id="ec872-331">Division</span></span>    |<span data-ttu-id="ec872-332">Abteilungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ec872-332">Division policy</span></span>         |<span data-ttu-id="ec872-333">3</span><span class="sxs-lookup"><span data-stu-id="ec872-333">3</span></span>         |
|<span data-ttu-id="ec872-334">Tochter</span><span class="sxs-lookup"><span data-stu-id="ec872-334">Subsidiary</span></span>   |<span data-ttu-id="ec872-335">Subsidiäre Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ec872-335">Subsidiary policy</span></span>        |<span data-ttu-id="ec872-336">4</span><span class="sxs-lookup"><span data-stu-id="ec872-336">4</span></span>         |

<span data-ttu-id="ec872-337">Wenn die West Region-Richtlinie aus der Gruppe "West Region" entfernt wird, werden die Richtlinienzuweisungen und-Prioritäten wie folgt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ec872-337">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="ec872-338">Gruppenname</span><span class="sxs-lookup"><span data-stu-id="ec872-338">Group name</span></span>  |<span data-ttu-id="ec872-339">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="ec872-339">Policy name</span></span>  |<span data-ttu-id="ec872-340">Rang</span><span class="sxs-lookup"><span data-stu-id="ec872-340">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ec872-341">Vertrieb</span><span class="sxs-lookup"><span data-stu-id="ec872-341">Sales</span></span>    |<span data-ttu-id="ec872-342">Vertriebsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ec872-342">Sales policy</span></span>       | <span data-ttu-id="ec872-343">1</span><span class="sxs-lookup"><span data-stu-id="ec872-343">1</span></span>        |
|<span data-ttu-id="ec872-344">Division</span><span class="sxs-lookup"><span data-stu-id="ec872-344">Division</span></span>    |<span data-ttu-id="ec872-345">Abteilungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ec872-345">Division policy</span></span>         |<span data-ttu-id="ec872-346">2</span><span class="sxs-lookup"><span data-stu-id="ec872-346">2</span></span>         |
|<span data-ttu-id="ec872-347">Tochter</span><span class="sxs-lookup"><span data-stu-id="ec872-347">Subsidiary</span></span>   |<span data-ttu-id="ec872-348">Subsidiäre Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ec872-348">Subsidiary policy</span></span>        |<span data-ttu-id="ec872-349">3</span><span class="sxs-lookup"><span data-stu-id="ec872-349">3</span></span>        |

<span data-ttu-id="ec872-350">In diesem Beispiel entfernen wir die Besprechungsrichtlinie für Teams aus einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ec872-350">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="ec872-351">Weitere Informationen finden Sie unter [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="ec872-351">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="ec872-352">Ändern einer Richtlinien Aufgabe für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="ec872-352">Change a policy assignment for a group</span></span>

<span data-ttu-id="ec872-353">Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das ```Set-CsGroupPolicyAssignment``` Cmdlet verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ec872-353">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="ec872-354">Ändern der Rangfolge</span><span class="sxs-lookup"><span data-stu-id="ec872-354">Change the ranking</span></span>
- <span data-ttu-id="ec872-355">Ändern der Richtlinie eines bestimmten Richtlinientyps</span><span class="sxs-lookup"><span data-stu-id="ec872-355">Change the policy of a given policy type</span></span>
- <span data-ttu-id="ec872-356">Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge</span><span class="sxs-lookup"><span data-stu-id="ec872-356">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="ec872-357">In diesem Beispiel ändern wir die Richtlinie für die Anruf Park Richtlinie einer Gruppe in eine Richtlinie mit dem Namen SupportCallPark und die Zuordnungs Rangfolge auf 3.</span><span class="sxs-lookup"><span data-stu-id="ec872-357">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="ec872-358">Weitere Informationen finden Sie unter [Satz-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="ec872-358">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="ec872-359">Ändern der effektiven Richtlinie für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec872-359">Change the effective policy for a user</span></span>

<span data-ttu-id="ec872-360">Im folgenden finden Sie ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-360">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="ec872-361">Zunächst verwenden wir das ```Get-CsUserPolicyAssignment``` Cmdlet zusammen mit dem ```PolicySource``` Parameter, um Details zu den Broadcast Richtlinien für Teams zu erhalten, die dem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ec872-361">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="ec872-362">Weitere Informationen finden Sie unter [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="ec872-362">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="ec872-363">Die Ausgabe zeigt, dass dem Benutzer direkt eine Team-Broadcast Richtlinie mit dem Namen "Employee Events" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Vendor Live Events" hat, die einer Gruppe zugeordnet ist, der der Benutzer angehört.</span><span class="sxs-lookup"><span data-stu-id="ec872-363">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="ec872-364">Jetzt entfernen wir die Mitarbeiter-Ereignis Richtlinie des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ec872-364">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="ec872-365">Das bedeutet, dass der Benutzer nicht mehr über eine Broadcast Richtlinie für Teams verfügt, die Ihnen direkt zugewiesen wurde, und erbt die Richtlinie für Anbieter-Live Ereignisse, die der Gruppe zugewiesen ist, der der Benutzer angehört.</span><span class="sxs-lookup"><span data-stu-id="ec872-365">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="ec872-366">Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="ec872-366">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="ec872-367">Sie können das folgende Cmdlet im Teams PowerShell-Modul verwenden, um dies bei einer Batch Richtlinienzuweisung zu tun, wobei $users eine Liste der von Ihnen angegebenen Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="ec872-367">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="ec872-368">Zuweisen eines Richtlinienpakets zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="ec872-368">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="ec872-369">Mit der Zuweisung von Batch Richtlinien Paketen können Sie einem Richtlinienpaket große Gruppen von Benutzern gleichzeitig zuweisen, ohne ein Skript verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ec872-369">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="ec872-370">Sie verwenden das ```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet, um einen Benutzer Batch und das Richtlinienpaket, das Sie zuweisen möchten, zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ec872-370">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="ec872-371">Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.</span><span class="sxs-lookup"><span data-stu-id="ec872-371">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="ec872-372">Anschließend können Sie das ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet verwenden, um den Fortschritt und den Status der Aufgaben in einem Batch zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ec872-372">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="ec872-373">Sie können Benutzer anhand der Objekt-ID oder der SIP-Adresse (Session Initiation Protocol) angeben.</span><span class="sxs-lookup"><span data-stu-id="ec872-373">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="ec872-374">Beachten Sie, dass die SIP-Adresse eines Benutzers häufig denselben Wert wie der Benutzerprinzipal Name (User Principal Name, UPN) oder die e-Mail-Adresse hat, dies ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec872-374">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="ec872-375">Wenn ein Benutzer über seinen UPN oder seine e-Mail-Adresse angegeben wird, dieser aber einen anderen Wert als seine SIP-Adresse hat, schlägt die Richtlinienzuweisung für den Benutzer fehl.</span><span class="sxs-lookup"><span data-stu-id="ec872-375">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="ec872-376">Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate aus dem Batch entfernt, bevor die Verarbeitung und der Status nur für die eindeutigen Benutzer bereitgestellt wird, die im Batch verbleiben.</span><span class="sxs-lookup"><span data-stu-id="ec872-376">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="ec872-377">Ein Batch kann bis zu 5.000-Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec872-377">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="ec872-378">Um optimale Ergebnisse zu erzielen, sollten Sie nicht mehr als ein paar Batches gleichzeitig einreichen.</span><span class="sxs-lookup"><span data-stu-id="ec872-378">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="ec872-379">Lassen Sie die Verarbeitung von Batches durchführen, bevor Sie weitere Stapel senden.</span><span class="sxs-lookup"><span data-stu-id="ec872-379">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="ec872-380">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="ec872-380">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="ec872-381">Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (falls noch nicht geschehen).</span><span class="sxs-lookup"><span data-stu-id="ec872-381">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="ec872-382">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="ec872-382">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="ec872-383">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ec872-383">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="ec872-384">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ec872-384">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="ec872-385">Zuweisen eines Richtlinienpakets zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="ec872-385">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="ec872-386">In diesem Beispiel verwenden wir das ```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet, um einem Batch von Benutzern das Education_PrimaryStudent-Richtlinienpaket zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec872-386">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="ec872-387">Weitere Informationen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="ec872-387">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="ec872-388">Abrufen des Status einer Stapelverarbeitungs Zuordnung</span><span class="sxs-lookup"><span data-stu-id="ec872-388">Get the status of a batch assignment</span></span>

<span data-ttu-id="ec872-389">Führen Sie die folgenden Schritte aus, um den Status einer Stapelverarbeitungs Zuweisung abzurufen, wobei Vorgangskennung die Vorgangs-ID ist, die vom ```New-CsBatchPolicyAssignmentOperation``` Cmdlet für einen bestimmten Batch zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ec872-389">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="ec872-390">Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehlern zu erhalten, die in der Eigenschaft enthalten sind ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="ec872-390">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="ec872-391">Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="ec872-391">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ec872-392">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ec872-392">Related topics</span></span>

[<span data-ttu-id="ec872-393">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec872-393">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
