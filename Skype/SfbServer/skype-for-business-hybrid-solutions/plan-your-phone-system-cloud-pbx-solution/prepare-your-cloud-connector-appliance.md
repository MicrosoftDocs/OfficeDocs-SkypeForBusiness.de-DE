---
title: Vorbereiten der Cloud Connector-Appliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Informationen Sie zum Vorbereiten Ihrer Appliance Cloud-Connector für die Bereitstellung und Verwendung mit Telefonsystem in Office 365 (Cloud, PBX).
ms.openlocfilehash: 54ee8394c9da5b00e6a9c9afa7d4a1f3419c2f41
ms.sourcegitcommit: 8a34b5f0295fc6059852dab6971429fda4d30b67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "20176090"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="e200f-103">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="e200f-103">Prepare your Cloud Connector appliance</span></span>
 
<span data-ttu-id="e200f-104">Informationen Sie zum Vorbereiten Ihrer Appliance Cloud-Connector für die Bereitstellung und Verwendung mit Telefonsystem in Office 365 (Cloud, PBX).</span><span class="sxs-lookup"><span data-stu-id="e200f-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>
  
<span data-ttu-id="e200f-105">In diesem Abschnitt wird beschrieben, wie Sie die Installationsdateien für Skype for Business Cloud Connector Edition abrufen, Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance auf die Bereitstellung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="e200f-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="e200f-106">Wenn Sie alle Schritte in diesem Abschnitt abgeschlossen haben, sind Sie bereit, Cloud Connector für einen einzelnen Standort oder für mehrere Standorte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e200f-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="e200f-107">Wenn Sie eine vorhandene Bereitstellung von Cloud-Connector, und Sie noch nicht Cloud Connector Version 2.1 aktualisiert haben, finden Sie unter [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e200f-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e200f-108">Microsoft unterstützt die aktuelle Version von Cloud-Connector Edition, Version 2.1.</span><span class="sxs-lookup"><span data-stu-id="e200f-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="e200f-109">Wenn Sie automatische Updates konfiguriert haben, wird Cloud Connector automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e200f-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="e200f-110">Wenn Sie manuelle Aktualisierung konfiguriert haben, müssen Sie zur Aktualisierung auf Version 2.1 innerhalb von 60 Tagen nach der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="e200f-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="e200f-111">Microsoft unterstützt die vorherige Version 60 Tage nach der Veröffentlichung von 2.1 zu Zeit aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e200f-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e200f-112">Für Cloud-Connector Version 2.1 oder höher muss die Host-Anwendung .NET Framework 4.6.1 oder höher installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e200f-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e200f-113">Für die erfolgreiche Bereitstellung Wenn Sie die Cmdlets zum Konfigurieren von Skype für Business Cloud Connector Edition ausführen, verwenden Sie immer der gleichen konsolensitzung zu, die Sie die Schritte in den.</span><span class="sxs-lookup"><span data-stu-id="e200f-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="e200f-114">Vermeiden Sie es während der Bereitstellung und Konfiguration, zwischen verschiedenen Sitzungen zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="e200f-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e200f-115">Es gibt einige Schritte, die Sie nur für die erste Appliance in der Bereitstellung ausführen: Erstellen einer Freigabe für das Standortverzeichnis, Herunterladen der Bits und Vorbereiten einer VHDX-Datei (Virtual Hard Disk, virtuelle Festplatte) anhand des ISO-Images von Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e200f-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="e200f-116">Herunterladen des Installationsprogramms für Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e200f-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="e200f-117">Laden Sie auf dem Hostserver, in die Cloud Connector VMs ausgeführt wird, die Installationsdateien gespeichert: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="e200f-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e200f-118">Der Hostserver muss in der Lage sein, während der Installation von Cloud Connector eine Internetverbindung herzustellen, da während der Installation zusätzliche Dateien heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 
  
2. <span data-ttu-id="e200f-119">Führen Sie das Installationsprogramm aus und akzeptieren Sie während der Installation die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="e200f-119">Run the installer and accept the default values during the installation.</span></span>
    
