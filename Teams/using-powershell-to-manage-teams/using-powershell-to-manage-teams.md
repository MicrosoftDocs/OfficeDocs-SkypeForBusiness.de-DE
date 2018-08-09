---
title: Verwenden von PowerShell zum Verwalten von Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
description: Informationen Sie zum Windows PowerShell verwenden, um alle Features von Microsoft-Teams verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a83d6281352ca4ef6a5a8d57d3a27692c7288d6
ms.sourcegitcommit: 41e325c5440e26cc39a3c8945020f597f8dfac96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "22213351"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="9ea9d-103">Verwenden von PowerShell zum Verwalten von Teams</span><span class="sxs-lookup"><span data-stu-id="9ea9d-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="9ea9d-104">Features in Teams können mithilfe von PowerShell oder der Microsoft-Teams und Skype für Business Admin Center verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="9ea9d-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="9ea9d-105">! [Hinweis] Nicht alle Features in Teams können mithilfe des Teams Connector-Moduls verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="9ea9d-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="9ea9d-106">Sie müssen möglicherweise die Skype für Business Connector verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ea9d-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="9ea9d-107">Finden Sie unter [herunterladen und Installieren der Skype für Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="9ea9d-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="9ea9d-108">Schritt 1: erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="9ea9d-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="9ea9d-109">Remoteverwaltung von Microsoft-Teams, mithilfe von PowerShell wird nur auf 64-Bit-Computern mit einem der folgenden Betriebssysteme unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9ea9d-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="9ea9d-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ea9d-110">Windows 10</span></span>
- <span data-ttu-id="9ea9d-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9ea9d-111">Windows 8.1</span></span>
- <span data-ttu-id="9ea9d-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="9ea9d-112">Windows 8</span></span> 
- <span data-ttu-id="9ea9d-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9ea9d-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="9ea9d-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9ea9d-114">Windows Server 2012</span></span>
- <span data-ttu-id="9ea9d-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="9ea9d-115">Windows Server 2008</span></span>
- <span data-ttu-id="9ea9d-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="9ea9d-116">Windows 7</span></span>
    
<span data-ttu-id="9ea9d-117">Zusätzlich zur ein unterstütztes Betriebssystem muss der Computer auch Folgendes ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9ea9d-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="9ea9d-118">PowerShell 3.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="9ea9d-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="9ea9d-119">Teams PowerShell Connector-Modul</span><span class="sxs-lookup"><span data-stu-id="9ea9d-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="9ea9d-120">Schritt 2: Install PowerShell 3.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="9ea9d-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="9ea9d-121">Verwenden Sie dieses Thema für die Hilfe</span><span class="sxs-lookup"><span data-stu-id="9ea9d-121">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="9ea9d-122">Schritt 3: Herunterladen Sie und installieren Sie des Teams Connector-Moduls</span><span class="sxs-lookup"><span data-stu-id="9ea9d-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="9ea9d-123">Verwenden Sie dieses Thema für die Hilfe</span><span class="sxs-lookup"><span data-stu-id="9ea9d-123">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="9ea9d-124">Nachfolgend finden Sie der Link zum Herunterladen von Isabella:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="9ea9d-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="9ea9d-125">Schritt 4: Verbinden Sie mithilfe des Teams Connector-Moduls</span><span class="sxs-lookup"><span data-stu-id="9ea9d-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="9ea9d-126">Verwenden Sie dieses Thema für die Hilfe</span><span class="sxs-lookup"><span data-stu-id="9ea9d-126">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="9ea9d-127">See Also</span><span class="sxs-lookup"><span data-stu-id="9ea9d-127">Related topics</span></span>
- [<span data-ttu-id="9ea9d-128">Verwalten von Teams Funktionen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ea9d-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)