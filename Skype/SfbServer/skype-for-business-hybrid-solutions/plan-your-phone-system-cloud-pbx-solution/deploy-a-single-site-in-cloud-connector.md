---
title: Bereitstellen eines einzelnen Standorts in Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Informationen Sie zu eine einzelne PSTN-Website in der Cloud Connector Edition bereitstellen.
ms.openlocfilehash: 6268a9207d36e89faf391ac77a7dd832ba65704f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="68fdc-103">Bereitstellen eines einzelnen Standorts in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="68fdc-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="68fdc-104">Informationen Sie zu eine einzelne PSTN-Website in der Cloud Connector Edition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="68fdc-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="68fdc-105">Sie können mit oder ohne Unterstützung von hoher Verfügbarkeit (HA) Skype für Business Cloud Connector Edition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="68fdc-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="68fdc-106">Wenn Sie hohe Verfügbarkeit aktivieren möchten, müssen Sie mindestens zwei Appliances an einem Standort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="68fdc-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="68fdc-107">Sie können auch eine vorhandene Appliance nach der Bereitstellung konvertieren, um hohe Verfügbarkeit zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="68fdc-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="68fdc-108">Bereitstellen der ersten Skype for Business Cloud Connector Edition-Appliance</span><span class="sxs-lookup"><span data-stu-id="68fdc-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="68fdc-109">Um die erste Appliance in einer Site bereitzustellen, öffnen Sie eine PowerShell-Konsole als Administrator. Führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="68fdc-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```
Register-CcAppliance
```

<span data-ttu-id="68fdc-p102">Befolgen Sie die Anweisungen zum Angeben des Namens und des Kennworts des Administratorkontos für den Mandanten. Verwenden Sie das Konto, das Sie für die Onlineverwaltung von Cloud Connector erstellt haben. Geben Sie außerdem gemäß den Anweisungen das Kennwort des externen Zertifikats, das Administratorkennwort für den abgesicherten Modus, das Kennwort des Domänenadministrators und das Kennwort des VM-Administrators an. </span><span class="sxs-lookup"><span data-stu-id="68fdc-p102">Follow the instructions to provide the tenant admin account name and password. Use the account you have created for Cloud Connector online management. Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="68fdc-113">In Version 1.4.2 und früher auch befolgen Sie die Anweisungen, die externe Zertifikatkennwort, Administratorkennwort abgesicherten Modus, Admin Domänenkennwort und VM Administratorkennwort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68fdc-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="68fdc-114">Befolgen Sie in Version 2.0 und höher außerdem die Anweisungen zum Bereitstellen des Kennworts für das externe Zertifikat, des Kennworts für „CceService“ und des Kennworts für „CABackupFile“.</span><span class="sxs-lookup"><span data-stu-id="68fdc-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="68fdc-115">Um die Installation zu starten, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="68fdc-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="68fdc-116">Hinzufügen einer Appliance zu einer vorhandenen Site</span><span class="sxs-lookup"><span data-stu-id="68fdc-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="68fdc-117">Sie können eine vorhandene Website Cloud Connector zur Unterstützung der HA durch Hinzufügen von zusätzlichen Einheiten für die Website erweitern.</span><span class="sxs-lookup"><span data-stu-id="68fdc-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="68fdc-118">Führen Sie die Schritten zur Vorbereitung Ihrer Appliance Cloud Connector, wie beschrieben unter [Vorbereiten der Appliance Cloud-Connector](prepare-your-cloud-connector-appliance.md)ein.</span><span class="sxs-lookup"><span data-stu-id="68fdc-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="68fdc-119">Beachten Sie, dass einige Schritte nur für die erste Appliance in der Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="68fdc-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="68fdc-120">Vergewissern Sie sich, dass das Standortverzeichnis vorhanden ist und dass es richtig für die Unterstützung von hoher Verfügbarkeit konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="68fdc-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="68fdc-p104">Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um die Topologieinformationen in der Konfiguration Ihres Office 365-Mandanten zu aktualisieren. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem der neu hinzugefügten Hostserver aus:</span><span class="sxs-lookup"><span data-stu-id="68fdc-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
  ```
  Register-CcAppliance
  ```

3. <span data-ttu-id="68fdc-p105">Aktualisieren Sie die Topologie in vorhandenen Appliances, indem Sie das folgende Cmdlet auf jedem Hostserver ausführen. Führen Sie das Cmdlet nur in den vorhandenen Appliances aus.</span><span class="sxs-lookup"><span data-stu-id="68fdc-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
  ```
  Publish-CcAppliance
  ```

4. <span data-ttu-id="68fdc-125">Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus.</span><span class="sxs-lookup"><span data-stu-id="68fdc-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="68fdc-126">Führen Sie es nicht in der vorhandenen Appliance aus.</span><span class="sxs-lookup"><span data-stu-id="68fdc-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="68fdc-127">Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem der neu hinzugefügten Hostserver aus:</span><span class="sxs-lookup"><span data-stu-id="68fdc-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
  ```
  Install-CcAppliance
  ```

> [!NOTE]
> <span data-ttu-id="68fdc-128">Wenn das Standortverzeichnis auf einen lokalen Ordnerpfad festgelegt ist, müssen Sie eine Dateifreigabe für diesen Ordner definieren und für das Standortverzeichnis in der neuen Appliance einen UNC-Pfad verwenden.</span><span class="sxs-lookup"><span data-stu-id="68fdc-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="68fdc-129">Sie können für das Standortverzeichnis der ersten Appliance den lokalen Pfad beibehalten oder es so ändern, dass der UNC-Pfad für die Freigabe des gleichen Ordners verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68fdc-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="68fdc-130">Wenn sich der Speicherort für das freigegebene Standortverzeichnis ändert, müssen alle bereits installierten Appliances deinstalliert und dann erneut installiert werden.</span><span class="sxs-lookup"><span data-stu-id="68fdc-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="68fdc-131">> Wichtig: Das Kennwort für das Konto CceService und das CABackupFile Konto muss auf allen Einheiten, die innerhalb der Website bereitgestellt übereinstimmen, damit die Appliances die Site Directory Freigabe als auch die verschlüsselte Zertifizierungsstelle Sicherungsdatei im Websiteverzeichnis zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="68fdc-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="68fdc-132">Entfernen einer Appliance aus einer vorhandenen Site</span><span class="sxs-lookup"><span data-stu-id="68fdc-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="68fdc-133">Wenn Sie eine Appliance aus einer vorhandenen Site entfernen möchten, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="68fdc-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="68fdc-134">Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie aus dem Standort entfernen möchten, um die Topologieinformationen in der Konfiguration Ihres Office 365-Mandanten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="68fdc-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
  ```
  Unregister-CcAppliance
  ```

2. <span data-ttu-id="68fdc-135">Führen Sie das folgende Cmdlet nur auf den Hostservern aus, von denen Sie alle virtuellen Maschinen der Appliance entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="68fdc-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
  ```
  Uninstall-CcAppliance
  ```


