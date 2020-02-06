---
title: Aktualisieren auf eine neue Version von Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Hier erfahren Sie, wie Sie Ihre Cloud Connector Edition-Bereitstellung aktualisieren.
ms.openlocfilehash: d2f9d2a2720f67a2110ba97b7d100e5673a0015c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814143"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="1d681-103">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1d681-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="1d681-104">Hier erfahren Sie, wie Sie Ihre Cloud Connector Edition-Bereitstellung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1d681-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="1d681-p101">Wenn Sie ein Mandantenkonto für die Onlineverwaltung eingerichtet und automatische Aktualisierungen aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition entsprechend Ihrer Zeitfensterkonfiguration für automatische Updates automatisch auf die neuere Version aktualisiert. Sie können auch manuelle Upgrades ausführen. </span><span class="sxs-lookup"><span data-stu-id="1d681-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="1d681-107">Cloud Connector Edition-Versionen 1.4.1 und höher führen standardmäßig automatische Updates aus.</span><span class="sxs-lookup"><span data-stu-id="1d681-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="1d681-108">Wenn Sie manuell auf die neueste Version (2,1) aktualisieren möchten, lesen Sie [Aktualisieren einer einzelnen Website auf eine neue Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="1d681-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="1d681-109">Für die automatische Aktualisierung muss der Cloud Connector-Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1d681-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="1d681-110">In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1d681-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="1d681-111">Der Prozess für automatische Updates wird gemäß dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="1d681-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="1d681-112">Tasks für Betriebssystemupdates</span><span class="sxs-lookup"><span data-stu-id="1d681-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="1d681-113">Überprüfen und Herunterladen von Betriebssystemupdates auf alle Cloud Connector-VMS</span><span class="sxs-lookup"><span data-stu-id="1d681-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="1d681-114">Installieren und aktualisieren Sie alle VMs des Cloud Connectors nacheinander, und starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="1d681-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="1d681-115">Überprüfen Sie nach dem Neustart des Cloud Connector VMS, ob ein weiterer Neustart erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1d681-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="1d681-116">Nachdem der Cloud Connector VMS erfolgreich gepatcht wurde, wiederholen Sie den Vorgang für den Cloud Connector-Hostcomputer.</span><span class="sxs-lookup"><span data-stu-id="1d681-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="1d681-117">Nachdem der Cloud Connector-Hostcomputer erfolgreich gestartet wurde, sind alle ausstehenden Betriebssystem Aktualisierungsaufgaben abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1d681-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="1d681-118">Aktualisierungsaufgaben für Cloud Connectors</span><span class="sxs-lookup"><span data-stu-id="1d681-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="1d681-119">Die Versionsdatei wird von der Downloadwebsite heruntergeladen und überprüft.</span><span class="sxs-lookup"><span data-stu-id="1d681-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="1d681-120">Die neue Version der MSI-Datei wird heruntergeladen. </span><span class="sxs-lookup"><span data-stu-id="1d681-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="1d681-121">Deinstallieren Sie die alte MSI-Datei. Installieren Sie die neue MSI-Datei.</span><span class="sxs-lookup"><span data-stu-id="1d681-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="1d681-122">Laden Sie die neue Version von Skype for Business-Bits herunter.</span><span class="sxs-lookup"><span data-stu-id="1d681-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="1d681-123">Die Appliance wird durch Aufrufen von „Register-CcAppliance“ registriert.</span><span class="sxs-lookup"><span data-stu-id="1d681-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="1d681-124">Installieren Sie die neue Cloud Connector-Version.</span><span class="sxs-lookup"><span data-stu-id="1d681-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="1d681-125">Die alte Appliance wird ausgeglichen, und die Netzwerkverbindung wird auf die neue Appliance umgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="1d681-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="1d681-126">Wenn der Cloud Connector in einem neuen Build aktualisiert wird, werden die Cmdlets für Cloud Connector möglicherweise nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1d681-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="1d681-127">Dies kann beispielsweise vorkommen, wenn ein PowerShell-Fenster geöffnet bleibt, während die automatische Aktualisierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1d681-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="1d681-128">Um die aktualisierten Cmdlets zu laden, führen Sie einen der folgenden Schritte aus: #a0 schließen Sie PowerShell auf der Cloud Connector-Appliance, und öffnen Sie dann PowerShell. #a1, oder führen Sie Import-Module CloudConnector-Force aus.</span><span class="sxs-lookup"><span data-stu-id="1d681-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="1d681-129">Aktualisieren eines einzelnen Standorts auf eine neue Version</span><span class="sxs-lookup"><span data-stu-id="1d681-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="1d681-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="1d681-130"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="1d681-131">Wenn der zu aktualisierende Standort nur eine Appliance umfasst, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1d681-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="1d681-132">Deinstallieren Sie die vorhandene Cloud Connector-Version unter Programme \*\*und Funktionen der System \> \> \*\*Steuerung.</span><span class="sxs-lookup"><span data-stu-id="1d681-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="1d681-133">Installieren Sie die neue Version von CloudConnector. msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)aus.</span><span class="sxs-lookup"><span data-stu-id="1d681-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="1d681-134">Vergewissern Sie sich, dass Sie über die Datei „CloudConnector.ini“ für die zu installierende Version verfügen und dass Sie alle erforderlichen Werte für Ihre Umgebung aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="1d681-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="1d681-135">Die INI-Datei einer früheren Version kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d681-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="1d681-136">Wenn Sie Cloud Connector aktualisieren, lesen Sie das Thema Vorbereiten der [Cloud Connector-Appliance](prepare-your-cloud-connector-appliance.md) , und stellen Sie sicher, dass Sitename und EnableReferSupport auf den richtigen Wert in der Datei CloudConnector. ini eingestellt sind.</span><span class="sxs-lookup"><span data-stu-id="1d681-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="1d681-137">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die aktuelle Appliance zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="1d681-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="1d681-138">Führen Sie das folgende Cmdlet aus, um die neueste Version herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="1d681-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="1d681-139">Führen Sie das folgende Cmdlet aus, um die Installation zu starten: </span><span class="sxs-lookup"><span data-stu-id="1d681-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="1d681-140">Führen Sie das folgende Cmdlet aus, um die neue Bereitstellung zu aktivieren und die vorherige Version zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="1d681-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="1d681-141">Wenn sich mehr als eine Appliance am Standort befindet, führen Sie die obigen Schritte aus, um die einzelnen Appliances nacheinander zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1d681-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="1d681-142">Wenn Sie den Domänenadministrator, den Administrator für virtuelle Computer, den Administrator für den abgesicherten Modus und die Administratoranmeldeinformationen für Mandanten aktualisieren möchten, können Sie das Cmdlet mit dem _UpdateAllCredentials_ -Parameter ausführen, um alle Anmeldeinformationen zurückzusetzen:</span><span class="sxs-lookup"><span data-stu-id="1d681-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="1d681-143">Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie aufgefordert, die neuen Anmeldeinformationen einzugeben. </span><span class="sxs-lookup"><span data-stu-id="1d681-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="1d681-144">Wenn Sie nur die Anmeldeinformationen des Mandantenadministrators zurücksetzen möchten, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="1d681-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="1d681-145">Upgrade von mehreren Standorten auf eine neue Version</span><span class="sxs-lookup"><span data-stu-id="1d681-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="1d681-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="1d681-146"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="1d681-p106">Führen Sie die Schritte für das Upgrade eines einzelnen Standorts nacheinander für jeden Standort in Ihrer Bereitstellung aus. Führen Sie nach dem Upgrade jedes Standorts unbedingt den Schritt [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) aus.</span><span class="sxs-lookup"><span data-stu-id="1d681-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

