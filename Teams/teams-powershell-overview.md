---
title: Übersicht über PowerShell für Microsoft Teams
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814364"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="7937c-103">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7937c-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="7937c-104">Microsoft Teams PowerShell ist eine Gruppe von Cmdlets zum direkten Verwalten von Teams über die PowerShell-Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="7937c-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="7937c-105">Das in .NET Standard geschriebene Teams PowerShell funktioniert auf allen Plattformen, einschließlich Azure Shell, auf PowerShell 5,1 unter Windows, PowerShell 6. x und höher.</span><span class="sxs-lookup"><span data-stu-id="7937c-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="7937c-106">Bevor Sie mit der Verwendung von PowerShell beginnen können, müssen Sie Sie [Installieren](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="7937c-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="7937c-107">Es gibt bekannte Probleme mit PowerShell 7 und PowerShell von Teams.</span><span class="sxs-lookup"><span data-stu-id="7937c-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="7937c-108">Es wird empfohlen, PowerShell 5,1 zu verwenden, bis die Probleme behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="7937c-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="7937c-109">Mitteilungen</span><span class="sxs-lookup"><span data-stu-id="7937c-109">Releases</span></span>


<span data-ttu-id="7937c-110">Teams PowerShell steht im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) in zwei Veröffentlichungstypen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7937c-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="7937c-111">**Allgemeine Verfügbarkeit (GA)**: produktionsfähige Cmdlets, monatlich aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7937c-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="7937c-112">**Öffentliche Vorschau**: früher Zugriff auf Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7937c-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="7937c-113">Kann häufiger als GA aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7937c-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="7937c-114">Detaillierte Informationen zu den Funktionserweiterungen und Verbesserungen für beide Versionen finden Sie in den Versionshinweisen zu [Teams PowerShell](teams-powershell-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="7937c-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="7937c-115">Verwalten von Teams mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="7937c-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="7937c-116">Sie verwenden Teams PowerShell-Module, um Teams vollständig zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="7937c-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="7937c-117">[Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/): Das PowerShell-Modul von Teams enthält Cmdlets für die Verwaltung von Teams, Chats und Kanälen.</span><span class="sxs-lookup"><span data-stu-id="7937c-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="7937c-118">Die neueste [PowerShell-Version von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.</span><span class="sxs-lookup"><span data-stu-id="7937c-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="7937c-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): der Skype for Business PowerShell-Connector ist nun Teil des Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="7937c-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="7937c-120">Eine vollständige Anleitung zum Verwalten von Teams, die diese Module verwenden, finden Sie unter Verwalten von Teams [mit PowerShell für Teams](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7937c-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="7937c-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7937c-121">Related topics</span></span>

[<span data-ttu-id="7937c-122">Installieren von Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="7937c-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="7937c-123">Verwalten von Teams mit PowerShell von Teams</span><span class="sxs-lookup"><span data-stu-id="7937c-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="7937c-124">Teams PowerShell-Anmerkungen zu dieser Version</span><span class="sxs-lookup"><span data-stu-id="7937c-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="7937c-125">Microsoft Teams-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="7937c-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="7937c-126">Skype for Business-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="7937c-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="7937c-127">Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams</span><span class="sxs-lookup"><span data-stu-id="7937c-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
