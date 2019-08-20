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
description: Hier erfahren Sie, wie Sie das Microsoft StaffHub PowerShell-Modul installieren und eine Verbindung herstellen.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464665"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="530ff-103">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="530ff-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="530ff-104">Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="530ff-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="530ff-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="530ff-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="530ff-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="530ff-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="530ff-107">StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="530ff-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="530ff-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="530ff-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="530ff-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="530ff-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="530ff-110">Führen Sie die in diesem Artikel aufgeführten Schritte aus, um das Microsoft StaffHub PowerShell-Modul zu installieren und eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="530ff-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="530ff-111">Sie benötigen diese, um StaffHub mithilfe von PowerShell zu verwalten und ihre StaffHub-Teams in Microsoft Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="530ff-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="530ff-112">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="530ff-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="530ff-113">Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator. Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="530ff-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="530ff-114">Informationen zum Abrufen der neuesten Version von Windows PowerShell finden Sie unter [Installieren von Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="530ff-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="530ff-115">Führen Sie die folgenden Schritte aus, um die aktuelle stabile Version des StaffHub PowerShell-Moduls zu installieren:</span><span class="sxs-lookup"><span data-stu-id="530ff-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="530ff-116">Sie können diesen Befehl nur ausführen, wenn Sie die neueste Version installieren müssen, die möglicherweise mehr Instabilitäten als die aktuelle stabile Version aufweist:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="530ff-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="530ff-117">Wenn während der Installation der neuesten Version eine Fehlermeldung mit mehr Instabilitäten angezeigt wird, können Sie Folgendes ausführen:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="530ff-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="530ff-118">Möglicherweise wird die folgende Warnmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="530ff-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="530ff-119">Geben `Y` Sie ein `Enter`, und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="530ff-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="530ff-120">Beenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="530ff-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="530ff-121">Herstellen einer Verbindung mit dem Microsoft StaffHub PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="530ff-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="530ff-122">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="530ff-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="530ff-123">Wenn Sie dazu aufgefordert werden, melden Sie sich als globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="530ff-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="530ff-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="530ff-124">Related topics</span></span>

- [<span data-ttu-id="530ff-125">Microsoft StaffHub PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="530ff-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="530ff-126">Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams</span><span class="sxs-lookup"><span data-stu-id="530ff-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