3. <span data-ttu-id="e200f-120">Bestätigen Sie, dass die Installation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e200f-120">Confirm that the installation completed successfully.</span></span>
    
## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="e200f-121">Überprüfen der Installation und Konfigurieren der Umgebung</span><span class="sxs-lookup"><span data-stu-id="e200f-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="e200f-122">Öffnen Sie eine PowerShell-Konsole als Administrator, und bestätigen Sie, dass die Skype für Business Cloud Connector Edition Cmdlets sind verfügbar, mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e200f-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>
    
  ```
  Get-Command *-Cc*
  ```

    <span data-ttu-id="e200f-123">Mit dem Befehl sollte eine Liste der Cmdlets für Skype für Business Cloud Connector Edition zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e200f-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>
    
2. <span data-ttu-id="e200f-124">Die VHDs, SfBBits und VersionInfo-Dateien werden im **Websiteverzeichnis** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e200f-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>
    
    <span data-ttu-id="e200f-125">Den Speicherort des **Websiteverzeichnisses** können Sie mit dem folgenden Cmdlet ermitteln:</span><span class="sxs-lookup"><span data-stu-id="e200f-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>
    
  ```
  Get-CcSiteDirectory
  ```

    <span data-ttu-id="e200f-126">Der Befehl sollte einen Speicherort in Ihrem Dateisystem zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e200f-126">The command should return a location in your file system.</span></span> <span data-ttu-id="e200f-127">Bei dem Speicherort kann es sich um einen lokalen Ordner oder um eine Dateifreigabe handeln.</span><span class="sxs-lookup"><span data-stu-id="e200f-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="e200f-128">Der Standardspeicherort für das **Websiteverzeichnis** lautet „%USERPROFILE%\CloudConnector\SiteRoot“.</span><span class="sxs-lookup"><span data-stu-id="e200f-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="e200f-129">Der Standardspeicherort sollte in der ersten für jeden Standort erstellten Appliance in eine Dateifreigabe geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>
    
    <span data-ttu-id="e200f-130">Für den ausgewählten Speicherort muss Folgendes gelten:</span><span class="sxs-lookup"><span data-stu-id="e200f-130">The location you select must be:</span></span>
    
  - <span data-ttu-id="e200f-131">Er wurde in der ersten an jedem Standort erstellten Appliance erstellt.</span><span class="sxs-lookup"><span data-stu-id="e200f-131">Created on the first appliance created in each site.</span></span>
    
  - <span data-ttu-id="e200f-132">Es handelt sich um einen freigegebenen Ordner, auf den andere Hostserver (Appliances) am gleichen Standort zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e200f-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>
    
    <span data-ttu-id="e200f-133">Um das **Websiteverzeichnis** auf einen anderen Speicherort als den Standard festzulegen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="e200f-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    <span data-ttu-id="e200f-134">Wenn Sie Hochverfügbarkeit (HA) für den Standort bereitstellen, vergewissern Sie sich, dass Sie das Cmdlet zum Festlegen des **Websiteverzeichnisses** auf den gleichen Speicherort auf jedem Hostserver innerhalb des Standorts ausführen.</span><span class="sxs-lookup"><span data-stu-id="e200f-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>
    
    <span data-ttu-id="e200f-135">Wenn Sie anmelden und jede Anwendung in der Website bereitstellen, stellen Sie sicher, dass das aktuelle Anmeldekonto Zugriff auf das **Websiteverzeichnis**wurde.</span><span class="sxs-lookup"><span data-stu-id="e200f-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>
    
