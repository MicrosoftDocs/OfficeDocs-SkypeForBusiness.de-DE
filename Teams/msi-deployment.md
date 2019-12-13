---
title: Installieren von Microsoft Teams mithilfe eines MSI-Pakets mit SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Administratoren können das Microsoft Teams-MSI-Paket für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32eb60b238d606ac30fe74c7551e01efe88242a
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002229"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="13c83-103">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="13c83-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="13c83-104">Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="13c83-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="13c83-105">Wenn Sie für die allgemeine Bereitstellung System Center Configuration Manager (SCCM), Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (als 32-Bit- und 64-Bit-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="13c83-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="13c83-106">Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen.</span><span class="sxs-lookup"><span data-stu-id="13c83-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="13c83-107">Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="13c83-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="13c83-108">(Sie können das automatische Starten nach der Installation der App deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="13c83-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="13c83-109">[Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="13c83-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="13c83-110">Hierbei handelt es sich um die Links zu den MSI-Dateien:</span><span class="sxs-lookup"><span data-stu-id="13c83-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="13c83-111">Entität</span><span class="sxs-lookup"><span data-stu-id="13c83-111">Entity</span></span>  |<span data-ttu-id="13c83-112">32-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-112">32 bit</span></span>      |<span data-ttu-id="13c83-113">64-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="13c83-114">Handels</span><span class="sxs-lookup"><span data-stu-id="13c83-114">Commercial</span></span>     | [<span data-ttu-id="13c83-115">32-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="13c83-116">64-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="13c83-117">Bundesregierung-gcc</span><span class="sxs-lookup"><span data-stu-id="13c83-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="13c83-118">32-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="13c83-119">64-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="13c83-120">Bundesregierung-gcc-Höchststand</span><span class="sxs-lookup"><span data-stu-id="13c83-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="13c83-121">32-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="13c83-122">64-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="13c83-123">Bundesregierung-DoD</span><span class="sxs-lookup"><span data-stu-id="13c83-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="13c83-124">32-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="13c83-125">64-Bit</span><span class="sxs-lookup"><span data-stu-id="13c83-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="13c83-126">Teams können auch in eine Bereitstellung von Office 365 ProPlus einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="13c83-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="13c83-127">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="13c83-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="13c83-128">Weitere Informationen zu SCCM finden Sie unter [Einführung in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="13c83-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="13c83-129">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="13c83-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="13c83-130">Rufen Sie das neueste Paket ab.</span><span class="sxs-lookup"><span data-stu-id="13c83-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="13c83-131">Verwenden Sie die vorausgefüllten Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="13c83-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="13c83-132">Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="13c83-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="13c83-133">Funktionsweise des MSI-Pakets für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13c83-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="13c83-134">PC-Installation</span><span class="sxs-lookup"><span data-stu-id="13c83-134">PC installation</span></span>

<span data-ttu-id="13c83-135">Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab.</span><span class="sxs-lookup"><span data-stu-id="13c83-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="13c83-136">Wenn sich ein Benutzer bei einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet und im Ordner „AppData“ des Benutzers eine Kopie der Microsoft Teams-App installiert.</span><span class="sxs-lookup"><span data-stu-id="13c83-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="13c83-137">Wenn die Microsoft Teams-App bereits im Ordner „AppData“ des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="13c83-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="13c83-138">Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="13c83-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="13c83-139">Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen.</span><span class="sxs-lookup"><span data-stu-id="13c83-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="13c83-140">Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert (außer in VDI-Umgebungen), sofern dies für den Benutzer möglich ist.</span><span class="sxs-lookup"><span data-stu-id="13c83-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="13c83-141">Falls eine sehr alte Version bereitgestellt wird, löst das MSI-Paket ein App-Update aus, bevor der Benutzer Microsoft Teams verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="13c83-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="13c83-142">Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann.</span><span class="sxs-lookup"><span data-stu-id="13c83-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="13c83-143">Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="13c83-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="13c83-144">Anforderungen an die Zielcomputer</span><span class="sxs-lookup"><span data-stu-id="13c83-144">Target computer requirements</span></span>

- <span data-ttu-id="13c83-145">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="13c83-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="13c83-146">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="13c83-146">Windows 7 or later</span></span>
- <span data-ttu-id="13c83-147">3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="13c83-147">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="13c83-148">VDI-Installation</span><span class="sxs-lookup"><span data-stu-id="13c83-148">VDI installation</span></span>

<span data-ttu-id="13c83-149">Eine vollständige Anleitung zum Bereitstellen der Desktop-App "Teams" auf VDI finden Sie unter [Teams für virtualisierte Desktopinfrastruktur](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="13c83-149">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="13c83-150">Verfahren für die Bereinigung und erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="13c83-150">Clean up and redeployment procedure</span></span>

<span data-ttu-id="13c83-151">Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="13c83-151">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="13c83-152">Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="13c83-152">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="13c83-153">Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile.</span><span class="sxs-lookup"><span data-stu-id="13c83-153">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="13c83-154">Löschen Sie nach der Deinstallation rekursiv das Verzeichnis „%localappdata%\Microsoft\Teams\“.</span><span class="sxs-lookup"><span data-stu-id="13c83-154">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="13c83-155">Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="13c83-155">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="13c83-156">Für die Schritte 1 und 2 können Sie unser Skript für die [Bereinigung von Microsoft Teams-Bereitstellungen](scripts/Powershell-script-teams-deployment-clean-up.md) über SCCM verwenden.</span><span class="sxs-lookup"><span data-stu-id="13c83-156">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="13c83-157">Deaktivieren des automatischen Starts für das MSI-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="13c83-157">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="13c83-158">Standardmäßig installiert das MSI-Paket den Teams-Client, sobald sich ein Benutzer anmeldet, und startet dann automatisch Teams.</span><span class="sxs-lookup"><span data-stu-id="13c83-158">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="13c83-159">Sie können dieses Verhalten mit folgenden Parametern wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="13c83-159">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="13c83-160">Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Paket installiert.</span><span class="sxs-lookup"><span data-stu-id="13c83-160">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="13c83-161">Jedoch wird der Teams-Client nicht gestartet, bis der Benutzer Teams manuell startet.</span><span class="sxs-lookup"><span data-stu-id="13c83-161">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="13c83-162">Auf dem Desktop des Benutzers wird eine Verknüpfung zum Starten von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="13c83-162">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="13c83-163">Nach dem erstmaligen manuellen Start wird Teams automatisch gestartet, wenn sich der Benutzer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="13c83-163">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="13c83-164">Für die 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="13c83-164">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="13c83-165">Für die 64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="13c83-165">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> <span data-ttu-id="13c83-166">Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="13c83-166">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="13c83-167">Auch wenn Sie es als Administrator ausführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht deaktivieren, wenn keine erweiterten Berechtigungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="13c83-167">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
