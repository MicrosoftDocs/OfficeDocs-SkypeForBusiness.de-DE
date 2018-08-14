---
title: Aktualisieren Sie grundlegende PowerShell-Befehlen - Microsoft-Teams
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Stetig für das Upgrade auf Teams, falls noch nicht im Admin Center in Ihrem Mandanten eingeschaltet
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b65cd7a7b9ef91194b2045193a98672bfd25326
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001719"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="09418-103">Aktualisieren Ihre Benutzer von Skype für Business Online auf Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="09418-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="09418-104">Die Befehle, die in diesem Artikel beschriebenen werden im Rahmen der [Einfachen Upgrade](https://aka.ms/UpgradeBasic) Prüfliste verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="09418-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="09418-105">Die Migration technische Aspekte des Upgrades unterstützen könnte benachrichtigen der Benutzer, dass Skype für Unternehmen durchführen eines auf Teams Upgrades und anschließendes auf einen Modus **nur Teams verschieben** .</span><span class="sxs-lookup"><span data-stu-id="09418-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="09418-106">Diese Schritte können über einen Skype für Business remote Windows PowerShell-Sitzung oder über die Microsoft-Teams & Skype für Business-Verwaltungskonsole ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="09418-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams & Skype for Business Admin Center.</span></span> 
 
<span data-ttu-id="09418-107">Wir sind aktiv Rollout Upgrade Tools für [Microsoft-Teams & Skype für Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), und es sollte bei Ihrem Mandanten bald verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="09418-107">We're actively rolling out upgrade tooling in the [Microsoft Teams & Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="09418-108">Sobald sie verfügbar ist, finden Sie Informationen zur Migration von Benutzern in [Ihrer Koexistenz festlegen und Einstellungen zu aktualisieren](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="09418-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span> 
 
<span data-ttu-id="09418-109">Wenn Sie noch heute Upgrade bereit sind, können Sie die [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) -Befehle in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="09418-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span> 
 
 |<span data-ttu-id="09418-110">Grundlegende-Upgrade – Schritt #</span><span class="sxs-lookup"><span data-stu-id="09418-110">Upgrade Basic step #</span></span> | <span data-ttu-id="09418-111">Modus</span><span class="sxs-lookup"><span data-stu-id="09418-111">Mode</span></span> | <span data-ttu-id="09418-112">PowerShell-Befehl</span><span class="sxs-lookup"><span data-stu-id="09418-112">PowerShell command</span></span> |
|-------|--------|------|
| [<span data-ttu-id="09418-113">5</span><span class="sxs-lookup"><span data-stu-id="09418-113">5</span></span>](upgrade-basic.md#step-5) |<span data-ttu-id="09418-114">Inseln + benachrichtigen der Skype für Geschäftsbenutzer</span><span class="sxs-lookup"><span data-stu-id="09418-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="09418-115">(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit **Inseln** Modus (Standard) werden)</span><span class="sxs-lookup"><span data-stu-id="09418-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="09418-116">_(beispielsweise $SipAddress = "TestUser@contoso.com")_</span><span class="sxs-lookup"><span data-stu-id="09418-116">_(for example, $SipAddress='TestUser@contoso.com')_</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="09418-117">5</span><span class="sxs-lookup"><span data-stu-id="09418-117">5</span></span>](upgrade-basic.md#step-5)  | <span data-ttu-id="09418-118">Skype für Unternehmen nur + benachrichtigen der Skype für Geschäftsbenutzer</span><span class="sxs-lookup"><span data-stu-id="09418-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="09418-119">(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit im Modus **für Unternehmen nur Skype** sind)</span><span class="sxs-lookup"><span data-stu-id="09418-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="09418-120">7</span><span class="sxs-lookup"><span data-stu-id="09418-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="09418-121">Nur Teams</span><span class="sxs-lookup"><span data-stu-id="09418-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


