---
title: Vorbereiten der Cloud Connector-Appliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Informationen Sie zum Vorbereiten Ihrer Appliance Cloud-Connector für die Bereitstellung und Verwendung mit Telefonsystem in Office 365 (Cloud, PBX).
ms.openlocfilehash: 8dcc15d2feb12516025afb5e60d916f94a81fa57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="24bb6-103">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="24bb6-103">Prepare your Cloud Connector appliance</span></span>
 
<span data-ttu-id="24bb6-104">Informationen Sie zum Vorbereiten Ihrer Appliance Cloud-Connector für die Bereitstellung und Verwendung mit Telefonsystem in Office 365 (Cloud, PBX).</span><span class="sxs-lookup"><span data-stu-id="24bb6-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>
  
<span data-ttu-id="24bb6-105">In diesem Abschnitt wird beschrieben, wie Sie die Installationsdateien für Skype for Business Cloud Connector Edition abrufen, Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance auf die Bereitstellung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="24bb6-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="24bb6-106">Wenn Sie alle Schritte in diesem Abschnitt abgeschlossen haben, sind Sie bereit, Cloud Connector für einen einzelnen Standort oder für mehrere Standorte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="24bb6-107">Wenn Sie eine vorhandene Bereitstellung von Cloud-Connector, und Sie noch nicht Cloud Connector Version 2.1 aktualisiert haben, finden Sie unter [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="24bb6-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="24bb6-108">Microsoft unterstützt die aktuelle Version von Cloud-Connector Edition, Version 2.1.</span><span class="sxs-lookup"><span data-stu-id="24bb6-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="24bb6-109">Wenn Sie automatische Updates konfiguriert haben, wird Cloud Connector automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="24bb6-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="24bb6-110">Wenn Sie manuelle Aktualisierung konfiguriert haben, müssen Sie zur Aktualisierung auf Version 2.1 innerhalb von 60 Tagen nach der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="24bb6-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="24bb6-111">Microsoft unterstützt die vorherige Version 60 Tage nach der Veröffentlichung von 2.1 zu Zeit aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="24bb6-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24bb6-112">Für Cloud-Connector Version 2.1 oder höher muss die Host-Anwendung .NET Framework 4.6.1 oder höher installiert sein.</span><span class="sxs-lookup"><span data-stu-id="24bb6-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="24bb6-113">Für die erfolgreiche Bereitstellung Wenn Sie die Cmdlets zum Konfigurieren von Skype für Business Cloud Connector Edition ausführen, verwenden Sie immer der gleichen konsolensitzung zu, die Sie die Schritte in den.</span><span class="sxs-lookup"><span data-stu-id="24bb6-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="24bb6-114">Vermeiden Sie es während der Bereitstellung und Konfiguration, zwischen verschiedenen Sitzungen zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="24bb6-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24bb6-115">Es gibt einige Schritte, die Sie nur für die erste Appliance in der Bereitstellung ausführen: Erstellen einer Freigabe für das Standortverzeichnis, Herunterladen der Bits und Vorbereiten einer VHDX-Datei (Virtual Hard Disk, virtuelle Festplatte) anhand des ISO-Images von Windows Server.</span><span class="sxs-lookup"><span data-stu-id="24bb6-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="24bb6-116">Herunterladen des Installationsprogramms für Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="24bb6-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="24bb6-117">Laden Sie auf dem Hostserver, in die Cloud Connector VMs ausgeführt wird, die Installationsdateien gespeichert: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="24bb6-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="24bb6-118">Der Hostserver muss in der Lage sein, während der Installation von Cloud Connector eine Internetverbindung herzustellen, da während der Installation zusätzliche Dateien heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 
  
2. <span data-ttu-id="24bb6-119">Führen Sie das Installationsprogramm aus und akzeptieren Sie während der Installation die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="24bb6-119">Run the installer and accept the default values during the installation.</span></span>
    
3. <span data-ttu-id="24bb6-120">Bestätigen Sie, dass die Installation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="24bb6-120">Confirm that the installation completed successfully.</span></span>
    
## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="24bb6-121">Überprüfen der Installation und Konfigurieren der Umgebung</span><span class="sxs-lookup"><span data-stu-id="24bb6-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="24bb6-122">Öffnen Sie eine PowerShell-Konsole als Administrator, und bestätigen Sie, dass die Skype für Business Cloud Connector Edition Cmdlets sind verfügbar, mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="24bb6-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>
    
  ```
  Get-Command *-Cc*
  ```

    <span data-ttu-id="24bb6-123">Mit dem Befehl sollte eine Liste der Cmdlets für Skype für Business Cloud Connector Edition zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24bb6-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>
    
2. <span data-ttu-id="24bb6-124">Die VHDs, SfBBits und VersionInfo-Dateien werden im **Websiteverzeichnis** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="24bb6-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>
    
    <span data-ttu-id="24bb6-125">Den Speicherort des **Websiteverzeichnisses** können Sie mit dem folgenden Cmdlet ermitteln:</span><span class="sxs-lookup"><span data-stu-id="24bb6-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>
    
  ```
  Get-CcSiteDirectory
  ```

    <span data-ttu-id="24bb6-126">Der Befehl sollte einen Speicherort in Ihrem Dateisystem zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="24bb6-126">The command should return a location in your file system.</span></span> <span data-ttu-id="24bb6-127">Bei dem Speicherort kann es sich um einen lokalen Ordner oder um eine Dateifreigabe handeln.</span><span class="sxs-lookup"><span data-stu-id="24bb6-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="24bb6-128">Der Standardspeicherort für das **Websiteverzeichnis** lautet „%USERPROFILE%\CloudConnector\SiteRoot“.</span><span class="sxs-lookup"><span data-stu-id="24bb6-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="24bb6-129">Der Standardspeicherort sollte in der ersten für jeden Standort erstellten Appliance in eine Dateifreigabe geändert werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>
    
    <span data-ttu-id="24bb6-130">Für den ausgewählten Speicherort muss Folgendes gelten:</span><span class="sxs-lookup"><span data-stu-id="24bb6-130">The location you select must be:</span></span>
    
  - <span data-ttu-id="24bb6-131">Er wurde in der ersten an jedem Standort erstellten Appliance erstellt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-131">Created on the first appliance created in each site.</span></span>
    
  - <span data-ttu-id="24bb6-132">Es handelt sich um einen freigegebenen Ordner, auf den andere Hostserver (Appliances) am gleichen Standort zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="24bb6-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>
    
    <span data-ttu-id="24bb6-133">Um das **Websiteverzeichnis** auf einen anderen Speicherort als den Standard festzulegen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24bb6-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    <span data-ttu-id="24bb6-134">Wenn Sie Hochverfügbarkeit (HA) für den Standort bereitstellen, vergewissern Sie sich, dass Sie das Cmdlet zum Festlegen des **Websiteverzeichnisses** auf den gleichen Speicherort auf jedem Hostserver innerhalb des Standorts ausführen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>
    
    <span data-ttu-id="24bb6-135">Wenn Sie anmelden und jede Anwendung in der Website bereitstellen, stellen Sie sicher, dass das aktuelle Anmeldekonto Zugriff auf das **Websiteverzeichnis**wurde.</span><span class="sxs-lookup"><span data-stu-id="24bb6-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>
    
3. <span data-ttu-id="24bb6-136">Das **Verzeichnis Appliance** ist das lokale Arbeiten-Stammverzeichnis für Skype für Business Cloud Connector Edition und den Speicherort, in dem externe Zertifikate und-Instanzen und Protokolle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="24bb6-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="24bb6-137">Der Standardspeicherort ist: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="24bb6-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>
    
    <span data-ttu-id="24bb6-138">Um den Speicherort des **Appliance-Verzeichnisses** zu suchen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24bb6-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>
    
  ```
  Get-CcApplianceDirectory
  ```

    <span data-ttu-id="24bb6-139">Um das **Appliance-Verzeichnis** auf einen anderen Speicherort als den Standard festzulegen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24bb6-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    <span data-ttu-id="24bb6-140">Als Appliance-Verzeichnis sollte ein lokaler Ordner in der Appliance festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="24bb6-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="24bb6-141">Das **Verzeichnis Appliance** sollte nur festgelegt werden, bevor Sie mit der Skype für Business Cloud Connector Edition-Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="24bb6-142">Wenn Sie das Verzeichnis nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="24bb6-143">Der Pfad zum **Appliance-Verzeichnis** darf keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="24bb6-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>
  
## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="24bb6-144">Festlegen des Pfads für das externe Zertifikat des Edges</span><span class="sxs-lookup"><span data-stu-id="24bb6-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="24bb6-p107">Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens zum externen Zertifikat des Edges festzulegen. Beispiel: „C:\certs\cce\ap.contoso.com.pfx“. Das Zertifikat muss private Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="24bb6-148">Beachten Sie, dass der Parameter „-Target“ speziell für Version 1.4.2 und höher gilt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
    <span data-ttu-id="24bb6-149">Geben Sie den vollständigen Pfad einschließlich Dateinamen zum externen Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="24bb6-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="24bb6-150">Das Zertifikat kann lokal oder in einer Dateifreigabe gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="24bb6-151">Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, wird der freigegebene Ordner muss auf die erste Appliance jeder Website erstellt werden und muss durch andere Geräte, die auf der gleichen Website gehören zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="24bb6-152">Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance-Verzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="24bb6-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="24bb6-153">**Wenn Sie Cloud Connector Version 1.4.2 aktualisiert haben oder höher**, sicherzustellen, dass Ihr vorbereitete externe Zertifikat enthält, privaten Schlüssel und die vollständige Zertifikatkette, einschließlich der Stammzertifizierungsstelle und die intermediate Zertifizierungsstelle Zertifikate. > **, wenn Sie haben Noch nicht aktualisierten Cloud Connector Version 1.4.2**, stellen Sie sicher, dass Ihr vorbereitete externe Zertifikat privaten Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="24bb6-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.> **If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="24bb6-154">Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt sein, der Windows standardmäßig vertraut.</span><span class="sxs-lookup"><span data-stu-id="24bb6-154">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="24bb6-155">Festlegen des Pfads für das externe Zertifikat des PSTN-Gateways/SBC</span><span class="sxs-lookup"><span data-stu-id="24bb6-155">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="24bb6-156">Wenn Sie zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC TLS verwenden, führen Sie das folgende Cmdlet aus, um den Pfad (einschließlich des Dateinamens) zum Gatewayzertifikat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-156">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="24bb6-157">Beispiel: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="24bb6-157">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="24bb6-158">Das Zertifikat muss die Stammzertifizierungsstelle und die Zwischenkette für das Zertifikat enthalten, das dem Gateway zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="24bb6-158">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> <span data-ttu-id="24bb6-159">Beachten Sie, dass der Parameter „-Target“ speziell für Version 1.4.2 und höher gilt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-159">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="24bb6-160">Erstellen von virtuellen Switches in Hyper-V-Manager</span><span class="sxs-lookup"><span data-stu-id="24bb6-160">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="24bb6-161">Öffnen Sie den **Hyper-V-Manager** > **Virtuellen Switch-Manager**und wählen Sie **Neuen virtuellen Switch-Manager**.</span><span class="sxs-lookup"><span data-stu-id="24bb6-161">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>
    
2. <span data-ttu-id="24bb6-162">Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit Ihrer internen Netzwerkdomäne verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="24bb6-162">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>
    
    <span data-ttu-id="24bb6-163">Wählen Sie **Gemeinsames Verwenden dieses Netzwerkadapters für das Verwaltungsbetriebssystem zulassen** für diesen virtuellen Switch aus.</span><span class="sxs-lookup"><span data-stu-id="24bb6-163">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
3. <span data-ttu-id="24bb6-164">Erstellen Sie einen externen virtuellen Switch, und binden Sie es an die physischen Netzwerkkarte, die mit dem Internet geleitet werden:</span><span class="sxs-lookup"><span data-stu-id="24bb6-164">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>
    
    <span data-ttu-id="24bb6-165">Für diese virtuellen Switch **Gemeinsames Verwenden dieses Netzwerkadapters Verwaltungsbetriebssystem zulassen** aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="24bb6-165">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