3. <span data-ttu-id="e200f-136">Das **Verzeichnis Appliance** ist das lokale Arbeiten-Stammverzeichnis für Skype für Business Cloud Connector Edition und den Speicherort, in dem externe Zertifikate und-Instanzen und Protokolle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e200f-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="e200f-137">Der Standardspeicherort ist: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="e200f-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>
    
    <span data-ttu-id="e200f-138">Um den Speicherort des **Appliance-Verzeichnisses** zu suchen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="e200f-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>
    
  ```
  Get-CcApplianceDirectory
  ```

    <span data-ttu-id="e200f-139">Um das **Appliance-Verzeichnis** auf einen anderen Speicherort als den Standard festzulegen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="e200f-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    <span data-ttu-id="e200f-140">Als Appliance-Verzeichnis sollte ein lokaler Ordner in der Appliance festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="e200f-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="e200f-141">Das **Verzeichnis Appliance** sollte nur festgelegt werden, bevor Sie mit der Skype für Business Cloud Connector Edition-Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="e200f-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="e200f-142">Wenn Sie das Verzeichnis nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e200f-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e200f-143">Der Pfad zum **Appliance-Verzeichnis** darf keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e200f-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>
  
## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="e200f-144">Festlegen des Pfads für das externe Zertifikat des Edges</span><span class="sxs-lookup"><span data-stu-id="e200f-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="e200f-p107">Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens zum externen Zertifikat des Edges festzulegen. Beispiel: „C:\certs\cce\ap.contoso.com.pfx“. Das Zertifikat muss private Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="e200f-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="e200f-148">Beachten Sie, dass der Parameter „-Target“ speziell für Version 1.4.2 und höher gilt.</span><span class="sxs-lookup"><span data-stu-id="e200f-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
    <span data-ttu-id="e200f-149">Geben Sie den vollständigen Pfad einschließlich Dateinamen zum externen Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="e200f-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="e200f-150">Das Zertifikat kann lokal oder in einer Dateifreigabe gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="e200f-151">Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, wird der freigegebene Ordner muss auf die erste Appliance jeder Website erstellt werden und muss durch andere Geräte, die auf der gleichen Website gehören zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="e200f-152">Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance-Verzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="e200f-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e200f-153">**Wenn Sie auf Cloud Connector, Version 1.4.2 oder höher, aktualisiert haben**, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel sowie die vollständige Zertifikatkette einschließlich des Zertifikats der Stammzertifizierungsstelle und der Zertifikate der Zwischenzertifizierungsstellen enthält. </span><span class="sxs-lookup"><span data-stu-id="e200f-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="e200f-154">**Wenn Sie noch NICHT auf Cloud Connector, Version 1.4.2, aktualisiert haben**, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="e200f-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="e200f-155">Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt sein, der Windows standardmäßig vertraut.</span><span class="sxs-lookup"><span data-stu-id="e200f-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="e200f-156">Festlegen des Pfads für das externe Zertifikat des PSTN-Gateways/SBC</span><span class="sxs-lookup"><span data-stu-id="e200f-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="e200f-157">Wenn Sie zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC TLS verwenden, führen Sie das folgende Cmdlet aus, um den Pfad (einschließlich des Dateinamens) zum Gatewayzertifikat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e200f-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="e200f-158">Beispiel: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="e200f-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="e200f-159">Das Zertifikat muss die Stammzertifizierungsstelle und die Zwischenkette für das Zertifikat enthalten, das dem Gateway zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="e200f-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> <span data-ttu-id="e200f-160">Beachten Sie, dass der Parameter „-Target“ speziell für Version 1.4.2 und höher gilt.</span><span class="sxs-lookup"><span data-stu-id="e200f-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="e200f-161">Erstellen von virtuellen Switches in Hyper-V-Manager</span><span class="sxs-lookup"><span data-stu-id="e200f-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="e200f-162">Öffnen Sie den **Hyper-V-Manager** > **Virtuellen Switch-Manager**und wählen Sie **Neuen virtuellen Switch-Manager**.</span><span class="sxs-lookup"><span data-stu-id="e200f-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>
    
2. <span data-ttu-id="e200f-163">Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit Ihrer internen Netzwerkdomäne verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="e200f-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>
    
    <span data-ttu-id="e200f-164">Wählen Sie **Gemeinsames Verwenden dieses Netzwerkadapters für das Verwaltungsbetriebssystem zulassen** für diesen virtuellen Switch aus.</span><span class="sxs-lookup"><span data-stu-id="e200f-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
