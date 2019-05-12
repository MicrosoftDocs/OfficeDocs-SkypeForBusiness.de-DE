---
title: Grundlegende Upgrade PowerShell | Microsoft-Teams | Interop-Richtlinie GRANT-Upgrade
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Stetig für das Upgrade auf Teams, falls noch nicht im Admin Center in Ihrem Mandanten eingeschaltet
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 281938456c4fca695b2254e7cf6e50078bb32c80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920432"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="82cf7-103">Aktualisieren Ihre Benutzer von Skype für Business Online auf Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="82cf7-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="82cf7-104">Die Befehle, die in diesem Artikel beschriebenen werden im Rahmen der [Einfachen Upgrade](https://aka.ms/UpgradeBasic) Prüfliste verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="82cf7-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="82cf7-105">Die Migration technische Aspekte des Upgrades unterstützen könnte benachrichtigen der Benutzer, dass Skype für Unternehmen durchführen eines auf Teams Upgrades und anschließendes auf einen Modus **nur Teams verschieben** .</span><span class="sxs-lookup"><span data-stu-id="82cf7-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="82cf7-106">Diese Schritte können über einen Skype für Business remote Windows PowerShell-Sitzung oder über das Microsoft-Teams, Administrationscenter ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82cf7-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="82cf7-107">Wir sind in der [Microsoft-Teams, Administrationscenter](manage-teams-skypeforbusiness-admin-center.md)tooling Upgrade aktiv Rollout, und es sollte bei Ihrem Mandanten bald verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="82cf7-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="82cf7-108">Sobald sie verfügbar ist, finden Sie Informationen zur Migration von Benutzern in [Ihrer Koexistenz festlegen und Einstellungen zu aktualisieren](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="82cf7-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="82cf7-109">Wenn Sie noch heute Upgrade bereit sind, können Sie die [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) -Befehle in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="82cf7-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="82cf7-110">Grundlegende-Upgrade – Schritt #</span><span class="sxs-lookup"><span data-stu-id="82cf7-110">Upgrade Basic step #</span></span> | <span data-ttu-id="82cf7-111">Modus</span><span class="sxs-lookup"><span data-stu-id="82cf7-111">Mode</span></span> | <span data-ttu-id="82cf7-112">PowerShell-Befehl</span><span class="sxs-lookup"><span data-stu-id="82cf7-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="82cf7-113">5</span><span class="sxs-lookup"><span data-stu-id="82cf7-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="82cf7-114">Inseln + benachrichtigen der Skype für Geschäftsbenutzer</span><span class="sxs-lookup"><span data-stu-id="82cf7-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="82cf7-115">(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit **Inseln** Modus (Standard) werden)</span><span class="sxs-lookup"><span data-stu-id="82cf7-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="82cf7-116">*(beispielsweise $SipAddress = "TestUser@contoso.com")*</span><span class="sxs-lookup"><span data-stu-id="82cf7-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="82cf7-117">5</span><span class="sxs-lookup"><span data-stu-id="82cf7-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="82cf7-118">Skype für Unternehmen nur + benachrichtigen der Skype für Geschäftsbenutzer</span><span class="sxs-lookup"><span data-stu-id="82cf7-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="82cf7-119">(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit im Modus **für Unternehmen nur Skype** sind)</span><span class="sxs-lookup"><span data-stu-id="82cf7-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="82cf7-120">7</span><span class="sxs-lookup"><span data-stu-id="82cf7-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="82cf7-121">Nur Teams</span><span class="sxs-lookup"><span data-stu-id="82cf7-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
