---
title: Aktivieren der Übersetzung von Inline Nachrichten
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
description: Hier erfahren Sie, wie Sie die Inline Übersetzung in Microsoft Teams mit dem Microsoft Teams Admin Center oder PowerShell aktivieren.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395384"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="4a174-103">Deaktivieren der Inline Nachrichtenübersetzung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a174-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="4a174-104">Inline-Nachrichtenübersetzung ist eine Microsoft Teams-Funktion, mit der Benutzer Teams-Nachrichten in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen können, die in Ihren persönlichen Spracheinstellungen angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4a174-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="4a174-105">Inline-Nachrichtenübersetzung wird standardmäßig für Ihre Organisation bereit gesetzt.</span><span class="sxs-lookup"><span data-stu-id="4a174-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="4a174-106">Sie müssen keine Änderungen vornehmen, wenn Sie Benutzern erlauben möchten, diese Funktion innerhalb des Teams-Clients zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a174-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="4a174-107">Dieser Rollout ist von Office 365-Abonnements in unseren Office 365 Government Community Cloud-und Office 365 Germany-Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4a174-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="4a174-108">Verwenden von PowerShell zum Deaktivieren der Inline Nachrichtenübersetzung</span><span class="sxs-lookup"><span data-stu-id="4a174-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="4a174-109">Sie können die Nachrichten Richtlinie verwenden, um die Inline Nachrichtenübersetzung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a174-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="4a174-110">Deaktivieren Sie die Richtlinie mit dem Cmdlet " [Satz-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="4a174-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4a174-111">Die Anwendung der Richtlinie dauert einige Minuten.</span><span class="sxs-lookup"><span data-stu-id="4a174-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="4a174-112">Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.</span><span class="sxs-lookup"><span data-stu-id="4a174-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="4a174-113">Verwenden des Microsoft Teams admin Centers zum Deaktivieren der Inline Nachrichtenübersetzung</span><span class="sxs-lookup"><span data-stu-id="4a174-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="4a174-114">Wählen Sie im **Microsoft Teams Admin Center**im linken Navigationsbereich **Messaging Richtlinien** aus, erstellen Sie dann entweder eine neue Richtlinie, oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option **Nachrichten übersetzen** auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="4a174-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="4a174-115">Der Dienst führt die Übersetzung durch und übergibt ihn an den Client, ohne dass dies Auswirkungen auf die in den Konformitätsdaten Sätzen erfassten Inhalte hat.</span><span class="sxs-lookup"><span data-stu-id="4a174-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="4a174-116">Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="4a174-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
