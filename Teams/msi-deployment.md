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
ms.openlocfilehash: 42944baab0552d28877c4974510087d69df1b697
ms.sourcegitcommit: 349df7248c168e629bc1bb633187e39a37b17ba5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "34421948"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="eb7cc-103">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="eb7cc-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="eb7cc-104">Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="eb7cc-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="eb7cc-105">Wenn Sie für die allgemeine Bereitstellung System Center Configuration Manager (SCCM), Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (als [32-Bit](https://aka.ms/teams32bitmsi)- und [64-Bit](https://aka.ms/teams64bitmsi)-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="eb7cc-106">Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="eb7cc-107">Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="eb7cc-108">(Sie können das automatische Starten nach der Installation der App deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="eb7cc-109">[Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="eb7cc-110">Teams können auch in eine Bereitstellung von Office 365 ProPlus einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="eb7cc-111">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="eb7cc-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="eb7cc-112">Weitere Informationen zu SCCM finden Sie unter [Einführung in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="eb7cc-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="eb7cc-113">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="eb7cc-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="eb7cc-114">Rufen Sie das neueste Paket ab.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="eb7cc-115">Verwenden Sie die vorausgefüllten Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="eb7cc-116">Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="eb7cc-117">Funktionsweise des MSI-Pakets für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb7cc-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="eb7cc-118">PC-Installation</span><span class="sxs-lookup"><span data-stu-id="eb7cc-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="eb7cc-119">Anleitungen zum Bereitstellen von Teams in einer virtuellen DesktopInfrastructure (VDI)-Umgebung finden Sie unter [VDI-Installation](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="eb7cc-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="eb7cc-120">Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="eb7cc-121">Wenn sich ein Benutzer in einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet, und eine Kopie der Teams-APP wird im AppData-Ordner des Benutzers installiert.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="eb7cc-122">Wenn die Microsoft Teams-App bereits im Ordner „AppData“ des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="eb7cc-123">Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="eb7cc-124">Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="eb7cc-125">Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert, sofern dies für den Benutzer möglich ist.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-125"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="eb7cc-126">Wenn eine sehr alte Version bereitgestellt wird, löst die MSI-App ein App-Update aus, bevor der Benutzer in der Lage ist, Teams zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="eb7cc-127">Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="eb7cc-128">Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="eb7cc-129">Anforderungen an die Zielcomputer</span><span class="sxs-lookup"><span data-stu-id="eb7cc-129">Target computer requirements</span></span>

- <span data-ttu-id="eb7cc-130">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="eb7cc-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="eb7cc-131">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="eb7cc-131">Windows 7 or later</span></span>
- <span data-ttu-id="eb7cc-132">3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="eb7cc-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="eb7cc-133">VDI-Installation</span><span class="sxs-lookup"><span data-stu-id="eb7cc-133">VDI installation</span></span>

<span data-ttu-id="eb7cc-134">Hier ist der Vorgang zum Bereitstellen der Desktop-App für Teams.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="eb7cc-135">Umfassende Anleitungen finden Sie unter [Teams für virtualisierte Desktop Infrastruktur](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="eb7cc-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="eb7cc-136">Laden Sie das MSI-Paket für Teams mit einem der folgenden Links in Abhängigkeit von der Umgebung herunter.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="eb7cc-137">Wir empfehlen die 64-Bit-Version für eine VDI-VM mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="eb7cc-138">32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="eb7cc-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="eb7cc-139">64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="eb7cc-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="eb7cc-140">Führen Sie den folgenden Befehl aus, um die MSI-Datei auf der VDI-VM zu installieren (oder vollständig zu aktualisieren).</span><span class="sxs-lookup"><span data-stu-id="eb7cc-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    <span data-ttu-id="eb7cc-141">Dadurch werden Teams in Programmdateien installiert.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="eb7cc-142">An diesem Punkt ist die Einrichtung des goldenen Bilds abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="eb7cc-143">In der nächsten interaktiven Anmeldesitzung werden Teams gestartet, und es werden Anmeldeinformationen angefordert.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="eb7cc-144">Beachten Sie, dass es nicht möglich ist, den automatischen Start von Teams bei der Installation von Teams auf VDI mithilfe der ALLUSERS-Eigenschaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSERS property.</span></span>

3. <span data-ttu-id="eb7cc-145">Führen Sie den folgenden Befehl aus, um die MSI-Datei von der VDI-VM zu deinstallieren (oder die Aktualisierung vorzubereiten).</span><span class="sxs-lookup"><span data-stu-id="eb7cc-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="eb7cc-146">Dadurch wird Microsoft Teams aus Programmdateien deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="eb7cc-147">Verfahren für die Bereinigung und erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="eb7cc-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="eb7cc-148">Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="eb7cc-149">Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="eb7cc-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="eb7cc-150">Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="eb7cc-151">Löschen Sie nach der Deinstallation rekursiv das Verzeichnis „%localappdata%\Microsoft\Teams\“.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="eb7cc-152">Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="eb7cc-153">Für die Schritte 1 und 2 können Sie unser Skript für die [Bereinigung von Microsoft Teams-Bereitstellungen](scripts/Powershell-script-teams-deployment-clean-up.md) über SCCM verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="eb7cc-154">Deaktivieren des automatischen Starts für das MSI-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="eb7cc-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="eb7cc-155">Standardmäßig installiert das MSI-Paket den Teams-Client, sobald sich ein Benutzer anmeldet, und startet dann automatisch Teams.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="eb7cc-156">Sie können dieses Verhalten mit folgenden Parametern wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="eb7cc-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="eb7cc-157">Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Paket installiert.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="eb7cc-158">Jedoch wird der Teams-Client nicht gestartet, bis der Benutzer Teams manuell startet.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="eb7cc-159">Auf dem Desktop des Benutzers wird eine Verknüpfung zum Starten von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="eb7cc-160">Nach dem erstmaligen manuellen Start wird Teams automatisch gestartet, wenn sich der Benutzer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="eb7cc-161">Für die 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="eb7cc-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="eb7cc-162">Für die 64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="eb7cc-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="eb7cc-163">Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="eb7cc-164">Auch wenn Sie es als Administrator ausführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht deaktivieren, wenn keine erweiterten Berechtigungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="eb7cc-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
