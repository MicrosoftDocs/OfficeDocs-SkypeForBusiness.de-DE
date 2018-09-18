---
title: Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882908"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="cd6f5-103">Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6f5-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="cd6f5-104">Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="cd6f5-105">Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="cd6f5-106">Wenn Sie Benutzern die Verwendung der Funktion im Microsoft Teams-Client ermöglichen möchten, müssen Sie diese Einstellung mithilfe von PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="cd6f5-107">Zurzeit ist diese Option im Admin Center für Microsoft Teams und Skype for Business nicht verfügbar, sie wird aber bald hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="cd6f5-108">Dieser Rollout ist von Office 365-Abonnements in Office 365 Government Community Cloud- und Office 365 Deutschland-Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="cd6f5-109">Aktivieren mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd6f5-109">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="cd6f5-110">Sie können die Funktion für die Inlineübersetzung von Nachrichten mithilfe der Nachrichtenrichtlinie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="cd6f5-111">Aktivieren Sie die Richtlinie mit dem [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="cd6f5-112">Die Anwendung der Richtlinie dauert ein paar Minuten.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="cd6f5-113">Die Benutzer müssen sich möglicherweise bei Microsoft Teams abmelden und dann wieder anmelden.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="cd6f5-114">Aktivieren über das Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="cd6f5-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="cd6f5-115">Die Option zum Aktivieren der Funktion für die Inlineübersetzung von Nachrichten über das Teams Admin Center wird in Kürze hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="cd6f5-116">Die Übersetzung findet ausschließlich auf dem Client statt und hat keine Auswirkungen auf in den Compliance-Datensätzen erfasste Inhalte.</span><span class="sxs-lookup"><span data-stu-id="cd6f5-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="cd6f5-117">Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="cd6f5-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>