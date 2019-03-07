---
title: Installieren von Microsoft Teams mithilfe eines MSI-Pakets (mit SCCM)
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Administratoren können das Microsoft Teams-MSI-Paket für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5ffceef19e91f5d3e694db7655d23efb67498ae
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464348"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="b278d-103">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="b278d-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="b278d-104">Sehen Sie sich die folgenden Sitzung auf Informationen zu den Vorteilen von der Windows-Desktop-Client, wie es geplant und wie diese bereitgestellt: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="b278d-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="b278d-105">Verwendung von System Center Configuration Manager oder Gruppenrichtlinien oder Drittanbieter-Verteilungsmechanismen für umfassenden Bereitstellung hat Microsoft MSI-Dateien ( [32-Bit-](https://aka.ms/teams32bitmsi) und [64-Bit](https://aka.ms/teams64bitmsi)) bereitgestellt, mit denen Administratoren für die Bereitstellung von Teams Massen können wählen Benutzer oder Computer.</span><span class="sxs-lookup"><span data-stu-id="b278d-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="b278d-106">Diese Dateien können Administratoren Remotebereitstellung Teams, damit Benutzer keine die app Teams manuell herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b278d-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="b278d-107">Bei der Bereitstellung automatisch Teams werden Einführung für alle Benutzer, die auf diesem Computer anmelden.</span><span class="sxs-lookup"><span data-stu-id="b278d-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="b278d-108">(Sie können Automatisches Starten nach der Installation der app deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b278d-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="b278d-109">[Finden Sie weiter unten](#disable-auto-lanuch-for-the-msi-installer).) Es wird empfohlen, dass Sie das Paket auf dem Computer bereitzustellen, sodass alle neuen Benutzer des Computers auch von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="b278d-109">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="b278d-110">Weitere Informationen zu SCCM finden Sie unter [Einführung zu System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="b278d-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="b278d-111">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b278d-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="b278d-112">Rufen Sie das neueste-Paket.</span><span class="sxs-lookup"><span data-stu-id="b278d-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="b278d-113">Verwenden Sie die Standardeinstellungen, durch die MSI-Datei vorausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b278d-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="b278d-114">Bereitstellen Sie auf Computern, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="b278d-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="b278d-115">Funktionsweise von Microsoft-Teams MSI-Paket</span><span class="sxs-lookup"><span data-stu-id="b278d-115">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="b278d-116">Die Teams MSI-Datei wird Program Files ein Installationsprogramm versehen.</span><span class="sxs-lookup"><span data-stu-id="b278d-116">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="b278d-117">Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie der Anwendung Teams im Anwendungsdaten-Ordner des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b278d-117">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="b278d-118">Wenn ein Benutzer bereits die Teams app im Ordner Anwendungsdaten installiert hat, wird der MSI-Installer den Prozess für diesen Benutzer übersprungen.</span><span class="sxs-lookup"><span data-stu-id="b278d-118">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="b278d-119">Verwenden Sie die MSI-Datei nicht zum Bereitstellen von Updates, da der Client Update automatisch wird, wenn es erkennt, dass eine neue Version aus dem Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b278d-119">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="b278d-120">Verwenden Sie erneut bereitstellen, um der neueste Version von Installer den Prozess der erneutes Bereitstellen von MSI-Datei weiter unten beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="b278d-120">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="b278d-121">Wenn Sie eine ältere Version von MSI-Paket bereitstellen, den Client wird automatisch nach Möglichkeit für den Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b278d-121"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="b278d-122">Wenn eine sehr alte Version bereitgestellt, ruft ab, wird die MSI-Datei eine Anwendung Aktualisierung auszulösen, bevor der Benutzer Teams nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="b278d-122">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="b278d-123">Wir empfohlen nicht, die Standardspeicherorte Installation zu ändern, wie dies den Update-Ablauf unterbrechen könnten.</span><span class="sxs-lookup"><span data-stu-id="b278d-123">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="b278d-124">Mit einer zu alten Version wird schließlich Benutzer Zugriff auf den Dienst blockieren.</span><span class="sxs-lookup"><span data-stu-id="b278d-124">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="b278d-125">Anforderungen für die Ziel-computer</span><span class="sxs-lookup"><span data-stu-id="b278d-125">Target computer requirements</span></span>

