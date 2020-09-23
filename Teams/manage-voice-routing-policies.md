---
title: Verwalten von VoIP-Routing Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie VoIP-Routing Richtlinien in Microsoft Teams erstellen und verwalten.
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217656"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="3a9da-103">Verwalten von VoIP-Routing Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a9da-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="3a9da-104">Wenn Sie in Ihrer Organisation ein [Direktes Routing für das Telefon System](direct-routing-landing-page.md) bereitgestellt haben, können Sie mithilfe der VoIP-Routing Richtlinien Teams und Skype for Business Online-Benutzern das empfangen und tätigen von Telefon anrufen mit dem öffentlichen Telefonnetz (PSTN) über Ihre lokale Telefonie-Infrastruktur ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3a9da-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="3a9da-105">Eine VoIP-Routing Richtlinie ist ein Container für PSTN-Verwendungsdaten Sätze.</span><span class="sxs-lookup"><span data-stu-id="3a9da-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="3a9da-106">Sie können VoIP-Routing Richtlinien erstellen und verwalten, **Voice**indem Sie  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Routing Richtlinien** wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a9da-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="3a9da-107">Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3a9da-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="3a9da-108">Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu.</span><span class="sxs-lookup"><span data-stu-id="3a9da-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="3a9da-109">Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="3a9da-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="3a9da-110">Es ist wichtig zu wissen, dass es für das Zuweisen einer VoIP-Routing Richtlinie zu einem Benutzer nicht möglich ist, in Teams PSTN-Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="3a9da-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="3a9da-111">Darüber hinaus müssen Sie den Benutzer für das direkte Routing des Telefonsystems aktivieren und andere Konfigurationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a9da-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="3a9da-112">Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="3a9da-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="3a9da-113">Erstellen einer benutzerdefinierten VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3a9da-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3a9da-114">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="3a9da-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3a9da-115">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3a9da-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="3a9da-116">![Screenshot der Seite "VoIP-Routing Richtlinie hinzufügen" im Microsoft Teams Admin Center ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="3a9da-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="3a9da-117">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3a9da-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="3a9da-118">Klicken Sie unter **PSTN-Verwendungsdaten Sätze**auf **PSTN-Verwendung hinzufügen**, und wählen Sie dann die Datensätze aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a9da-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="3a9da-119">Wenn Sie einen neuen PSTN-Verwendungsdaten Satz erstellen müssen, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3a9da-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="3a9da-120">Wenn Sie mehrere PSTN-Verwendungsdaten Sätze hinzugefügt haben, ordnen Sie diese in der gewünschten Reihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="3a9da-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="3a9da-121">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="3a9da-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="3a9da-122">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3a9da-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3a9da-123">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a9da-123">Using PowerShell</span></span>

<span data-ttu-id="3a9da-124">Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="3a9da-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="3a9da-125">Bearbeiten einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3a9da-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3a9da-126">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="3a9da-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3a9da-127">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3a9da-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="3a9da-128">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="3a9da-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="3a9da-129">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="3a9da-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3a9da-130">Klicken Sie auf **PSTN-Verwendungsdaten Sätze hinzufügen/entfernen**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3a9da-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3a9da-131">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a9da-131">Using PowerShell</span></span>

<span data-ttu-id="3a9da-132">Weitere Informationen finden Sie unter [Satz-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="3a9da-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="3a9da-133">Zuweisen einer benutzerdefinierten VoIP-Routing Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="3a9da-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="3a9da-134">Siehe auch [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="3a9da-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a9da-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3a9da-135">Related topics</span></span>

[<span data-ttu-id="3a9da-136">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a9da-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="3a9da-137">Konfigurieren des VoIP-Routings für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="3a9da-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="3a9da-138">Aktivieren des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="3a9da-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="3a9da-139">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a9da-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
