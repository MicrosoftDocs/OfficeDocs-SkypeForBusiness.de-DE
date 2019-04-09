---
title: Installieren Sie das Modul StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Installieren und mit dem Microsoft StaffHub PowerShell-Modul verbunden.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555133"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="73d01-103">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="73d01-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73d01-104">Die Übermittlung wirksamer wird 1 Oktober 2019, Microsoft StaffHub zurückgezogen werden.</span><span class="sxs-lookup"><span data-stu-id="73d01-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="73d01-105">Wir erstellen StaffHub-Funktionen in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="73d01-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="73d01-106">Heute, Teams enthält die Schichten app für zeitplanverwaltung und zusätzliche Funktionen, die über einen Zeitraum einführen werden.</span><span class="sxs-lookup"><span data-stu-id="73d01-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="73d01-107">StaffHub werden nicht für alle Benutzer auf 1 Oktober 2019 mehr.</span><span class="sxs-lookup"><span data-stu-id="73d01-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="73d01-108">Jeder Benutzer, der versucht, StaffHub öffnen wird eine Meldung mit der Weiterleitung zum Herunterladen von Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73d01-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="73d01-109">Weitere Informationen finden Sie unter [Microsoft StaffHub zurückgezogen werden](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="73d01-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="73d01-110">Verwenden Sie die Schritte in diesem Artikel zum Installieren und mit dem Microsoft StaffHub PowerShell-Modul verbunden.</span><span class="sxs-lookup"><span data-stu-id="73d01-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="73d01-111">Sie benötigen diese StaffHub mithilfe von PowerShell verwalten und Ihre StaffHub Teams, die Microsoft-Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="73d01-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="73d01-112">Installieren des Microsoft StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="73d01-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="73d01-113">Laden Sie das [StaffHub PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="73d01-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="73d01-114">Öffnen Sie Windows PowerShell 3.0 oder höher als Administrator an.</span><span class="sxs-lookup"><span data-stu-id="73d01-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="73d01-115">Zu diesem Zweck klicken Sie auf **Start**, geben Sie ein **Windows PowerShell**, mit der rechten Maustaste in **Windows PowerShell**, und wählen Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="73d01-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="73d01-116">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="73d01-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="73d01-117">Überprüfen Sie den Ordnerpfad in der Ausgabe, und stellen Sie sicher, dass alle Ordner im Pfad auf dem Computer vorhanden sind, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="73d01-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="73d01-118">Wenn Ordner nicht vorhanden sind, erstellen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="73d01-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="73d01-119">Führen Sie Folgendes ein, wobei &lt;Pfad&gt; ist der Pfad in der Ausgabe aus Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="73d01-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="73d01-120">Beispielsweise könnte der Pfad C:\Users\User1\Documents\WindowsPowerShell\Modules aussehen.</span><span class="sxs-lookup"><span data-stu-id="73d01-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="73d01-121">Verbinden Sie mit dem Microsoft StaffHub PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="73d01-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="73d01-122">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="73d01-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="73d01-123">Wenn Sie aufgefordert werden, melden Sie sich als ein globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="73d01-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="73d01-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="73d01-124">Related topics</span></span>

- [<span data-ttu-id="73d01-125">Referenz zu Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="73d01-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="73d01-126">Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams</span><span class="sxs-lookup"><span data-stu-id="73d01-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
