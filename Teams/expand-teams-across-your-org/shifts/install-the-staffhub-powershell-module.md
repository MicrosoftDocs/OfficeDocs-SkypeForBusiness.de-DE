---
title: Installieren des StaffHub PowerShell-Moduls
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Vorabversion des Microsoft StaffHub PowerShell-Moduls installieren und eine Verbindung herstellen.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142034"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cdf3c-103">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="cdf3c-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdf3c-104">Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="cdf3c-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="cdf3c-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="cdf3c-107">StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="cdf3c-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="cdf3c-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="cdf3c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="cdf3c-110">Führen Sie die in diesem Artikel aufgeführten Schritte aus, um die Vorabversion des Microsoft StaffHub PowerShell-Moduls zu installieren und eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="cdf3c-111">Sie benötigen diese, um [Ihre StaffHub-Teams in Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cdf3c-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cdf3c-112">Installieren der Vorabversion des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="cdf3c-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="cdf3c-113">Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator. Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cdf3c-114">Informationen zum Abrufen der neuesten Version von Windows PowerShell finden Sie unter [Installieren von Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cdf3c-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="cdf3c-115">Führen Sie die folgenden Schritte aus, um die Vorabversion des StaffHub PowerShell-Moduls zu installieren:</span><span class="sxs-lookup"><span data-stu-id="cdf3c-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="cdf3c-116">Möglicherweise wird die folgende Warnmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cdf3c-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="cdf3c-117">Geben `Y`Sie ein, und `Enter`klicken Sie dann auf.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="cdf3c-118">Beenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cdf3c-119">Herstellen einer Verbindung mit dem Microsoft StaffHub PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="cdf3c-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="cdf3c-120">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="cdf3c-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="cdf3c-121">Wenn Sie dazu aufgefordert werden, melden Sie sich als globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="cdf3c-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cdf3c-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cdf3c-122">Related topics</span></span>

- [<span data-ttu-id="cdf3c-123">Microsoft StaffHub PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="cdf3c-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="cdf3c-124">Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams</span><span class="sxs-lookup"><span data-stu-id="cdf3c-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
