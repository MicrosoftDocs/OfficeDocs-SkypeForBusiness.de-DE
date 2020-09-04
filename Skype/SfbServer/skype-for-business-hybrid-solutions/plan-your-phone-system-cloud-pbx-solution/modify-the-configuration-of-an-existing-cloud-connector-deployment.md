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
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359111"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="60492-103">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="60492-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="60492-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="60492-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="60492-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="60492-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="60492-106">Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher-Bereitstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="60492-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="60492-107">Ändern der Konfiguration eines einzelnen Standorts</span><span class="sxs-lookup"><span data-stu-id="60492-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="60492-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="60492-109">Wenn der Standort nur eine Appliance enthält und Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, können Sie die CloudConnector.ini Datei ändern und die Bereitstellung erneut starten.</span><span class="sxs-lookup"><span data-stu-id="60492-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="60492-110">Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf dem Hostserver zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="60492-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="60492-111">Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="60492-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="60492-112">Aktualisieren Sie die CloudConnector.ini Datei im Appliance-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="60492-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="60492-113">Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="60492-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="60492-114">Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="60492-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="60492-115">Führen Sie das folgende Cmdlet aus, um Skype for Business Cloud Connector Edition zu installieren:</span><span class="sxs-lookup"><span data-stu-id="60492-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="60492-116">Wenn sich mehr als eine Appliance am Standort befindet, müssen Sie die folgenden Schritte ausführen, die CloudConnector.ini Datei ändern und die Appliances nacheinander bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="60492-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="60492-117">Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer in der aktuellen Appliance zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="60492-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="60492-118">Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="60492-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="60492-119">Aktualisieren Sie die CloudConnector.ini Datei im Appliance-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="60492-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="60492-120">Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="60492-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="60492-121">Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="60492-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="60492-122">Führen Sie das folgende Cmdlet für alle anderen Appliances am Standort aus, um die neueste Konfiguration zu übernehmen:</span><span class="sxs-lookup"><span data-stu-id="60492-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="60492-123">Führen Sie das folgende Cmdlet aus, um Cloud Connector in der aktuellen Appliance erneut bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="60492-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="60492-124">Ändern der Konfiguration mehrerer Standorte</span><span class="sxs-lookup"><span data-stu-id="60492-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="60492-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="60492-126">Wenn Sie die Konfiguration für mehrere Websites in einer Bereitstellung ändern möchten, führen Sie die Schritte für einen einzelnen Standort aus, und aktualisieren Sie gleichzeitig einen Standort.</span><span class="sxs-lookup"><span data-stu-id="60492-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="60492-127">Ändern der Konfiguration Ihrer Microsoft 365-oder Office 365-Organisation, um automatische Updates zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="60492-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="60492-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="60492-129">Zum Aktivieren von automatischen Updates für das Betriebssystem und für automatische Bits-Aktualisierungen müssen Sie das Skype for Business mandantenadministrator Konto für die Online Verwaltung verwenden und die Remote-Mandanten-PowerShell wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="60492-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="60492-130">Wenn Sie automatische Updates für das Betriebssystem oder automatische Bits-Updates deaktiviert haben, verpassen Ihr Host und Ihr virtueller Computer möglicherweise wichtige Windows-Updates und Cloud Connector wird nicht automatisch auf die neue Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="60492-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="60492-131">Es wird dringend empfohlen, dass Sie automatische Updates aktivieren.</span><span class="sxs-lookup"><span data-stu-id="60492-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="60492-132">Die EnableAutoUpdate-Eigenschaft der Website muss auf true (der Standardwert) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="60492-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="60492-133">Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass EnableAutoUpdate auf true festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="60492-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="60492-134">Erstellen des Zeitfensters für die automatische Aktualisierung für den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="60492-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="60492-135">Das Zeitfenster kann täglich, wöchentlich und monatlich sein.</span><span class="sxs-lookup"><span data-stu-id="60492-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="60492-136">Alle Zeitfenster benötigen eine Startzeit und eine Dauer.</span><span class="sxs-lookup"><span data-stu-id="60492-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="60492-137">Für ein tägliches Zeitfenster werden nur Anfangszeit und Dauer benötigt.</span><span class="sxs-lookup"><span data-stu-id="60492-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="60492-138">Für ein wöchentliches Zeitfenster werden Tage der Woche benötigt, wobei es sich um einen einzelnen Tag oder mehrere Tage handeln kann.</span><span class="sxs-lookup"><span data-stu-id="60492-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="60492-139">Für ein monatliches Zeitfenster können zwei Typen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="60492-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="60492-140">Der erste Typ besteht darin, den Tag des Monats anzugeben, bei dem es sich um einen einzelnen Tag handeln kann.</span><span class="sxs-lookup"><span data-stu-id="60492-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="60492-141">Der zweite Typ besteht darin, die Wochen des Monats zusammen mit den Wochentagen anzugeben, bei denen es sich sowohl um ein einzelnes Element als auch um mehrere Elemente handeln kann.</span><span class="sxs-lookup"><span data-stu-id="60492-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="60492-142">Für jeden Mandanten kann 20 Zeitfenster definiert werden.</span><span class="sxs-lookup"><span data-stu-id="60492-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="60492-143">Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für das Betriebssystemupdate und das Bits-Update erstellt.</span><span class="sxs-lookup"><span data-stu-id="60492-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="60492-144">Führen Sie die folgenden Cmdlets aus, um das Tages-, Wochen-oder Monats Zeitfenster festzulegen:</span><span class="sxs-lookup"><span data-stu-id="60492-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="60492-145">Zuweisen von Aktualisierungszeit Fenstern zur Website</span><span class="sxs-lookup"><span data-stu-id="60492-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="60492-146">Die Zeitfenster für Bits-Aktualisierung und Betriebssystemupdates werden separat konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="60492-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="60492-147">Beide können einem oder mehreren Zeitfenstern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="60492-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="60492-148">Jedes Zeitfenster kann unterschiedlichen Standorten und unterschiedlichen Zwecken zugewiesen werden (Bits-Update und Betriebssystemupdate).</span><span class="sxs-lookup"><span data-stu-id="60492-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="60492-149">Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website festzulegen:</span><span class="sxs-lookup"><span data-stu-id="60492-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="60492-150">Aktualisieren der dedizierten Administratoranmeldeinformationen für Mandanten</span><span class="sxs-lookup"><span data-stu-id="60492-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="60492-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="60492-152">Administrative Änderungen in der Microsoft 365-oder Office 365-Organisation für Cloud Connector werden von einem Konto mit den erforderlichen Berechtigungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="60492-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="60492-153">In Cloud Connector-Versionen vor 2,0 ist dieses Konto ein dediziertes globales mandantenadministrator Konto.</span><span class="sxs-lookup"><span data-stu-id="60492-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="60492-154">In Cloud Connector-Versionen 2,0 und höher kann dieses Konto ein Microsoft 365-oder Office 365 Konto mit Skype for Business Administrator Rechten sein.</span><span class="sxs-lookup"><span data-stu-id="60492-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="60492-155">Wenn sich die Anmeldeinformationen Ihres Administratorkontos in Microsoft 365 oder Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator-PowerShell-Befehl auf jeder von Ihnen bereitgestellten Cloud Connector-Appliance ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="60492-156">Aktualisieren des Kennworts für den Hostserver</span><span class="sxs-lookup"><span data-stu-id="60492-156">Update the password for the host server</span></span>
<span data-ttu-id="60492-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="60492-158">Dieser Abschnitt gilt für Cloud Connector, Version 2,0 und höher.</span><span class="sxs-lookup"><span data-stu-id="60492-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="60492-159">Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="60492-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="60492-160">Wenn das Kennwort auf dem Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60492-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="60492-161">Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, verwenden Sie die Cmdlets [Get-CcCredential](get-cccredential.md) und [Sets-CcCredential](set-cccredential.md) , und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="60492-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="60492-162">Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen:</span><span class="sxs-lookup"><span data-stu-id="60492-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="60492-163">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="60492-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="60492-164">Get-CcCredential-AccountType "vmadmin"-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="60492-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="60492-165">Get-CcCredential-AccountType "cceservice"-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="60492-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="60492-166">Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.</span><span class="sxs-lookup"><span data-stu-id="60492-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="60492-167">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="60492-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="60492-168">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="60492-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="60492-169">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="60492-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="60492-170">Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="60492-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="60492-171">Standardmäßig verwenden "vmadmin" und DomainAdmin dasselbe Kennwort wie "cceservice".</span><span class="sxs-lookup"><span data-stu-id="60492-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="60492-172">Wenn die in Schritt 1 zurückgegebenen DomainAdmin-, "vmadmin"-und "cceservice"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="60492-173">Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:</span><span class="sxs-lookup"><span data-stu-id="60492-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="60492-174">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="60492-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="60492-175">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="60492-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="60492-176">Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:</span><span class="sxs-lookup"><span data-stu-id="60492-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="60492-177">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="60492-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="60492-178">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene "vmadmin"-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="60492-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="60492-179">Aktualisieren des Kennworts für das "cceservice"-Konto</span><span class="sxs-lookup"><span data-stu-id="60492-179">Update the password for the CceService account</span></span>
<span data-ttu-id="60492-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="60492-181">Dieser Abschnitt gilt für Cloud Connector, Version 2.0.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="60492-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="60492-182">Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus.</span><span class="sxs-lookup"><span data-stu-id="60492-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="60492-183">Das "cceservice"-Konto wird während der Cloud Connector Edition-Bereitstellung erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML "und"% System Drive% \Programdata\Cloudconnector\credentials..CceService.xml ".</span><span class="sxs-lookup"><span data-stu-id="60492-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="60492-184">Um sicherzustellen, dass alle Appliances auf die Websiteverzeichnis Freigabe zugreifen können, muss das Kennwort für das "cceservice"-Konto auf allen innerhalb des Standorts bereitgestellten Appliances identisch sein.</span><span class="sxs-lookup"><span data-stu-id="60492-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="60492-185">Denken Sie dabei an Folgendes:</span><span class="sxs-lookup"><span data-stu-id="60492-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="60492-186">Standardmäßig wird das "cceservice"-Konto als "Kennwort läuft nie ablaufen" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="60492-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="60492-187">Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="60492-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="60492-188">Sie sollten das Kennwort während nicht-Spitzennutzungszeiten und außerhalb der Zeitfenster für die automatische Aktualisierung für Bits oder Windows-Updates aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60492-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="60492-189">Wenn Sie das Kennwort aktualisieren, muss die Appliance entladen und neu gestartet werden, was einige Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="60492-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="60492-190">Durch einen Neustart der Appliance werden automatische Updatevorgänge unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="60492-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="60492-191">Wenn Sie das Kennwort für das "cceservice"-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und diese in der lokal gespeicherten Datei aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60492-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="60492-192">Für jede Appliance, die zum gleichen PSTN-Standort gehört, müssen Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="60492-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="60492-193">Führen Sie die folgenden Befehle aus, um die Kontonamen und Kennwörter abzurufen, die Sie später verwenden werden:</span><span class="sxs-lookup"><span data-stu-id="60492-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="60492-194">Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Appliance zu entleeren und in den manuellen Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="60492-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="60492-195">Aktualisieren Sie das Kennwort des "cceservice"-Kontos auf dem Hostserver.</span><span class="sxs-lookup"><span data-stu-id="60492-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="60492-196">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="60492-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="60492-197">Führen Sie das Cmdlet Restore-CcCredentials aus, um die Kennwörter nach der Beschreibung erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="60492-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="60492-198">Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie vor der Cloud Connector-Bereitstellung mit Ausnahme des "cceservice"-Kontos eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="60492-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="60492-199">Geben Sie für das "cceservice"-Konto Ihr neues Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="60492-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="60492-200">Stellen Sie sicher, dass das neue Kennwort für das "cceservice"-Konto für alle Appliances am PSTN-Standort identisch ist.</span><span class="sxs-lookup"><span data-stu-id="60492-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="60492-201">Standardmäßig verwenden "vmadmin" und DomainAdmin dasselbe Kennwort wie "cceservice".</span><span class="sxs-lookup"><span data-stu-id="60492-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="60492-202">Wenn die in Schritt 1 zurückgegebenen DomainAdmin-, "vmadmin"-und "cceservice"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="60492-203">Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:</span><span class="sxs-lookup"><span data-stu-id="60492-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="60492-204">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="60492-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="60492-205">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="60492-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="60492-206">Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:</span><span class="sxs-lookup"><span data-stu-id="60492-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="60492-207">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="60492-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="60492-208">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene "vmadmin"-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="60492-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="60492-209">Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Appliance aus dem manuellen Wartungsmodus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="60492-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="60492-210">Nachdem Sie diese Schritte für alle Appliances am gleichen PSTN-Standort ausgeführt haben, löschen Sie die folgenden Dateien im Websitestamm Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="60492-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="60492-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="60492-211">CcLockFile</span></span>
    
    - <span data-ttu-id="60492-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="60492-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="60492-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="60492-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="60492-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="60492-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="60492-215">Hinzufügen einer neuen SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="60492-215">Add a new SIP domain</span></span>
