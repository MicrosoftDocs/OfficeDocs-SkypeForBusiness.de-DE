---
title: Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher-Bereitstellung zu ändern.
ms.openlocfilehash: 77e9940e10cc356afbade5592bf41a0cdba66b0f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779381"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="8bb0f-103">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8bb0f-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="8bb0f-104">Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher-Bereitstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="8bb0f-105">Ändern der Konfiguration eines einzelnen Standorts</span><span class="sxs-lookup"><span data-stu-id="8bb0f-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="8bb0f-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="8bb0f-107">Wenn der Standort nur eine Appliance enthält und Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, können Sie die Datei "cloudconnector. ini ändern und die Bereitstellung erneut starten.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="8bb0f-108">Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf dem Hostserver zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="8bb0f-109">Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="8bb0f-110">Aktualisieren Sie die Datei "cloudconnector. ini im Appliance-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="8bb0f-111">Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="8bb0f-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="8bb0f-112">Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="8bb0f-113">Führen Sie das folgende Cmdlet aus, um Skype for Business Cloud Connector Edition zu installieren:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="8bb0f-114">Wenn sich mehr als eine Appliance am Standort befindet, müssen Sie die folgenden Schritte ausführen, die Datei "cloudconnector. ini ändern und die Appliances nacheinander bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="8bb0f-115">Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer in der aktuellen Appliance zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="8bb0f-116">Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="8bb0f-117">Aktualisieren Sie die Datei "cloudconnector. ini im Appliance-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="8bb0f-118">Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="8bb0f-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="8bb0f-119">Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="8bb0f-120">Führen Sie das folgende Cmdlet für alle anderen Appliances am Standort aus, um die neueste Konfiguration zu übernehmen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="8bb0f-121">Führen Sie das folgende Cmdlet aus, um Cloud Connector in der aktuellen Appliance erneut bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="8bb0f-122">Ändern der Konfiguration mehrerer Standorte</span><span class="sxs-lookup"><span data-stu-id="8bb0f-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="8bb0f-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="8bb0f-124">Wenn Sie die Konfiguration für mehrere Websites in einer Bereitstellung ändern möchten, führen Sie die Schritte für einen einzelnen Standort aus, und aktualisieren Sie gleichzeitig einen Standort.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="8bb0f-125">Ändern der Konfiguration Ihrer Office 365 Organisation zur Aktivierung automatischer Updates</span><span class="sxs-lookup"><span data-stu-id="8bb0f-125">Modify the configuration of your Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="8bb0f-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="8bb0f-127">Zum Aktivieren von automatischen Updates für das Betriebssystem und für automatische Bits-Aktualisierungen müssen Sie das Skype for Business mandantenadministrator Konto für die Online Verwaltung verwenden und die Remote-Mandanten-PowerShell wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="8bb0f-128">Wenn Sie automatische Updates für das Betriebssystem oder automatische Bits-Updates deaktiviert haben, verpassen Ihr Host und Ihr virtueller Computer möglicherweise wichtige Windows-Updates und Cloud Connector wird nicht automatisch auf die neue Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="8bb0f-129">Es wird dringend empfohlen, dass Sie automatische Updates aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="8bb0f-130">Die EnableAutoUpdate-Eigenschaft der Website muss auf true (der Standardwert) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="8bb0f-131">Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass EnableAutoUpdate auf true festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="8bb0f-132">Erstellen des Zeitfensters für die automatische Aktualisierung für den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="8bb0f-133">Das Zeitfenster kann täglich, wöchentlich und monatlich sein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="8bb0f-134">Alle Zeitfenster benötigen eine Startzeit und eine Dauer.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="8bb0f-135">Für ein tägliches Zeitfenster werden nur Anfangszeit und Dauer benötigt.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="8bb0f-136">Für ein wöchentliches Zeitfenster werden Tage der Woche benötigt, wobei es sich um einen einzelnen Tag oder mehrere Tage handeln kann.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="8bb0f-137">Für ein monatliches Zeitfenster können zwei Typen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="8bb0f-138">Der erste Typ besteht darin, den Tag des Monats anzugeben, bei dem es sich um einen einzelnen Tag handeln kann.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="8bb0f-139">Der zweite Typ besteht darin, die Wochen des Monats zusammen mit den Wochentagen anzugeben, bei denen es sich sowohl um ein einzelnes Element als auch um mehrere Elemente handeln kann.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="8bb0f-140">Für jeden Mandanten kann 20 Zeitfenster definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="8bb0f-141">Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für das Betriebssystemupdate und das Bits-Update erstellt.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="8bb0f-142">Führen Sie die folgenden Cmdlets aus, um das Tages-, Wochen-oder Monats Zeitfenster festzulegen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="8bb0f-143">Zuweisen von Aktualisierungszeit Fenstern zur Website</span><span class="sxs-lookup"><span data-stu-id="8bb0f-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="8bb0f-144">Die Zeitfenster für Bits-Aktualisierung und Betriebssystemupdates werden separat konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="8bb0f-145">Beide können einem oder mehreren Zeitfenstern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="8bb0f-146">Jedes Zeitfenster kann unterschiedlichen Standorten und unterschiedlichen Zwecken zugewiesen werden (Bits-Update und Betriebssystemupdate).</span><span class="sxs-lookup"><span data-stu-id="8bb0f-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="8bb0f-147">Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website festzulegen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="8bb0f-148">Aktualisieren der dedizierten Administratoranmeldeinformationen für Mandanten</span><span class="sxs-lookup"><span data-stu-id="8bb0f-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="8bb0f-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="8bb0f-150">Administrative Änderungen in der Office 365 Organisation für Cloud Connector werden von einem Konto mit den erforderlichen Berechtigungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-150">Administrative changes in the Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="8bb0f-151">In Cloud Connector-Versionen vor 2,0 ist dieses Konto ein dediziertes globales mandantenadministrator Konto.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="8bb0f-152">In Cloud Connector-Versionen 2,0 und höher kann dieses Konto ein Office 365 Konto mit Skype for Business Administrator Rechten sein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="8bb0f-153">Wenn sich die Anmeldeinformationen Ihres Administratorkontos in Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator-PowerShell-Befehl auf jeder von Ihnen bereitgestellten Cloud Connector-Appliance ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="8bb0f-154">Aktualisieren des Kennworts für den Hostserver</span><span class="sxs-lookup"><span data-stu-id="8bb0f-154">Update the password for the host server</span></span>
<span data-ttu-id="8bb0f-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="8bb0f-156">Dieser Abschnitt gilt für Cloud Connector, Version 2,0 und höher.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="8bb0f-157">Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="8bb0f-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="8bb0f-158">Wenn das Kennwort auf dem Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="8bb0f-159">Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, verwenden Sie die Cmdlets [Get-CcCredential](get-cccredential.md) und [Sets-CcCredential](set-cccredential.md) , und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="8bb0f-160">Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="8bb0f-161">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="8bb0f-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="8bb0f-162">Get-CcCredential-AccountType "vmadmin"-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="8bb0f-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="8bb0f-163">Get-CcCredential-AccountType "cceservice"-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="8bb0f-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="8bb0f-164">Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="8bb0f-165">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="8bb0f-166">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="8bb0f-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="8bb0f-167">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="8bb0f-168">Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="8bb0f-169">Standardmäßig verwenden "vmadmin" und DomainAdmin dasselbe Kennwort wie "cceservice".</span><span class="sxs-lookup"><span data-stu-id="8bb0f-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="8bb0f-170">Wenn die in Schritt 1 zurückgegebenen DomainAdmin-, "vmadmin"-und "cceservice"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="8bb0f-171">Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="8bb0f-172">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="8bb0f-173">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="8bb0f-174">Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="8bb0f-175">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="8bb0f-176">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene "vmadmin"-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="8bb0f-177">Aktualisieren des Kennworts für das "cceservice"-Konto</span><span class="sxs-lookup"><span data-stu-id="8bb0f-177">Update the password for the CceService account</span></span>
<span data-ttu-id="8bb0f-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="8bb0f-179">Dieser Abschnitt gilt für Cloud Connector, Version 2.0.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="8bb0f-180">Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="8bb0f-181">Das "cceservice"-Konto wird während der Cloud Connector Edition-Bereitstellung erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "und"%SystemDrive%\Programdata\Cloudconnector\credentials.. "Cceservice". xml ".</span><span class="sxs-lookup"><span data-stu-id="8bb0f-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="8bb0f-182">Um sicherzustellen, dass alle Appliances auf die Websiteverzeichnis Freigabe zugreifen können, muss das Kennwort für das "cceservice"-Konto auf allen innerhalb des Standorts bereitgestellten Appliances identisch sein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="8bb0f-183">Denken Sie dabei an Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="8bb0f-184">Standardmäßig wird das "cceservice"-Konto als "Kennwort läuft nie ablaufen" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="8bb0f-185">Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="8bb0f-186">Sie sollten das Kennwort während nicht-Spitzennutzungszeiten und außerhalb der Zeitfenster für die automatische Aktualisierung für Bits oder Windows-Updates aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="8bb0f-187">Wenn Sie das Kennwort aktualisieren, muss die Appliance entladen und neu gestartet werden, was einige Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="8bb0f-188">Durch einen Neustart der Appliance werden automatische Updatevorgänge unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="8bb0f-189">Wenn Sie das Kennwort für das "cceservice"-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und diese in der lokal gespeicherten Datei aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="8bb0f-190">Für jede Appliance, die zum gleichen PSTN-Standort gehört, müssen Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="8bb0f-191">Führen Sie die folgenden Befehle aus, um die Kontonamen und Kennwörter abzurufen, die Sie später verwenden werden:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="8bb0f-192">Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Appliance zu entleeren und in den manuellen Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="8bb0f-193">Aktualisieren Sie das Kennwort des "cceservice"-Kontos auf dem Hostserver.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="8bb0f-194">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="8bb0f-195">Führen Sie das Cmdlet Restore-CcCredentials aus, um die Kennwörter nach der Beschreibung erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="8bb0f-196">Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie vor der Cloud Connector-Bereitstellung mit Ausnahme des "cceservice"-Kontos eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="8bb0f-197">Geben Sie für das "cceservice"-Konto Ihr neues Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="8bb0f-198">Stellen Sie sicher, dass das neue Kennwort für das "cceservice"-Konto für alle Appliances am PSTN-Standort identisch ist.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="8bb0f-199">Standardmäßig verwenden "vmadmin" und DomainAdmin dasselbe Kennwort wie "cceservice".</span><span class="sxs-lookup"><span data-stu-id="8bb0f-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="8bb0f-200">Wenn die in Schritt 1 zurückgegebenen DomainAdmin-, "vmadmin"-und "cceservice"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="8bb0f-201">Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="8bb0f-202">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="8bb0f-203">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="8bb0f-204">Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="8bb0f-205">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="8bb0f-206">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene "vmadmin"-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="8bb0f-207">Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Appliance aus dem manuellen Wartungsmodus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="8bb0f-208">Nachdem Sie diese Schritte für alle Appliances am gleichen PSTN-Standort ausgeführt haben, löschen Sie die folgenden Dateien im Websitestamm Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="8bb0f-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="8bb0f-209">CcLockFile</span></span>
    
    - <span data-ttu-id="8bb0f-210">FQDN\<des externen SIP-Pools Site_ Edge\></span><span class="sxs-lookup"><span data-stu-id="8bb0f-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="8bb0f-211">FQDN\<des externen SIP-Pools Tenant_ Edge\></span><span class="sxs-lookup"><span data-stu-id="8bb0f-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="8bb0f-212">FQDN\<des externen SIP-Pools TenantConfigLock_ Edge\></span><span class="sxs-lookup"><span data-stu-id="8bb0f-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="8bb0f-213">Hinzufügen einer neuen SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="8bb0f-213">Add a new SIP domain</span></span>
