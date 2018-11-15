---
title: Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2afc1d0374333fdbb0bec9246d04224c6a82f032
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532702"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="c8ba0-103">Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8ba0-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="c8ba0-104">Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="c8ba0-105">Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="c8ba0-106">Wenn Sie Benutzern die Verwendung dieses Features innerhalb des Teams Clients zulassen möchten, müssen Sie diese Einstellung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="c8ba0-107">Einführung wird von Office 365-Abonnements in unserer Community-Cloud der Office 365 Government und Office 365 Deutschland Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="c8ba0-108">Aktivieren mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8ba0-108">Enable by using PowerShell</span></span>

<span data-ttu-id="c8ba0-109">Sie können das Feature zum Inline-Nachricht Übersetzung mithilfe der Gruppenrichtlinien Messaging aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="c8ba0-110">Aktivieren Sie die Richtlinie mit dem Cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c8ba0-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="c8ba0-111">Die Richtlinie hat ein paar Minuten anwenden.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="c8ba0-112">Benutzer müssen sich abmelden und wieder anmelden, um Teams.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="c8ba0-113">Aktivieren Sie mithilfe der Microsoft-Teams & Skype für Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="c8ba0-113">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="c8ba0-114">Wählen Sie in der **Microsoft-Teams & Skype für Business Admin Center**in der linken Leiste **Messaging Policies** , klicken Sie dann entweder eine neue Richtlinie erstellen oder Bearbeiten einer vorhandenen Richtlinie und die Option **Benutzer können Nachrichten übersetzen** \*\*festlegen, auf \*\*.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-114">In the **Microsoft Teams & Skype for Business Admin Center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="c8ba0-115">Übersetzung wird vom Dienst erfolgt, und an den Client Layoutelemente ohne Auswirkung auf die Inhalte in die Compliance-Datensätze erfasst übermittelt.</span><span class="sxs-lookup"><span data-stu-id="c8ba0-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="c8ba0-116">Weitere Informationen zur Übersetzung hierzu finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="c8ba0-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>