<span data-ttu-id="60492-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="60492-217">Gehen Sie folgendermaßen vor, um der vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="60492-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="60492-218">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben.</span><span class="sxs-lookup"><span data-stu-id="60492-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="60492-219">Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365 oder Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="60492-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="60492-220">Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder den neuen Domänen.</span><span class="sxs-lookup"><span data-stu-id="60492-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="60492-221">Fordern Sie ein neues externes Edge-Zertifikat mit zusätzlichen San-Namen für "SIP. Domain" für jede in ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an.</span><span class="sxs-lookup"><span data-stu-id="60492-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="60492-222">Legen Sie den Pfad für das neue externe Edge-Zertifikat wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="60492-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="60492-223">Befolgen Sie die Anweisungen zum [Ändern der Konfiguration eines einzelnen Standorts](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder zum [Ändern der Konfiguration mehrerer Standorte](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="60492-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="60492-224">Ändern der primären SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="60492-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="60492-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="60492-226">Wenn Sie die primäre SIP-Domäne in ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="60492-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="60492-227">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben.</span><span class="sxs-lookup"><span data-stu-id="60492-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="60492-228">Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365 oder Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="60492-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="60492-229">Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="60492-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="60492-230">Fordern Sie ein neues externes Edge-Zertifikat mit zusätzlichen San-Namen für "SIP. Domain" für jede in ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an.</span><span class="sxs-lookup"><span data-stu-id="60492-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="60492-231">Legen Sie den Pfad für das neue externe Edge-Zertifikat wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="60492-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="60492-232">Entfernen Sie die mandantenregistrierung für jede Appliance an einem Standort, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="60492-233">Entfernen Sie die Website Registrierung für jede Website, indem Sie das folgende Cmdlet in Skype for Business Online PowerShell ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="60492-234">Deinstallieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="60492-235">Registrieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="60492-236">Installieren Sie jede Appliance nacheinander, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="60492-237">Ersetzen des externen Edge-Zertifikats durch ein neues Zertifikat</span><span class="sxs-lookup"><span data-stu-id="60492-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="60492-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="60492-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="60492-239">Wenn Sie das externe Edge-Zertifikat auf Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edge-Zertifikat erhalten, die PFX-Datei vorbereiten, die den privaten Schlüssel und die vollständige Zertifikatkette enthält, und dann auf jeder Appliance die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="60492-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="60492-240">Stellen Sie die Appliance mithilfe des Enter-CCUpdate "-Cmdlets in den Wartungsmodus ein.</span><span class="sxs-lookup"><span data-stu-id="60492-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="60492-241">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="60492-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="60492-242">Wenn das Kennwort des neuen Zertifikats mit dem des alten identisch ist, wird der Import erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="60492-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="60492-243">Wenn das Kennwort unterschiedlich ist, wird eine Fehlermeldung angezeigt, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das Cmdlet "Register-ccappliance" "mit dem Parameter"-local "ausführen und dann Schritt 2 wiederholen.</span><span class="sxs-lookup"><span data-stu-id="60492-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="60492-244">Verwenden Sie das Cmdlet Exit-CCUpdate ", um die Appliance aus dem Wartungsmodus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="60492-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

