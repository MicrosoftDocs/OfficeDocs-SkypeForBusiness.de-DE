---
title: Installieren des StaffHub PowerShell-Moduls
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie das Microsoft StaffHub PowerShell-Modul installieren und eine Verbindung herstellen.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eab331c8d8b2213225ad8c7ee216f9f6ec2b51
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681881"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="603b3-103">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="603b3-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="603b3-104">Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="603b3-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="603b3-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="603b3-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="603b3-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="603b3-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="603b3-107">StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="603b3-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="603b3-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="603b3-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="603b3-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="603b3-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="603b3-110">Führen Sie die in diesem Artikel aufgeführten Schritte aus, um das Microsoft StaffHub PowerShell-Modul zu installieren und eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="603b3-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="603b3-111">Sie benötigen diese, um StaffHub mithilfe von PowerShell zu verwalten und ihre StaffHub-Teams in Microsoft Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="603b3-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="603b3-112">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="603b3-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="603b3-113">Laden Sie das [StaffHub PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)herunter.</span><span class="sxs-lookup"><span data-stu-id="603b3-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="603b3-114">Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator.</span><span class="sxs-lookup"><span data-stu-id="603b3-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="603b3-115">Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="603b3-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="603b3-116">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="603b3-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="603b3-117">Überprüfen Sie den Ordnerpfad in der Ausgabe, und stellen Sie sicher, dass alle Ordner im Pfad auf dem Computer vorhanden sind, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="603b3-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="603b3-118">Wenn Ordner fehlen, erstellen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="603b3-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="603b3-119">Führen Sie die folgenden Schritte aus, um die Installation des StaffHub PowerShell-Moduls zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="603b3-119">Run the following to allow for the installation of the StaffHub PowerShell module:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

6. <span data-ttu-id="603b3-120">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei Path der Pfad in der Ausgabe aus Schritt 2 ist.</span><span class="sxs-lookup"><span data-stu-id="603b3-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="603b3-121">Der Pfad sieht beispielsweise wie C:\Users\User1\Documents\WindowsPowerShell\Modules. aus.</span><span class="sxs-lookup"><span data-stu-id="603b3-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="603b3-122">Herstellen einer Verbindung mit dem Microsoft StaffHub PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="603b3-122">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="603b3-123">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="603b3-123">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="603b3-124">Wenn Sie dazu aufgefordert werden, melden Sie sich als globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="603b3-124">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="603b3-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="603b3-125">Related topics</span></span>

- [<span data-ttu-id="603b3-126">Microsoft StaffHub PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="603b3-126">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="603b3-127">Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams</span><span class="sxs-lookup"><span data-stu-id="603b3-127">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
