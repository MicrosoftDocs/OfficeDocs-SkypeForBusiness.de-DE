---
title: Parken und Fortsetzen von Anrufen in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie in Microsoft Teams mithilfe von Parken und Abrufen einen Anruf in Wartestellung setzen.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424593"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="fa43f-103">Parken und Fortsetzen von Anrufen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa43f-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="fa43f-104">Parken und Abrufen ist eine Funktion, mit der ein Nutzer einen Anruf in Wartestellung setzen kann.</span><span class="sxs-lookup"><span data-stu-id="fa43f-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="fa43f-105">Wenn ein Anruf abgestellt wird, generiert der Dienst einen eindeutigen Code für den Abruf des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa43f-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="fa43f-106">Der Benutzer, der den Anruf abgestellt hat, oder eine andere Person können diesen Code dann mit einer unterstützten APP oder einem Gerät verwenden, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="fa43f-107">(Weitere Informationen finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .)</span><span class="sxs-lookup"><span data-stu-id="fa43f-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="fa43f-108">Einige häufige Szenarien für die Verwendung von Call Park sind:</span><span class="sxs-lookup"><span data-stu-id="fa43f-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="fa43f-109">Eine Empfangsdame parkt einen Anruf für jemanden, der in einer Fabrik arbeitet.</span><span class="sxs-lookup"><span data-stu-id="fa43f-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="fa43f-110">Der Rezeptionist kündigt dann den Anruf und die Codenummer über das öffentliche adresssystem an.</span><span class="sxs-lookup"><span data-stu-id="fa43f-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="fa43f-111">Der Benutzer, für den der Anruf ansteht, kann dann in der Factory-Etage ein Team Telefon aufnehmen und den Code zum Abrufen des Anrufs eingeben.</span><span class="sxs-lookup"><span data-stu-id="fa43f-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="fa43f-112">Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, da der Akku des Geräts knapp wird.</span><span class="sxs-lookup"><span data-stu-id="fa43f-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="fa43f-113">Der Benutzer kann dann den Code eingeben, um den Anruf von einem Team-Tischtelefon abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="fa43f-114">Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams-Kanal, damit ein Experte den Anruf abruft und dem Kunden hilft.</span><span class="sxs-lookup"><span data-stu-id="fa43f-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="fa43f-115">Ein Experte gibt den Code in Teams-Clients ein, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="fa43f-116">Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP-Benutzer sein und muss in eine Anruf Park Richtlinie aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="fa43f-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="fa43f-117">Parken und Abrufen von Anrufen steht nur im [Bereitstellungsmodus für Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) zur Verfügung und wird von Skype for Business-IP-Telefonen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa43f-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="fa43f-118">Konfigurieren des Anruf Parks und Abrufen</span><span class="sxs-lookup"><span data-stu-id="fa43f-118">Configure call park and retrieve</span></span>

<span data-ttu-id="fa43f-119">Sie müssen ein Teamadministrator sein, um den Parken von Anrufen zu konfigurieren und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="fa43f-120">Sie ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fa43f-120">It is disabled by default.</span></span> <span data-ttu-id="fa43f-121">Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf Park Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="fa43f-122">Wenn Sie die gleiche Richtlinie auf eine Reihe von Benutzern anwenden, können Sie Anrufe unter sich selbst Parken und abrufen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="fa43f-123">So aktivieren Sie eine Anruf Park Richtlinie</span><span class="sxs-lookup"><span data-stu-id="fa43f-123">To enable a call park policy</span></span>

1. <span data-ttu-id="fa43f-124">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Richtlinien für den **VoIP**-  >  **Anruf Park**.</span><span class="sxs-lookup"><span data-stu-id="fa43f-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="fa43f-125">Klicken Sie auf der Registerkarte **Richtlinien verwalten** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fa43f-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="fa43f-126">Geben Sie der Richtlinie einen Namen, und wählen Sie dann "Parken **von** **anrufen zulassen** " auf ein.</span><span class="sxs-lookup"><span data-stu-id="fa43f-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Screenshot der Richtlinieneinstellungen für das Parken von Anrufen](media/call-park-add-policy.png)

4. <span data-ttu-id="fa43f-128">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="fa43f-128">Select **Save**.</span></span>

<span data-ttu-id="fa43f-129">Sie können die Richtlinie bearbeiten, indem Sie Sie in der Liste auswählen und dann auf **Bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="fa43f-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="fa43f-130">Damit die Richtlinie funktioniert, muss Sie Benutzern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fa43f-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="fa43f-131">Sie können [die Richtlinie Benutzern einzeln zuweisen](assign-policies.md) oder Sie einer Gruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fa43f-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="fa43f-132">So weisen Sie einer Gruppe eine Anruf Teil Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="fa43f-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="fa43f-133">Klicken Sie auf der Seite **Anruf Park Richtlinien** auf der Registerkarte **Gruppenrichtlinien Zuweisung** auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fa43f-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="fa43f-134">Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fa43f-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="fa43f-135">Wählen Sie einen Rang im Vergleich zu anderen Gruppenaufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="fa43f-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="fa43f-136">Wählen Sie unter **Richtlinie auswählen**die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="fa43f-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="fa43f-137">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="fa43f-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa43f-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fa43f-138">Related topics</span></span>

[<span data-ttu-id="fa43f-139">Parken eines Anrufs in Teams</span><span class="sxs-lookup"><span data-stu-id="fa43f-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="fa43f-140">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa43f-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="fa43f-141">Neu – CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="fa43f-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="fa43f-142">Satz-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="fa43f-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="fa43f-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="fa43f-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)