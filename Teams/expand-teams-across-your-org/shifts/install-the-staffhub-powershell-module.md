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
description: Hier erfahren Sie, wie Sie das Microsoft StaffHub PowerShell-Modul installieren und eine Verbindung herstellen und ihre StaffHub-Teams in Microsoft Teams verschieben.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52b4e0c41520468bc1e05734644d1beb05fed5be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905727"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="516fb-103">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="516fb-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="516fb-104">Am 31. Dezember 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="516fb-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="516fb-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="516fb-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="516fb-106">Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="516fb-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="516fb-107">StaffHub wird am 31. Dezember 2019 für alle Benutzer eingestellt.</span><span class="sxs-lookup"><span data-stu-id="516fb-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="516fb-108">Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet.</span><span class="sxs-lookup"><span data-stu-id="516fb-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="516fb-109">Weitere Informationen finden Sie unter [Microsoft StaffHub wird eingestellt](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="516fb-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="516fb-110">Führen Sie die in diesem Artikel aufgeführten Schritte aus, um das Microsoft StaffHub PowerShell-Modul zu installieren und eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="516fb-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="516fb-111">Sie benötigen diese, um [Ihre StaffHub-Teams in Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="516fb-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="516fb-112">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="516fb-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="516fb-113">Laden Sie das [StaffHub PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftStaffHub)herunter.</span><span class="sxs-lookup"><span data-stu-id="516fb-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="516fb-114">Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator. Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="516fb-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="516fb-115">Informationen zum Abrufen der neuesten Version von Windows PowerShell finden Sie unter [Installieren von Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="516fb-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="516fb-116">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="516fb-116">Run the following:</span></span>

    ```PowerShell
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="516fb-117">Überprüfen Sie den Ordnerpfad in der Ausgabe, und stellen Sie sicher, dass alle Ordner im Pfad auf dem Computer vorhanden sind, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="516fb-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="516fb-118">Wenn Ordner fehlen, erstellen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="516fb-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="516fb-119">Führen Sie die folgenden Schritte aus, um die Installation des StaffHub PowerShell-Moduls zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="516fb-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="516fb-120">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei Path der Pfad in der Ausgabe aus Schritt 3 ist.</span><span class="sxs-lookup"><span data-stu-id="516fb-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="516fb-121">Der Pfad sieht beispielsweise wie C:\Users\User1\Documents\WindowsPowerShell\Modules. aus.</span><span class="sxs-lookup"><span data-stu-id="516fb-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="516fb-122">Stellen Sie sicher, dass Sie jeden Befehl separat ausführen.</span><span class="sxs-lookup"><span data-stu-id="516fb-122">Be sure to run each command separately.</span></span>

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="516fb-123">Beenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="516fb-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="516fb-124">Öffnen Sie Windows PowerShell 3,0 oder höher als globaler Administrator, und führen Sie dann die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="516fb-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="516fb-125">Herstellen einer Verbindung mit dem Microsoft StaffHub PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="516fb-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="516fb-126">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="516fb-126">Run the following:</span></span>

    ```PowerShell
    Connect-StaffHub
    ```

2. <span data-ttu-id="516fb-127">Wenn Sie dazu aufgefordert werden, melden Sie sich als globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="516fb-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="516fb-128">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="516fb-128">Related topics</span></span>

- [<span data-ttu-id="516fb-129">Microsoft StaffHub PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="516fb-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="516fb-130">Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams</span><span class="sxs-lookup"><span data-stu-id="516fb-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
