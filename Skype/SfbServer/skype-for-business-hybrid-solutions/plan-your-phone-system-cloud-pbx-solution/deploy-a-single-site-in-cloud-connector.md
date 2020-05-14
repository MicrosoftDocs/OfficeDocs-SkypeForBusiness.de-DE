---
title: Bereitstellen eines einzelnen Standorts in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Erfahren Sie mehr über die Bereitstellungeines einzelnen PSTN-Standorts in Cloud Connector Edition.
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220535"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="63636-103">Bereitstellen eines einzelnen Standorts in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="63636-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="63636-104">Erfahren Sie mehr über die Bereitstellungeines einzelnen PSTN-Standorts in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="63636-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="63636-105">Sie können Skype for Business Cloud Connector Edition mit oder ohne Unterstützung für hohe Verfügbarkeit (ha) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="63636-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="63636-106">Wenn Sie ha aktivieren möchten, müssen Sie zwei oder mehr Appliances innerhalb eines Standorts bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="63636-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="63636-107">Sie können eine vorhandene Appliance auch konvertieren, um ha zu unterstützen, nachdem Sie bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="63636-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="63636-108">Bereitstellen der ersten Skype for Business Cloud Connector Edition-Appliance</span><span class="sxs-lookup"><span data-stu-id="63636-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="63636-109">Um die erste Appliance an einem Standort bereitzustellen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="63636-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="63636-110">Befolgen Sie die Anweisungen, um den Namen und das Kennwort des mandantenadministrator Kontos anzugeben.</span><span class="sxs-lookup"><span data-stu-id="63636-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="63636-111">Verwenden Sie das Konto, das Sie für die Online Verwaltung von Cloud Connector erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="63636-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="63636-112">Befolgen Sie außerdem die Anweisungen, um das Kennwort für das externe Zertifikat, das Administratorkennwort für den sicheren Modus, das Domänenadministratorkennwort und das VM-Administratorkennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="63636-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="63636-113">Befolgen Sie in Version 1.4.2 und früher auch die Anweisungen zum Bereitstellen des externen Zertifikats Kennworts, des Safe Mode-Administratorkennworts, des Domänenadministrator Kennworts und des VM-Administratorkennworts.</span><span class="sxs-lookup"><span data-stu-id="63636-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="63636-114">Befolgen Sie in Version 2,0 und höher auch die Anweisungen, um das externe Zertifikat Kennwort, das "cceservice"-Kennwort und das CABackupFile-Kennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="63636-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="63636-115">Öffnen Sie zum Starten der Installation eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="63636-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="63636-116">Hinzufügen einer Appliance zu einer vorhandenen Website</span><span class="sxs-lookup"><span data-stu-id="63636-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="63636-117">Sie können einen vorhandenen Cloud Connector-Standort erweitern, um ha zu unterstützen, indem Sie dem Standort zusätzliche Appliances hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="63636-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="63636-118">Befolgen Sie die Schritte zum Vorbereiten Ihrer Cloud Connector-Appliance wie unter [prepare your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="63636-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="63636-119">Beachten Sie, dass einige Schritte nur für die erste Appliance in Ihrer Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="63636-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="63636-120">Stellen Sie sicher, dass das Websiteverzeichnis vorhanden und für die ha-Unterstützung ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="63636-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="63636-121">Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um die Topologieinformationen in Ihrer Microsoft 365-oder Office 365-Organisationskonfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="63636-121">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="63636-122">Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet jeweils nacheinander auf jedem neu hinzugefügten Hostserver aus:</span><span class="sxs-lookup"><span data-stu-id="63636-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="63636-123">Aktualisieren Sie die Topologie auf vorhandenen Appliances, indem Sie das folgende Cmdlet auf jedem Hostserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="63636-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="63636-124">Führen Sie das Cmdlet nur für die vorhandenen Appliances aus.</span><span class="sxs-lookup"><span data-stu-id="63636-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="63636-125">Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus.</span><span class="sxs-lookup"><span data-stu-id="63636-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="63636-126">Führen Sie dieses Cmdlet nicht für die vorhandene Appliance aus.</span><span class="sxs-lookup"><span data-stu-id="63636-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="63636-127">Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet auf jedem neu hinzugefügten Hostserver nacheinander aus.</span><span class="sxs-lookup"><span data-stu-id="63636-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="63636-128">Wenn das Websiteverzeichnis auf einen lokalen Ordnerpfad festgelegt wurde, müssen Sie eine Dateifreigabe für diesen Ordner definieren und einen UNC-Pfad für das Websiteverzeichnis in der neuen Appliance verwenden.</span><span class="sxs-lookup"><span data-stu-id="63636-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="63636-129">Sie können das erste Appliance-Websiteverzeichnis mit dem lokalen Pfad belassen oder es so ändern, dass der UNC-Pfad für die Freigabe in demselben Ordner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63636-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="63636-130">Wenn sich der Speicherort für das freigegebene Websiteverzeichnis ändert, müssen alle zuvor installierten Appliances deinstalliert und dann neu installiert werden.</span><span class="sxs-lookup"><span data-stu-id="63636-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="63636-131">> wichtig: das Kennwort für das "cceservice"-Konto und das CABackupFile-Konto muss auf allen innerhalb des Standorts bereitgestellten Appliances identisch sein, damit die Appliances auf die Websiteverzeichnis Freigabe und die Sicherungsdatei der verschlüsselten Zertifizierungsstelle im Websiteverzeichnis zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="63636-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="63636-132">Entfernen einer Appliance von einer vorhandenen Website</span><span class="sxs-lookup"><span data-stu-id="63636-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="63636-133">Wenn Sie eine Appliance aus einer vorhandenen Website entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="63636-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="63636-134">Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie aus dem Standort entfernen möchten, um die Topologieinformationen in Ihrer Microsoft 365-oder Office 365-Organisationskonfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="63636-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="63636-135">Führen Sie das folgende Cmdlet nur auf den Hostservern aus, aus denen Sie alle virtuellen Computer der Appliance entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="63636-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


