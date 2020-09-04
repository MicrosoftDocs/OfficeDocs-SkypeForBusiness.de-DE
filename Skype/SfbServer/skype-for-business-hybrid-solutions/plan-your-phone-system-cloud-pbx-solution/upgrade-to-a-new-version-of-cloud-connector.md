---
title: Upgrade auf eine neue Version von Cloud Connector
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
description: Erfahren Sie mehr über das Upgrade Ihrer Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359291"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="19a1c-103">Upgrade auf eine neue Version von Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="19a1c-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="19a1c-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="19a1c-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="19a1c-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="19a1c-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="19a1c-106">Erfahren Sie mehr über das Upgrade Ihrer Cloud Connector Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="19a1c-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="19a1c-107">Wenn Sie ein Online Verwaltungs Mandantenkonto eingerichtet und automatische Updates aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition automatisch auf die neuere Version aktualisiert – entsprechend der Konfiguration für das Zeitfenster für die automatische Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="19a1c-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="19a1c-108">Sie können auch ein Manuelles Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="19a1c-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="19a1c-109">Cloud Connector Edition-Versionen 1.4.1 und höher führen standardmäßig automatische Updates aus.</span><span class="sxs-lookup"><span data-stu-id="19a1c-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="19a1c-110">Wenn Sie manuell auf die neueste Version (2,1) aktualisieren möchten, finden Sie weitere Informationen unter [Upgrade an Single Site to a New Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="19a1c-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="19a1c-111">Für die automatische Aktualisierung muss der Cloud Connector-Dienst aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="19a1c-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="19a1c-112">In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:</span><span class="sxs-lookup"><span data-stu-id="19a1c-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="19a1c-113">Der automatische Updateprozess wird entsprechend dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="19a1c-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="19a1c-114">Betriebssystem-Updateaufgaben</span><span class="sxs-lookup"><span data-stu-id="19a1c-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="19a1c-115">Überprüfen und Herunterladen von Betriebssystemupdates auf alle Cloud Connector-VMS.</span><span class="sxs-lookup"><span data-stu-id="19a1c-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="19a1c-116">Installieren und aktualisieren Sie alle Cloud Connector-VMS nacheinander, und starten Sie neu.</span><span class="sxs-lookup"><span data-stu-id="19a1c-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="19a1c-117">Überprüfen Sie nach dem Neustart des Cloud Connector-VMS, ob ein anderer Neustart erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="19a1c-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="19a1c-118">Nachdem die Cloud Connector-VMS erfolgreich gepatcht wurden, wiederholen Sie den Vorgang für den Cloud Connector-Hostcomputer.</span><span class="sxs-lookup"><span data-stu-id="19a1c-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="19a1c-119">Nachdem der Cloud Connector-Hostcomputer erfolgreich gestartet wurde, sind alle ausstehenden Betriebssystem-Updateaufgaben abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="19a1c-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="19a1c-120">Cloud Connector-Aktualisierungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="19a1c-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="19a1c-121">Laden Sie die Versionsdatei von der Download Website herunter, und überprüfen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="19a1c-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="19a1c-122">Laden Sie die neue Version der MSI-Datei herunter.</span><span class="sxs-lookup"><span data-stu-id="19a1c-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="19a1c-123">Deinstallieren Sie die alte MSI-Datei; Installieren Sie die neue MSI-Datei.</span><span class="sxs-lookup"><span data-stu-id="19a1c-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="19a1c-124">Laden Sie die neue Version von Skype for Business Bits herunter.</span><span class="sxs-lookup"><span data-stu-id="19a1c-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="19a1c-125">Registrieren Sie die Appliance durch Aufrufen von Register-ccappliance ".</span><span class="sxs-lookup"><span data-stu-id="19a1c-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="19a1c-126">Installieren Sie die neue Cloud Connector-Version.</span><span class="sxs-lookup"><span data-stu-id="19a1c-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="19a1c-127">Entleeren Sie die alte Appliance, und wechseln Sie die Netzwerkverbindung zur neuen Appliance.</span><span class="sxs-lookup"><span data-stu-id="19a1c-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="19a1c-128">Wenn Cloud Connector für einen neuen Build aktualisiert wird, werden die Cloud Connector-Cmdlets möglicherweise nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="19a1c-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="19a1c-129">Dies kann beispielsweise der Fall sein, wenn ein PowerShell-Fenster geöffnet bleibt, während die automatische Aktualisierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="19a1c-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="19a1c-130">Führen Sie einen der folgenden Schritte aus, um die aktualisierten Cmdlets zu laden: > close PowerShell in der Cloud Connector-Appliance, und öffnen Sie dann PowerShell. > oder können Sie Import-Module "cloudconnector-Force ausführen.</span><span class="sxs-lookup"><span data-stu-id="19a1c-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="19a1c-131">Aktualisieren einer einzelnen Website auf eine neue Version</span><span class="sxs-lookup"><span data-stu-id="19a1c-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="19a1c-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="19a1c-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="19a1c-133">Wenn es nur eine Appliance am Standort gibt, die Sie aktualisieren möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="19a1c-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="19a1c-134">Deinstallieren Sie die vorhandene Cloud Connector-Version in den Programmen \*\* \> \> und Funktionen der System\*\*Steuerung.</span><span class="sxs-lookup"><span data-stu-id="19a1c-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="19a1c-135">Installieren Sie die neue Version von CloudConnector.msi von [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="19a1c-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="19a1c-136">Vergewissern Sie sich, dass Sie über die CloudConnector.ini Datei für die Version verfügen, die Sie installieren, und dass Sie alle erforderlichen Werte für Ihre Umgebung aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="19a1c-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="19a1c-137">Sie können die INI-Datei nicht aus einer früheren Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="19a1c-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="19a1c-138">Wenn Sie Cloud Connector aktualisieren, lesen Sie das Thema [prepare your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md) , und stellen Sie sicher, dass Sitename und "enablerefersupport" auf den korrekten Wert in der Datei CloudConnector.ini festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="19a1c-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="19a1c-139">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die aktuelle Appliance zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="19a1c-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="19a1c-140">Führen Sie das folgende Cmdlet aus, um die neueste Version herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="19a1c-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="19a1c-141">Führen Sie das folgende Cmdlet aus, um die Installation zu starten:</span><span class="sxs-lookup"><span data-stu-id="19a1c-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="19a1c-142">Führen Sie das folgende Cmdlet aus, um die neue Bereitstellung zu aktivieren und die vorherige Version zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="19a1c-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="19a1c-143">Wenn sich mehr als eine Appliance am Standort befindet, führen Sie die oben beschriebenen Schritte aus, um die einzelnen Appliances nacheinander zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="19a1c-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="19a1c-144">Wenn Sie die Anmeldeinformationen des Domänenadministrators, des Administrators virtueller Computer, des Administrators und des Mandanten für den sicheren Modus aktualisieren möchten, können Sie das Cmdlet mit dem Parameter  _UpdateAllCredentials_ ausführen, um alle Anmeldeinformationen zurückzusetzen:</span><span class="sxs-lookup"><span data-stu-id="19a1c-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="19a1c-145">Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie zur Eingabe der neuen Anmeldeinformationen heraufgestuft.</span><span class="sxs-lookup"><span data-stu-id="19a1c-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="19a1c-146">Wenn Sie nur Ihre mandantenadministrator-Anmeldeinformationen zurücksetzen möchten, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="19a1c-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="19a1c-147">Aktualisieren mehrerer Websites auf eine neue Version</span><span class="sxs-lookup"><span data-stu-id="19a1c-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="19a1c-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="19a1c-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="19a1c-149">Befolgen Sie die Schritte für das Upgrade eines einzelnen Standorts, und aktualisieren Sie jeweils einen Standort für jeden Standort in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="19a1c-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="19a1c-150">Stellen Sie sicher, dass [Ihre Cloud Connector-Bereitstellung](validate-your-cloud-connector-deployment.md) nach dem Upgrade jeder Website überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="19a1c-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