3. <span data-ttu-id="e200f-165">Erstellen Sie einen externen virtuellen Switch, und binden Sie es an die physischen Netzwerkkarte, die mit dem Internet geleitet werden:</span><span class="sxs-lookup"><span data-stu-id="e200f-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>
    
    <span data-ttu-id="e200f-166">Für diese virtuellen Switch **Gemeinsames Verwenden dieses Netzwerkadapters Verwaltungsbetriebssystem zulassen** aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="e200f-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
4. <span data-ttu-id="e200f-167">Legen Sie den Namen des Switches, der Ihrem Umkreisnetzwerk mit Ihrem internen Netzwerkdomäne **SfB CCE Corpnet wechseln**eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="e200f-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>
    
    <span data-ttu-id="e200f-168">Legen Sie den Namen des Switches, der das Umkreisnetzwerk mit dem Internet- **SfB CCE Internet wechseln**verbindet.</span><span class="sxs-lookup"><span data-stu-id="e200f-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>
    
## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="e200f-169">Aktualisieren der Konfigurationsdatei „CloudConnector.ini“</span><span class="sxs-lookup"><span data-stu-id="e200f-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="e200f-170">Vorbereiten der CloudConnector.ini-Datei, die unter Verwendung der Informationen aus den [Determine Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="e200f-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>
  
<span data-ttu-id="e200f-171">Führen Sie zum Aktualisieren der Datei zunächst das folgende Cmdlet aus, um die Beispielvorlage (CloudConnector.Sample.ini) zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="e200f-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>
  