- <span data-ttu-id="b278d-126">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="b278d-126">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="b278d-127">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="b278d-127">Windows 7 or later</span></span>
- <span data-ttu-id="b278d-128">3 GB freier Festplattenspeicher für die einzelnen Benutzerprofilen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b278d-128">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="b278d-129">Bereinigen und Verfahren für die erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b278d-129">Clean up and redeployment procedure</span></span>
<span data-ttu-id="b278d-130">Wenn ein Benutzer aus ihrem Benutzerprofil Teams deinstalliert, wird der MSI-Installer nachverfolgen, dass der Benutzer hat die app Teams deinstalliert und Teams nicht mehr für dieses Benutzerprofil zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b278d-130">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="b278d-131">Um Teams für diesen Benutzer auf einem bestimmten Computer erneut bereitstellen, auf dem sie deinstalliert wurde, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b278d-131">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="b278d-132">Deinstallieren von Teams App für jede Benutzerprofil installiert.</span><span class="sxs-lookup"><span data-stu-id="b278d-132">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="b278d-133">Nach dem Deinstallieren, Directory rekursiv unter % localappdata%\Microsoft\Teams\ löschen.</span><span class="sxs-lookup"><span data-stu-id="b278d-133">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="b278d-134">Erneutes Bereitstellen des MSI-Pakets an dem jeweiligen Computer.</span><span class="sxs-lookup"><span data-stu-id="b278d-134">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="b278d-135">[Bereitstellung von Microsoft-Teams, bereinigen Sie](scripts/Powershell-script-teams-deployment-clean-up.md) Skript können Sie die Schritte 1 und 2 über SCCM erreichen.</span><span class="sxs-lookup"><span data-stu-id="b278d-135">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="b278d-136">Automatisches Starten für die MSI-Installer deaktivieren</span><span class="sxs-lookup"><span data-stu-id="b278d-136">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="b278d-137">Standardverhalten der die MSI-Datei ist, installieren Sie den Client Teams, sobald ein Benutzer anmeldet, und anschließend Teams automatisch starten.</span><span class="sxs-lookup"><span data-stu-id="b278d-137">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="b278d-138">Sie können dieses Verhalten mit den Parametern unter wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="b278d-138">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="b278d-139">Wenn ein Benutzer in Windows anmeldet, werden die Teams mit der MSI-Datei installiert werden</span><span class="sxs-lookup"><span data-stu-id="b278d-139">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="b278d-140">Jedoch wird der Client Teams nicht gestartet werden, bis der Benutzer Teams manuell gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="b278d-140">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="b278d-141">Eine Verknüpfung zum Starten von Teams wird auf dem Desktop des Benutzers hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="b278d-141">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="b278d-142">Nachdem manuell gestartet, Teams werden automatisch gestartet werden, wenn der Benutzer angemeldet</span><span class="sxs-lookup"><span data-stu-id="b278d-142">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="b278d-143">Für 32-Bit-version</span><span class="sxs-lookup"><span data-stu-id="b278d-143">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="b278d-144">Für die 64-Bit-version</span><span class="sxs-lookup"><span data-stu-id="b278d-144">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  <span data-ttu-id="b278d-145">Wenn Sie die MSI-Datei manuell ausführen, müssen Sie es mit erhöhten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="b278d-145">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="b278d-146">Auch wenn Sie es als Administrator Ausführen ohne mit erhöhten Berechtigungen ausführen, wird das Installationsprogramm nicht die Option zum Deaktivieren der automatischen Start konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="b278d-146">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
