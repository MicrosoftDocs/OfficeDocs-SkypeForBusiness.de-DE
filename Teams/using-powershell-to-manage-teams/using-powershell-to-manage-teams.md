---
title: Verwenden von PowerShell zum Verwalten von Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Informationen Sie zum Windows PowerShell verwenden, um alle Features von Microsoft-Teams verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0daff64e5a0f6f876de4adb7b60d913fbcce78cb
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016077"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="fb1dd-103">Verwenden von PowerShell zum Verwalten von Teams</span><span class="sxs-lookup"><span data-stu-id="fb1dd-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="fb1dd-104">Features in Teams können mithilfe von PowerShell oder der Microsoft-Teams und Skype für Business Admin Center verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="fb1dd-105">! [Hinweis] Nicht alle Features in Teams können mithilfe des Teams Connector-Moduls verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="fb1dd-106">Sie müssen möglicherweise die Skype für Business Connector verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="fb1dd-107">Finden Sie unter [herunterladen und Installieren der Skype für Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="fb1dd-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="fb1dd-108">Schritt 1: erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fb1dd-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="fb1dd-109">Remoteverwaltung von Microsoft-Teams, mithilfe von PowerShell wird nur auf 64-Bit-Computern mit einem der folgenden Betriebssysteme unterstützt:</span><span class="sxs-lookup"><span data-stu-id="fb1dd-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="fb1dd-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="fb1dd-110">Windows 10</span></span>
- <span data-ttu-id="fb1dd-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="fb1dd-111">Windows 8.1</span></span>
- <span data-ttu-id="fb1dd-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="fb1dd-112">Windows 8</span></span> 
- <span data-ttu-id="fb1dd-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fb1dd-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="fb1dd-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fb1dd-114">Windows Server 2012</span></span>
- <span data-ttu-id="fb1dd-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="fb1dd-115">Windows Server 2008</span></span>
- <span data-ttu-id="fb1dd-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="fb1dd-116">Windows 7</span></span>
    
<span data-ttu-id="fb1dd-117">Zusätzlich zur ein unterstütztes Betriebssystem muss der Computer auch Folgendes ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fb1dd-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="fb1dd-118">PowerShell 3.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="fb1dd-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="fb1dd-119">Teams PowerShell Connector-Modul</span><span class="sxs-lookup"><span data-stu-id="fb1dd-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="fb1dd-120">Schritt 2: Install PowerShell 3.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="fb1dd-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="fb1dd-121">Verwenden Sie dieses Thema für die Hilfe</span><span class="sxs-lookup"><span data-stu-id="fb1dd-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="fb1dd-122">Schritt 3: Herunterladen Sie und installieren Sie des Teams Connector-Moduls</span><span class="sxs-lookup"><span data-stu-id="fb1dd-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="fb1dd-123">Verwenden Sie dieses Thema für die Hilfe</span><span class="sxs-lookup"><span data-stu-id="fb1dd-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="fb1dd-124">Nachfolgend finden Sie der Link zum Herunterladen von Isabella:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="fb1dd-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="fb1dd-125">Schritt 4: Verbinden Sie mithilfe des Teams Connector-Moduls</span><span class="sxs-lookup"><span data-stu-id="fb1dd-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="fb1dd-126">Verwenden Sie dieses Thema für die Hilfe</span><span class="sxs-lookup"><span data-stu-id="fb1dd-126">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="fb1dd-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fb1dd-127">Related topics</span></span>
- [<span data-ttu-id="fb1dd-128">Verwalten von Teams Funktionen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb1dd-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)