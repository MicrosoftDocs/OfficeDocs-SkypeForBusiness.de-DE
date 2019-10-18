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
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f6c6a2eca313b70640dbf61a87c6c5742ea318
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570735"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="2454e-103">Aktivieren der Inline Nachrichtenübersetzung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2454e-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="2454e-104">Bei der Inline Nachrichtenübersetzung handelt es sich um ein neues Microsoft Teams-Feature, mit dem Benutzer Teams-Nachrichten in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen können, die in Ihren persönlichen Spracheinstellungen für Office 365 angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2454e-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="2454e-105">Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2454e-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="2454e-106">Wenn Sie zulassen möchten, dass Benutzer dieses Feature innerhalb des Teams-Clients verwenden können, müssen Sie diese Einstellung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2454e-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="2454e-107">Dieser Rollout ist von Office 365-Abonnements in unseren Office 365 Government Community Cloud-und Office 365 Germany-Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2454e-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="2454e-108">Verwenden von PowerShell zum Aktivieren der Inline Nachrichtenübersetzung</span><span class="sxs-lookup"><span data-stu-id="2454e-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="2454e-109">Sie können die Nachrichten Richtlinie verwenden, um die Übersetzung der Inline Nachricht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2454e-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="2454e-110">Aktivieren Sie die Richtlinie mit dem Cmdlet " [Satz-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="2454e-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="2454e-111">Die Anwendung der Richtlinie dauert einige Minuten.</span><span class="sxs-lookup"><span data-stu-id="2454e-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="2454e-112">Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.</span><span class="sxs-lookup"><span data-stu-id="2454e-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="2454e-113">Verwenden des Microsoft Teams admin Centers zum Aktivieren der Inline Nachrichtenübersetzung</span><span class="sxs-lookup"><span data-stu-id="2454e-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="2454e-114">Wählen Sie im **Microsoft Teams Admin Center**im linken Navigationsbereich **Messaging Richtlinien** aus, und erstellen Sie dann entweder eine neue Richtlinie oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option **Benutzer können Nachrichten übersetzen** **auf ein.**</span><span class="sxs-lookup"><span data-stu-id="2454e-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="2454e-115">Der Dienst führt die Übersetzung durch und übergibt ihn an den Client, ohne dass dies Auswirkungen auf die in den Konformitätsdaten Sätzen erfassten Inhalte hat.</span><span class="sxs-lookup"><span data-stu-id="2454e-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="2454e-116">Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="2454e-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>