```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="e200f-172">Die Beispielvorlage wird im **Appliance-Verzeichnis** gespeichert. </span><span class="sxs-lookup"><span data-stu-id="e200f-172">The sample template is stored in the **Appliance Directory**.</span></span>
  
<span data-ttu-id="e200f-p111">Nachdem Sie sie mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei als „CloudConnector.ini“ im **Appliance-Verzeichnis**. Sie können **Get-CcApplianceDirectory** ausführen, um den Pfad zum **Appliance-Verzeichnis** zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e200f-p111">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**. You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>
  
<span data-ttu-id="e200f-175">Beachten Sie Folgendes beim Aktualisieren der INI-Datei:</span><span class="sxs-lookup"><span data-stu-id="e200f-175">When updating the .ini file, consider the following:</span></span>
  
> [!NOTE]
> <span data-ttu-id="e200f-176">In diesem Abschnitt werden nicht alle Werte für die INI-Datei besprochen, sondern nur die wichtigsten.</span><span class="sxs-lookup"><span data-stu-id="e200f-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="e200f-177">Eine vollständige Liste finden Sie im Abschnitt " [Determine Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) " neben dem Thema [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="e200f-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="e200f-178">Weitere Informationen zu den Werten, die Sie für zusätzliche Appliances oder neue Standorte ändern müssen, finden Sie unter [Bereitstellung eines einzelnen Standort mit hoher Verfügbarkeit im Vergleich zur Bereitstellung mehrerer Standorte](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Thema [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e200f-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
- <span data-ttu-id="e200f-p113">**SiteName:** Der Standardwert lautet **Site1**. Sie müssen ihn aktualisieren, bevor Sie Cloud Connector bereitstellen können. Der Grund: Wenn Sie **Register-CcAppliance** ausführen, um eine Appliance an einem vorhandenen oder neuen Standort zu registrieren, bestimmt das Cmdlet anhand von **SiteName**, welcher Standort registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e200f-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>
    
     <span data-ttu-id="e200f-181">Wenn Sie die Appliance an einem neuen Standort registrieren möchten, muss der Wert für **SiteName** eindeutig sein und sich von dem für vorhandene Standorte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e200f-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="e200f-182">Wenn Sie die Appliance zu einer vorhandenen Website registrieren möchten, muss der Wert für **SiteName** in INI-Datei in Ihrer Office 365-Mandantenkonfiguration definierten Namen den übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e200f-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="e200f-183">Wenn Sie eine Konfigurationsdatei von einem Standort an einen anderen kopieren, stellen Sie sicher, dass Sie den Wert für **SiteName** für jeden Standort entsprechend aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>
    
- <span data-ttu-id="e200f-184">**ServerName:** Der Servername sollte nicht den Domänennamen enthalten und ist auf 15 Zeichen begrenzt. </span><span class="sxs-lookup"><span data-stu-id="e200f-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>
    
- <span data-ttu-id="e200f-185">**HardwareType:** Wenn Sie nicht festgelegt oder lassen Sie den Wert auf NULL festgelegt, wird der Standardwert der **Normal** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="e200f-186">Wenn Sie die größere Version von Cloud-Connector zur Unterstützung von 500 gleichzeitige Anrufe pro Hostcomputer wie beschrieben unter [Plan for Skype für Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)bereitstellen möchten, verwenden Sie **Normal** .</span><span class="sxs-lookup"><span data-stu-id="e200f-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="e200f-187">Verwenden Sie **Minimum** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e200f-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>
    
- <span data-ttu-id="e200f-p116">**Virtuelle Switches für Internet/Unternehmensnetzwerk/Verwaltung**: Fügen Sie die Namen der virtuellen Switches hinzu, die Sie erstellt haben. Für den virtuellen Switch für die Verwaltung behalten Sie den Standardwert bei. Das Bereitstellungsskript erstellt den virtuellen Switch für die Verwaltung zu Beginn der Bereitstellung und löscht ihn, sobald die Bereitstellung abgeschlossen ist.
</span><span class="sxs-lookup"><span data-stu-id="e200f-p116">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created. For the management virtual switch, leave the default value. The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>
    
- <span data-ttu-id="e200f-p117">**ManagementIPPrefix:** „ManagementIPPrefix“ im Netzwerkabschnitt muss ein anderes Subnetz als das der anderen internen IPs sein. Beispiel: Der Standardwert für „ManagementIPPrefix“ lautet 192.168.213.0, während die AD-IP-Adresse 192.168.0.238 lautet.</span><span class="sxs-lookup"><span data-stu-id="e200f-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>
    
    <span data-ttu-id="e200f-p118">Die Bereitstellungsskripts erstellen auf jedem virtuellen Computer einen Verwaltungs-Netzwerkadapter, weisen eine Verwaltungs-IP zu und verbinden diese mit einem virtuellen Switch für die Verwaltung. Dadurch kann der Hostserver über dieses Verwaltungsnetzwerk eine Verbindung zu jedem virtuellen Computer herstellen und diesen verwalten. Der virtuelle Switch für die Verwaltung wird gelöscht, nachdem die Bereitstellung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e200f-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>
    
- <span data-ttu-id="e200f-196">**Spezifische Konfigurationen für die Basis-VM:** Die Einstellungen in diesem Abschnitt müssen für das Cmdlet **Convert-CcIsoToVhdx** konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>
    
    <span data-ttu-id="e200f-p119">Während der Vorbereitung des Basis-VM-Images wird die Basis-VM mit dem internen Netzwerkswitch verbunden. Die folgenden Einstellungen sind entscheidend, damit die VM auf das Internet zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="e200f-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>
    
  - <span data-ttu-id="e200f-199">[Common]BaseVMIP: die IP-Adresse des Unternehmensnetzwerks, die dem virtuellen Basiscomputer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e200f-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="e200f-200">[Network]CorpnetDefaultGateway: das Standard-Gateway, das dem virtuellen Basiscomputer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e200f-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="e200f-201">[Network]CorpnetDNSIPAddress: die DNS-IP-Adresse, die dem virtuellen Basiscomputer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e200f-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="e200f-202">[Network]WSUSServer: die IP-Adresse des Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="e200f-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>
    
  - <span data-ttu-id="e200f-203">[Network]WSUSStatusServer: die IP-Adresse des Statusservers für den Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="e200f-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>
    
  - <span data-ttu-id="e200f-204">„[Network]EnableReferSupport“: Damit wird definiert, ob SIP REFER-Unterstützung in der Trunk-Konfiguration Ihrer IP-PBX aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e200f-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>
    
- <span data-ttu-id="e200f-205">**Interne IPs:**</span><span class="sxs-lookup"><span data-stu-id="e200f-205">**Internal IPs:**</span></span>
    
  - <span data-ttu-id="e200f-206">Stellen Sie sicher, dass Subnetzmaske CorpnetIPPrefixLength korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="e200f-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="e200f-207">Stellen Sie sicher, dass keine Konflikte IP für diese interne IP-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e200f-207">Make sure there are no IP conflicts for these internal IPs.</span></span>
    
- <span data-ttu-id="e200f-208">**Externe IPs:**</span><span class="sxs-lookup"><span data-stu-id="e200f-208">**External IPs:**</span></span>
    
  - <span data-ttu-id="e200f-209">Für MR öffentliche IP-Adresse: Geben Sie entweder ExternalMRIPs für nicht-NAT oder ExternalMRPublicIPs für NAT</span><span class="sxs-lookup"><span data-stu-id="e200f-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>
    
  - <span data-ttu-id="e200f-210">ExternalSIPIPs und ExternalMRIPs können identisch sein.</span><span class="sxs-lookup"><span data-stu-id="e200f-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>
    
  - <span data-ttu-id="e200f-211">Stellen Sie sicher, dass Subnetzmaske InternetIPPrefixLength korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="e200f-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="e200f-212">Stellen Sie sicher, dass keine Konflikte IP für diese externen IP-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e200f-212">Make sure there are no IP conflicts for these external IPs.</span></span>
    
- <span data-ttu-id="e200f-213">**Gateways:**</span><span class="sxs-lookup"><span data-stu-id="e200f-213">**Gateways:**</span></span>
    
  - <span data-ttu-id="e200f-p120">Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das sekundäre Gateway. Bei mehr als zwei Gateways erstellen Sie zusätzliche Abschnitte, indem Sie den vorhandenen Abschnitt kopieren und einfügen und ihn dann aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>
    
  - <span data-ttu-id="e200f-216">Stellen Sie sicher, dass die IP-Adresse und der Port des bzw. der Gateways korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="e200f-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>
    
  - <span data-ttu-id="e200f-217">Um HA auf PSTN-Gateway-Ebene zu unterstützen, belassen Sie die sekundären Gateways, und fügen Sie alle weiteren Gateways hinzu, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e200f-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="e200f-218">Kopieren und fügen Sie einen vorhandenen Eintrag, und klicken Sie dann zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-218">You can copy and paste an existing entry and then update it.</span></span>
    
- <span data-ttu-id="e200f-219">Optional können Sie den LocalRoute-Wert, um ausgehenden Anruf Nummern einschränken aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>
    
## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="e200f-220">Laden Sie die Bits in das Websiteverzeichnis herunter.</span><span class="sxs-lookup"><span data-stu-id="e200f-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="e200f-221">Führen Sie das folgende Cmdlet aus, um die Bits und Versionsinformationsdateien in das **Websiteverzeichnis** herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="e200f-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>
  
```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="e200f-222">Diesen Schritt müssen Sie nur für die erste Appliance ausführen.</span><span class="sxs-lookup"><span data-stu-id="e200f-222">You need to perform this step for the first appliance only.</span></span> 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="e200f-223">Vorbereiten des virtuellen Basisdatenträgers (VHDX) anhand der heruntergeladenen ISO-Datei</span><span class="sxs-lookup"><span data-stu-id="e200f-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="e200f-224">In diesem Schritt wird eine virtuelle Festplattendatei (VHDX) vom Windows Server 2012 ISO-Image vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="e200f-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="e200f-225">Die VHDX wird zum Erstellen der virtuellen Computer während der Bereitstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e200f-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="e200f-226">Ein temporärer virtuellen Computer (Basis VM) erstellt werden, und Windows Server 2012 aus der ISO-Datei installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e200f-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="e200f-227">Nach Erstellen des virtuellen Computers werden einige erforderliche Komponenten installiert und das neueste Windows-Update angewendet.</span><span class="sxs-lookup"><span data-stu-id="e200f-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="e200f-228">Zum Abschluss wird der virtuelle Basiscomputer generalisiert (sysprep) und bereinigt, sodass nur die generierte virtuelle Festplattendatei zurückbleibt.</span><span class="sxs-lookup"><span data-stu-id="e200f-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e200f-229">Diesen Schritt müssen Sie nur für die erste Appliance ausführen.</span><span class="sxs-lookup"><span data-stu-id="e200f-229">You need to perform this step for the first appliance only.</span></span> 
  
