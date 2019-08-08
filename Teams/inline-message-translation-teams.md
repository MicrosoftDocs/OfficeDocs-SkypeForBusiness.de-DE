---
title: Aktivieren der Inline Nachrichtenübersetzung in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b6da80dda90c57a55a75c885b42bc08a824b613
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245349"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="e3eab-103">Aktivieren der Inline Nachrichtenübersetzung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e3eab-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="e3eab-104">Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e3eab-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="e3eab-105">Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e3eab-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="e3eab-106">Wenn Sie zulassen möchten, dass Benutzer dieses Feature innerhalb des Teams-Clients verwenden können, müssen Sie diese Einstellung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e3eab-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="e3eab-107">Dieser Rollout ist von Office 365-Abonnements in unseren Office 365 Government Community Cloud-und Office 365 Germany-Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e3eab-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="e3eab-108">Verwenden von PowerShell zum Aktivieren der Inline Nachrichtenübersetzung</span><span class="sxs-lookup"><span data-stu-id="e3eab-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="e3eab-109">Sie können die Nachrichten Richtlinie verwenden, um die Übersetzung der Inline Nachricht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e3eab-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="e3eab-110">Aktivieren Sie die Richtlinie mit dem Cmdlet " [Satz-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="e3eab-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="e3eab-111">Die Anwendung der Richtlinie dauert einige Minuten.</span><span class="sxs-lookup"><span data-stu-id="e3eab-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="e3eab-112">Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.</span><span class="sxs-lookup"><span data-stu-id="e3eab-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="e3eab-113">Verwenden des Microsoft Teams admin Centers zum Aktivieren der Inline Nachrichtenübersetzung</span><span class="sxs-lookup"><span data-stu-id="e3eab-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="e3eab-114">Wählen Sie im **Microsoft Teams Admin Center**im linken Navigationsbereich **Messaging Richtlinien** aus, und erstellen Sie dann entweder eine neue Richtlinie oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option \*\*\*\* **Benutzer können Nachrichten übersetzen** auf ein.</span><span class="sxs-lookup"><span data-stu-id="e3eab-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="e3eab-115">Der Dienst führt die Übersetzung durch und übergibt ihn an den Client, ohne dass dies Auswirkungen auf die in den Konformitätsdaten Sätzen erfassten Inhalte hat.</span><span class="sxs-lookup"><span data-stu-id="e3eab-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="e3eab-116">Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="e3eab-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>