---
title: Wechseln von Skype for Business Online Connector zum PowerShell-Modul von Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie von Skype for Business Online Connector zum Teams PowerShell-Modul wechseln, um Teams zu verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469666"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="90662-103">Wechseln von Skype for Business Online Connector zum PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="90662-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="90662-104">Um von der Verwendung von Skype for Business Online Connector zum Teams PowerShell-Modul zum Verwalten von Teams zu wechseln, müssen Sie Ihre vorhandenen PowerShell-Skripts aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="90662-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="90662-105">In diesem Artikel wird die Vorgehensweise erläutert.</span><span class="sxs-lookup"><span data-stu-id="90662-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="90662-106">Installieren Sie das neueste PowerShell-Modul für Teams.</span><span class="sxs-lookup"><span data-stu-id="90662-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="90662-107">Eine schrittweise Anleitung finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="90662-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="90662-108">Deinstallieren Sie Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="90662-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="90662-109">Klicken Sie dazu in der Systemsteuerung auf **Programme und Funktionen**, wählen Sie **Skype for Business Online, Windows PowerShell-Modul**aus, und wählen Sie dann **deinstallieren**aus.</span><span class="sxs-lookup"><span data-stu-id="90662-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="90662-110">Ändern Sie in ihren PowerShell-Skripts den Modulnamen, auf den in ```Import-Module``` from ```SkypeOnlineConnector``` oder to verwiesen wird ```LyncOnlineConnector``` ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="90662-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="90662-111">Ändern Sie beispielsweise ```Import-Module -Name SkypeOnlineConnector``` in ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="90662-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="90662-112">Administratoren sollten die Verwendung von [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) weiterhin verwenden und die Sitzung importieren, bevor Sie die Skype for Business Online-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="90662-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="90662-113">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="90662-113">Related topics</span></span>

[<span data-ttu-id="90662-114">Installieren von Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="90662-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="90662-115">Verwalten von Teams mit PowerShell von Teams</span><span class="sxs-lookup"><span data-stu-id="90662-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="90662-116">Teams PowerShell-Anmerkungen zu dieser Version</span><span class="sxs-lookup"><span data-stu-id="90662-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="90662-117">Microsoft Teams-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="90662-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="90662-118">Skype for Business-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="90662-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