<span data-ttu-id="e200f-p123">Bevor Sie mit diesem Schritt fortfahren, vergewissern Sie sich, dass der Switch für das Unternehmensnetzwerk erstellt wurde. Bestätigen Sie auch, dass die folgenden Einstellungen in der Datei „CloudConnector.ini“ richtig konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="e200f-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>
  
- <span data-ttu-id="e200f-232">[Network] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="e200f-232">[Network]CorpnetSwitchName</span></span>
    
- <span data-ttu-id="e200f-233">[Allgemeine] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="e200f-233">[Common]BaseVMIP</span></span>
    
- <span data-ttu-id="e200f-234">[Network] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="e200f-234">[Network]CorpnetIPPrefixLength</span></span>
    
- <span data-ttu-id="e200f-235">[Network] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="e200f-235">[Network]CorpnetDefaultGateway</span></span>
    
- <span data-ttu-id="e200f-236">[Network] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="e200f-236">[Network]CorpnetDNSIPAddress</span></span>
    
<span data-ttu-id="e200f-237">Starten Sie eine PowerShell-Konsole als Administrator und führen Sie das folgende Cmdlet aus, um das ISO-Image in eine virtuelle Festplatte (VHD) zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="e200f-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="e200f-p124">Geben Sie den vollständigen Pfad einschließlich Dateinamen zum ISO-Image an. Beispiel: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="e200f-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>
  
