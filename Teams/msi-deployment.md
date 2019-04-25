---
title: Installieren von Microsoft Teams mithilfe eines MSI-Pakets mit SCCM
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
ms.openlocfilehash: 8412b6998e824c05ac4d7f394d2283c265f78b04
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225555"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="ed9b4-103">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="ed9b4-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="ed9b4-104">Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="ed9b4-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="ed9b4-105">Wenn Sie für die allgemeine Bereitstellung System Center Configuration Manager (SCCM), Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (als [32-Bit](https://aka.ms/teams32bitmsi)- und [64-Bit](https://aka.ms/teams64bitmsi)-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="ed9b4-106">Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="ed9b4-107">Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="ed9b4-108">(Sie können das automatische Starten nach der Installation der App deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="ed9b4-109">[Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="ed9b4-110">Weitere Informationen zu SCCM finden Sie unter [Einführung in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="ed9b4-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="ed9b4-111">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="ed9b4-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="ed9b4-112">Rufen Sie das neueste Paket ab.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="ed9b4-113">Verwenden Sie die vorausgefüllten Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="ed9b4-114">Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="ed9b4-115">Funktionsweise des MSI-Pakets für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed9b4-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="ed9b4-116">PC-installation</span><span class="sxs-lookup"><span data-stu-id="ed9b4-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="ed9b4-117">Anleitungen zum Bereitstellen von Teams in einer virtuellen DesktopInfrastructure (VDI)-Umgebung finden Sie unter [VDI-Installation](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="ed9b4-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="ed9b4-118">Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="ed9b4-119">Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie der Teams app im Anwendungsdaten-Ordner des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="ed9b4-120">Wenn die Microsoft Teams-App bereits im Ordner „AppData“ des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="ed9b4-121">Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="ed9b4-122">Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="ed9b4-123">Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert, sofern dies für den Benutzer möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="ed9b4-124">Wenn eine sehr alte Version bereitgestellt, ruft ab, lösen die MSI-Datei ein app-Update, bevor der Benutzer Teams nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="ed9b4-125">Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="ed9b4-126">Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="ed9b4-127">Anforderungen an die Zielcomputer</span><span class="sxs-lookup"><span data-stu-id="ed9b4-127">Target computer requirements</span></span>

- <span data-ttu-id="ed9b4-128">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="ed9b4-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="ed9b4-129">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="ed9b4-129">Windows 7 or later</span></span>
- <span data-ttu-id="ed9b4-130">3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="ed9b4-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="ed9b4-131">VDI-installation</span><span class="sxs-lookup"><span data-stu-id="ed9b4-131">VDI installation</span></span>

<span data-ttu-id="ed9b4-132">Hier ist der Prozess zum Bereitstellen von Teams-desktop-app.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="ed9b4-133">Vollständige Anleitung finden Sie unter [virtualisierten Desktop Infrastructure-Teams](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="ed9b4-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="ed9b4-134">Herunterladen Sie Teams MSI-Paket mit einer der folgenden Links je nach der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="ed9b4-135">Wir empfehlen die 64-Bit-Version für eine VDI VM mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="ed9b4-136">32-Bit-version</span><span class="sxs-lookup"><span data-stu-id="ed9b4-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="ed9b4-137">64-Bit-version</span><span class="sxs-lookup"><span data-stu-id="ed9b4-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="ed9b4-138">Führen Sie den folgenden Befehl zum Installieren der MSI-Datei für die VDI-VM (oder Abschließen der Aktualisierung).</span><span class="sxs-lookup"><span data-stu-id="ed9b4-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="ed9b4-139">Dies installiert Teams Program Files.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="ed9b4-140">Zu diesem Zeitpunkt ist das goldene Bild Setup abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="ed9b4-141">Die nächste interaktive Sitzung beginnt Teams und fordert die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="ed9b4-142">Beachten Sie, dass es nicht möglich, automatisch gestartet Teams bei der Installation von Teams auf VDI mithilfe der ALLUSER-Eigenschaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="ed9b4-143">Führen Sie den folgenden Befehl zum Deinstallieren der MSI-Datei aus der VDI VM (oder Vorbereiten der Aktualisierung).</span><span class="sxs-lookup"><span data-stu-id="ed9b4-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="ed9b4-144">Dies deinstalliert Teams aus Program Files.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="ed9b4-145">Verfahren für die Bereinigung und erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ed9b4-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="ed9b4-146">Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="ed9b4-147">Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="ed9b4-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="ed9b4-148">Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="ed9b4-149">Löschen Sie nach der Deinstallation rekursiv das Verzeichnis „%localappdata%\Microsoft\Teams\“.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="ed9b4-150">Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="ed9b4-151">Für die Schritte 1 und 2 können Sie unser Skript für die [Bereinigung von Microsoft Teams-Bereitstellungen](scripts/Powershell-script-teams-deployment-clean-up.md) über SCCM verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="ed9b4-152">Deaktivieren des automatischen Starts für das MSI-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="ed9b4-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="ed9b4-153">Standardmäßig installiert das MSI-Paket den Teams-Client, sobald sich ein Benutzer anmeldet, und startet dann automatisch Teams.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="ed9b4-154">Sie können dieses Verhalten mit folgenden Parametern wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="ed9b4-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="ed9b4-155">Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Paket installiert.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="ed9b4-156">Jedoch wird der Teams-Client nicht gestartet, bis der Benutzer Teams manuell startet.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="ed9b4-157">Auf dem Desktop des Benutzers wird eine Verknüpfung zum Starten von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="ed9b4-158">Nach dem erstmaligen manuellen Start wird Teams automatisch gestartet, wenn sich der Benutzer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="ed9b4-159">Für die 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="ed9b4-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="ed9b4-160">Für die 64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="ed9b4-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="ed9b4-161">Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="ed9b4-162">Auch wenn Sie es als Administrator ausführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht deaktivieren, wenn keine erweiterten Berechtigungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ed9b4-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