4. <span data-ttu-id="24bb6-166">Legen Sie den Namen des Switches, der Ihrem Umkreisnetzwerk mit Ihrem internen Netzwerkdomäne **SfB CCE Corpnet wechseln**eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-166">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>
    
    <span data-ttu-id="24bb6-167">Legen Sie den Namen des Switches, der das Umkreisnetzwerk mit dem Internet- **SfB CCE Internet wechseln**verbindet.</span><span class="sxs-lookup"><span data-stu-id="24bb6-167">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>
    
## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="24bb6-168">Aktualisieren der Konfigurationsdatei „CloudConnector.ini“</span><span class="sxs-lookup"><span data-stu-id="24bb6-168">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="24bb6-169">Vorbereiten der CloudConnector.ini-Datei, die unter Verwendung der Informationen aus den [Determine Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="24bb6-169">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>
  
<span data-ttu-id="24bb6-170">Führen Sie zum Aktualisieren der Datei zunächst das folgende Cmdlet aus, um die Beispielvorlage (CloudConnector.Sample.ini) zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="24bb6-170">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>
  
```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="24bb6-171">Die Beispielvorlage wird im **Appliance-Verzeichnis** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="24bb6-171">The sample template is stored in the **Appliance Directory**.</span></span>
  
<span data-ttu-id="24bb6-172">Nachdem Sie sie mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei als „CloudConnector.ini“ im **Appliance-Verzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="24bb6-172">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="24bb6-173">Führen Sie **Get-CcApplianceDirectory** , um den Pfad zu dem **Verzeichnis Appliance**zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-173">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>
  
<span data-ttu-id="24bb6-174">Beachten Sie Folgendes beim Aktualisieren der INI-Datei:</span><span class="sxs-lookup"><span data-stu-id="24bb6-174">When updating the .ini file, consider the following:</span></span>
  
> [!NOTE]
> <span data-ttu-id="24bb6-175">In diesem Abschnitt werden nicht alle Werte für die INI-Datei besprochen, sondern nur die wichtigsten.</span><span class="sxs-lookup"><span data-stu-id="24bb6-175">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="24bb6-176">Eine vollständige Liste finden Sie im Abschnitt [Determine Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) des [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md) Thema. > Weitere Informationen dazu, welche Werte für zusätzliche Einheiten oder neue Websites geändert werden müssen, finden Sie unter [ Einzelne Website mit hoher Verfügbarkeit (HA) im Vergleich zu Bereitstellungen mit mehreren Standorten](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Thema[mehrere Standorte in der Cloud Connector bereitstellen](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="24bb6-176">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.> For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
- <span data-ttu-id="24bb6-p113">**SiteName:** Der Standardwert lautet **Site1**. Sie müssen ihn aktualisieren, bevor Sie Cloud Connector bereitstellen können. Der Grund: Wenn Sie **Register-CcAppliance** ausführen, um eine Appliance an einem vorhandenen oder neuen Standort zu registrieren, bestimmt das Cmdlet anhand von **SiteName**, welcher Standort registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>
    
     <span data-ttu-id="24bb6-179">Wenn Sie die Appliance an einem neuen Standort registrieren möchten, muss der Wert für **SiteName** eindeutig sein und sich von dem für vorhandene Standorte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-179">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="24bb6-180">Wenn Sie die Appliance zu einer vorhandenen Website registrieren möchten, muss der Wert für **SiteName** in INI-Datei in Ihrer Office 365-Mandantenkonfiguration definierten Namen den übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-180">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="24bb6-181">Wenn Sie eine Konfigurationsdatei von einem Standort an einen anderen kopieren, stellen Sie sicher, dass Sie den Wert für **SiteName** für jeden Standort entsprechend aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-181">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>
    
- <span data-ttu-id="24bb6-182">**ServerName:** Der Servername sollte nicht den Domänennamen enthalten und ist auf 15 Zeichen begrenzt. </span><span class="sxs-lookup"><span data-stu-id="24bb6-182">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>
    
- <span data-ttu-id="24bb6-183">**HardwareType:** Wenn Sie nicht festgelegt oder lassen Sie den Wert auf NULL festgelegt, wird der Standardwert der **Normal** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-183">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="24bb6-184">Wenn Sie die größere Version von Cloud-Connector zur Unterstützung von 500 gleichzeitige Anrufe pro Hostcomputer wie beschrieben unter [Plan for Skype für Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)bereitstellen möchten, verwenden Sie **Normal** .</span><span class="sxs-lookup"><span data-stu-id="24bb6-184">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="24bb6-185">Verwenden Sie **Minimum** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-185">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>
    
- <span data-ttu-id="24bb6-186">**Virtuelle Switches für Internet/Unternehmensnetzwerk/Verwaltung**: Fügen Sie die Namen der virtuellen Switches hinzu, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="24bb6-186">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="24bb6-187">Für den virtuellen Switch für die Verwaltung behalten Sie den Standardwert bei.</span><span class="sxs-lookup"><span data-stu-id="24bb6-187">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="24bb6-188">Das Bereitstellungsskript erstellt den virtuellen Switch für die Verwaltung zu Beginn der Bereitstellung und löscht ihn, sobald die Bereitstellung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="24bb6-188">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>
    
- <span data-ttu-id="24bb6-p117">**ManagementIPPrefix:** „ManagementIPPrefix“ im Netzwerkabschnitt muss ein anderes Subnetz als das der anderen internen IPs sein. Beispiel: Der Standardwert für „ManagementIPPrefix“ lautet 192.168.213.0, während die AD-IP-Adresse 192.168.0.238 lautet.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>
    
    <span data-ttu-id="24bb6-p118">Die Bereitstellungsskripts erstellen auf jedem virtuellen Computer einen Verwaltungs-Netzwerkadapter, weisen eine Verwaltungs-IP zu und verbinden diese mit einem virtuellen Switch für die Verwaltung. Dadurch kann der Hostserver über dieses Verwaltungsnetzwerk eine Verbindung zu jedem virtuellen Computer herstellen und diesen verwalten. Der virtuelle Switch für die Verwaltung wird gelöscht, nachdem die Bereitstellung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>
    
- <span data-ttu-id="24bb6-194">**Base VM-spezifische Konfigurationen:** Einstellungen in diesem Abschnitt müssen für das Cmdlet **Convert-CcIsoToVhdx** konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-194">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>
    
    <span data-ttu-id="24bb6-p119">Während der Vorbereitung des Basis-VM-Images wird die Basis-VM mit dem internen Netzwerkswitch verbunden. Die folgenden Einstellungen sind entscheidend, damit die VM auf das Internet zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="24bb6-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>
    
  - <span data-ttu-id="24bb6-197">[Common]BaseVMIP: die IP-Adresse des Unternehmensnetzwerks, die dem virtuellen Basiscomputer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24bb6-197">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="24bb6-198">[Network]CorpnetDefaultGateway: das Standard-Gateway, das dem virtuellen Basiscomputer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24bb6-198">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="24bb6-199">[Network]CorpnetDNSIPAddress: die DNS-IP-Adresse, die dem virtuellen Basiscomputer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24bb6-199">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="24bb6-200">[Network]WSUSServer: die IP-Adresse des Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="24bb6-200">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>
    
  - <span data-ttu-id="24bb6-201">[Network]WSUSStatusServer: die IP-Adresse des Statusservers für den Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="24bb6-201">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>
    
  - <span data-ttu-id="24bb6-202">„[Network]EnableReferSupport“: Damit wird definiert, ob SIP REFER-Unterstützung in der Trunk-Konfiguration Ihrer IP-PBX aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="24bb6-202">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>
    
- <span data-ttu-id="24bb6-203">**Interne IPs:**</span><span class="sxs-lookup"><span data-stu-id="24bb6-203">**Internal IPs:**</span></span>
    
  - <span data-ttu-id="24bb6-204">Stellen Sie sicher, dass Subnetzmaske CorpnetIPPrefixLength korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="24bb6-204">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="24bb6-205">Stellen Sie sicher, dass keine Konflikte IP für diese interne IP-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="24bb6-205">Make sure there are no IP conflicts for these internal IPs.</span></span>
    
- <span data-ttu-id="24bb6-206">**Externe IPs:**</span><span class="sxs-lookup"><span data-stu-id="24bb6-206">**External IPs:**</span></span>
    
  - <span data-ttu-id="24bb6-207">Für MR öffentliche IP-Adresse: Geben Sie entweder ExternalMRIPs für nicht-NAT oder ExternalMRPublicIPs für NAT</span><span class="sxs-lookup"><span data-stu-id="24bb6-207">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>
    
  - <span data-ttu-id="24bb6-208">ExternalSIPIPs und ExternalMRIPs können identisch sein.</span><span class="sxs-lookup"><span data-stu-id="24bb6-208">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>
    
  - <span data-ttu-id="24bb6-209">Stellen Sie sicher, dass Subnetzmaske InternetIPPrefixLength korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="24bb6-209">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="24bb6-210">Stellen Sie sicher, dass keine Konflikte IP für diese externen IP-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="24bb6-210">Make sure there are no IP conflicts for these external IPs.</span></span>
    
- <span data-ttu-id="24bb6-211">**Gateways:**</span><span class="sxs-lookup"><span data-stu-id="24bb6-211">**Gateways:**</span></span>
    
  - <span data-ttu-id="24bb6-p120">Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das sekundäre Gateway. Bei mehr als zwei Gateways erstellen Sie zusätzliche Abschnitte, indem Sie den vorhandenen Abschnitt kopieren und einfügen und ihn dann aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>
    
  - <span data-ttu-id="24bb6-214">Stellen Sie sicher, dass die IP-Adresse und der Port des bzw. der Gateways korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="24bb6-214">Make sure that the IP address and port of the gateway(s) are correct.</span></span>
    
  - <span data-ttu-id="24bb6-215">Um HA auf PSTN-Gateway-Ebene zu unterstützen, belassen Sie die sekundären Gateways, und fügen Sie alle weiteren Gateways hinzu, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="24bb6-215">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="24bb6-216">Kopieren und fügen Sie einen vorhandenen Eintrag, und klicken Sie dann zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-216">You can copy and paste an existing entry and then update it.</span></span>
    
- <span data-ttu-id="24bb6-217">Optional können Sie den LocalRoute-Wert, um ausgehenden Anruf Nummern einschränken aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-217">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>
    
## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="24bb6-218">Laden Sie die Bits in das Websiteverzeichnis herunter.</span><span class="sxs-lookup"><span data-stu-id="24bb6-218">Download the bits to the Site Directory</span></span>

<span data-ttu-id="24bb6-219">Führen Sie das folgende Cmdlet aus, um die Bits und Versionsinformationsdateien in das **Websiteverzeichnis** herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="24bb6-219">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>
  
```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="24bb6-220">Diesen Schritt müssen Sie nur für die erste Appliance ausführen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-220">You need to perform this step for the first appliance only.</span></span> 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="24bb6-221">Vorbereiten des virtuellen Basisdatenträgers (VHDX) anhand der heruntergeladenen ISO-Datei</span><span class="sxs-lookup"><span data-stu-id="24bb6-221">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="24bb6-222">In diesem Schritt wird eine virtuelle Festplattendatei (VHDX) vom Windows Server 2012 ISO-Image vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="24bb6-222">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="24bb6-223">Die VHDX wird zum Erstellen der virtuellen Computer während der Bereitstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="24bb6-223">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="24bb6-224">Ein temporärer virtuellen Computer (Basis VM) erstellt werden, und Windows Server 2012 aus der ISO-Datei installiert werden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-224">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="24bb6-225">Nach Erstellen des virtuellen Computers werden einige erforderliche Komponenten installiert und das neueste Windows-Update angewendet.</span><span class="sxs-lookup"><span data-stu-id="24bb6-225">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="24bb6-226">Zum Abschluss wird der virtuelle Basiscomputer generalisiert (sysprep) und bereinigt, sodass nur die generierte virtuelle Festplattendatei zurückbleibt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-226">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24bb6-227">Diesen Schritt müssen Sie nur für die erste Appliance ausführen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-227">You need to perform this step for the first appliance only.</span></span> 
  
