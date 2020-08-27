---
title: Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Rufnummernanzeige Richtlinien in Microsoft Teams verwenden und verwalten, um die Rufnummernanzeige von Teams-Benutzern in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255528"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="33948-103">Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33948-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="33948-104">Als Administrator können Sie die Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Rufnummernanzeige (auch als Anruf Leitungs-ID bezeichnet) zu ändern oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="33948-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="33948-105">Standardmäßig kann die Telefonnummer von Teams-Benutzern angezeigt werden, wenn Sie einen Anruf an ein PSTN-Telefon durchführen, und die Telefonnummer der PSTN-Anrufer kann angezeigt werden, wenn Sie einen Teams-Nutzer anrufen.</span><span class="sxs-lookup"><span data-stu-id="33948-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="33948-106">Sie können die Richtlinien für die Rufnummernanzeige verwenden, um eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzuzeigen oder die Anzeige einer eingehenden Nummer zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="33948-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="33948-107">Wenn Benutzer beispielsweise einen Anruf führen, können Sie die Rufnummernanzeige ändern, um die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="33948-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="33948-108">Sie verwalten die Richtlinien für die Rufnummernanzeige, indem Sie **Voice**  >  im Microsoft Teams Admin Center zu den Richtlinien für die VoIP **-Anruferkennung** wechseln.</span><span class="sxs-lookup"><span data-stu-id="33948-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="33948-109">Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="33948-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="33948-110">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="33948-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="33948-111">Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="33948-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="33948-112">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**  >  **-Richtlinien für Anrufer**.</span><span class="sxs-lookup"><span data-stu-id="33948-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="33948-113">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="33948-113">Click **Add**.</span></span> <br>
<span data-ttu-id="33948-114">![Screenshot der Seite "neue Rufnummernanzeige" im Admin Center](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="33948-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="33948-115">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="33948-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="33948-116">Wählen Sie hier die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="33948-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="33948-117">**Eingehende Anrufer-ID blockieren**: Aktivieren Sie diese Einstellung, um die Rufnummernanzeige für eingehende Anrufe zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="33948-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="33948-118">**Überschreiben Sie die Richtlinie für die Rufnummern**Anzeige: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie bezüglich der Anzeige der Rufnummer für Anrufer überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="33948-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="33948-119">Das bedeutet, dass Benutzer auswählen können, ob Sie Ihre Rufnummernanzeige anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="33948-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="33948-120">Weitere Informationen finden Sie unter [Endbenutzer-Steuerung der ausgehenden Rufnummern](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)Anzeige.</span><span class="sxs-lookup"><span data-stu-id="33948-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="33948-121">**Ersetzen Sie die Rufnummern**Anzeige durch: Legen Sie die Rufnummernanzeige für die Benutzer angezeigt, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="33948-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="33948-122">**Nummer des Benutzers**: zeigt die Nummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="33948-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="33948-123">**Dienstnummer**: Hier können Sie eine Dienst Telefonnummer einrichten, die als Rufnummernanzeige angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="33948-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="33948-124">**Anonym**: zeigt die Rufnummernanzeige als "Anonym" an.</span><span class="sxs-lookup"><span data-stu-id="33948-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="33948-125">**Ersetzen Sie die Rufnummernanzeige durch diese Service-Nummer**: Wählen Sie eine Dienstnummer aus, um die Rufnummernanzeige der Nutzer zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="33948-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="33948-126">Diese Option steht zur Verfügung, wenn Sie im **Feld Rufnummernanzeige ersetzen die Rufnummern** **Anzeige ausgewählt haben** .</span><span class="sxs-lookup"><span data-stu-id="33948-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="33948-127">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="33948-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="33948-128">Bearbeiten einer Rufnummernanzeige-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="33948-128">Edit a caller ID policy</span></span>

<span data-ttu-id="33948-129">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="33948-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="33948-130">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**  >  **-Richtlinien für Anrufer**.</span><span class="sxs-lookup"><span data-stu-id="33948-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="33948-131">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="33948-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="33948-132">Ändern Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="33948-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="33948-133">Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="33948-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="33948-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="33948-134">Related topics</span></span>

[<span data-ttu-id="33948-135">Neu – CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="33948-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="33948-136">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33948-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