<span data-ttu-id="e200f-240">Die erstellte VHD-Datei wird im **Websiteverzeichnis** \Bits\VHD Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e200f-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="e200f-241">Sie können den Pfad zum **Websiteverzeichnis** abrufen, indem Sie **Get-CcSiteDirectory** ausführen.</span><span class="sxs-lookup"><span data-stu-id="e200f-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e200f-242">Standardmäßig sind auf dem virtuellen Basiscomputer keine Proxyeinstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e200f-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="e200f-243">Wenn ein Proxy die VM über Windows Update in der Netzwerkumgebung erforderlich ist, sollten Sie die Option - PauseBeforeUpdate hinzufügen, beim Ausführen von "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="e200f-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="e200f-244">Das Skript wird angehalten, bevor Sie Windows Update, und Sie müssen die Möglichkeit, auf dem virtuellen Computer Proxy manuell einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e200f-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="e200f-245">Nachdem der Proxy eingerichtet ist und der VM auf das Internet zugreifen kann, können Sie das Skript wieder aufnehmen und die verbleibenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="e200f-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="e200f-246">Erstellen von VHDs für eine Bereitstellung mit mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="e200f-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="e200f-247">Dieser optionale Schritt ist nur auf Bereitstellungen mit mehreren Standorten anwendbar.</span><span class="sxs-lookup"><span data-stu-id="e200f-247">This is an optional step that applies only to multi-site deployments.</span></span>
  
