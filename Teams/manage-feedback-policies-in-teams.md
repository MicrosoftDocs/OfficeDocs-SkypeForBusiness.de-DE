---
title: Verwalten von Feedback Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe von Feedback Richtlinien steuern können, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: b489e574a1d1c2a2b1ac5faf69626e997dbbfaa9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938484"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="78f6c-103">Verwalten von Feedback Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="78f6c-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="78f6c-104">Benutzer in Ihrer Organisation können Feedback zu Teams an Microsoft senden lassen Sie uns wissen, wie wir vorgehen, und zwar direkt von den Desktop-und Webclients der Teams aus.</span><span class="sxs-lookup"><span data-stu-id="78f6c-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="78f6c-105">Wir arbeiten ständig an der Verbesserung der Teams, und wir nutzen dieses Feedback, um Teams besser zu machen.</span><span class="sxs-lookup"><span data-stu-id="78f6c-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="78f6c-106">**Das Feature "Feedback senden"**</span><span class="sxs-lookup"><span data-stu-id="78f6c-106">**The Give feedback feature**</span></span>

<span data-ttu-id="78f6c-107">Benutzer können Kommentare und Vorschläge zu Teams an uns **senden, indem Sie**  >  **Feedback** in Teams geben.</span><span class="sxs-lookup"><span data-stu-id="78f6c-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="78f6c-108">Daten, die durch **Feedback** gesendet werden, gelten als "Support Daten" unter Ihrem Microsoft 365-oder Office 365-Vertrag, einschließlich Informationen, die andernfalls als "Kundendaten" oder "persönliche Daten" gelten.</span><span class="sxs-lookup"><span data-stu-id="78f6c-108">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="78f6c-110">**Umfragen**</span><span class="sxs-lookup"><span data-stu-id="78f6c-110">**Surveys**</span></span>

<span data-ttu-id="78f6c-111">Benutzer können auch Ihre Erfahrungen mit Teams bewerten und uns Informationen über die von Ihnen gegebene Bewertung senden.</span><span class="sxs-lookup"><span data-stu-id="78f6c-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="78f6c-112">Diese Popup Umfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78f6c-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="78f6c-113">Wenn ein Benutzer in der Benachrichtigung auf **Feedback bereitstellen** klickt, wird die Umfrage angezeigt, damit Sie abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="78f6c-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Screenshot der Umfrage Benachrichtigung und des Formulars in Microsoft Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="78f6c-115">Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können</span><span class="sxs-lookup"><span data-stu-id="78f6c-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="78f6c-116">Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können, indem Sie **Feedback geben und angeben** , ob Sie die Umfrage erhalten.</span><span class="sxs-lookup"><span data-stu-id="78f6c-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="78f6c-117">Standardmäßig werden allen Benutzern in Ihrer Organisation automatisch die globale (org-Wide Standard)-Richtlinie zugewiesen, und das Feature " **Feedback senden** " und die Umfrage sind in der Richtlinie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="78f6c-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="78f6c-118">Die Ausnahme bilden Teams für Bildungseinrichtungen, in denen die Features für Lehrer und Behinderte für Schüler aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="78f6c-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="78f6c-119">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78f6c-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="78f6c-120">Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="78f6c-120">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="78f6c-121">Angenommen, Sie möchten allen Benutzern in Ihrer Organisation das Senden **von Feedback über Feedback und empfangen** von Umfragen mit Ausnahme von neuen Mitarbeitern in der Schulung gestatten.</span><span class="sxs-lookup"><span data-stu-id="78f6c-121">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="78f6c-122">In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und neuen Mitarbeitern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="78f6c-122">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="78f6c-123">Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.</span><span class="sxs-lookup"><span data-stu-id="78f6c-123">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="78f6c-124">Sie können Feedback Richtlinien mithilfe von PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="78f6c-124">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="78f6c-125">Verwenden Sie das Cmdlet **New-CsTeamsFeedbackPolicy** , *das [hier gefunden](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)werden kann*, um eine benutzerdefinierte Richtlinie und das **Grant-CsTeamsFeedbackPolicy-** Cmdlet zu erstellen, um es einem oder mehreren Benutzern oder Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="78f6c-125">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="78f6c-126">Um die Features zu deaktivieren und zu aktivieren, setzen Sie die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="78f6c-126">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="78f6c-127">**Feedback geben**: Legen Sie den **userInitiatedMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können.</span><span class="sxs-lookup"><span data-stu-id="78f6c-127">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="78f6c-128">Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.</span><span class="sxs-lookup"><span data-stu-id="78f6c-128">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="78f6c-129">**Umfragen**: setzen Sie den **receiveSurveysMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können.</span><span class="sxs-lookup"><span data-stu-id="78f6c-129">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="78f6c-130">Damit Benutzer die Umfrage erhalten und Sie Sie deaktivieren können, setzen Sie den Parameter auf **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="78f6c-130">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="78f6c-131">In Teams können Benutzer dann zu **Einstellungen**  >  **Datenschutz** wechseln und auswählen, ob Sie an Umfragen teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="78f6c-131">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="78f6c-132">Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.</span><span class="sxs-lookup"><span data-stu-id="78f6c-132">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="78f6c-133">Erstellen einer benutzerdefinierten Feedback Richtlinie</span><span class="sxs-lookup"><span data-stu-id="78f6c-133">Create a custom feedback policy</span></span>

<span data-ttu-id="78f6c-134">In diesem Beispiel erstellen wir eine Feedback-Richtlinie namens "New Hire Feedback Policy" und deaktivieren die Möglichkeit, **Feedback durch Feedback** und die Umfrage zu geben.</span><span class="sxs-lookup"><span data-stu-id="78f6c-134">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="78f6c-135">Zuweisen einer benutzerdefinierten Feedback Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="78f6c-135">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="78f6c-136">In diesem Beispiel weisen wir einem Benutzer mit dem Namen Benutzer1 eine benutzerdefinierte Richtlinie mit dem Namen "New Hire Feedback Policy" zu.</span><span class="sxs-lookup"><span data-stu-id="78f6c-136">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="78f6c-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="78f6c-137">Related topics</span></span>

- [<span data-ttu-id="78f6c-138">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="78f6c-138">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="78f6c-139">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="78f6c-139">Assign policies to your users in Teams</span></span>](assign-policies.md)