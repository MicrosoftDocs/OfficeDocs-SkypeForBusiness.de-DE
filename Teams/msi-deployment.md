---
title: Installieren von Microsoft Teams mithilfe eines MSI-Pakets mit SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Administratoren können das Microsoft Teams-MSI-Paket für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c009433696ac554114a2a06955b4f33beb6543f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281617"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="a5104-103">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="a5104-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="a5104-104">Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="a5104-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="a5104-105">Wenn Sie für die allgemeine Bereitstellung System Center Configuration Manager (SCCM), Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (als [32-Bit](https://aka.ms/teams32bitmsi)- und [64-Bit](https://aka.ms/teams64bitmsi)-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a5104-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="a5104-106">Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen.</span><span class="sxs-lookup"><span data-stu-id="a5104-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="a5104-107">Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="a5104-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="a5104-108">(Sie können das automatische Starten nach der Installation der App deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5104-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="a5104-109">[Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="a5104-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="a5104-110">Weitere Informationen zu SCCM finden Sie unter [Einführung in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="a5104-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="a5104-111">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="a5104-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="a5104-112">Rufen Sie das neueste Paket ab.</span><span class="sxs-lookup"><span data-stu-id="a5104-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="a5104-113">Verwenden Sie die vorausgefüllten Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a5104-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="a5104-114">Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a5104-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="a5104-115">Funktionsweise des MSI-Pakets für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5104-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="a5104-116">PC-Installation</span><span class="sxs-lookup"><span data-stu-id="a5104-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="a5104-117">Anleitungen zum Bereitstellen von Teams in einer virtuellen DesktopInfrastructure (VDI)-Umgebung finden Sie unter [VDI-Installation](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="a5104-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="a5104-118">Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab.</span><span class="sxs-lookup"><span data-stu-id="a5104-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="a5104-119">Wenn sich ein Benutzer in einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet, und eine Kopie der Teams-APP wird im AppData-Ordner des Benutzers installiert.</span><span class="sxs-lookup"><span data-stu-id="a5104-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="a5104-120">Wenn die Microsoft Teams-App bereits im Ordner „AppData“ des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a5104-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="a5104-121">Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a5104-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="a5104-122">Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen.</span><span class="sxs-lookup"><span data-stu-id="a5104-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="a5104-123">Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert, sofern dies für den Benutzer möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a5104-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="a5104-124">Wenn eine sehr alte Version bereitgestellt wird, löst die MSI-App ein App-Update aus, bevor der Benutzer in der Lage ist, Teams zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5104-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="a5104-125">Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann.</span><span class="sxs-lookup"><span data-stu-id="a5104-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="a5104-126">Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a5104-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="a5104-127">Anforderungen an die Zielcomputer</span><span class="sxs-lookup"><span data-stu-id="a5104-127">Target computer requirements</span></span>

- <span data-ttu-id="a5104-128">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="a5104-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="a5104-129">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="a5104-129">Windows 7 or later</span></span>
- <span data-ttu-id="a5104-130">3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="a5104-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="a5104-131">VDI-Installation</span><span class="sxs-lookup"><span data-stu-id="a5104-131">VDI installation</span></span>

<span data-ttu-id="a5104-132">Hier ist der Vorgang zum Bereitstellen der Desktop-App für Teams.</span><span class="sxs-lookup"><span data-stu-id="a5104-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="a5104-133">Umfassende Anleitungen finden Sie unter [Teams für virtualisierte Desktop Infrastruktur](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="a5104-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="a5104-134">Laden Sie das MSI-Paket für Teams mit einem der folgenden Links in Abhängigkeit von der Umgebung herunter.</span><span class="sxs-lookup"><span data-stu-id="a5104-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="a5104-135">Wir empfehlen die 64-Bit-Version für eine VDI-VM mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="a5104-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="a5104-136">32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="a5104-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="a5104-137">64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="a5104-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="a5104-138">Führen Sie den folgenden Befehl aus, um die MSI-Datei auf der VDI-VM zu installieren (oder vollständig zu aktualisieren).</span><span class="sxs-lookup"><span data-stu-id="a5104-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    <span data-ttu-id="a5104-139">Dadurch werden Teams in Programmdateien installiert.</span><span class="sxs-lookup"><span data-stu-id="a5104-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="a5104-140">An diesem Punkt ist die Einrichtung des goldenen Bilds abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a5104-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="a5104-141">In der nächsten interaktiven Anmeldesitzung werden Teams gestartet, und es werden Anmeldeinformationen angefordert.</span><span class="sxs-lookup"><span data-stu-id="a5104-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="a5104-142">Beachten Sie, dass es nicht möglich ist, den automatischen Start von Teams bei der Installation von Teams auf VDI mithilfe der ALLUSERS-Eigenschaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5104-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSERS property.</span></span>

3. <span data-ttu-id="a5104-143">Führen Sie den folgenden Befehl aus, um die MSI-Datei von der VDI-VM zu deinstallieren (oder die Aktualisierung vorzubereiten).</span><span class="sxs-lookup"><span data-stu-id="a5104-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="a5104-144">Dadurch wird Microsoft Teams aus Programmdateien deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="a5104-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="a5104-145">Verfahren für die Bereinigung und erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a5104-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="a5104-146">Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="a5104-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="a5104-147">Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="a5104-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="a5104-148">Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile.</span><span class="sxs-lookup"><span data-stu-id="a5104-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="a5104-149">Löschen Sie nach der Deinstallation rekursiv das Verzeichnis „%localappdata%\Microsoft\Teams\“.</span><span class="sxs-lookup"><span data-stu-id="a5104-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="a5104-150">Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="a5104-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="a5104-151">Für die Schritte 1 und 2 können Sie unser Skript für die [Bereinigung von Microsoft Teams-Bereitstellungen](scripts/Powershell-script-teams-deployment-clean-up.md) über SCCM verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5104-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="a5104-152">Deaktivieren des automatischen Starts für das MSI-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="a5104-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="a5104-153">Standardmäßig installiert das MSI-Paket den Teams-Client, sobald sich ein Benutzer anmeldet, und startet dann automatisch Teams.</span><span class="sxs-lookup"><span data-stu-id="a5104-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="a5104-154">Sie können dieses Verhalten mit folgenden Parametern wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="a5104-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="a5104-155">Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Paket installiert.</span><span class="sxs-lookup"><span data-stu-id="a5104-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="a5104-156">Jedoch wird der Teams-Client nicht gestartet, bis der Benutzer Teams manuell startet.</span><span class="sxs-lookup"><span data-stu-id="a5104-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="a5104-157">Auf dem Desktop des Benutzers wird eine Verknüpfung zum Starten von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a5104-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="a5104-158">Nach dem erstmaligen manuellen Start wird Teams automatisch gestartet, wenn sich der Benutzer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a5104-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="a5104-159">Für die 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="a5104-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="a5104-160">Für die 64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="a5104-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="a5104-161">Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5104-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="a5104-162">Auch wenn Sie es als Administrator ausführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht deaktivieren, wenn keine erweiterten Berechtigungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a5104-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
