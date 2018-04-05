---
title: Installieren Sie die MSI-Datei von Microsoft-Teams
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Administratoren können die Teams MSI-Datei zu Massen Bereitstellen von Microsoft-Teams, um Benutzer oder Computer auszuwählen.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a2031a567b96db6987c6c9c035631f17fd3d03f
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="4e317-103">Installieren Sie die MSI-Datei von Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="4e317-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="4e317-104">Verwendung von System Center Configuration Manager oder Gruppenrichtlinien oder 3. Partei Verteilungsmechanismen für umfassenden Bereitstellung hat Microsoft MSI-Dateien ( [32-Bit-](http://aka.ms/teams32bitmsi) und [64-Bit](http://aka.ms/teams64bitmsi)) bereitgestellt, mit denen Administratoren für die Bereitstellung von Teams Massen können wählen Benutzer oder Computer.</span><span class="sxs-lookup"><span data-stu-id="4e317-104">To use System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or machines.</span></span> <span data-ttu-id="4e317-105">Diese Dateien können Administratoren Remotebereitstellung Teams, damit Benutzer keine die app Teams manuell herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4e317-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="4e317-106">Bei der Bereitstellung automatisch Teams werden Einführung für alle Benutzer, die auf diesem Computer anmelden.</span><span class="sxs-lookup"><span data-stu-id="4e317-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="4e317-107">Es wird empfohlen, dass Sie das Paket mit dem Computer bereitzustellen, sodass alle neuen Benutzer des Computers auch von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="4e317-107">We recommend that you deploy the package to the machine, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="4e317-108">Weitere Informationen zu SCCM finden Sie unter [Einführung zu System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="4e317-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="4e317-109">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="4e317-109">Deployment Procedure (Recommended)</span></span>
1. <span data-ttu-id="4e317-110">Rufen Sie das neueste-Paket</span><span class="sxs-lookup"><span data-stu-id="4e317-110">Retrieve the latest package</span></span>
2. <span data-ttu-id="4e317-111">Verwenden Sie die Standardwerte vorausgefüllt, durch die MSI-Datei</span><span class="sxs-lookup"><span data-stu-id="4e317-111">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="4e317-112">Bereitstellen Sie auf Computern, wenn möglich</span><span class="sxs-lookup"><span data-stu-id="4e317-112">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="4e317-113">Funktionsweise von Microsoft-Teams MSI-Paket</span><span class="sxs-lookup"><span data-stu-id="4e317-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="4e317-114">Die Teams MSI-Datei wird Program Files ein Installationsprogramm versehen.</span><span class="sxs-lookup"><span data-stu-id="4e317-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="4e317-115">Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie der Anwendung Teams im Anwendungsdaten-Ordner des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4e317-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="4e317-116">Wenn ein Benutzer bereits die Teams app im Ordner Anwendungsdaten installiert hat, wird der MSI-Installer den Prozess für diesen Benutzer übersprungen.</span><span class="sxs-lookup"><span data-stu-id="4e317-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="4e317-117">Verwenden Sie die MSI-Datei nicht zum Bereitstellen von Updates, der Client automatisch aktualisieren, wenn es erkennt, dass eine neue Version aus dem Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4e317-117">Do not use the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="4e317-118">Verwenden Sie erneut bereitstellen, um der neueste Version von Installer den Prozess der erneutes Bereitstellen von MSI-Datei weiter unten beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="4e317-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="4e317-119">Wenn Sie eine ältere Version von MSI-Paket bereitstellen, den Client wird automatisch nach Möglichkeit für den Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4e317-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="4e317-120">Wenn eine sehr alte Version bereitgestellt, ruft ab, wird die MSI-Datei eine Anwendung Aktualisierung auszulösen, bevor der Benutzer Teams nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="4e317-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="4e317-121">Wir empfohlen nicht, die Standardspeicherorte Installation zu ändern, wie dies den Update-Ablauf unterbrechen könnten.</span><span class="sxs-lookup"><span data-stu-id="4e317-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="4e317-122">Klicken Sie dann wird dem Benutzer Zugriff auf den Dienst schließlich blockieren.</span><span class="sxs-lookup"><span data-stu-id="4e317-122">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="4e317-123">Ziel-Computer-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e317-123">Target machine requirements</span></span>

1. <span data-ttu-id="4e317-124">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="4e317-124">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="4e317-125">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="4e317-125">Windows 7 or later</span></span>
2. <span data-ttu-id="4e317-126">3GB freier Festplattenspeicher für die einzelnen Benutzerprofilen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="4e317-126">3GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="4e317-127">Bereinigen nach oben und erneute Bereitstellung von Verfahren</span><span class="sxs-lookup"><span data-stu-id="4e317-127">Clean up and redeployment Procedure</span></span>
<span data-ttu-id="4e317-128">Wenn ein Benutzer aus ihrem Benutzerprofil Teams deinstalliert, wird der MSI-Installer nachverfolgen, dass der Benutzer hat die app Teams deinstalliert und Teams nicht mehr für dieses Benutzerprofil zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4e317-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="4e317-129">Um Teams für diesen Benutzer auf einem bestimmten Computer erneut bereitstellen, auf dem sie deinstalliert wurde, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4e317-129">To redeploy Teams for this user on a particular machine where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="4e317-130">Deinstallieren von Teams App für jede Benutzerprofil installiert</span><span class="sxs-lookup"><span data-stu-id="4e317-130">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="4e317-131">Nach dem Deinstallieren, Directory rekursiv unter %localappdata%\Microsoft\Teams\ löschen</span><span class="sxs-lookup"><span data-stu-id="4e317-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="4e317-132">Erneutes Bereitstellen des MSI-Pakets an den jeweiligen Computer</span><span class="sxs-lookup"><span data-stu-id="4e317-132">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="4e317-133">[Bereitstellung von Microsoft-Teams, bereinigen Sie](.\scripts\Powershell-script-teams-deployment-clean-up.md) Skript können Sie die Schritte 1 und 2 über SCCM erreichen.</span><span class="sxs-lookup"><span data-stu-id="4e317-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

