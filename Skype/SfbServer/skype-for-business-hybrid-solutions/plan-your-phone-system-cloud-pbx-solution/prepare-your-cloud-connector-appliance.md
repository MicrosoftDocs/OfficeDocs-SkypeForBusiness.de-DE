---
title: Vorbereiten der Cloud Connector-Appliance
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
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und die Verwendung mit dem Telefon System in Office 365 (Cloud PBX) vorbereiten.
ms.openlocfilehash: 6dbbc7eb1639859f889d6674e9f000507912d35a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983840"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="047d3-103">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="047d3-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="047d3-104">Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und die Verwendung mit dem Telefon System in Office 365 (Cloud PBX) vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="047d3-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="047d3-105">In diesem Abschnitt wird beschrieben, wie Sie die Skype for Business Cloud Connector Edition-Installationsdateien abrufen, die Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance für die Bereitstellung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="047d3-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="047d3-106">Nachdem Sie alle Schritte in diesem Abschnitt abgeschlossen haben, sind Sie bereit, Cloud Connector für eine einzelne Website oder mehrere Standorte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="047d3-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="047d3-107">Wenn Sie über eine vorhandene Cloud Connector-Bereitstellung verfügen und noch nicht auf Cloud Connector, Version 2,1, aktualisiert haben, lesen Sie [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="047d3-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="047d3-108">Microsoft unterstützt die aktuelle Version von Cloud Connector Edition, Version 2,1.</span><span class="sxs-lookup"><span data-stu-id="047d3-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="047d3-109">Wenn Sie die automatische Aktualisierung konfiguriert haben, wird Cloud Connector automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="047d3-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="047d3-110">Wenn Sie die manuelle Aktualisierung konfiguriert haben, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung auf Version 2,1 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="047d3-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="047d3-111">Microsoft unterstützt die vorherige Version 60 Tage nach der Veröffentlichung von 2,1, damit Sie Zeit zum Upgrade erhalten.</span><span class="sxs-lookup"><span data-stu-id="047d3-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="047d3-112">Für Cloud Connector, Version 2,1 und höher, muss die Host-Appliance .NET Framework 4.6.1 oder höher installiert haben.</span><span class="sxs-lookup"><span data-stu-id="047d3-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="047d3-113">Verwenden Sie für eine erfolgreiche Bereitstellung beim Ausführen der Cmdlets zum Konfigurieren Skype for Business Cloud Connector Edition immer dieselbe Konsolensitzung wie die, die Sie in gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="047d3-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="047d3-114">Vermeiden Sie während der Bereitstellung und Konfiguration das Wechseln zu anderen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="047d3-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="047d3-115">Es gibt einige Schritte, die Sie nur für die erste Appliance in Ihrer Bereitstellung ausführen: Erstellen einer Freigabe für das Websiteverzeichnis, Herunterladen der Bits und Vorbereiten einer Virtual Hard Disk (VHDX)-Datei aus dem Windows Server-ISO-Image.</span><span class="sxs-lookup"><span data-stu-id="047d3-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="047d3-116">Laden Sie den Skype for Business Cloud Connector Edition-Installer herunter.</span><span class="sxs-lookup"><span data-stu-id="047d3-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="047d3-117">Laden Sie auf dem Hostserver, auf dem die Cloud Connector-VMS ausgeführt werden sollen [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller), die Installationsdateien herunter:.</span><span class="sxs-lookup"><span data-stu-id="047d3-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="047d3-118">Der Hostserver muss während der Installation von Cloud Connector auf das Internet zugreifen können, da während der Installation zusätzliche Dateien heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="047d3-119">Führen Sie das Installationsprogramm aus, und übernehmen Sie die Standardwerte während der Installation.</span><span class="sxs-lookup"><span data-stu-id="047d3-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="047d3-120">Bestätigen Sie, dass die Installation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="047d3-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="047d3-121">Überprüfen der Installation und Konfigurieren der Umgebung</span><span class="sxs-lookup"><span data-stu-id="047d3-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="047d3-122">Öffnen Sie eine PowerShell-Konsole als Administrator, und vergewissern Sie sich, dass die Skype for Business Cloud Connector Edition-Cmdlets mit dem folgenden Cmdlet verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="047d3-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="047d3-123">Der Befehl sollte eine Liste der Cmdlets für Skype for Business Cloud Connector Edition zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="047d3-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="047d3-124">Die VHD-, SfBBits-und VERSIONINFO-Dateien werden im **Websiteverzeichnis**gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047d3-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="047d3-125">Sie können den Speicherort des **Websiteverzeichnisses** mit dem folgenden Cmdlet ermitteln:</span><span class="sxs-lookup"><span data-stu-id="047d3-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="047d3-126">Der Befehl sollte einen Speicherort in Ihrem Dateisystem zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="047d3-126">The command should return a location in your file system.</span></span> <span data-ttu-id="047d3-127">Bei dem Speicherort kann es sich um einen lokalen Ordner oder eine Dateifreigabe handeln.</span><span class="sxs-lookup"><span data-stu-id="047d3-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="047d3-128">Der Standardspeicherort für das **Websiteverzeichnis** lautet:%USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="047d3-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="047d3-129">Der Standardspeicherort sollte in eine Dateifreigabe auf der ersten Appliance geändert werden, die an jedem Standort erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="047d3-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="047d3-130">Der Speicherort, den Sie auswählen, muss wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="047d3-130">The location you select must be:</span></span>

   - <span data-ttu-id="047d3-131">Erstellt auf der ersten Appliance, die an jedem Standort erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="047d3-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="047d3-132">Ein freigegebener Ordner, auf den andere Hostserver (Appliances) am gleichen Standort zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="047d3-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="047d3-133">Um das **Websiteverzeichnis** auf einen anderen Speicherort als den Standardwert festzulegen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="047d3-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="047d3-134">Wenn Sie hohe Verfügbarkeit für die Website bereitstellen, stellen Sie sicher, dass Sie das-Cmdlet ausführen, um das **Websiteverzeichnis** auf jedem Hostserver innerhalb des Standorts auf denselben Speicherort festzulegen.</span><span class="sxs-lookup"><span data-stu-id="047d3-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="047d3-135">Wenn Sie sich anmelden und jede Appliance am Standort bereitstellen, stellen Sie sicher, dass Ihr aktuelles Anmeldekonto über den richtigen Zugriff auf das **Websiteverzeichnis**verfügt.</span><span class="sxs-lookup"><span data-stu-id="047d3-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="047d3-136">Das **Appliance-Verzeichnis** ist das lokale Arbeits Stammverzeichnis für Skype for Business Cloud Connector Edition und der Speicherort, an dem externe Zertifikate, Instanzen und Protokolle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="047d3-137">Der Standardspeicherort ist:%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="047d3-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="047d3-138">Führen Sie das folgende Cmdlet aus, um den Speicherort des **Appliance-Verzeichnisses**zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="047d3-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="047d3-139">Um das **Appliance-Verzeichnis** auf einen anderen Speicherort als den Standardwert festzulegen, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="047d3-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="047d3-140">Das Appliance-Verzeichnis sollte auf einen lokalen Ordner der Appliance festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="047d3-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="047d3-141">Legen Sie das Appliance- **Verzeichnis** nur vor dem Start der Skype for Business Cloud Connector Edition-Bereitstellung fest.</span><span class="sxs-lookup"><span data-stu-id="047d3-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="047d3-142">Wenn Sie Sie nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="047d3-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="047d3-143">Der Pfad zum **Appliance-Verzeichnis** darf keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="047d3-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="047d3-144">Festlegen des Pfads für das Zertifikat für externe Edges</span><span class="sxs-lookup"><span data-stu-id="047d3-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="047d3-145">Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Datei namens auf das externe Edge-Zertifikat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="047d3-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="047d3-146">Beispiel: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="047d3-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="047d3-147">Das Zertifikat muss private Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="047d3-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="047d3-148">Beachten Sie, dass der-target-Parameter für die Versionen 1.4.2 und höher spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="047d3-149">Geben Sie den vollständigen Pfad zum externen Zertifikat an, einschließlich des Datei namens.</span><span class="sxs-lookup"><span data-stu-id="047d3-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="047d3-150">Das Zertifikat kann lokal oder in einer Dateifreigabe gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="047d3-151">Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, muss der freigegebene Ordner auf der ersten Appliance jedes Standorts erstellt werden und von anderen Appliances, die demselben Standort angehören, zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="047d3-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="047d3-152">Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance-Verzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="047d3-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="047d3-153">**Wenn Sie auf Cloud Connector, Version 1.4.2 oder höher, aktualisiert haben**, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel und die vollständige Zertifikatkette einschließlich des Stammzertifizierungsstellen-Zertifikats und der Zwischenzertifizierungsstellen Zertifikate enthält.</span><span class="sxs-lookup"><span data-stu-id="047d3-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="047d3-154">**Wenn Sie noch nicht auf Cloud Connector, Version 1.4.2, aktualisiert haben**, stellen Sie sicher, dass das vorbereitete externe Zertifikat private Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="047d3-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="047d3-155">Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt werden, die standardmäßig von Windows als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="047d3-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="047d3-156">Festlegen des Pfads für das externe PSTN-Gateway/SBC-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="047d3-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="047d3-157">Wenn Sie TLS zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC verwenden, führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Datei namens auf das Gateway-Zertifikat festzulegen.</span><span class="sxs-lookup"><span data-stu-id="047d3-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="047d3-158">Beispiel: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="047d3-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="047d3-159">Das Zertifikat muss die Stammzertifizierungsstelle und die zwischen Kette für das dem Gateway zugewiesene Zertifikat enthalten:</span><span class="sxs-lookup"><span data-stu-id="047d3-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="047d3-160">Beachten Sie, dass der-target-Parameter für die Versionen 1.4.2 und höher spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="047d3-161">Erstellen virtueller Switches in Hyper-V-Manager</span><span class="sxs-lookup"><span data-stu-id="047d3-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="047d3-162">Öffnen Sie den**Virtual Switch Manager**für **Hyper-V Manager** > , und wählen Sie **neuer virtueller Switch-Manager**aus.</span><span class="sxs-lookup"><span data-stu-id="047d3-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="047d3-163">Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit ihrer internen Netzwerkdomäne verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="047d3-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="047d3-164">Wählen Sie **Verwaltung Betriebssystem zulassen aus, um diesen Netzwerkadapter** für diesen virtuellen Switch freizugeben.</span><span class="sxs-lookup"><span data-stu-id="047d3-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="047d3-165">Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der an das Internet weitergeleitet wird:</span><span class="sxs-lookup"><span data-stu-id="047d3-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="047d3-166">Deaktivieren Sie die Option Verwaltungsbetriebssystem für diesen virtuellen Switch **freigeben, um diesen Netzwerkadapter freizugeben** .</span><span class="sxs-lookup"><span data-stu-id="047d3-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="047d3-167">Legen Sie den Namen des Switches, der Ihr Umkreisnetzwerk mit ihrer internen Netzwerkdomäne verbindet, mit dem **SFB CCE Corpnet Switch**fest.</span><span class="sxs-lookup"><span data-stu-id="047d3-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="047d3-168">Legen Sie den Namen des Switches fest, der Ihr Umkreisnetzwerk mit dem Internet- **Switch des SFB CCE**verbindet.</span><span class="sxs-lookup"><span data-stu-id="047d3-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="047d3-169">Aktualisieren der Konfigurationsdatei "cloudconnector. ini</span><span class="sxs-lookup"><span data-stu-id="047d3-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="047d3-170">Bereiten Sie die Datei "cloudconnector. ini mit den Informationen vor, die Sie unter [bestimmen der Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Planen für Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) gesammelt haben.</span><span class="sxs-lookup"><span data-stu-id="047d3-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="047d3-171">Um die Datei zu aktualisieren, führen Sie zuerst das folgende Cmdlet aus, um die Beispielvorlage ("cloudconnector. Sample. ini) abzurufen:</span><span class="sxs-lookup"><span data-stu-id="047d3-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="047d3-172">Die Beispielvorlage wird im Appliance- **Verzeichnis**gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047d3-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="047d3-173">Nachdem Sie es mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei als "cloudconnector. ini im **Appliance-Verzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="047d3-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="047d3-174">Sie können **Get-CcApplianceDirectory** ausführen, um den Pfad zum **Appliance-Verzeichnis**zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="047d3-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="047d3-175">Berücksichtigen Sie beim Aktualisieren der INI-Datei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="047d3-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="047d3-176">Nicht alle Werte für die. ini-Datei werden in diesem Abschnitt behandelt, sondern nur diejenigen, die eine besondere Überlegung haben.</span><span class="sxs-lookup"><span data-stu-id="047d3-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="047d3-177">Eine vollständige Liste finden Sie im Abschnitt [bestimmen der Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="047d3-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="047d3-178">Weitere Informationen darüber, welche Werte für zusätzliche Appliances oder neue Websites geändert werden müssen, finden Sie unter [Single Site with High Availability (ha) im Vergleich zu Multi-Site-Bereitstellungen](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Thema [deploy multiple Sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="047d3-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="047d3-179">**Sitename:** Der Standardwert ist **site1**.</span><span class="sxs-lookup"><span data-stu-id="047d3-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="047d3-180">Sie müssen es vor der Bereitstellung von Cloud Connector aktualisieren, da das Cmdlet beim Ausführen von **Register-ccappliance "** zum Registrieren einer Appliance auf einem vorhandenen oder neuen Standort den Standort Sitename **verwendet, um zu** ermitteln, welche Website registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="047d3-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="047d3-181">Wenn Sie die Appliance auf einem neuen Standort registrieren möchten, muss der Wert von **Sitename** eindeutig sein und sich von vorhandenen Websites unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="047d3-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="047d3-182">Wenn Sie die Appliance auf einem vorhandenen Standort registrieren möchten, muss der Wert für **Sitename** in. ini mit dem in der Office 365 Mandanten Konfiguration definierten Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="047d3-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="047d3-183">Wenn Sie eine Konfigurationsdatei von einer Website in eine andere kopieren, stellen Sie sicher, dass Sie den Wert **für Sitename für jeden** Standort entsprechend aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="047d3-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="047d3-184">**Servername:** Der Servername sollte nicht den Domänennamen enthalten und sollte auf 15 Zeichen reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="047d3-185">**Hardwaretyp:** Wenn Sie den Wert nicht auf NULL festlegen oder beibehalten, wird der Standardwert **Normal** verwendet.</span><span class="sxs-lookup"><span data-stu-id="047d3-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="047d3-186">Verwenden Sie **Normal** , wenn Sie die größere Version von Cloud Connector zur Unterstützung von 500 gleichzeitigen Anrufen pro Hostcomputer bereitstellen möchten, wie unter [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="047d3-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="047d3-187">Verwenden Sie **mindestens** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="047d3-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="047d3-188">**Virtuelle Switches für Internet/Corpnet/Verwaltung:**: Fügen Sie den Namen der virtuellen Switches hinzu, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="047d3-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="047d3-189">Lassen Sie den Standardwert für den virtuellen Switch für die Verwaltung unverändert.</span><span class="sxs-lookup"><span data-stu-id="047d3-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="047d3-190">Das Bereitstellungsskript erstellt den virtuellen Switch für die Verwaltung zu Beginn der Bereitstellung und löscht ihn, sobald die Bereitstellung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="047d3-191">**ManagementIPPrefix:** ManagementIPPrefix im Abschnitt "Netzwerk" muss ein anderes Subnetz als andere interne IPS sein.</span><span class="sxs-lookup"><span data-stu-id="047d3-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="047d3-192">Wenn beispielsweise der Standardwert angezeigt wird, ist ManagementIPPrefix 192.168.213.0, während AD-IPAddress 192.168.0.238 ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="047d3-193">Die Bereitstellungsskripts erstellen einen Verwaltungsnetzwerkadapter auf jedem virtuellen Computer, weisen eine Verwaltungs-IP zu und verbinden ihn mit einem virtuellen Switch für die Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="047d3-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="047d3-194">Dadurch kann der Hostserver über dieses Verwaltungsnetzwerk eine Verbindung zu jedem virtuellen Computer herstellen und ihn verwalten.</span><span class="sxs-lookup"><span data-stu-id="047d3-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="047d3-195">Der virtuelle Verwaltungs Switch wird gelöscht, wenn die Bereitstellung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="047d3-196">**Grundlegende VM-spezifische Konfigurationen:** Die Einstellungen in diesem Abschnitt müssen für das Cmdlet **Convert-CcIsoToVhdx** konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="047d3-197">Während der Vorbereitung des Basis-VM-Images wird die Basis-VM mit dem internen Netzwerk Switch verbunden.</span><span class="sxs-lookup"><span data-stu-id="047d3-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="047d3-198">Die folgenden Einstellungen sind wichtig, damit die VM auf das Internet zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="047d3-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="047d3-199">Common BaseVMIP: die Corpnet-IP-Adresse, die der Basis-VM zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="047d3-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="047d3-200">Netzwerk CorpnetDefaultGateway: das Standardgateway, das der Basis-VM zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="047d3-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="047d3-201">Netzwerk CorpnetDNSIPAddress: die DNS-IP-Adresse, die der Basis-VM zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="047d3-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="047d3-202">Netzwerk WSUSServer: die IP-Adresse des Windows Server-Update Diensts.</span><span class="sxs-lookup"><span data-stu-id="047d3-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="047d3-203">Netzwerk WSUSStatusServer: die IP-Adresse des Windows Server Update Service-Statusservers.</span><span class="sxs-lookup"><span data-stu-id="047d3-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="047d3-204">Netzwerk "Enablerefersupport": Dadurch wird definiert, ob SIP-Refer-Unterstützung für die trunk Konfiguration für Ihre IP/Nebenstellenanlage aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="047d3-205">**Interne IPS:**</span><span class="sxs-lookup"><span data-stu-id="047d3-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="047d3-206">Stellen Sie sicher, dass Subnetzmaske CorpnetIPPrefixLength korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="047d3-207">Stellen Sie sicher, dass für diese internen IPS keine IP-Konflikte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="047d3-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="047d3-208">**Externe IPS:**</span><span class="sxs-lookup"><span data-stu-id="047d3-208">**External IPs:**</span></span>

  - <span data-ttu-id="047d3-209">Für Mr Public IP: Geben Sie entweder "externalmrips" für nicht-NAT oder ExternalMRPublicIPs für NAT an.</span><span class="sxs-lookup"><span data-stu-id="047d3-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="047d3-210">ExternalSIPIPs und "externalmrips" können identisch sein.</span><span class="sxs-lookup"><span data-stu-id="047d3-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="047d3-211">Stellen Sie sicher, dass Subnetzmaske InternetIPPrefixLength korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="047d3-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="047d3-212">Stellen Sie sicher, dass es keine IP-Konflikte für diese externen IPS gibt.</span><span class="sxs-lookup"><span data-stu-id="047d3-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="047d3-213">**Gateways**</span><span class="sxs-lookup"><span data-stu-id="047d3-213">**Gateways:**</span></span>

  - <span data-ttu-id="047d3-214">Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das sekundäre Gateway.</span><span class="sxs-lookup"><span data-stu-id="047d3-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="047d3-215">Wenn Sie über mehr als zwei Gateways verfügen, erstellen Sie zusätzliche Abschnitte, indem Sie das vorhandene kopieren und einfügen und dann aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="047d3-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="047d3-216">Stellen Sie sicher, dass die IP-Adresse und der Port der Gateways korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="047d3-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="047d3-217">Um die PSTN-Gatewayebene ha zu unterstützen, lassen Sie das sekundäre Gateway, und fügen Sie alle zusätzlichen Gateways hinzu, die Sie verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="047d3-218">Sie können einen vorhandenen Eintrag kopieren und einfügen und ihn dann aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="047d3-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="047d3-219">Optional können Sie den LocalRoute-Wert aktualisieren, um ausgehende Rufnummern einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="047d3-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="047d3-220">Laden Sie die Bits in das Websiteverzeichnis herunter.</span><span class="sxs-lookup"><span data-stu-id="047d3-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="047d3-221">Führen Sie das folgende Cmdlet aus, um die Bits-und Versions Informationsdateien in das **Websiteverzeichnis**herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="047d3-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="047d3-222">Sie müssen diesen Schritt nur für die erste Appliance ausführen.</span><span class="sxs-lookup"><span data-stu-id="047d3-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="047d3-223">Vorbereiten des virtuellen Basisdatenträgers (VHDX) aus der heruntergeladenen ISO-Datei</span><span class="sxs-lookup"><span data-stu-id="047d3-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="047d3-224">In diesem Schritt wird eine VHDX-Datei (Virtual Hard Disk) aus dem Windows Server 2012 ISO-Abbild vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="047d3-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="047d3-225">Die VHDX wird zum Erstellen virtueller Computer während der Bereitstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="047d3-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="047d3-226">Ein temporärer virtueller Computer (Basis-VM) wird erstellt, und Windows Server 2012 werden aus der ISO-Datei installiert.</span><span class="sxs-lookup"><span data-stu-id="047d3-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="047d3-227">Nachdem die VM erstellt wurde, werden einige erforderliche Komponenten installiert, und das neueste Windows-Update wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="047d3-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="047d3-228">Am Ende wird die Basis-VM generalisiert (Sysprep) und bereinigt, sodass nur die generierte virtuelle Datenträgerdatei bleibt.</span><span class="sxs-lookup"><span data-stu-id="047d3-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="047d3-229">Sie müssen diesen Schritt nur für die erste Appliance ausführen.</span><span class="sxs-lookup"><span data-stu-id="047d3-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="047d3-230">Bevor Sie mit diesem Schritt fortfahren, stellen Sie sicher, dass der Corpnet-Schalter erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="047d3-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="047d3-231">Vergewissern Sie sich außerdem, dass die folgenden Einstellungen in der Datei "cloudconnector. ini ordnungsgemäß konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="047d3-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="047d3-232">Netzwerk CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="047d3-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="047d3-233">Common BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="047d3-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="047d3-234">Netzwerk CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="047d3-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="047d3-235">Netzwerk CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="047d3-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="047d3-236">Netzwerk CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="047d3-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="047d3-237">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um das ISO-Abbild auf eine virtuelle Festplatte (VHD) zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="047d3-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="047d3-238">Geben Sie den vollständigen Pfad einschließlich des Datei namens in das ISO-Abbild ein.</span><span class="sxs-lookup"><span data-stu-id="047d3-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="047d3-239">Beispiel: C:\ISO\WindowsServer2012R2.ISO.</span><span class="sxs-lookup"><span data-stu-id="047d3-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="047d3-240">Die erstellte VHD-Datei wird im Ordner \Bits\VHD des **Websiteverzeichnisses** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047d3-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="047d3-241">Sie können den Pfad zum **Websiteverzeichnis** abrufen, indem Sie das **Get-CcSiteDirectory-** Objekt durchführen.</span><span class="sxs-lookup"><span data-stu-id="047d3-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="047d3-242">Standardmäßig sind Proxyeinstellungen nicht auf der Basis-VM konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="047d3-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="047d3-243">Wenn ein Proxy in Ihrer Netzwerkumgebung erforderlich ist, um den virtuellen Computer über Windows Update zu aktualisieren, sollten Sie den-PauseBeforeUpdate-Schalter bei der Ausführung von "Convert-CcIsoToVhdx" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="047d3-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="047d3-244">Das Skript wird vor Windows Update angehalten, und Sie haben die Möglichkeit, einen Proxy für die VM manuell einzurichten.</span><span class="sxs-lookup"><span data-stu-id="047d3-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="047d3-245">Nachdem der Proxy eingerichtet wurde und der VM auf das Internet zugreifen kann, können Sie das Skript fortsetzen, um die verbleibenden Schritte abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="047d3-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="047d3-246">Erstellen von virtuellen Festplatten für eine Bereitstellung mit mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="047d3-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="047d3-247">Dies ist ein optionaler Schritt, der nur für Bereitstellungen mit mehreren Standorten gilt.</span><span class="sxs-lookup"><span data-stu-id="047d3-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="047d3-248">Wenn Sie eine Bereitstellung mit mehreren Standorten bereitstellen, müssen Sie die ISO nicht für jeden Standort in eine VHD konvertieren.</span><span class="sxs-lookup"><span data-stu-id="047d3-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="047d3-249">Sie können die für die erste Website erstellte VHDX für einen zweiten Standort auf den Hostserver kopieren.</span><span class="sxs-lookup"><span data-stu-id="047d3-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="047d3-250">Kopieren Sie die Datei an denselben Dateispeicherort ( **Standortverzeichnis** \Bits\VHD-Ordner) und denselben Dateinamen auf dem Hostserver für einen zusätzlichen Standort.</span><span class="sxs-lookup"><span data-stu-id="047d3-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="047d3-251">Festlegen der PowerShell-Ausführungsrichtlinie auf RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="047d3-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="047d3-252">Für die bereitgestellten PowerShell-Skripts muss die Ausführungsrichtlinie auf RemoteSigned festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="047d3-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="047d3-253">Um die aktuelle Einstellung anzuzeigen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="047d3-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="047d3-254">Wenn er nicht auf "RemoteSigned" festgelegt ist, führen Sie das folgende Cmdlet aus, um es zu ändern:</span><span class="sxs-lookup"><span data-stu-id="047d3-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="047d3-255">Ändern der lokalen Gruppenrichtlinie auf dem Hostcomputer (Version 1.4.1 und früher)</span><span class="sxs-lookup"><span data-stu-id="047d3-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="047d3-256">Diese Aufgabe ist für Cloud Connector-Versionen 1.4.2 und höher nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="047d3-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="047d3-257">Das "cceservice"-Konto wird während der Skype for Business Cloud Connector Edition-Bereitstellung erstellt.</span><span class="sxs-lookup"><span data-stu-id="047d3-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="047d3-258">Er führt den Cloud Connector-Verwaltungsdienst aus und erfordert die Berechtigung zum Deinstallieren von "cloudconnector. msi.</span><span class="sxs-lookup"><span data-stu-id="047d3-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="047d3-259">Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung nicht entladen werden soll, wenn sich der Benutzer abmeldet.</span><span class="sxs-lookup"><span data-stu-id="047d3-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="047d3-260">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="047d3-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="047d3-261">So ändern Sie die Gruppenrichtlinieneinstellung</span><span class="sxs-lookup"><span data-stu-id="047d3-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="047d3-262">Öffnen Sie den **Gruppenrichtlinien-Editor** , indem Sie gpedit. msc verwenden.</span><span class="sxs-lookup"><span data-stu-id="047d3-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="047d3-263">Navigieren Sie im **Gruppenrichtlinien-Editor**zu Administrative Vorlagen > System > User Profile, um die Benutzerregistrierung beim Abmelden des Benutzers nicht gewaltsam zu entladen >.</span><span class="sxs-lookup"><span data-stu-id="047d3-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="047d3-264">Legen Sie den Wert auf **aktiviert**fest.</span><span class="sxs-lookup"><span data-stu-id="047d3-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="047d3-265">Einrichten des Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="047d3-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="047d3-266">Ein Office 365 Mandant mit Skype for Business Online-und Telefon System in Office 365 ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="047d3-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="047d3-267">Stellen Sie sicher, dass Ihr Mandant eingerichtet und konfiguriert ist, bevor Sie versuchen, Cloud Connector zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="047d3-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="047d3-268">Für einige Office 365-Setupschritte müssen Sie die mandantenfähige Remote-PowerShell (TRPS) zum Konfigurieren Ihres Office 365 Mandanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="047d3-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="047d3-269">**Diese sollte auf dem Hostserver installiert sein.**</span><span class="sxs-lookup"><span data-stu-id="047d3-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="047d3-270">Sie können das Skype for Business Online Modul für PowerShell unter: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="047d3-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="047d3-271">Erstellen Sie ein dediziertes Skype for Business Administratorkonto für die Online Verwaltung von Cloud Connector, beispielsweise CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="047d3-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="047d3-272">Dieses Konto wird von Appliance zum Hinzufügen oder Entfernen von Appliance, aktivieren oder Deaktivieren des automatischen Betriebssystemupdates, aktivieren oder Deaktivieren der automatischen binären Aktualisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="047d3-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="047d3-273">Legen Sie das Kennwort für dieses Konto so fest, dass es nie abläuft, damit Sie es nicht bei jedem Ablauf des Diensts ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="047d3-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


