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
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e2354c28916af3c1c0be47848ee7bd2a72bf278
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238666"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="d8100-103">Installieren von Microsoft Teams mithilfe eines MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="d8100-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="d8100-104">Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="d8100-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="d8100-105">Wenn Sie für die allgemeine Bereitstellung System Center Configuration Manager (SCCM), Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (als [32-Bit](https://aka.ms/teams32bitmsi)- und [64-Bit](https://aka.ms/teams64bitmsi)-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d8100-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="d8100-106">Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen.</span><span class="sxs-lookup"><span data-stu-id="d8100-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="d8100-107">Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="d8100-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="d8100-108">(Sie können das automatische Starten nach der Installation der App deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8100-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="d8100-109">[Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.</span><span class="sxs-lookup"><span data-stu-id="d8100-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="d8100-110">Teams können auch in eine Bereitstellung von Office 365 ProPlus einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="d8100-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="d8100-111">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="d8100-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="d8100-112">Weitere Informationen zu SCCM finden Sie unter [Einführung in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="d8100-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="d8100-113">Bereitstellungsverfahren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="d8100-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="d8100-114">Rufen Sie das neueste Paket ab.</span><span class="sxs-lookup"><span data-stu-id="d8100-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="d8100-115">Verwenden Sie die vorausgefüllten Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d8100-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="d8100-116">Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d8100-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="d8100-117">Funktionsweise des MSI-Pakets für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8100-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="d8100-118">PC-Installation</span><span class="sxs-lookup"><span data-stu-id="d8100-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="d8100-119">Eine Anleitung zum Bereitstellen von Teams in einer virtuellen Desktop-Infrastruktur-Umgebung (VDI) finden Sie unter [VDI-Installation](#vdi-installation).</span><span class="sxs-lookup"><span data-stu-id="d8100-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="d8100-120">Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab.</span><span class="sxs-lookup"><span data-stu-id="d8100-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="d8100-121">Wenn sich ein Benutzer bei einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet und im Ordner „AppData“ des Benutzers eine Kopie der Microsoft Teams-App installiert.</span><span class="sxs-lookup"><span data-stu-id="d8100-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="d8100-122">Wenn die Microsoft Teams-App bereits im Ordner „AppData“ des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d8100-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="d8100-123">Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d8100-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="d8100-124">Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen.</span><span class="sxs-lookup"><span data-stu-id="d8100-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="d8100-125">Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert (außer in VDI-Umgebungen), sofern dies für den Benutzer möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d8100-125">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="d8100-126">Falls eine sehr alte Version bereitgestellt wird, löst das MSI-Paket ein App-Update aus, bevor der Benutzer Microsoft Teams verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="d8100-126">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="d8100-127">Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann.</span><span class="sxs-lookup"><span data-stu-id="d8100-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="d8100-128">Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d8100-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="d8100-129">Anforderungen an die Zielcomputer</span><span class="sxs-lookup"><span data-stu-id="d8100-129">Target computer requirements</span></span>

- <span data-ttu-id="d8100-130">.NET Framework 4.5 oder höher</span><span class="sxs-lookup"><span data-stu-id="d8100-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="d8100-131">Windows 7 oder höher</span><span class="sxs-lookup"><span data-stu-id="d8100-131">Windows 7 or later</span></span>
- <span data-ttu-id="d8100-132">3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="d8100-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="d8100-133">VDI-Installation</span><span class="sxs-lookup"><span data-stu-id="d8100-133">VDI installation</span></span>

<span data-ttu-id="d8100-134">Dies ist der Vorgang zur Bereitstellung der Team-App für Desktop.</span><span class="sxs-lookup"><span data-stu-id="d8100-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="d8100-135">Eine vollständige Dokumentation finden Sie unter [Teams für Virtualized Desktop Infrastructure](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="d8100-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="d8100-136">Laden Sie das MSI-Paket für Teams mithilfe eines der folgenden Links (je nach Umgebung) herunter.</span><span class="sxs-lookup"><span data-stu-id="d8100-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="d8100-137">Wir empfehlen die 64-Bit-Version für eine VDI-VM mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="d8100-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="d8100-138">32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="d8100-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="d8100-139">64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="d8100-139">For the 64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="d8100-140">Führen Sie den folgenden Befehl aus, um die MSI-Datei auf der VDI-VM zu installieren (oder die Aktualisierung durchzuführen).</span><span class="sxs-lookup"><span data-stu-id="d8100-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="d8100-141">Dadurch wird Teams im Ordner Programmdateien installiert.</span><span class="sxs-lookup"><span data-stu-id="d8100-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="d8100-142">An diesem Punkt ist die Einrichtung des „Golden Image“ abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d8100-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="d8100-143">Bei der nächsten interaktiven Anmeldesitzung startet Teams und fordert Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="d8100-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="d8100-144">Beachten Sie, dass es nicht möglich ist, das automatische Starten von Teams bei der Installation von Teams auf der VDI mithilfe der ALLUSER-Eigenschaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8100-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="d8100-145">Führen Sie den folgenden Befehl aus, um die MSI-Datei von der VDI-VM zu deinstallieren (oder die Aktualisierung vorzubereiten).</span><span class="sxs-lookup"><span data-stu-id="d8100-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="d8100-146">Dadurch wird Teams aus den-Programmdateien deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="d8100-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="d8100-147">Verfahren für die Bereinigung und erneute Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="d8100-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="d8100-148">Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="d8100-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="d8100-149">Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="d8100-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="d8100-150">Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile.</span><span class="sxs-lookup"><span data-stu-id="d8100-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="d8100-151">Löschen Sie nach der Deinstallation rekursiv das Verzeichnis „%localappdata%\Microsoft\Teams\“.</span><span class="sxs-lookup"><span data-stu-id="d8100-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="d8100-152">Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="d8100-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="d8100-153">Für die Schritte 1 und 2 können Sie unser Skript für die [Bereinigung von Microsoft Teams-Bereitstellungen](scripts/Powershell-script-teams-deployment-clean-up.md) über SCCM verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8100-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="d8100-154">Deaktivieren des automatischen Starts für das MSI-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="d8100-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="d8100-155">Standardmäßig installiert das MSI-Paket den Teams-Client, sobald sich ein Benutzer anmeldet, und startet dann automatisch Teams.</span><span class="sxs-lookup"><span data-stu-id="d8100-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="d8100-156">Sie können dieses Verhalten mit folgenden Parametern wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="d8100-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="d8100-157">Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Paket installiert.</span><span class="sxs-lookup"><span data-stu-id="d8100-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="d8100-158">Jedoch wird der Teams-Client nicht gestartet, bis der Benutzer Teams manuell startet.</span><span class="sxs-lookup"><span data-stu-id="d8100-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="d8100-159">Auf dem Desktop des Benutzers wird eine Verknüpfung zum Starten von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d8100-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="d8100-160">Nach dem erstmaligen manuellen Start wird Teams automatisch gestartet, wenn sich der Benutzer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="d8100-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="d8100-161">Für die 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="d8100-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="d8100-162">Für die 64-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="d8100-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="d8100-163">Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="d8100-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="d8100-164">Auch wenn Sie es als Administrator ausführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht deaktivieren, wenn keine erweiterten Berechtigungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d8100-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
