---
title: Öffentliche Vorschau in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über die öffentliche Vorschau in Microsoft Teams. Testen Sie neue Features, und senden Sie Feedback.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530982"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="d1663-104">Public Preview für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1663-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="d1663-p102">Die in der Vorschau enthaltenen Features sind möglicherweise nicht vollständig und können geändert werden, bevor sie im öffentlichen Release verfügbar gemacht wird. Sie werden nur zu Evaluierungs- und Untersuchungszwecken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d1663-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="d1663-p103">Public Preview für Microsoft Teams bietet frühzeitigen Zugriff auf unveröffentlichte Features in Teams. Mit der Vorschau können Sie bevorstehende Features untersuchen und testen. Wir freuen uns über Ihr Feedback zu jedem Feature in öffentlichen Vorschauen. Die öffentliche Vorschau ist für jeden Teams-Benutzer aktiviert, daher müssen Sie sich keine Gedanken über die Auswirkungen auf die gesamte Organisation machen.</span><span class="sxs-lookup"><span data-stu-id="d1663-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="d1663-111">Festlegen der Updaterichtlinie</span><span class="sxs-lookup"><span data-stu-id="d1663-111">Set the Update policy</span></span>

 <span data-ttu-id="d1663-112">Die öffentliche Vorschau ist für jeden Benutzer aktiviert, und die Option zum Aktivieren der öffentlichen Vorschau wird in einer Administratorrichtlinie gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d1663-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="d1663-113">Updaterichtlinien werden zur Verwaltung der Teams- und Office-Vorschaubenutzer verwendet, die Features von Vorabversionen oder Vorschauen in der Teams-App sehen.</span><span class="sxs-lookup"><span data-stu-id="d1663-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="d1663-114">Sie können die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden und anpassen, oder eine oder mehrere benutzerdefinierte Richtlinien für Ihre Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1663-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="d1663-115">Die Richtlinie muss bestimmten Benutzern zugewiesen werden, da sie die globale Richtlinie nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="d1663-115">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="d1663-116">Melden Sie sich beim Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="d1663-116">Sign in to the admin center.</span></span>
2. <span data-ttu-id="d1663-117">Wählen Sie **Teams**>**Updaterichtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="d1663-117">Select **Teams**>**Update policies**.</span></span>

   ![Auswählen der Option "Updaterichtlinien"](media/updatePolicies.png)

3. <span data-ttu-id="d1663-119">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d1663-119">Select **Add**.</span></span>
4. <span data-ttu-id="d1663-120">Benennen Sie die Updaterichtlinie, fügen Sie eine Beschreibung hinzu, und aktivieren Sie **Vorschaufeatures anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d1663-120">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="d1663-121">Sie können die Richtlinie auch mit dem `CsTeamsUpdateManagementPolicy`-Cmdlet von PowerShell festlegen.</span><span class="sxs-lookup"><span data-stu-id="d1663-121">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="d1663-122">Aktivieren der öffentlichen Vorschau</span><span class="sxs-lookup"><span data-stu-id="d1663-122">Enable public preview</span></span>

<span data-ttu-id="d1663-123">Wenn Sie die öffentliche Vorschau auf einem Desktop- oder Webclient aktivieren möchten, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="d1663-123">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="d1663-124">Wählen Sie Ihr Profil aus, um das Teams-Menü anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1663-124">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="d1663-125">Wählen Sie **Info** → **Public Preview** aus.</span><span class="sxs-lookup"><span data-stu-id="d1663-125">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="d1663-126">Wählen Sie **Zur Public Preview wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="d1663-126">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1663-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d1663-127">Related topics</span></span>

[<span data-ttu-id="d1663-128">Öffentliche Entwicklervorschau</span><span class="sxs-lookup"><span data-stu-id="d1663-128">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