<span data-ttu-id="e200f-p127">Wenn Sie eine Bereitstellung mit mehreren Standorten bereitstellen, ist es nicht erforderlich, das ISO für jeden Standort in VHD zu konvertieren. Sie können die für den ersten Standort erstellte VHDX für einen zweiten Standort auf den Hostserver kopieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>
  
 <span data-ttu-id="e200f-250">Kopieren Sie die Datei auf den gleichen Speicherort ( **Websiteverzeichnis** \Bits\VHD Ordner) und mit dem gleichen Dateinamen auf den Hostserver für eine zusätzliche Site.</span><span class="sxs-lookup"><span data-stu-id="e200f-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="e200f-251">Festlegen der PowerShell-Ausführungsrichtlinie auf „RemoteSigned“</span><span class="sxs-lookup"><span data-stu-id="e200f-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="e200f-p128">Für die bereitgestellten PowerShell-Skripts muss die Ausführungsrichtlinie auf „RemoteSigned“ festgelegt werden. Um die aktuelle Einstellung anzuzeigen, öffnen Sie eine PowerShell-Konsole als Administrator und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="e200f-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="e200f-254">Wenn die Einstellung nicht „RemoteSigned“ lautet, führen Sie das folgende Cmdlet aus, um sie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="e200f-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="e200f-255">Ändern lokaler Gruppenrichtlinien auf dem Hostcomputer (Version 1.4.1 und niedriger)</span><span class="sxs-lookup"><span data-stu-id="e200f-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="e200f-256">Diese Aufgabe ist für Cloud Connector, Version 1.4.2 und höher, nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e200f-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 
  
<span data-ttu-id="e200f-257">Das Konto „CceService“ wird bei der Bereitstellung von Skype for Business Cloud Connector Edition erstellt.</span><span class="sxs-lookup"><span data-stu-id="e200f-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="e200f-258">Der Cloud Connector-Verwaltungsdienst ausgeführt und erfordert die Berechtigung zum Deinstallieren der cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="e200f-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="e200f-259">Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung bei der Abmeldung des Benutzers nicht entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e200f-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="e200f-260">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e200f-260">Follow the steps below:</span></span>
  
### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="e200f-261">So ändern Sie die Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e200f-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="e200f-262">Öffnen Sie die **Gruppenrichtlinien-Editor** , indem Sie gpedit.msc ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e200f-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>
    
2. <span data-ttu-id="e200f-263">Navigieren Sie im **Gruppenrichtlinien-Editor** zu „Administrative Vorlagen > System > UserProfile“ und zur Option, das Entladen der Benutzerregistrierung bei Abmelden des Benutzers nicht zu erzwingen. </span><span class="sxs-lookup"><span data-stu-id="e200f-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 
    
3. <span data-ttu-id="e200f-264">Legen Sie seinen Wert auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="e200f-264">Set its value to **Enabled**.</span></span>
    
## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="e200f-265">Einrichten des Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="e200f-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="e200f-266">Ein Office 365-Mandanten mit Skype für Business Online und Telefonsystem in Office 365 ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e200f-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="e200f-267">Vergewissern Sie sich Ihrem Mandanten wird eingerichtet und konfiguriert haben, bevor Sie versuchen, Cloud-Connector verwenden.</span><span class="sxs-lookup"><span data-stu-id="e200f-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>
  
<span data-ttu-id="e200f-268">Einige Office 365 Setupschritte müssen Sie Mandanten Remote PowerShell (TRPS) verwenden, um Ihre Office 365-Mandanten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="e200f-269">**Die Installation sollte auf dem Hostserver erfolgen.**</span><span class="sxs-lookup"><span data-stu-id="e200f-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="e200f-270">Sie können die Skype Business Online-Modul für PowerShell aus herunterladen: [Skype für Online Business Windows PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="e200f-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="e200f-271">Erstellen Sie einen dedizierten Skype für Business-Administratorkonto für die Cloud Connector online-Verwaltung, beispielsweise CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e200f-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="e200f-272">Dieses Konto wird von der Appliance verwendet, um eine Appliance hinzuzufügen oder zu entfernen, automatische Betriebssystemaktualisierung zu aktivieren oder zu deaktivieren oder automatische Binärdateiaktualisierung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e200f-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="e200f-273">Legen Sie das Kennwort für dieses Konto so fest, dass es nie abläuft, damit Sie es nicht jedes Mal für den Dienst ändern müssen, wenn es abläuft.</span><span class="sxs-lookup"><span data-stu-id="e200f-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>
  

