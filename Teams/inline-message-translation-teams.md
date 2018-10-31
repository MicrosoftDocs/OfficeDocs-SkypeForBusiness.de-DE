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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851568"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="d9bf8-103">Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d9bf8-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="d9bf8-104">Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="d9bf8-105">Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="d9bf8-106">Wenn Sie Benutzern die Verwendung der Funktion im Microsoft Teams-Client ermöglichen möchten, müssen Sie diese Einstellung mithilfe von PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="d9bf8-107">Zurzeit ist diese Option im Admin Center für Microsoft Teams und Skype for Business nicht verfügbar, sie wird aber bald hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="d9bf8-108">Dieser Rollout ist von Office 365-Abonnements in Office 365 Government Community Cloud- und Office 365 Deutschland-Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="d9bf8-109">Aktivieren mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9bf8-109">Enable by using PowerShell</span></span>

<span data-ttu-id="d9bf8-110">Sie können die Funktion für die Inlineübersetzung von Nachrichten mithilfe der Nachrichtenrichtlinie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="d9bf8-111">Aktivieren Sie die Richtlinie mit dem [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="d9bf8-112">Die Anwendung der Richtlinie dauert ein paar Minuten.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="d9bf8-113">Die Benutzer müssen sich möglicherweise bei Microsoft Teams abmelden und dann wieder anmelden.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="d9bf8-114">Aktivieren Sie mithilfe der Microsoft-Teams & Skype für Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="d9bf8-114">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="d9bf8-115">So aktivieren Sie das Inline-Nachricht Übersetzung Feature mithilfe der Microsoft-Teams & Skype für Business Admin Center die Option wird in Kürze bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-115">The option to turn on the inline message translation feature using the Microsoft Teams & Skype for Business Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="d9bf8-116">Die Übersetzung findet ausschließlich auf dem Client statt und hat keine Auswirkungen auf in den Compliance-Datensätzen erfasste Inhalte.</span><span class="sxs-lookup"><span data-stu-id="d9bf8-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="d9bf8-117">Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="d9bf8-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>