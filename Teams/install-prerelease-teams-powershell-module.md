---
title: Installieren der Pre-Release-Version des Teams PowerShell-Moduls
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Führen Sie die folgenden Schritte aus, um die Vorabversion des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu installieren.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321768"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="2f147-103">Installieren der Pre-Release-Version des Teams PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="2f147-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="2f147-104">In diesem Artikel wird beschrieben, wie Sie die neueste Vorabversion des Teams PowerShell-Moduls aus dem [PowerShell-Test Katalog](https://www.poshtestgallery.com/packages/MicrosoftTeams/)installieren.</span><span class="sxs-lookup"><span data-stu-id="2f147-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="2f147-105">Sie benötigen die Vorabversion des Teams PowerShell-Moduls in Szenarien, in denen Cmdlets für die Verwaltung eines Teams-Features in der allgemein verfügbaren Version des Moduls nicht unterstützt werden und nur in der Pre-Release-Version verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2f147-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="2f147-106">Führen Sie die folgenden Schritte aus, um die neueste Vorabversion des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2f147-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="2f147-107">Installieren Sie das Teams PowerShell-Modul nicht aus dem PowerShell-Test Katalog parallel mit einer Version des Moduls aus dem [öffentlichen PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="2f147-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="2f147-108">Führen Sie die folgenden Schritte aus, um das Team-PowerShell-Modul zunächst aus dem öffentlichen PowerShell-Katalog zu deinstallieren und dann die neueste Version des Moduls aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2f147-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="2f147-109">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="2f147-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="2f147-110">Starten Sie eine neue Instanz des Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="2f147-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="2f147-111">Führen Sie die folgenden Schritte aus, um das PowerShell-Modul von Teams aus dem öffentlichen PowerShell-Katalog zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="2f147-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="2f147-112">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="2f147-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="2f147-113">Starten Sie das Windows PowerShell-Modul erneut, und führen Sie dann die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="2f147-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="2f147-114">Führen Sie die folgenden Schritte aus, um das neueste Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren:</span><span class="sxs-lookup"><span data-stu-id="2f147-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="2f147-115">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="2f147-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="2f147-116">Aktualisieren auf die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog</span><span class="sxs-lookup"><span data-stu-id="2f147-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="2f147-117">Wenn Sie das Teams PowerShell-Modul bereits aus dem PowerShell-Test Katalog installiert haben, führen Sie die folgenden Schritte aus, um auf die neueste Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2f147-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="2f147-118">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="2f147-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="2f147-119">Starten Sie eine neue Instanz des Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="2f147-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="2f147-120">Führen Sie die folgenden Schritte aus, um die aktuell installierte Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="2f147-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="2f147-121">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="2f147-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="2f147-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2f147-122">Related topics</span></span>

- [<span data-ttu-id="2f147-123">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f147-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
