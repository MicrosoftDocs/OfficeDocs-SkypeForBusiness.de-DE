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
description: Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1-oder höher-Bereitstellung zu ändern.
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799435"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="74356-103">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="74356-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="74356-104">Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1-oder höher-Bereitstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74356-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="74356-105">Ändern der Konfiguration einer einzelnen Site</span><span class="sxs-lookup"><span data-stu-id="74356-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="74356-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="74356-107">Wenn die Site nur eine Appliance enthält und Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, können Sie die Datei „CloudConnector.ini“ ändern und die Bereitstellung erneut starten.</span><span class="sxs-lookup"><span data-stu-id="74356-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="74356-108">Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Maschinen auf dem Hostserver zu deinstallieren: </span><span class="sxs-lookup"><span data-stu-id="74356-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="74356-109">Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="74356-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="74356-110">Aktualisieren Sie die Datei „CloudConnector.ini“ im Verzeichnis der Appliance.</span><span class="sxs-lookup"><span data-stu-id="74356-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="74356-111">Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für vorherige Versionen fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="74356-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="74356-112">Führen Sie das folgende Cmdlet aus, um die Appliance wieder zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="74356-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="74356-113">Führen Sie das folgende Cmdlet aus, um Skype for Business Cloud Connector Edition zu installieren:</span><span class="sxs-lookup"><span data-stu-id="74356-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="74356-114">Wenn am Standort mehrere Appliances vorhanden sind, müssen Sie diese Schritte ausführen, die Datei „CloudConnector.ini“ ändern und die Appliances nacheinander erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="74356-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="74356-115">Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf der aktuellen Appliance zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="74356-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="74356-116">Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="74356-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="74356-117">Aktualisieren Sie die Datei „CloudConnector.ini“ im Verzeichnis der Appliance.</span><span class="sxs-lookup"><span data-stu-id="74356-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="74356-118">Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für vorherige Versionen fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="74356-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="74356-119">Führen Sie das folgende Cmdlet aus, um die Appliance wieder zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="74356-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="74356-120">Führen Sie das folgende Cmdlet in allen anderen Appliances am Standort aus, um die aktuelle Konfiguration zu übernehmen:</span><span class="sxs-lookup"><span data-stu-id="74356-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="74356-121">Führen Sie das folgende Cmdlet aus, um den Cloud Connector für die aktuelle Appliance erneut bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="74356-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="74356-122">Ändern der Konfiguration mehrerer Sites</span><span class="sxs-lookup"><span data-stu-id="74356-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="74356-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="74356-124">Wenn Sie die Konfiguration für mehrere Websites in einer Bereitstellung ändern möchten, führen Sie die Schritte für eine einzelne Website aus, und aktualisieren Sie jeweils eine Website.</span><span class="sxs-lookup"><span data-stu-id="74356-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="74356-125">Ändern der Konfiguration Ihres Office 365-Mandanten, um automatische Updates zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="74356-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="74356-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="74356-127">Wenn Sie automatische Updates für das Betriebssystem und automatische Bits-Updates aktivieren möchten, müssen Sie das Skype for Business-mandantenadministrator Konto für die Online Verwaltung verwenden und die Mandanten-Remote-PowerShell wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="74356-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="74356-128">Wenn Sie automatische Updates für das Betriebssystem oder automatische Updates für Bits deaktiviert haben, verpassen Ihr Host und Ihr virtueller Computer möglicherweise wichtige Windows-Updates, und Cloud Connector wird nicht automatisch auf die neue Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="74356-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="74356-129">Es wird dringend empfohlen, automatische Updates zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="74356-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="74356-130">Die EnableAutoUpdate-Eigenschaft der Website muss auf "true" (der Standardwert) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="74356-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="74356-131">Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass „EnableAutoUpdate“ auf „true“ festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="74356-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="74356-132">Erstellen Sie ein Zeitfenster für automatische Updates für den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="74356-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="74356-p103">Dabei kann es sich um ein tägliches, wöchentliches oder monatliches Zeitfenster handeln. Für alle Zeitfenster ist eine Startzeit und eine Dauer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74356-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="74356-135">Für tägliche Zeitfenster müssen Sie nur die Startzeit und die Dauer angeben. </span><span class="sxs-lookup"><span data-stu-id="74356-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="74356-136">Für wöchentliche Zeitfenster werden die Wochentage benötigt, das heißt ein einzelner Tag oder mehrere Tage.</span><span class="sxs-lookup"><span data-stu-id="74356-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="74356-p104">Bei einem monatlichen Zeitfenster sind zwei Typen möglich. Zunächst können Sie einen Tag im Monat angeben, also einen einzigen Tag. Beim zweiten Typ können Sie Wochen im Monat sowie Wochentage angeben (ein Element oder mehrere Elemente).</span><span class="sxs-lookup"><span data-stu-id="74356-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="74356-p105">Für jeden Mandanten können 20 Zeitfenster definiert sein. Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für Betriebssystemupdates und Updates der Bits erstellt. Führen Sie die folgenden Cmdlets aus, um tägliche, wöchentliche oder monatliche Zeitfenster festzulegen:</span><span class="sxs-lookup"><span data-stu-id="74356-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="74356-143">Weisen Sie der Website Aktualisierungszeit Fenster zu.</span><span class="sxs-lookup"><span data-stu-id="74356-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="74356-144">Die Zeitfenster für BITS-Updates und Betriebssystemupdates werden getrennt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="74356-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="74356-145">Beiden Updatearten können Sie ein oder mehrere Zeitfenstern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="74356-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="74356-146">Jedes Zeitfenster kann verschiedenen Sites und Zwecken zugewiesen sein (BITS-Update und Betriebssystemupdate).</span><span class="sxs-lookup"><span data-stu-id="74356-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="74356-147">Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website einzurichten:</span><span class="sxs-lookup"><span data-stu-id="74356-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="74356-148">Aktualisieren der Anmeldeinformationen für den dedizierten Mandantenadministrator </span><span class="sxs-lookup"><span data-stu-id="74356-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="74356-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="74356-150">Administrative Änderungen im Office 365-Mandanten für Cloud Connector erfolgen über ein Konto mit den erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="74356-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="74356-151">In Cloud Connector-Versionen vor 2,0 ist dieses Konto ein dediziertes globales mandantenadministrator Konto.</span><span class="sxs-lookup"><span data-stu-id="74356-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="74356-152">In Cloud Connector-Versionen 2,0 und höher kann dieses Konto ein Office 365-Konto mit Skype for Business-Administrator Rechten sein.</span><span class="sxs-lookup"><span data-stu-id="74356-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="74356-153">Wenn sich die Anmeldeinformationen für Ihr Administratorkonto in Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator PowerShell-Befehl auf jeder von Ihnen bereitgestellten Cloud Connector-Appliance ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="74356-154">Aktualisieren des Kennworts für den Hostserver </span><span class="sxs-lookup"><span data-stu-id="74356-154">Update the password for the host server</span></span>
<span data-ttu-id="74356-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="74356-156">Dieser Abschnitt gilt für Cloud Connector Version 2,0 und höher.</span><span class="sxs-lookup"><span data-stu-id="74356-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="74356-157">Alle Anmeldeinformationen für den Cloud Connector werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="74356-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="74356-158">Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="74356-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="74356-159">Wenn Sie die lokal gespeicherten Anmeldeinformationen auf der Cloud Connector-Appliance aktualisieren möchten, verwenden Sie die Cmdlets [Get-CcCredential](get-cccredential.md) und [CcCredential](set-cccredential.md) , und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="74356-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="74356-160">Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen: </span><span class="sxs-lookup"><span data-stu-id="74356-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="74356-161">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="74356-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="74356-162">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="74356-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="74356-163">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="74356-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="74356-164">Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.</span><span class="sxs-lookup"><span data-stu-id="74356-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="74356-165">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="74356-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="74356-166">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="74356-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="74356-167">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance-local" aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="74356-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="74356-168">Achten Sie darauf, das gleiche Kennwort einzugeben, das Sie vor der Cloud Connector-Bereitstellung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="74356-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="74356-p110">Für „VmAdmin“ und „DomainAdmin“ wird standardmäßig das gleiche Kennwort wie für „CceService“ verwendet. Wenn in Schritt 1 andere Kennwörter für „DomainAdmin“, „VMAdmin“ und „CceService“ zurückgegeben wurden, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="74356-171">Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="74356-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="74356-172">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="74356-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="74356-173">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „DomainAdmin“ ein.</span><span class="sxs-lookup"><span data-stu-id="74356-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="74356-174">Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="74356-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="74356-175">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="74356-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="74356-176">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „VmAdmin“ ein. </span><span class="sxs-lookup"><span data-stu-id="74356-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="74356-177">Aktualisieren des Kennworts für das CceService-Konto</span><span class="sxs-lookup"><span data-stu-id="74356-177">Update the password for the CceService account</span></span>
<span data-ttu-id="74356-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="74356-179">Dieser Abschnitt gilt für Cloud Connector Version 2.0.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="74356-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="74356-180">Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus.</span><span class="sxs-lookup"><span data-stu-id="74356-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="74356-181">Das CceService-Konto wird während der Cloud Connector Edition-Bereitstellung erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "und"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".</span><span class="sxs-lookup"><span data-stu-id="74356-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="74356-182">Um sicherzustellen, dass alle Appliances auf die Websiteverzeichnis Freigabe zugreifen können, muss das Kennwort für das CceService-Konto auf allen innerhalb der Website bereitgestellten Appliances identisch sein.</span><span class="sxs-lookup"><span data-stu-id="74356-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="74356-183">Berücksichtigen Sie dabei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="74356-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="74356-184">Standardmäßig ist das CceService-Konto als "Kennwort läuft nie ab" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="74356-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="74356-185">Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="74356-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="74356-186">Sie sollten das Kennwort während der Verwendung außerhalb der Spitzenzeiten und außerhalb der Zeitfenster für automatische Updates für Bits oder Windows-Updates aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="74356-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="74356-187">Wenn Sie das Kennwort aktualisieren, muss die Appliance entleert und neu gestartet werden, was einige Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="74356-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="74356-188">Beim Neustart der Appliance werden die automatischen Aktualisierungsvorgänge unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="74356-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="74356-189">Wenn Sie das Kennwort für das CceService-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und in der lokal gespeicherten Datei aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="74356-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="74356-190">Für jede Appliance, die zur gleichen PSTN-Website gehört, müssen Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="74356-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="74356-191">Führen Sie die folgenden Befehle aus, um die Kontonamen und Kennwörter abzurufen, die Sie später verwenden werden:</span><span class="sxs-lookup"><span data-stu-id="74356-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="74356-192">Führen Sie das Cmdlet "Enter-CcUpdate" aus, um die Appliance zu entladen und in den manuellen Wartungsmodus zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="74356-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="74356-193">Aktualisieren Sie das Kennwort des CceService-Kontos auf dem Hostserver.</span><span class="sxs-lookup"><span data-stu-id="74356-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="74356-194">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="74356-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="74356-195">Führen Sie das Cmdlet Restore-CcCredentials aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="74356-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="74356-196">Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben, mit Ausnahme des CceService-Kontos.</span><span class="sxs-lookup"><span data-stu-id="74356-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="74356-197">Geben Sie für das CceService-Konto Ihr neues Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="74356-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="74356-198">Stellen Sie sicher, dass das neue Kennwort für das CceService-Konto für alle Appliances auf der PSTN-Website identisch ist.</span><span class="sxs-lookup"><span data-stu-id="74356-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="74356-p116">Für „VmAdmin“ und „DomainAdmin“ wird standardmäßig das gleiche Kennwort wie für „CceService“ verwendet. Wenn in Schritt 1 andere Kennwörter für „DomainAdmin“, „VMAdmin“ und „CceService“ zurückgegeben wurden, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="74356-201">Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="74356-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="74356-202">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="74356-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="74356-203">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „DomainAdmin“ ein.</span><span class="sxs-lookup"><span data-stu-id="74356-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="74356-204">Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="74356-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="74356-205">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="74356-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="74356-206">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „VmAdmin“ ein. </span><span class="sxs-lookup"><span data-stu-id="74356-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="74356-207">Führen Sie das Cmdlet Exit-CcUpdate aus, um die Appliance aus dem manuellen Wartungsmodus zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="74356-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="74356-208">Nachdem Sie diese Schritte für alle Appliances auf derselben PSTN-Website ausgeführt haben, löschen Sie die folgenden Dateien im Stammverzeichnis der Website:</span><span class="sxs-lookup"><span data-stu-id="74356-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="74356-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="74356-209">CcLockFile</span></span>
    
    - <span data-ttu-id="74356-210">FQDN\<des externen SIP-Pools Site_ Edge\></span><span class="sxs-lookup"><span data-stu-id="74356-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="74356-211">FQDN\<des externen SIP-Pools Tenant_ Edge\></span><span class="sxs-lookup"><span data-stu-id="74356-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="74356-212">FQDN\<des externen SIP-Pools TenantConfigLock_ Edge\></span><span class="sxs-lookup"><span data-stu-id="74356-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="74356-213">Hinzufügen einer neuen SIP-Domäne </span><span class="sxs-lookup"><span data-stu-id="74356-213">Add a new SIP domain</span></span>