<span data-ttu-id="24bb6-p123">Bevor Sie mit diesem Schritt fortfahren, vergewissern Sie sich, dass der Switch für das Unternehmensnetzwerk erstellt wurde. Bestätigen Sie auch, dass die folgenden Einstellungen in der Datei „CloudConnector.ini“ richtig konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="24bb6-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>
  
- <span data-ttu-id="24bb6-230">[Network] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="24bb6-230">[Network]CorpnetSwitchName</span></span>
    
- <span data-ttu-id="24bb6-231">[Allgemeine] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="24bb6-231">[Common]BaseVMIP</span></span>
    
- <span data-ttu-id="24bb6-232">[Network] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="24bb6-232">[Network]CorpnetIPPrefixLength</span></span>
    
- <span data-ttu-id="24bb6-233">[Network] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="24bb6-233">[Network]CorpnetDefaultGateway</span></span>
    
- <span data-ttu-id="24bb6-234">[Network] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="24bb6-234">[Network]CorpnetDNSIPAddress</span></span>
    
<span data-ttu-id="24bb6-235">Starten Sie eine PowerShell-Konsole als Administrator und führen Sie das folgende Cmdlet aus, um das ISO-Image in eine virtuelle Festplatte (VHD) zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="24bb6-235">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="24bb6-p124">Geben Sie den vollständigen Pfad einschließlich Dateinamen zum ISO-Image an. Beispiel: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>
  