<span data-ttu-id="8bb0f-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="8bb0f-215">Gehen Sie folgendermaßen vor, um der vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="8bb0f-216">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="8bb0f-217">Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="8bb0f-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="8bb0f-218">Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder den neuen Domänen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="8bb0f-219">Fordern Sie ein neues externes Edge-Zertifikat mit zusätzlichen San-Namen für "SIP. Domain" für jede in ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="8bb0f-220">Legen Sie den Pfad für das neue externe Edge-Zertifikat wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="8bb0f-221">Befolgen Sie die Anweisungen zum [Ändern der Konfiguration eines einzelnen Standorts](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder zum [Ändern der Konfiguration mehrerer Standorte](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="8bb0f-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="8bb0f-222">Ändern der primären SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="8bb0f-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="8bb0f-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="8bb0f-224">Wenn Sie die primäre SIP-Domäne in ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="8bb0f-225">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="8bb0f-226">Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="8bb0f-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="8bb0f-227">Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="8bb0f-228">Fordern Sie ein neues externes Edge-Zertifikat mit zusätzlichen San-Namen für "SIP. Domain" für jede in ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="8bb0f-229">Legen Sie den Pfad für das neue externe Edge-Zertifikat wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="8bb0f-230">Entfernen Sie die mandantenregistrierung für jede Appliance an einem Standort, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="8bb0f-231">Entfernen Sie die Website Registrierung für jede Website, indem Sie das folgende Cmdlet in Skype for Business Online PowerShell ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="8bb0f-232">Deinstallieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="8bb0f-233">Registrieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="8bb0f-234">Installieren Sie jede Appliance nacheinander, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="8bb0f-235">Ersetzen des externen Edge-Zertifikats durch ein neues Zertifikat</span><span class="sxs-lookup"><span data-stu-id="8bb0f-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="8bb0f-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8bb0f-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="8bb0f-237">Wenn Sie das externe Edge-Zertifikat auf Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edge-Zertifikat erhalten, die PFX-Datei vorbereiten, die den privaten Schlüssel und die vollständige Zertifikatkette enthält, und dann auf jeder Appliance die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="8bb0f-238">Stellen Sie die Appliance mithilfe des Enter-CCUpdate "-Cmdlets in den Wartungsmodus ein.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="8bb0f-239">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8bb0f-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="8bb0f-240">Wenn das Kennwort des neuen Zertifikats mit dem des alten identisch ist, wird der Import erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="8bb0f-241">Wenn das Kennwort unterschiedlich ist, wird eine Fehlermeldung angezeigt, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das Cmdlet "Register-ccappliance" "mit dem Parameter"-local "ausführen und dann Schritt 2 wiederholen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="8bb0f-242">Verwenden Sie das Cmdlet Exit-CCUpdate ", um die Appliance aus dem Wartungsmodus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8bb0f-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

