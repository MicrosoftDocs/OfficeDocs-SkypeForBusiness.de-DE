---
title: Verwenden von Inline-Nachricht Übersetzung in Microsoft-Teams
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
description: Informationen Sie zum Verwenden von Inline-Übersetzung in Microsoft-Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882908"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="41ef6-103">Verwenden von Inline-Nachricht Übersetzung in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="41ef6-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="41ef6-104">Inline-Nachricht Übersetzung ist ein neues Microsoft-Teams-Feature, mit dem Benutzer Teams Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , die durch ihre persönliche Sprachoptionen für Office 365 angegebenen übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="41ef6-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="41ef6-105">Inline-Nachricht Übersetzung ist standardmäßig für Ihre Organisation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="41ef6-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="41ef6-106">Wenn Sie Benutzern die Verwendung dieses Features innerhalb des Teams Clients zulassen möchten, müssen Sie diese Einstellung aktivieren mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41ef6-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="41ef6-107">Derzeit, diese Option ist nicht verfügbar in den Microsoft-Teams und Skype für Business Admin Center, werden jedoch bald.</span><span class="sxs-lookup"><span data-stu-id="41ef6-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="41ef6-108">Einführung wird von Office 365-Abonnements in unserer Community-Cloud der Office 365 Government und Office 365 Deutschland Umgebungen ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="41ef6-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="41ef6-109">Aktivieren mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="41ef6-109">Enable by using PowerShell</span></span>

<span data-ttu-id="41ef6-110">Sie können das Feature zum Inline-Nachricht Übersetzung mithilfe der Gruppenrichtlinien Messaging aktivieren.</span><span class="sxs-lookup"><span data-stu-id="41ef6-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="41ef6-111">Aktivieren Sie die Richtlinie mit dem Cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="41ef6-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="41ef6-112">Die Richtlinie hat ein paar Minuten anwenden.</span><span class="sxs-lookup"><span data-stu-id="41ef6-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="41ef6-113">Benutzer müssen sich abmelden und wieder anmelden, um Teams.</span><span class="sxs-lookup"><span data-stu-id="41ef6-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="41ef6-114">Aktivieren Sie mithilfe der Verwaltungskonsole Teams</span><span class="sxs-lookup"><span data-stu-id="41ef6-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="41ef6-115">Die Option aktivieren Sie das Feature zum Inline-Nachricht Übersetzung mithilfe der Verwaltungskonsole Teams wird in Kürze bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="41ef6-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="41ef6-116">Übersetzung ist ausschließlich mithilfe der clientseitigen und hat keine Auswirkung auf die Inhalte in die Compliance-Datensätze erfasst.</span><span class="sxs-lookup"><span data-stu-id="41ef6-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="41ef6-117">Weitere Informationen zur Übersetzung hierzu finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="41ef6-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>