<span data-ttu-id="24bb6-238">Die erstellte VHD-Datei wird im **Websiteverzeichnis** \Bits\VHD Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="24bb6-238">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="24bb6-239">Sie können den Pfad zum **Websiteverzeichnis** abrufen, indem Sie **Get-CcSiteDirectory** ausführen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-239">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="24bb6-240">Standardmäßig sind auf dem virtuellen Basiscomputer keine Proxyeinstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="24bb6-240">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="24bb6-241">Wenn ein Proxy die VM über Windows Update in der Netzwerkumgebung erforderlich ist, sollten Sie die Option - PauseBeforeUpdate hinzufügen, beim Ausführen von "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="24bb6-241">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="24bb6-242">Das Skript wird angehalten, bevor Sie Windows Update, und Sie müssen die Möglichkeit, auf dem virtuellen Computer Proxy manuell einzurichten.</span><span class="sxs-lookup"><span data-stu-id="24bb6-242">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="24bb6-243">Nachdem der Proxy eingerichtet ist und der VM auf das Internet zugreifen kann, können Sie das Skript wieder aufnehmen und die verbleibenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="24bb6-243">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="24bb6-244">Erstellen von VHDs für eine Bereitstellung mit mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="24bb6-244">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="24bb6-245">Dieser optionale Schritt ist nur auf Bereitstellungen mit mehreren Standorten anwendbar.</span><span class="sxs-lookup"><span data-stu-id="24bb6-245">This is an optional step that applies only to multi-site deployments.</span></span>
  
