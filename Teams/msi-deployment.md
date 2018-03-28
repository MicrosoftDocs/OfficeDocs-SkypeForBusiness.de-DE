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
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="22c47-103">Installieren Sie die MSI-Datei von Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="22c47-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="22c47-104">Um die Nutzung von System Center Configuration Manager oder Gruppenrichtlinien oder 3. Partei Verteilungsmechanismen für umfassenden Bereitstellung hat Microsoft MSI-Dateien ( [32-Bit-](http://aka.ms/teams32bitmsi) und [64-Bit](http://aka.ms/teams64bitmsi)) für Administratoren, die während der Bereitstellung von Massen nutzen bereitgestellt. Microsoft-Teams, Benutzer oder Computer auswählen.</span><span class="sxs-lookup"><span data-stu-id="22c47-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="22c47-105">Diese Dateien können Administratoren Remotebereitstellung Teams, damit Benutzer keine die app Teams manuell herunterladen.</span><span class="sxs-lookup"><span data-stu-id="22c47-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="22c47-106">Bei der Bereitstellung automatisch Teams werden Einführung für alle Benutzer, die auf diesem Computer anmelden.</span><span class="sxs-lookup"><span data-stu-id="22c47-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="22c47-107">Es wird empfohlen, dass Sie das Paket mit dem Computer bereitzustellen, sodass alle neuen Benutzer mit den Computern auch von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="22c47-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="22c47-108">Weitere Informationen zu SCCM finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="22c47-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="22c47-109">Einführung zu System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="22c47-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="22c47-110">Bereitstellungsverfahren (Empfehlungen)</span><span class="sxs-lookup"><span data-stu-id="22c47-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="22c47-111">Rufen Sie das neueste-Paket</span><span class="sxs-lookup"><span data-stu-id="22c47-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="22c47-112">Verwenden Sie die Standardwerte vorausgefüllt, durch die MSI-Datei</span><span class="sxs-lookup"><span data-stu-id="22c47-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="22c47-113">Bereitstellen Sie auf Computern, wenn möglich</span><span class="sxs-lookup"><span data-stu-id="22c47-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="22c47-114">Funktionsweise von Microsoft-Teams MSI-Paket</span><span class="sxs-lookup"><span data-stu-id="22c47-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="22c47-115">Die Teams MSI-Datei wird Program Files ein Installationsprogramm versehen.</span><span class="sxs-lookup"><span data-stu-id="22c47-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="22c47-116">Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie des Teams Anwendung im Anwendungsdaten-Ordner des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="22c47-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="22c47-117">Wenn ein Benutzer bereits die Teams app im Ordner Anwendungsdaten installiert hat, wird der MSI-Installer den Prozess für diesen Benutzer übersprungen.</span><span class="sxs-lookup"><span data-stu-id="22c47-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="22c47-118">Nutzen Sie die MSI-Datei zum Bereitstellen von Updates nicht, der Client automatisch aktualisieren, wenn es erkennt, dass eine neue Version aus dem Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="22c47-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="22c47-119">Verwenden Sie erneut bereitstellen, um der neueste Version von Installer den Prozess der erneutes Bereitstellen von MSI-Datei weiter unten beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="22c47-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="22c47-120">Wenn Sie eine ältere Version von MSI-Paket bereitstellen, den Client wird automatisch nach Möglichkeit für den Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="22c47-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="22c47-121">Wenn eine sehr alte Version bereitgestellt, ruft ab, wird die MSI-Datei eine Anwendung Aktualisierung auszulösen, bevor der Benutzer Teams nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="22c47-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="22c47-122">Es wird nicht empfohlen, dass Sie alle Installationsverzeichnisse ändern, wie dies den Update-Ablauf unterbrechen könnten.</span><span class="sxs-lookup"><span data-stu-id="22c47-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="22c47-123">Klicken Sie dann wird dem Benutzer Zugriff auf den Dienst schließlich blockieren.</span><span class="sxs-lookup"><span data-stu-id="22c47-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="22c47-124">Anforderungen an die Ziel-Computer:</span><span class="sxs-lookup"><span data-stu-id="22c47-124">Target machine requirements:</span></span>

1. <span data-ttu-id="22c47-125">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="22c47-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="22c47-126">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="22c47-126">Windows 7 or later</span></span>
2. <span data-ttu-id="22c47-127">32GB Speicherplatz für jedes Benutzerprofil (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="22c47-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="22c47-128">Bereinigen Up\redeployment Verfahren</span><span class="sxs-lookup"><span data-stu-id="22c47-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="22c47-129">Wenn ein Benutzer von Teams für ihre Benutzerprofil deinstalliert wird, wird der MSI-Installer nachverfolgen, dass der Benutzer hat die app Teams deinstalliert und Teams nicht mehr für dieses Benutzerprofil zu installieren.</span><span class="sxs-lookup"><span data-stu-id="22c47-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="22c47-130">Wenn Sie Teams erneut bereitstellen für diesen Benutzer auf einem bestimmten Computer, bei denen es war, Sie deinstalliert müssen:</span><span class="sxs-lookup"><span data-stu-id="22c47-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="22c47-131">Deinstallieren von Teams App für jede Benutzerprofil installiert</span><span class="sxs-lookup"><span data-stu-id="22c47-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="22c47-132">Nach dem Deinstallieren, Directory rekursiv unter %localappdata%\Microsoft\Teams\ löschen</span><span class="sxs-lookup"><span data-stu-id="22c47-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="22c47-133">Erneutes Bereitstellen des MSI-Pakets an den jeweiligen Computer</span><span class="sxs-lookup"><span data-stu-id="22c47-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="22c47-134">Sie können die [Bereitstellung von Microsoft-Teams, bereinigen Sie](.\scripts\Powershell-script-teams-deployment-clean-up.md) Skript zum Ausführen dieser Schritte 1 und 2 über SCCM nutzen.</span><span class="sxs-lookup"><span data-stu-id="22c47-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

