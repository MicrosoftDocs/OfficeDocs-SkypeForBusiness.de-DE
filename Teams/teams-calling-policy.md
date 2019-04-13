---
title: Aufrufen von Gruppenrichtlinien in Microsoft-Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Informationen Sie zu Richtlinieneinstellungen in der Microsoft-Teams aufrufen.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860262"
---
<a name="calling-policy-in-microsoft-teams"></a><span data-ttu-id="c6ced-103">Aufrufen von Gruppenrichtlinien in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="c6ced-103">Calling policy in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="c6ced-104">In Microsoft-Teams Richtlinien-Steuerelements aufrufen, denen der Aufruf und Features für die anrufweiterleitung für Benutzer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c6ced-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="c6ced-105">Aufrufen von Standortrichtlinien wird bestimmt, ob ein Benutzer private aufgerufen werden kann, verwenden Sie die anrufweiterleitung oder Gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern, Weiterleitung von Anrufen an Voicemail, senden Anrufe an Gruppen aufrufen Delegierung für eingehende und ausgehende Anrufe, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="c6ced-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="c6ced-106">Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte aufrufende Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c6ced-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="c6ced-107">Aufrufen von Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="c6ced-107">Calling policy settings</span></span>

|<span data-ttu-id="c6ced-108">Aufrufen der richtlinieneinstellung</span><span class="sxs-lookup"><span data-stu-id="c6ced-108">Calling policy setting</span></span> | <span data-ttu-id="c6ced-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6ced-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="c6ced-110">Benutzer kann private Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="c6ced-110">User can make private calls</span></span> | <span data-ttu-id="c6ced-111">Steuert alle aufrufende Funktionen in Teams.</span><span class="sxs-lookup"><span data-stu-id="c6ced-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="c6ced-112">Deaktivieren Dies wird alle Anruffunktionen in Teams deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c6ced-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="c6ced-113">Die anrufweiterleitung und Gleichzeitiges Klingeln an andere Benutzer</span><span class="sxs-lookup"><span data-stu-id="c6ced-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="c6ced-114">Steuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden kann oder eine andere Person gleichzeitig Anrufen kann.</span><span class="sxs-lookup"><span data-stu-id="c6ced-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="c6ced-115">Die anrufweiterleitung und Gleichzeitiges Klingeln an externe Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="c6ced-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="c6ced-116">Steuert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden kann, oder eine externe Nummer gleichzeitig Anrufen kann.</span><span class="sxs-lookup"><span data-stu-id="c6ced-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="c6ced-117">Voicemail wird für eingehende Anrufe an die Benutzer verfügbar</span><span class="sxs-lookup"><span data-stu-id="c6ced-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="c6ced-118">Ermöglicht die eingehende Anrufe an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6ced-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="c6ced-119">Gültige Optionen sind **immer aktiviert**, **immer deaktiviert**oder **Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="c6ced-120">Zum Aufrufen von Gruppen können eingehende Anrufe weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="c6ced-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="c6ced-121">Steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="c6ced-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="c6ced-122">Erlaubt die Delegierung für eingehende und ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="c6ced-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="c6ced-123">Ermöglicht die eingehende Anrufe an die Stellvertretungen weitergeleitet werden sollen; ermöglicht die Stellvertretungen zu ausgehenden Anrufe im Namen der Benutzer, für den sie Berechtigungen delegiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6ced-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="c6ced-124">Verhindern, dass Gebühren umgehen und senden Sie Anrufe über das Telefonfestnetz</span><span class="sxs-lookup"><span data-stu-id="c6ced-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="c6ced-125">Durch Festlegen dieser auf **aktiviert** wird, sendet Anrufe über PSTN und Gebühren für statt über das Netzwerk laufen und umgeht die Gebühren anfallen.</span><span class="sxs-lookup"><span data-stu-id="c6ced-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="c6ced-126">Beschäftigt auf beschäftigt ist während eines Anrufs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6ced-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="c6ced-127">Konfiguriert, wie eingehende Anrufe verarbeitet werden, wenn ein Benutzer bereits in einem Anruf oder einer Konferenz ist.</span><span class="sxs-lookup"><span data-stu-id="c6ced-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="c6ced-128">Neue oder eingehende Anrufe können mit einer Besetztzeichen abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="c6ced-128">New or incoming calls can be rejected with a busy signal.</span></span> |

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="c6ced-129">Erstellen Sie eine benutzerdefinierte Richtlinie an aufrufende</span><span class="sxs-lookup"><span data-stu-id="c6ced-129">Create a custom calling policy</span></span>

<span data-ttu-id="c6ced-130">Befolgen Sie diese Schritte, um eine neue benutzerdefinierte aufrufende Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6ced-130">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="c6ced-131">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-131">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="c6ced-132">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="c6ced-132">Select **New policy**.</span></span>
3. <span data-ttu-id="c6ced-133">Aktivieren Sie die Features, die Sie in der aufrufenden Richtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c6ced-133">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="c6ced-134">Alle ausgewählten Optionen sind standardmäßig **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="c6ced-134">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="c6ced-135">Um zu steuern, ob Benutzer eingehende Anrufe an die Voicemail weitergeleitet werden können, wählen Sie **immer aktiviert** , oder **Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-135">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="c6ced-136">Um zu verhindern, an die Voicemail-routing, wählen Sie **immer deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-136">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="c6ced-137">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="c6ced-137">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="c6ced-138">Ändern einer vorhandenen Richtlinie aufrufen</span><span class="sxs-lookup"><span data-stu-id="c6ced-138">Modify an existing calling policy</span></span>

<span data-ttu-id="c6ced-139">Befolgen Sie diese Schritte zum Ändern einer vorhandenen Richtlinie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c6ced-139">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="c6ced-140">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-140">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="c6ced-141">Klicken Sie neben der Richtlinie, die Sie ändern, und wählen Sie **Bearbeiten**möchten.</span><span class="sxs-lookup"><span data-stu-id="c6ced-141">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="c6ced-142">Aktivieren Sie die Features, die Sie in der aufrufenden Richtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c6ced-142">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="c6ced-143">Alle ausgewählten Optionen sind standardmäßig **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="c6ced-143">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="c6ced-144">Um zu steuern, ob Benutzer eingehende Anrufe an die Voicemail weitergeleitet werden können, wählen Sie **immer aktiviert** , oder **Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-144">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="c6ced-145">Um zu verhindern, an die Voicemail-routing, wählen Sie **immer deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-145">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="c6ced-146">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="c6ced-146">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="c6ced-147">Zuweisen einer Richtlinie für aufrufenden zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="c6ced-147">Assign a calling policy to a user</span></span>

<span data-ttu-id="c6ced-148">Befolgen Sie diese Schritte, um eine benutzerdefinierte Richtlinie an aufrufen, die einem Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c6ced-148">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="c6ced-149">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-149">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="c6ced-150">Klicken Sie neben den Namen der Richtlinie, wählen Sie sie aus, und wählen Sie dann auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-150">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="c6ced-151">Suchen Sie nach den Namen des Benutzers, klicken Sie im Bereich **Benutzer verwalten** .</span><span class="sxs-lookup"><span data-stu-id="c6ced-151">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="c6ced-152">(Sie müssen mindestens drei Zeichen eingeben.)</span><span class="sxs-lookup"><span data-stu-id="c6ced-152">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="c6ced-153">Wählen Sie den Namen des Benutzers aus, und wählen Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c6ced-153">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="c6ced-154">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="c6ced-154">Select **Save**.</span></span>
