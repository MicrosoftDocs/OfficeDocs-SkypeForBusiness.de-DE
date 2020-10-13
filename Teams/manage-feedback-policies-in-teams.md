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
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433038"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="22c35-103">Verwalten von Feedback Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22c35-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="22c35-104">Benutzer in Ihrer Organisation können Feedback zu Teams an Microsoft senden lassen Sie uns wissen, wie wir vorgehen, und zwar direkt von den Desktop-und Webclients der Teams aus.</span><span class="sxs-lookup"><span data-stu-id="22c35-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="22c35-105">Wir arbeiten ständig an der Verbesserung der Teams, und wir nutzen dieses Feedback, um Teams besser zu machen.</span><span class="sxs-lookup"><span data-stu-id="22c35-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="22c35-106">Feedback Richtlinien sind in gcc-, gcc-Hochspannungs-oder DoD-Bereitstellungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="22c35-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="22c35-107">**Das Feature "Feedback senden"**</span><span class="sxs-lookup"><span data-stu-id="22c35-107">**The Give feedback feature**</span></span>

<span data-ttu-id="22c35-108">Benutzer können Kommentare und Vorschläge zu Teams an uns **senden, indem Sie**  >  **Feedback** in Teams geben.</span><span class="sxs-lookup"><span data-stu-id="22c35-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="22c35-109">Daten, die durch **Feedback** gesendet werden, gelten als "Support Daten" unter Ihrem Microsoft 365-oder Office 365-Vertrag, einschließlich Informationen, die andernfalls als "Kundendaten" oder "persönliche Daten" gelten.</span><span class="sxs-lookup"><span data-stu-id="22c35-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="22c35-111">**Umfragen**</span><span class="sxs-lookup"><span data-stu-id="22c35-111">**Surveys**</span></span>

<span data-ttu-id="22c35-112">Benutzer können auch Ihre Erfahrungen mit Teams bewerten und uns Informationen über die von Ihnen gegebene Bewertung senden.</span><span class="sxs-lookup"><span data-stu-id="22c35-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="22c35-113">Diese Popup Umfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22c35-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="22c35-114">Wenn ein Benutzer in der Benachrichtigung auf **Feedback bereitstellen** klickt, wird die Umfrage angezeigt, damit Sie abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="22c35-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Screenshot der Umfrage Benachrichtigung und des Formulars in Microsoft Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="22c35-116">Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können</span><span class="sxs-lookup"><span data-stu-id="22c35-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="22c35-117">Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können, indem Sie **Feedback geben und angeben** , ob Sie die Umfrage erhalten.</span><span class="sxs-lookup"><span data-stu-id="22c35-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="22c35-118">Standardmäßig werden allen Benutzern in Ihrer Organisation automatisch die globale (org-Wide Standard)-Richtlinie zugewiesen, und das Feature " **Feedback senden** " und die Umfrage sind in der Richtlinie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="22c35-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="22c35-119">Die Ausnahme bilden Teams für Bildungseinrichtungen, in denen die Features für Lehrer und Behinderte für Schüler aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="22c35-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="22c35-120">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="22c35-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="22c35-121">Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="22c35-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="22c35-122">Angenommen, Sie möchten allen Benutzern in Ihrer Organisation das Senden **von Feedback über Feedback und empfangen** von Umfragen mit Ausnahme von neuen Mitarbeitern in der Schulung gestatten.</span><span class="sxs-lookup"><span data-stu-id="22c35-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="22c35-123">In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und neuen Mitarbeitern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="22c35-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="22c35-124">Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.</span><span class="sxs-lookup"><span data-stu-id="22c35-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="22c35-125">Sie können Feedback Richtlinien mithilfe von PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="22c35-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="22c35-126">Verwenden Sie das Cmdlet **New-CsTeamsFeedbackPolicy** , *das [hier gefunden](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)werden kann*, um eine benutzerdefinierte Richtlinie und das **Grant-CsTeamsFeedbackPolicy-** Cmdlet zu erstellen, um es einem oder mehreren Benutzern oder Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="22c35-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="22c35-127">Um die Features zu deaktivieren und zu aktivieren, setzen Sie die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="22c35-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="22c35-128">**Feedback geben**: Legen Sie den **userInitiatedMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können.</span><span class="sxs-lookup"><span data-stu-id="22c35-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="22c35-129">Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.</span><span class="sxs-lookup"><span data-stu-id="22c35-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="22c35-130">**Umfragen**: setzen Sie den **receiveSurveysMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können.</span><span class="sxs-lookup"><span data-stu-id="22c35-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="22c35-131">Damit Benutzer die Umfrage erhalten und Sie Sie deaktivieren können, setzen Sie den Parameter auf **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="22c35-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="22c35-132">In Teams können Benutzer dann zu **Einstellungen**  >  **Datenschutz** wechseln und auswählen, ob Sie an Umfragen teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="22c35-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="22c35-133">Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.</span><span class="sxs-lookup"><span data-stu-id="22c35-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="22c35-134">Erstellen einer benutzerdefinierten Feedback Richtlinie</span><span class="sxs-lookup"><span data-stu-id="22c35-134">Create a custom feedback policy</span></span>

<span data-ttu-id="22c35-135">In diesem Beispiel erstellen wir eine Feedback-Richtlinie namens "New Hire Feedback Policy" und deaktivieren die Möglichkeit, **Feedback durch Feedback** und die Umfrage zu geben.</span><span class="sxs-lookup"><span data-stu-id="22c35-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="22c35-136">Zuweisen einer benutzerdefinierten Feedback Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="22c35-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="22c35-137">In diesem Beispiel weisen wir einem Benutzer mit dem Namen Benutzer1 eine benutzerdefinierte Richtlinie mit dem Namen "New Hire Feedback Policy" zu.</span><span class="sxs-lookup"><span data-stu-id="22c35-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="22c35-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="22c35-138">Related topics</span></span>

- [<span data-ttu-id="22c35-139">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22c35-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="22c35-140">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22c35-140">Assign policies to your users in Teams</span></span>](assign-policies.md)