---
title: Installieren von Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie die PowerShell-Steuerelemente für die Verwaltung von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814464"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="69796-103">Installieren von Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="69796-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="69796-104">In diesem Artikel wird erläutert, wie Sie das Microsoft Teams PowerShell-Modul mithilfe von [PowerShellGet](/powershell/scripting/gallery/installing-psget)installieren.</span><span class="sxs-lookup"><span data-stu-id="69796-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="69796-105">Diese Anweisungen funktionieren auf [Azure Cloud Shell](/azure/cloud-shell/overview)-, Linux-, macOS-und Windows-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="69796-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="69796-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="69796-106">Requirements</span></span>

<span data-ttu-id="69796-107">Für Teams PowerShell ist PowerShell 5,1 oder höher auf allen Plattformen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69796-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="69796-108">Installieren Sie die [neueste PowerShell-Version](/powershell/scripting/install/installing-powershell) , die für Ihr Betriebssystem verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="69796-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="69796-109">Es gibt bekannte Probleme mit PowerShell 7 und PowerShell von Teams.</span><span class="sxs-lookup"><span data-stu-id="69796-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="69796-110">Für eine optimale Benutzerfreundlichkeit empfehlen wir, PowerShell 5,1 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69796-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="69796-111">Installieren des Teams PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="69796-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="69796-112">Für ein optimales Nutzungserlebnis verwenden Sie entweder allgemeine Verfügbarkeit (GA) oder öffentliche Preview-Module – nicht beide.</span><span class="sxs-lookup"><span data-stu-id="69796-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="69796-113">Sie sind nicht für die Zusammenarbeit vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="69796-113">They're not intended to work together.</span></span>


<span data-ttu-id="69796-114">Verwenden Sie die **PowerShellGet** -Cmdlets, um das PowerShell-Modul von Teams zu installieren.</span><span class="sxs-lookup"><span data-stu-id="69796-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="69796-115">Für die Installation des Moduls für alle Benutzer eines Systems sind erhöhte Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69796-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="69796-116">Starten Sie die PowerShell-Sitzung mit " **als Administrator ausführen** " in Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux:</span><span class="sxs-lookup"><span data-stu-id="69796-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="69796-117">Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet**konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="69796-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="69796-118">Wenn Sie das PSGallery zum ersten Mal verwenden, wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="69796-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="69796-119">Beantworten Sie " **Ja** " oder " **Ja",** um mit der Installation fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="69796-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="69796-120">Installieren von Teams PowerShell Public Preview</span><span class="sxs-lookup"><span data-stu-id="69796-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="69796-121">Wenn Sie die öffentliche Preview-Version von Teams PowerShell verwenden, wird dringend empfohlen, Skype for Business Online Connector zunächst zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="69796-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="69796-122">Das Installieren des Public Preview-Moduls für Teams PowerShell für alle Benutzer in einem System erfordert erhöhte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="69796-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="69796-123">Starten Sie die PowerShell-Sitzung mit " **als Administrator ausführen** " in Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux.</span><span class="sxs-lookup"><span data-stu-id="69796-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="69796-124">Wenn Sie PowerShell 5,1 verwenden, müssen Sie das **PowerShellGet** -Modul vorher aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="69796-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="69796-125">Nachdem Sie **PowerShellGet**aktualisiert haben, schließen Sie eine erhöhte PowerShell-Sitzung, und öffnen Sie Sie erneut, um sicherzustellen, dass die neueste **PowerShellGet** geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="69796-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="69796-126">Führen Sie den folgenden PowerShell-Befehl aus, um Teams PowerShell Public Preview zu installieren.</span><span class="sxs-lookup"><span data-stu-id="69796-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="69796-127">Sie können die aktuelle Preview-Version im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) oder in PowerShell finden, indem Sie "suchen-Modul Microsoft Teams-AllowPrerelease" ausführen.</span><span class="sxs-lookup"><span data-stu-id="69796-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="69796-128">Installieren des Skype for Business Online-Connectors</span><span class="sxs-lookup"><span data-stu-id="69796-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="69796-129">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="69796-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="69796-130">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="69796-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="69796-131">Anmelden</span><span class="sxs-lookup"><span data-stu-id="69796-131">Sign in</span></span>

<span data-ttu-id="69796-132">Um mit der Arbeit mit Teams PowerShell zu beginnen, melden Sie sich mit ihren Azure-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="69796-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="69796-133">Wenn Sie die neueste Version von [Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="69796-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="69796-134">Aktualisieren von Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="69796-134">Update Teams PowerShell</span></span>

<span data-ttu-id="69796-135">Um Teams PowerShell zu aktualisieren, öffnen Sie eine neue erweiterte PowerShell-Eingabeaufforderung, und führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="69796-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="69796-136">Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, tritt beim Aktualisieren des Moduls ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="69796-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="69796-137">Schließen Sie PowerShell, und öffnen Sie eine neue erhöhte PowerShell-Sitzung erneut.</span><span class="sxs-lookup"><span data-stu-id="69796-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="69796-138">Deinstallieren von Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="69796-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="69796-139">Um Teams PowerShell zu deinstallieren, öffnen Sie eine neue erweiterte PowerShell-Eingabeaufforderung, und führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="69796-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="69796-140">Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, tritt beim Deinstallieren des Moduls ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="69796-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="69796-141">Schließen Sie PowerShell, und öffnen Sie eine neue erhöhte PowerShell-Sitzung erneut.</span><span class="sxs-lookup"><span data-stu-id="69796-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69796-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="69796-142">Next Steps</span></span>

<span data-ttu-id="69796-143">Jetzt sind Sie bereit, Teams mithilfe von Teams PowerShell zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="69796-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="69796-144">Weitere Informationen finden Sie unter [Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md) für die ersten Schritte.</span><span class="sxs-lookup"><span data-stu-id="69796-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69796-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="69796-145">Related topics</span></span>

[<span data-ttu-id="69796-146">Verwalten von Teams mit PowerShell von Teams</span><span class="sxs-lookup"><span data-stu-id="69796-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="69796-147">Teams PowerShell-Anmerkungen zu dieser Version</span><span class="sxs-lookup"><span data-stu-id="69796-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="69796-148">Microsoft Teams-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="69796-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="69796-149">Skype for Business-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="69796-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