<span data-ttu-id="74356-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="74356-215">Gehen Sie wie folgt vor, um Ihrer vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="74356-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="74356-216">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="74356-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="74356-217">Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="74356-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="74356-218">Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder den neuen Domänen.</span><span class="sxs-lookup"><span data-stu-id="74356-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="74356-219">Fordern Sie ein neues Edge-externes Zertifikat mit zusätzlichen San-Namen für SIP. Domain für jede SIP-Domäne an, die in ihrer Cloud Connector-Konfiguration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="74356-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="74356-220">Legen Sie den Pfad für das neue externe Zertifikat des Edges wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="74356-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="74356-221">Befolgen Sie die Anweisungen zum [Ändern der Konfiguration einer einzelnen Site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder [Ändern der Konfiguration mehrerer Sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="74356-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="74356-222">Ändern der primären SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="74356-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="74356-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="74356-224">Wenn Sie die primäre SIP-Domäne in ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="74356-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="74356-225">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="74356-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="74356-226">Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="74356-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="74356-227">Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="74356-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="74356-228">Fordern Sie ein neues Edge-externes Zertifikat mit zusätzlichen San-Namen für SIP. Domain für jede SIP-Domäne an, die in ihrer Cloud Connector-Konfiguration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="74356-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="74356-229">Legen Sie den Pfad für das neue externe Zertifikat des Edges wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="74356-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="74356-230">Entfernen Sie die mandantenregistrierung für jede Appliance auf einer Website, indem Sie das folgende Cmdlet in Administrator-PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="74356-231">Entfernen Sie die Siteregistrierung für jede Site, indem Sie das folgende Cmdlet in Skype for Business Online-PowerShell ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="74356-232">Deinstallieren Sie jede Appliance, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="74356-233">Registrieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="74356-234">Installieren Sie jede Appliance einzeln, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="74356-235">Ersetzen des Zertifikats für externe Edge durch ein neues Zertifikat</span><span class="sxs-lookup"><span data-stu-id="74356-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="74356-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="74356-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="74356-237">Wenn Sie das Zertifikat für externe Edge auf Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edge-Zertifikat anfordern, die PFX-Datei vorbereiten, die den privaten Schlüssel und die vollständige Zertifikatkette enthält, und dann auf jeder Appliance die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="74356-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="74356-238">Setzen Sie die Appliance mithilfe des Cmdlets Enter-CcUpdate in den Wartungsmodus.</span><span class="sxs-lookup"><span data-stu-id="74356-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="74356-239">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="74356-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="74356-240">Wenn das Kennwort des neuen Zertifikats mit dem alten übereinstimmt, wird der Import erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74356-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="74356-241">Wenn das Kennwort anders ist, erhalten Sie eine Fehlermeldung, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das Cmdlet "Register-CcAppliance" mit dem Parameter "-local" ausführen und dann Schritt 2 wiederholen.</span><span class="sxs-lookup"><span data-stu-id="74356-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="74356-242">Verwenden Sie das Cmdlet Exit-CcUpdate, um die Appliance aus dem Wartungsmodus zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="74356-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

