---
title: Standard-Upgrade-PowerShell | Microsoft Teams | Grant Upgrade-Interop-Richtlinie
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Notlösung für das Upgrade auf Teams, wenn das Admin Center nicht in Ihrem Mandanten leuchtet
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397cabcbba35c153d234bc4355d12e4eb44b5c57
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435089"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="05f4e-103">Aktualisieren Ihrer Benutzer von Skype for Business Online auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05f4e-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="05f4e-104">Die in diesem Artikel beschriebenen Befehle sind so konzipiert, dass Sie als Teil der [Upgrade Basic](https://aka.ms/UpgradeBasic) -Checkliste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05f4e-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="05f4e-105">Die technischen Migrationsaspekte Ihres Upgrades führen dazu, dass Ihre Nutzer benachrichtigt werden, dass Skype for Business ein Upgrade auf Teams durchführt und diese dann in den Modus **nur für Teams** verschiebt.</span><span class="sxs-lookup"><span data-stu-id="05f4e-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="05f4e-106">Diese Schritte können über eine Skype for Business-Remote-Windows PowerShell-Sitzung oder über das Microsoft Teams Admin Center durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="05f4e-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="05f4e-107">Wir arbeiten aktiv am Upgrade-Tool im [Microsoft Teams Admin Center](manage-teams-skypeforbusiness-admin-center.md)und sollten in Kürze für Ihren Mandanten verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="05f4e-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="05f4e-108">Sobald es verfügbar ist, finden Sie Informationen zum Migrieren Ihrer Benutzer beim [Festlegen ihrer Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="05f4e-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="05f4e-109">Wenn Sie zum heutigen Upgrade bereit sind, können Sie die in der folgenden Tabelle aufgelisteten [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) -Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="05f4e-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="05f4e-110">Upgrade grundlegender Schritt #</span><span class="sxs-lookup"><span data-stu-id="05f4e-110">Upgrade Basic step #</span></span> | <span data-ttu-id="05f4e-111">Modus</span><span class="sxs-lookup"><span data-stu-id="05f4e-111">Mode</span></span> | <span data-ttu-id="05f4e-112">PowerShell-Befehl</span><span class="sxs-lookup"><span data-stu-id="05f4e-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="05f4e-113">5</span><span class="sxs-lookup"><span data-stu-id="05f4e-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="05f4e-114">Inseln + Benachrichtigung des Skype for Business-Benutzers</span><span class="sxs-lookup"><span data-stu-id="05f4e-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="05f4e-115">(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im Modus " **Inseln** " (Standard) befinden)</span><span class="sxs-lookup"><span data-stu-id="05f4e-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="05f4e-116">*(Beispiel: $SipAddress = "testuser@contoso.com")*</span><span class="sxs-lookup"><span data-stu-id="05f4e-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="05f4e-117">5</span><span class="sxs-lookup"><span data-stu-id="05f4e-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="05f4e-118">Nur Skype for Business + Benachrichtigung des Skype for Business-Benutzers</span><span class="sxs-lookup"><span data-stu-id="05f4e-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="05f4e-119">(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit **nur im Skype for Business** -Modus befinden)</span><span class="sxs-lookup"><span data-stu-id="05f4e-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="05f4e-120">7</span><span class="sxs-lookup"><span data-stu-id="05f4e-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="05f4e-121">Nur für Teams</span><span class="sxs-lookup"><span data-stu-id="05f4e-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