<span data-ttu-id="24bb6-p127">Wenn Sie eine Bereitstellung mit mehreren Standorten bereitstellen, ist es nicht erforderlich, das ISO für jeden Standort in VHD zu konvertieren. Sie können die für den ersten Standort erstellte VHDX für einen zweiten Standort auf den Hostserver kopieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>
  
 <span data-ttu-id="24bb6-248">Kopieren Sie die Datei auf den gleichen Speicherort ( **Websiteverzeichnis** \Bits\VHD Ordner) und mit dem gleichen Dateinamen auf den Hostserver für eine zusätzliche Site.</span><span class="sxs-lookup"><span data-stu-id="24bb6-248">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="24bb6-249">Festlegen der PowerShell-Ausführungsrichtlinie auf „RemoteSigned“</span><span class="sxs-lookup"><span data-stu-id="24bb6-249">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="24bb6-p128">Für die bereitgestellten PowerShell-Skripts muss die Ausführungsrichtlinie auf „RemoteSigned“ festgelegt werden. Um die aktuelle Einstellung anzuzeigen, öffnen Sie eine PowerShell-Konsole als Administrator und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24bb6-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="24bb6-252">Wenn die Einstellung nicht „RemoteSigned“ lautet, führen Sie das folgende Cmdlet aus, um sie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="24bb6-252">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="24bb6-253">Ändern lokaler Gruppenrichtlinien auf dem Hostcomputer (Version 1.4.1 und niedriger)</span><span class="sxs-lookup"><span data-stu-id="24bb6-253">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="24bb6-254">Diese Aufgabe ist für Cloud Connector, Version 1.4.2 und höher, nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24bb6-254">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 
  
<span data-ttu-id="24bb6-255">Das Konto „CceService“ wird bei der Bereitstellung von Skype for Business Cloud Connector Edition erstellt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-255">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="24bb6-256">Der Cloud Connector-Verwaltungsdienst ausgeführt und erfordert die Berechtigung zum Deinstallieren der cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="24bb6-256">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="24bb6-257">Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung bei der Abmeldung des Benutzers nicht entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="24bb6-257">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="24bb6-258">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24bb6-258">Follow the steps below:</span></span>
  
### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="24bb6-259">So ändern Sie die Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="24bb6-259">To change the Group Policy setting</span></span>

1. <span data-ttu-id="24bb6-260">Öffnen Sie die **Gruppenrichtlinien-Editor** , indem Sie gpedit.msc ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="24bb6-260">Open the **Group Policy Editor** by running gpedit.msc.</span></span>
    
2. <span data-ttu-id="24bb6-261">Navigieren Sie im **Gruppenrichtlinien-Editor** zu „Administrative Vorlagen > System > UserProfile“ und zur Option, das Entladen der Benutzerregistrierung bei Abmelden des Benutzers nicht zu erzwingen. </span><span class="sxs-lookup"><span data-stu-id="24bb6-261">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 
    
3. <span data-ttu-id="24bb6-262">Legen Sie seinen Wert auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="24bb6-262">Set its value to **Enabled**.</span></span>
    
## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="24bb6-263">Einrichten des Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="24bb6-263">Set up your Office 365 tenant</span></span>

<span data-ttu-id="24bb6-264">Ein Office 365-Mandanten mit Skype für Business Online und Telefonsystem in Office 365 ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24bb6-264">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="24bb6-265">Vergewissern Sie sich Ihrem Mandanten wird eingerichtet und konfiguriert haben, bevor Sie versuchen, Cloud-Connector verwenden.</span><span class="sxs-lookup"><span data-stu-id="24bb6-265">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>
  
<span data-ttu-id="24bb6-266">Einige Office 365 Setupschritte müssen Sie Mandanten Remote PowerShell (TRPS) verwenden, um Ihre Office 365-Mandanten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-266">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="24bb6-267">**Die Installation sollte auf dem Hostserver erfolgen.**</span><span class="sxs-lookup"><span data-stu-id="24bb6-267">**This should be installed on the host server.**</span></span> <span data-ttu-id="24bb6-268">Sie können die Skype Business Online-Modul für PowerShell aus herunterladen:[Skype für Online Business Windows PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="24bb6-268">You can download the Skype for Business Online module for PowerShell from:[Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="24bb6-269">Erstellen Sie einen dedizierten Skype für Business-Administratorkonto für die Cloud Connector online-Verwaltung, beispielsweise CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="24bb6-269">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="24bb6-270">Dieses Konto wird von der Appliance verwendet, um eine Appliance hinzuzufügen oder zu entfernen, automatische Betriebssystemaktualisierung zu aktivieren oder zu deaktivieren oder automatische Binärdateiaktualisierung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="24bb6-270">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="24bb6-271">Legen Sie das Kennwort für dieses Konto so fest, dass es nie abläuft, damit Sie es nicht jedes Mal für den Dienst ändern müssen, wenn es abläuft.</span><span class="sxs-lookup"><span data-stu-id="24bb6-271">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>
  

