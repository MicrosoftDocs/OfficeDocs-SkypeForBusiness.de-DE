---
title: Bereitstellen von Skype Raum Systeme mithilfe von System Center Configuration Manager
ms.author: jambirk
author: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lesen Sie dieses Thema zu erfahren Sie mehr über die Bereitstellung von Skype Raum Systemen v2 auf umfangreiche Bereitstellungen.
ms.openlocfilehash: c84517ba5ceb7eea582b379c8cabe5014dde43d5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372752"
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="4e4f0-103">Bereitstellen von Skype Raum Systemen v2 mithilfe von System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e4f0-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="4e4f0-104">In diesem Artikel können Sie die erforderliche Informationen zu Ihrer Skype Raum Systemen v2-Bereitstellungen mithilfe von System Center Configuration Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="4e4f0-105">Mit den Methoden leicht zu bedienende zur Verfügung gestellt von System Center Configuration Manager können Sie das Betriebssystem und andere Anwendungen für mehrere Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="4e4f0-106">Verwenden Sie den unten dargestellten, durch die Konfiguration der Konfigurations-Manager, leiten Ansatz, und passen Sie die Beispielpaketen und der Bedarf für Ihre Organisation in dieser Anleitung bereitgestellten Skripts.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Skype-Chatroom-Systemen v2 Bereitstellungsprozess von Configuration Manager](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="4e4f0-108">Diese Lösung wurde mit Surface Pro basierenden Bereitstellungen nur getestet.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="4e4f0-109">Folgen Sie den Hersteller Richtlinien für Konfigurationen, die nicht auf Surface Pro basieren.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="4e4f0-110">Überprüfen Sie die Komponenten</span><span class="sxs-lookup"><span data-stu-id="4e4f0-110">Validate prerequisites</span></span>

<span data-ttu-id="4e4f0-111">Um Skype Raum Systemen v2 mit Configuration Manager bereitstellen, stellen Sie sicher, dass die folgenden Voraussetzungen und Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="4e4f0-112">System Center Configuration Manager-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e4f0-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="4e4f0-113">System Center Configuration Manager Version muss mindestens 1706 oder höher.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="4e4f0-114">Es wird empfohlen, 1710 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="4e4f0-115">Checken Sie [Unterstützung für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) , um Informationen zu den Windows-10-Versionen zu erhalten, der Konfigurations-Manager unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="4e4f0-116">Eine unterstützte Version von Windows Assessment and Deployment Kit (ADK) für Windows 10 muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="4e4f0-117">Finden Sie unter den Versionen von [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) , die Sie mit verschiedenen Versionen von Configuration Manager verwenden können, und stellen Sie sicher, dass Ihre Bereitstellung die richtige Version umfasst.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="4e4f0-118">Die Servern des Systems müssen zugewiesen wurden die Verteilung Point-Rolle, und die Startabbilder beim für So aktivieren Sie Netzwerk initiierte Bereitstellungen [vor dem Start Unterstützung des PXE-Umgebung ()](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="4e4f0-119">Wenn PXE-Unterstützung nicht aktiviert ist, können Sie für die Bereitstellung [startbaren Medium](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="4e4f0-120">Ein Netzwerk für den Inhaltszugriff muss zur Unterstützung der neuen Computer (bare-Metal) Bereitstellungsszenarien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="4e4f0-121">Mehr über die Konfiguration des ein Netzwerk für den Inhaltszugriff finden Sie unter [Verwalten von Konten Zugriff auf die Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="4e4f0-122">Wir empfehlen, dass Sie [multicast-Support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), aktivieren, wenn Sie wahrscheinlich dasselbe Skype Raum Systemen v2 Bild für mehrere Einheiten zur selben Zeit bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="4e4f0-123">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="4e4f0-123">Networking requirements</span></span>

-   <span data-ttu-id="4e4f0-124">Ihr Netzwerk sollte auf einen Dynamic Host Configuration Protocol (DHCP)-Server konfiguriert werden, für die automatische Verteilung von IP-Adresse an die Subnetze dem Skype Raum Systemen v2 Einheiten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4e4f0-125">Die DHCP-Lease muss auf einen anderen Wert länger als die Dauer der Bild-Bereitstellung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="4e4f0-126">Andernfalls kann die Bereitstellung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="4e4f0-127">Im Netzwerk, einschließlich Switches und virtuelle LANs (VLANs), sollte so konfiguriert werden, dass PXE unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="4e4f0-128">Hersteller Ihres für Weitere Informationen zur Konfiguration von IP-Hilfsprogramm und PXE finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="4e4f0-129">Alternativ können Sie [startbaren Medien](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) für die Bereitstellung verwenden, wenn PXE-Unterstützung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4e4f0-130">Für Surface Pro werden Geräte, über das Netzwerk (PXE-Start) starten nur unterstützt, wenn Sie einen Ethernet-Adapter oder Dockingstation von Microsoft verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="4e4f0-131">Drittanbieter-Ethernet-Adapter unterstützen nicht PXE-Start mit Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="4e4f0-132">Weitere Informationen finden Sie unter [Ethernet-Adapter und Fläche Bereitstellung](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="4e4f0-133">Konfigurieren von System Center Configuration Manager für die Bereitstellung eines Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="4e4f0-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="4e4f0-134">In diesem Artikel wird vorausgesetzt, Sie bereits ist eine fehlerfreie Bereitstellung von System Center Configuration Manager, und nicht Detail alle die erforderlichen Schritte zum Bereitstellen und Konfigurieren von Configuration Manager von Grund auf neu.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="4e4f0-135">Die [Dokumentation und die Konfiguration Anleitung](https://docs.microsoft.com/sccm/) für System Center Configuration Manager ist eine hervorragende Ressource. Es wird empfohlen, dass Sie mit diesen Ressourcen starten, wenn Sie noch Konfigurations-Manager bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="4e4f0-136">Gehen Sie folgendermaßen vor, um sicherzustellen, dass das Betriebssystem Bereitstellungsfeatures (OSD) ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="4e4f0-137">Überprüfen und Aktualisieren von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e4f0-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="4e4f0-138">Navigieren Sie in der Configuration Manager-Konsole zu **Administration** \> **Updates und Wartung**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="4e4f0-139">Überprüfen der installierten Build und die anwendbaren Aktualisierungen, die noch nicht installiert wurden haben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="4e4f0-140">Überprüfen Sie die [Unterstützung für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Wenn Sie die Bereitstellung aktualisieren müssen, wählen Sie das Update installieren möchten, und wählen Sie dann **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="4e4f0-141">Nachdem der Download abgeschlossen ist, wählen Sie das Update, und wählen Sie dann **Update Pack installieren**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="4e4f0-142">Konfigurieren von Verteilungspunkte PXE und Multicast-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4e4f0-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="4e4f0-143">Navigieren Sie in der Configuration Manager-Konsole zu **Administration** \> **Verteilungspunkte**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="4e4f0-144">Wählen Sie den Verteilung Punkt Server, der die Skype Raum Systemen v2 Bereitstellung dienen, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="4e4f0-145">Wählen Sie die **PXE** -Registerkarte, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="4e4f0-146">Aktivieren der PXE-Unterstützung für clients</span><span class="sxs-lookup"><span data-stu-id="4e4f0-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="4e4f0-147">Zulassen Sie dieser Verteilungspunkt auf eingehende PXE-Anfragen reagieren</span><span class="sxs-lookup"><span data-stu-id="4e4f0-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="4e4f0-148">Aktivieren der Unterstützung von unbekannten computer</span><span class="sxs-lookup"><span data-stu-id="4e4f0-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="4e4f0-149">*Optional:* Um multicast-Support zu aktivieren, wählen Sie die **Multicast** -Registerkarte, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="4e4f0-150">Aktivieren Sie Multicast zum Senden von Daten für mehrere Clients gleichzeitig</span><span class="sxs-lookup"><span data-stu-id="4e4f0-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="4e4f0-151">Konfigurieren Sie den UDP-Port-Bereich gemäß den Anweisungen in Ihr Netzwerkteam Empfehlung</span><span class="sxs-lookup"><span data-stu-id="4e4f0-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="4e4f0-152">Konfigurieren Sie das Netzwerk für den Inhaltszugriff</span><span class="sxs-lookup"><span data-stu-id="4e4f0-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="4e4f0-153">Navigieren Sie in der Configuration Manager-Konsole zu **Administration** \> **Standortkonfiguration** \> **Websites**, und wählen Sie dann die Website.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="4e4f0-154">Wählen Sie in der Gruppe **Einstellungen** **Konfigurieren Websitekomponenten** \> **Software Distribution**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="4e4f0-155">Wählen Sie die Registerkarte **Netzwerk für den Inhaltszugriff** festlegen, eine oder mehrere Konten, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="4e4f0-156">Die Konten benötigen keine spezielle Rechte, mit Ausnahme der **auf diesen Computer über das Netzwerk** direkt auf dem Verteilergruppen Point-Server.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="4e4f0-157">Eine generische Domänenbenutzerkonto wird geeignet.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="4e4f0-158">Weitere Informationen finden Sie unter [Verwalten von Konten Zugriff auf die Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="4e4f0-159">Konfigurieren einer Boot-Bild</span><span class="sxs-lookup"><span data-stu-id="4e4f0-159">Configure a boot image</span></span>

1.  <span data-ttu-id="4e4f0-160">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssystem** \> **Boot Bilder**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="4e4f0-161">Wählen Sie **Start-Image (x64)**, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="4e4f0-162">Wählen Sie die Registerkarte **Datenquelle** aus, und aktivieren Sie **diese Boot-Abbild vom PXE-fähige Verteilungspunkt bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="4e4f0-163">Wählen Sie die **Optionalen Komponenten** -Registerkarte, um die erforderlichen Komponenten zu installieren:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="4e4f0-164">Wählen Sie Stern-Symbol, und suchen Sie nach **HTML (Windows PE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="4e4f0-165">Wählen Sie **OK** , um die Unterstützung von HTML in dem Boot-Abbild hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="4e4f0-166">*Optional:* Zum Anpassen der Bereitstellung, wählen Sie die Registerkarte **Anpassung** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="4e4f0-167">Aktivieren Sie **Befehl unterstützen (nur zu Testzwecken)** aus, wenn Sie während der Bereitstellung in einem Eingabeaufforderungsfenster zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="4e4f0-168">Wenn diese Option aktiviert ist, können Sie ein Eingabeaufforderungsfenster, indem Sie **F8** auswählen, können Sie jederzeit während der Bereitstellung starten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="4e4f0-169">Sie können auch ein benutzerdefiniertes Hintergrundbild während der Bereitstellung anzuzeigende angeben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="4e4f0-170">Aktivieren, um ein Bild festzulegen, **Geben Sie die benutzerdefinierten Hintergrund Image-Datei (UNC-Pfad** , und wählen Sie den Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="4e4f0-171">Wenn Sie aufgefordert werden, wählen Sie **Ja** aus, und verteilen Sie das aktualisierte Boot Image an Ihre Verteilungspunkte.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="4e4f0-172">Weitere Informationen finden Sie unter [Manage Boot Bilder mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="4e4f0-173">Sie können ein startbares USB-Medium um Konfigurations-Manager Task Sequence-basierten Bereitstellungen für Umgebungen zu initiieren, die keine PXE-Unterstützung verfügen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="4e4f0-174">Das startbare Medium enthält nur Boot Image, optionale prestart Befehle und ihre erforderlichen Dateien und Binärdateien Konfigurations-Manager zur Unterstützung der mit Windows PE starten und eine Verbindung zu den Konfigurations-Manager für den Rest des Bereitstellungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="4e4f0-175">Weitere Informationen finden Sie unter [Erstellen eines startbaren Medium](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="4e4f0-176">Konfigurations-Manager-Pakete erstellen</span><span class="sxs-lookup"><span data-stu-id="4e4f0-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="4e4f0-177">Konfigurations-Manager erfordert eine Reihe von Paketen zum Bereitstellen und Konfigurieren der Skype Raum System v2 Einheiten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="4e4f0-178">Sie benötigen zum Erstellen und konfigurieren die folgenden Pakete, und klicken Sie dann den Konfigurations-Manager-Website-Systemen, die die Verteilung Point-Serverrolle zugewiesen wurden verteilen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="4e4f0-179">**Paketname**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-179">**Package name**</span></span>                     | <span data-ttu-id="4e4f0-180">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-180">**Type**</span></span>               | <span data-ttu-id="4e4f0-181">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="4e4f0-182">SRS v2 - Anwendungspaket SRS</span><span class="sxs-lookup"><span data-stu-id="4e4f0-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="4e4f0-183">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-183">Software package</span></span>       | <span data-ttu-id="4e4f0-184">Paket für das Skype Raum Systemen v2 Deployment kit</span><span class="sxs-lookup"><span data-stu-id="4e4f0-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                      |
| <span data-ttu-id="4e4f0-185">SRS v2 - Sysprep-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="4e4f0-186">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-186">Software package</span></span>       | <span data-ttu-id="4e4f0-187">Paket für die benutzerdefinierte Unattended.xml Skype Raum Systemen v2 Einheiten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4e4f0-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>            |
| <span data-ttu-id="4e4f0-188">SRS v2 - Set-SRSComputerName-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="4e4f0-189">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-189">Software package</span></span>       | <span data-ttu-id="4e4f0-190">Paket für die HTML-Anwendung (HTA) zuweisen einen Computernamen während der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="4e4f0-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="4e4f0-191">SRS v2 - SRS Setup konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4e4f0-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="4e4f0-192">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-192">Software package</span></span>       | <span data-ttu-id="4e4f0-193">So konfigurieren Sie die Bereitstellung der app v2 Skype Raum Systeme Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-193">Package to configure deployment of the Skype Room Systems v2 app</span></span>                          |
| <span data-ttu-id="4e4f0-194">SRS v2 - aktualisiert OS Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="4e4f0-195">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-195">Software package</span></span>       | <span data-ttu-id="4e4f0-196">Paket zum Bereitstellen von Updates obligatorisch Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="4e4f0-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="4e4f0-197">SRS v2 - Root Certificate-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="4e4f0-198">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-198">Software package</span></span>       | <span data-ttu-id="4e4f0-199">Optional - Pakets zum Bereitstellen von des Stammzertifikats (nicht für die Domäne eingebundener Einheiten erforderlich)</span><span class="sxs-lookup"><span data-stu-id="4e4f0-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="4e4f0-200">SRS v2 - OMS Microsoft Agent-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-200">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="4e4f0-201">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-201">Software package</span></span>       | <span data-ttu-id="4e4f0-202">Optional - Pakets zum Bereitstellen und Konfigurieren des Microsoft Operations Management Suite-Agents</span><span class="sxs-lookup"><span data-stu-id="4e4f0-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="4e4f0-203">SRS v2 - Paket mit Windows PE Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4e4f0-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="4e4f0-204">Softwarepaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-204">Software package</span></span>       | <span data-ttu-id="4e4f0-205">Paket für das benutzerdefinierte Hintergrundbild zur Verwendung mit Boot-Bilder</span><span class="sxs-lookup"><span data-stu-id="4e4f0-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="4e4f0-206">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4e4f0-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="4e4f0-207">Betriebssystemabbilds</span><span class="sxs-lookup"><span data-stu-id="4e4f0-207">Operating system image</span></span> | <span data-ttu-id="4e4f0-208">Paket für das Betriebssystem-Installationsdatei (install.wim)</span><span class="sxs-lookup"><span data-stu-id="4e4f0-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="4e4f0-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4e4f0-209">Surface Pro</span></span>                          | <span data-ttu-id="4e4f0-210">Treiberpakets</span><span class="sxs-lookup"><span data-stu-id="4e4f0-210">Driver package</span></span>         | <span data-ttu-id="4e4f0-211">Paket für das Gerätetreiber und Firmware für Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4e4f0-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="4e4f0-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4e4f0-212">Surface Pro 4</span></span>                        | <span data-ttu-id="4e4f0-213">Treiberpakets</span><span class="sxs-lookup"><span data-stu-id="4e4f0-213">Driver package</span></span>         | <span data-ttu-id="4e4f0-214">Paket für das Gerätetreiber und Firmware für Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4e4f0-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="4e4f0-215">Weitere Informationen finden Sie unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="4e4f0-216">Erstellen Sie die Ordner für das Paket Quelldateien</span><span class="sxs-lookup"><span data-stu-id="4e4f0-216">Create folders for the package source files</span></span>

<span data-ttu-id="4e4f0-217">Konfigurations-Manager erfordert die Quelldateien des Pakets in einer bestimmten Ordnerstruktur organisiert werden, wenn sie zuerst erstellt werden und wenn sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="4e4f0-218">Erstellen Sie die folgende Ordnerstruktur, die Zentraladministrationswebsite für System Center Configuration Manager oder primärer oder auf eine Serverfreigabe Host Paket Quelldateien verwendeten:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="4e4f0-219">SRS v2 - OMS Microsoft Agent-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-219">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="4e4f0-220">SRS v2 - aktualisiert OS Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="4e4f0-221">SRS v2 - Root Certificate-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="4e4f0-222">SRS v2 - Set-SRSComputerName-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="4e4f0-223">SRS v2 - Anwendungspaket SRS</span><span class="sxs-lookup"><span data-stu-id="4e4f0-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="4e4f0-224">SRS v2 - SRS Setup konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4e4f0-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="4e4f0-225">SRS v2 - Sysprep-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="4e4f0-226">Treiber</span><span class="sxs-lookup"><span data-stu-id="4e4f0-226">Drivers</span></span>
    -   <span data-ttu-id="4e4f0-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4e4f0-227">Surface Pro</span></span>
    -   <span data-ttu-id="4e4f0-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4e4f0-228">Surface Pro 4</span></span>
-   <span data-ttu-id="4e4f0-229">Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="4e4f0-229">Operating Systems</span></span>
    -   <span data-ttu-id="4e4f0-230">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4e4f0-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="4e4f0-231">Sie können auch [herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) und verwenden die Zipdatei, die enthält die Ordnerstruktur für die Pakete, die Skripts, die Sie verwenden müssen, und der Task Sequence Vorlage, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="4e4f0-232">Erstellen Sie das Microsoft Operations Management Suite-Agent-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-232">Create the Microsoft Operations Management Suite agent package</span></span>

1. <span data-ttu-id="4e4f0-233">Laden Sie den Vorgänge Management Suite X-64 Agent aus <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-233">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="4e4f0-234">Extrahieren Sie das Paket in den Ordner **SRS v2 - Microsoft OMS-Agent-Paket** , indem Sie ein Eingabeaufforderungsfenster öffnen und **MMASetup-AMD64.exe/c:** an der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-234">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="4e4f0-235">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="4e4f0-236">Geben Sie die folgenden Informationen, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="4e4f0-237">Namen<strong>: SRS v2 - Agent-Paket Microsoft OMS</strong></span><span class="sxs-lookup"><span data-stu-id="4e4f0-237">Name<strong>: SRS v2 - Microsoft OMS Agent Package</strong></span></span>

   - <span data-ttu-id="4e4f0-238">Hersteller<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="4e4f0-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="4e4f0-239">Version<strong>: 8.1.11081.0</strong> (Geben Sie die Version der der heruntergeladenen Installationsdatei)</span><span class="sxs-lookup"><span data-stu-id="4e4f0-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="4e4f0-240">Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - OMS-Agent-Paket Microsoft** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="4e4f0-241">**Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="4e4f0-242">Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="4e4f0-243">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="4e4f0-244">Erstellen Sie das Betriebssystem Updates-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="4e4f0-245">In den Ordner **SRS v2 - Paket mit Updates OS** Erstellen eines neuen PowerShell-Skripts, die mit dem Namen **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="4e4f0-246">Kopieren Sie das folgende Skript in das Skript für **Install-SRSv2-OS-Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="4e4f0-247">Alternativ können Sie das Skript für Install-SRSv2-OS-Updates.ps1 [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="4e4f0-248">Laden Sie die obligatorische Windows Update-Pakete in den gleichen Ordner.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4e4f0-249">Zum Zeitpunkt der Veröffentlichung des Artikels, war nur [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="4e4f0-250">Überprüfen Sie [Konfigurieren einer Skype Raum Systemen v2-Konsole](console.md), um festzustellen, ob andere Updates erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-250">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="4e4f0-251">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="4e4f0-252">Geben Sie die folgenden Informationen, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="4e4f0-253">Name: **SRS v2 – OS Paket aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="4e4f0-254">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="4e4f0-255">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="4e4f0-256">Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - Paket mit OS Updates** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="4e4f0-257">**Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="4e4f0-258">Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="4e4f0-259">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="4e4f0-260">Erstellen Sie das Stamm-Zertifikat-Paket (optional)</span><span class="sxs-lookup"><span data-stu-id="4e4f0-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="4e4f0-261">Sie erstellen diese Package, um das Stammzertifikat für Geräte verteilen, die mit einer Active Directory-Domäne verknüpft werden, werden nicht aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="4e4f0-262">Erstellen Sie dieses Paket nur, wenn beide die folgenden Bedingungen gelten:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="4e4f0-263">Ihre Bereitstellung umfasst lokalen Lync oder Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="4e4f0-264">Skype-Chatroom-Systemen v2 Einheiten werden für die Verwendung in einer Arbeitsgruppe statt Mitglied einer Domäne konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-264">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="4e4f0-265">Kopieren Sie das Stammzertifikat, in den Ordner **SRS v2 – Root Certificate-Paket** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="4e4f0-266">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="4e4f0-267">Geben Sie die folgenden Informationen, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="4e4f0-268">Name: **SRS v2 – Root Certificate-Paket**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="4e4f0-269">Hersteller: *der Name Ihrer Organisation*</span><span class="sxs-lookup"><span data-stu-id="4e4f0-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="4e4f0-270">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="4e4f0-271">Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 – Root Certificate-Paket** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="4e4f0-272">**Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="4e4f0-273">Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="4e4f0-274">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-274">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="4e4f0-275">Erstellen Sie das Skype Raum Systemen v2 Kit Bereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-275">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="4e4f0-276">Herunterladen der neuesten Version des **Skype Raum Systemen v2 Deployment Kit** von <https://go.microsoft.com/fwlink/?linkid=851168>, und installieren Sie es auf einer Arbeitsstation.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-276">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="4e4f0-277">Kopieren Sie den Inhalt von **C:\\Program Files (x86)\\Skype Raum System Deployment Kit** in den Ordner **SRS v2 - SRS Anwendungspaket** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="4e4f0-278">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="4e4f0-279">Geben Sie die folgenden Informationen, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="4e4f0-280">Name: **SRS v2 – SRS Anwendungspaket**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="4e4f0-281">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="4e4f0-282">Version: **3.1.104.0** (Geben Sie die Version der der heruntergeladenen Installationsdatei)</span><span class="sxs-lookup"><span data-stu-id="4e4f0-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="4e4f0-283">Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 – SRS Anwendungspaket** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="4e4f0-284">**Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="4e4f0-285">Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="4e4f0-286">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="4e4f0-287">Erstellen Sie das Computer Namen Assignment-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="4e4f0-288">Erstellen Sie eine neue HTML-Anwendung mit dem Namen **Set-SRSComputerName.hta** in den Ordner **SRS v2 - Set-SRSComputerName-Paket** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="4e4f0-289">Kopieren Sie das folgende Skript in die **Set-SRSComputerName.hta** -Datei.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="4e4f0-290">Alternativ können Sie die Set-SRSComputerName.hta Datei [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="4e4f0-291">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="4e4f0-292">Geben Sie die folgenden Informationen, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="4e4f0-293">Name: **SRS v2 - Set-SRSComputerName-Paket**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="4e4f0-294">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="4e4f0-295">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="4e4f0-296">Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - Set-SRSComputerName-Paket** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="4e4f0-297">**Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="4e4f0-298">Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="4e4f0-299">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="4e4f0-300">Erstellen Sie das Sysprep-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="4e4f0-301">Erstellen Sie eine neue XML-Datei namens **Unattend.xml** in den Ordner **SRS v2 – Sysprep-Paket** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="4e4f0-302">Kopieren Sie den folgenden Text in der Datei **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="4e4f0-303">Alternativ können Sie die Datei Unattend.xml [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="4e4f0-304">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="4e4f0-305">Geben Sie die folgenden Informationen, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="4e4f0-306">Name: **SRS v2 - Sysprep-Paket**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="4e4f0-307">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="4e4f0-308">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="4e4f0-309">Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 – Sysprep-Paket** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="4e4f0-310">**Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="4e4f0-311">Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="4e4f0-312">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="4e4f0-313">Erstellen Sie das Windows-10-Enterprise-Paket</span><span class="sxs-lookup"><span data-stu-id="4e4f0-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="4e4f0-314">Erhalten Sie eine Windows 10 Enterprise X64 Media, und kopieren Sie die Datei **install.wim** , um die **Betriebssysteme\\Windows 10 Enterprise** Ordner.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="4e4f0-315">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Betriebssystemabbilder**, und wählen Sie dann **Operating System Image hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="4e4f0-316">Geben Sie den Pfad zu der **install.wim** -Datei, die Sie gerade kopiert haben, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="4e4f0-317">Aktualisieren Sie das Feld **Version** die Buildnummer des Bilds Windows 10 Enterprise entsprechend, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="4e4f0-318">Überprüfen Sie die Seite **Details** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="4e4f0-319">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-319">Select **Close**.</span></span>

<span data-ttu-id="4e4f0-320">Weitere Informationen finden Sie unter [Manage Betriebssystem Bilder mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="4e4f0-321">Erstellen Sie Surface Pro Gerät Treiberpakete.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="4e4f0-322">Skype-Chatroom-Systemen v2 wird für Surface Pro und Surface Pro 4 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-322">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="4e4f0-323">Sie müssen ein Paket für jedes Surface Pro Modell zu erstellen, die Ihnen in Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e4f0-324">Die Treiber müssen mit der Windows 10 Enterprise Build und Skype Raum Systemen v2 Deployment Kit Version kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-324">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="4e4f0-325">Weitere Informationen finden Sie unter [Laden Sie die neueste Firmware und Treiber für Fläche Geräte](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) und [Konfigurieren einer Konsole](console.md).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="4e4f0-326">Laden Sie die aktuellsten Treiber und Firmware.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="4e4f0-327">Für Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="4e4f0-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="4e4f0-328">Für Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="4e4f0-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="4e4f0-329">Extrahieren Sie die heruntergeladene Treiber und Firmware.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="4e4f0-330">Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie an der Befehlszeile einen der folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="4e4f0-331">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **-Treiber**, und wählen Sie dann **Import-Treiber**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="4e4f0-332">Wählen Sie **alle Treiber in den folgenden Netzwerkpfad (UNC) zu importieren**, wählen Sie den Quellordner (z. B. C:\\_Sources\\Treiber\\Surface Pro), und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="4e4f0-333">Klicken Sie auf der Seite **Geben Sie die Details für die importierten Treiber** wählen Sie alle aufgelisteten Treiber, und wählen Sie dann **diese Treiber aktivieren und ermöglichen Computern installieren**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="4e4f0-334">Wählen Sie **Kategorien**, Erstellen einer neuen Kategorie, die einzelnen Details des Modells Fläche entspricht, wählen Sie **OK**aus, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="4e4f0-335">Wählen Sie **Neues Paket**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="4e4f0-336">Geben Sie den Paketnamen an, der mit das Surface Pro Modell übereinstimmt, geben Sie einen Pfad zum Speichern von Paketdateien Treiber im, wählen Sie **OK**aus, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="4e4f0-337">Auf der Seite **Boot Bilder** stellen Sie sicher, dass keine Bilder Boot ausgewählt sind, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="4e4f0-338">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-338">Select **Close**.</span></span>

11. <span data-ttu-id="4e4f0-339">Wechseln Sie zu **Software Library** \> **Betriebssysteme** \> - **Treiber**wählen **Ordner \> Ordner erstellen**, und geben Sie einen Ordnernamen, die einzelnen Details des Modells Surface Pro gesucht, die Sie gerade die Treiber für importiert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="4e4f0-340">Verschieben Sie alle importierten Treiber in den neu erstellten Ordner für einfachere Navigation und Vorgang.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="4e4f0-341">Wiederholen Sie die gleichen Schritte für andere Surface Pro Modelle möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="4e4f0-342">Weitere Informationen finden Sie unter [Manage Treiber in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="4e4f0-343">Verteilen von Configuration Manager-Paketen</span><span class="sxs-lookup"><span data-stu-id="4e4f0-343">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="4e4f0-344">Alle Pakete müssen an die Server verteilt werden, die die Verteilungspunktrolle in der Configuration Manager-Hierarchie zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-344">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="4e4f0-345">Gehen Sie zum Paket Verteilung initiieren.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-345">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="4e4f0-346">Verteilen Sie Softwarepakete.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-346">Distribute software packages.</span></span>

    1.  <span data-ttu-id="4e4f0-347">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="4e4f0-348">Wählen Sie die Software-Pakete, die Sie verteilen möchten, und wählen Sie dann auf **Content verteilen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-348">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="4e4f0-349">Überprüfen Sie die Liste der Pakete, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-349">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="4e4f0-350">Die Liste alle Verteilung Point-Server (oder Punkt Verteilergruppen, je nach der Hierarchie der Konfigurations-Manager) hinzu, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-350">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="4e4f0-351">Wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-351">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="4e4f0-352">Verteilen von Treiberpaketen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-352">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="4e4f0-353">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Treiberpakete**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-353">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="4e4f0-354">Wählen Sie die Treiberpakete, die Sie verteilen möchten, und wählen Sie dann auf **Inhalt zu verteilen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-354">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="4e4f0-355">Überprüfen Sie die Liste der Pakete, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-355">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="4e4f0-356">Die Liste alle Verteilung Point-Server (oder Punkt Verteilergruppen, je nach der Hierarchie der Konfigurations-Manager) hinzu, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-356">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="4e4f0-357">Wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-357">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="4e4f0-358">Verteilen Sie Betriebssystem-Pakete.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-358">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="4e4f0-359">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Betriebssystemabbilder**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-359">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="4e4f0-360">Wählen Sie alle Betriebssystemabbilder, die Sie verteilen möchten, und wählen Sie dann auf **Inhalt zu verteilen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-360">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="4e4f0-361">Überprüfen Sie die Liste der Pakete, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-361">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="4e4f0-362">Die Liste alle Verteilung Point-Server (oder Punkt Verteilergruppen, je nach der Hierarchie der Konfigurations-Manager) hinzu, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-362">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="4e4f0-363">Wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-363">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="4e4f0-364">Paket Verteilung kann je nach der Größe der Verteilungspakete, Konfigurations-Manager-Hierarchie, Anzahl der Verteilung Point Server und die Bandbreite in Ihrem Netzwerk verfügbar einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-364">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="4e4f0-365">Bevor Sie eine Skype Raum Systemen v2 Einheit bereitstellen können, müssen alle Pakete verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-365">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>
> 
> <span data-ttu-id="4e4f0-366">Sie können den Status Ihrer Paket Verteilung in der Configuration Manager-Konsole auf **Überwachung** überprüfen \> **Verteilungsstatus** \> **Status des Inhalts**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-366">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="4e4f0-367">Konfigurations-Manager Task sequences</span><span class="sxs-lookup"><span data-stu-id="4e4f0-367">Configuration Manager task sequences</span></span>

<span data-ttu-id="4e4f0-368">Mit System Center Configuration Manager verwenden Sie Task Sequences, um die Schritte zur Bereitstellung eines Betriebssystemabbilds auf einem Zielcomputer zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-368">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="4e4f0-369">Zum Bereitstellen von Skype Raum Systemen v2 Einheit automatisiert zu erstellen Sie eine Aufgabensequenz, die zum Starten der Zielcomputer Skype Raum Systemen v2, das Windows-10-Enterprise-Betriebssystemabbild, das Sie installieren möchten und andere Boot-Abbild verweist Weitere zusätzliche Inhalte wie andere Anwendungen oder Softwareupdates.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-369">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="4e4f0-370">Importieren Sie die Beispiel Aufgabensequenz</span><span class="sxs-lookup"><span data-stu-id="4e4f0-370">Import the sample task sequence</span></span>

<span data-ttu-id="4e4f0-371">Sie können herunterladen und auf einfache Weise importieren eine Beispiel-Aufgabensequenz und entsprechend Ihren Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-371">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="4e4f0-372">[**Herunterladen**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) der Aufgabensequenz Sample, und kopieren Sie die heruntergeladene Zip-Datei an einen freigegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-372">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="4e4f0-373">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Task Sequences**, und wählen Sie dann **Import Task Sequence**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-373">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="4e4f0-374">Wählen Sie **Durchsuchen**, wechseln Sie auf den Speicherort des freigegebenen Ordners, den Sie in Schritt 1 verwendet haben, wählen Sie die **Skype Raum Systemen v2-Bereitstellung (EN-US) ZIP** -Datei, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-374">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="4e4f0-375">Legen Sie die **Aktion** auf **Neu erstellen**, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-375">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="4e4f0-376">Bestätigen Sie die Einstellungen, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-376">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="4e4f0-377">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-377">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="4e4f0-378">Überprüfen Sie, dass die Pakete Verweis ordnungsgemäß mit jedem Task Sequence Schritt verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-378">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="4e4f0-379">Wählen Sie die importierten Aufgabensequenz aus, und wählen Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-379">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="4e4f0-380">Den Task Sequence Editor wird geöffnet und zeigt jede sequenziellen Schritt, die Sie benötigen zum Bereitstellen und Konfigurieren von Skype Raum Systemen v2 Einheit.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-380">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

2. <span data-ttu-id="4e4f0-381">Durch die einzelnen Schritte durchlaufen Sie, und schließen Sie die empfohlenen Updates:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-381">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="4e4f0-382">**In Windows PE neu starten**: Dieser Schritt wird neu gestartet, und klicken Sie dann in Windows PXE startet den Computer.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-382">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="4e4f0-383">In diesem Schritt muss werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-383">No changes are required for this step.</span></span>

   2. <span data-ttu-id="4e4f0-384">**Partition Datenträger 0 – UEFI**: in diesem Schritt löscht die Datenträgerkonfiguration und Partitionen basierend auf den konfigurierten Einstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-384">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="4e4f0-385">Es wird empfohlen, dass Sie keine Änderungen an diesen Schritt vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-385">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="4e4f0-386">**SRS Computername festgelegt**: Dieser Schritt umfasst das eine HTML-Anwendung eine Benutzeroberfläche zum Festlegen von eines Computernamen für die Skype Raum Systemen v2 Einheit während der Bereitstellung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-386">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
      -  <span data-ttu-id="4e4f0-387">Dies ist ein optionaler Schritt, aber es kann nur deaktiviert werden, wenn Sie über ein alternativer Prozess die Benennung von Computern verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-387">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="4e4f0-388">Stellen Sie sicher, dass das Paket **SRS v2 - Set-SRSComputerName** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-388">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="4e4f0-389">Falls nicht, suchen Sie das Paket, und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-389">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="4e4f0-390">**Betriebssystem anwenden**: in diesem Schritt gibt an, das Betriebssystemabbild bereitgestellt werden und die unbeaufsichtigte Sysprep Antwortdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-390">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="4e4f0-391">Stellen Sie sicher, dass die richtige Windows 10 Enterprise Operating System Image-Datei ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-391">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="4e4f0-392">Stellen Sie sicher, dass die **Verwendung einer unbeaufsichtigten oder Sysprep-Antwortdatei für eine benutzerdefinierte Installation** ist aktiviert, und der **SRS v2 - Sysprep-Paket** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-392">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="4e4f0-393">Außerdem sicherstellen Sie, dass **Dateinamen** **unattend.xml**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-393">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="4e4f0-394">**Windows-Einstellungen gelten**: in diesem Schritt erfasst Informationen über die Windows-Installation.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-394">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="4e4f0-395">Enthalten Sie Lizenzierung und Registrierung Informationen, einschließlich der Produktschlüssel, Kennworts eines lokalen Administratorkontos und Zeitzone (je nach Ihren Anforderungen).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-395">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="4e4f0-396">**Netzwerkeinstellungen anwenden**: in diesem Schritt können Sie einer Arbeitsgruppe oder Name der Active Directory-Domäne und Organisationseinheit angeben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-396">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="4e4f0-397">Empfohlene Schritte, die Sie bei der Bereitstellung von Skype Raum Systemen v2 Einheiten als Mitglied einer Domäne ADSI Directory durchführen müssen, finden Sie unter [Skype Raum System Domäne beitretenden Considerations](domain-joining-considerations.md) .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-397">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Skype Room Systems v2 units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="4e4f0-398">**Treiber anwenden:** Dieser Schritt und seine Unterschritte dienen zum entsprechenden Gerätetreiber und Firmware basierend auf dem Surface Pro Modell haben Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-398">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="4e4f0-399">Aktualisieren Sie jeden Schritt zum Angeben des entsprechenden Treiberpakets dieser Bereitstellung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-399">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="4e4f0-400">Jedes Paket Nutzung der Windows-Verwaltungsinstrumentation (WMI) Filter zum Bereitstellen von relevanten Treiber konfiguriert und Firmware basierend auf dem Surface Pro Marke und das Modell.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-400">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="4e4f0-401">Es wird dringend empfohlen, dass Sie die Konfiguration dieser Treiber nicht ändern, andernfalls Bereitstellung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-401">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="4e4f0-402">**Einrichten von Windows und Konfigurations-Manager**: in diesem Schritt bereitstellen und konfigurieren Sie den Konfigurations-Manager-Client.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-402">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="4e4f0-403">Aktualisieren Sie diesen Schritt, um die integrierten Konfigurations-Manager-Client-Paket angeben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-403">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="4e4f0-404">**Stammzertifikat installieren**: in diesem Schritt das Stammzertifikat für Geräte nicht in die Domäne eingebundener verteilt und daher ist optional und standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-404">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="4e4f0-405">Aktivieren Sie diesen Schritt, wenn Sie ein Stammzertifikat für die Skype Raum Systemen v2 Einheiten bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-405">Enable this step if you need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
      -   <span data-ttu-id="4e4f0-406">Wenn Sie benötigen, um diesen Schritt ausführen, stellen Sie sicher, dass der **SRS v2 – Root Certificate-Paket** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-406">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="4e4f0-407">**Installieren und Konfigurieren von OMS-Agent**: in diesem Schritt installiert die 64-Bit-Version des Microsoft Operations Management Suite-Agents und den Verbindung mit den Arbeitsbereich Protokoll Analytics-Agent konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-407">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="4e4f0-408">Dieser Schritt ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-408">This step is disabled by default.</span></span> <span data-ttu-id="4e4f0-409">Aktivieren Sie diesen Schritt nur aus, wenn Sie OMS verwenden also, um die Integrität der Skype Raum Systemen v2 Einheiten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-409">Enable this step only if you’re going to use OMS to monitor the health of your Skype Room Systems v2 units.</span></span>
       -   <span data-ttu-id="4e4f0-410">Bearbeiten Sie diesen Schritt und aktualisieren Sie die Befehlszeilenparameter, um das **Workspace-ID** und den **Arbeitsbereich Schlüssel**anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-410">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="4e4f0-411">Weitere Informationen zum Beziehen der Vorgänge Management Suite Workspace-ID und den Primärschlüssel finden Sie unter [mit dem Protokoll Analytics-Dienst in Azure-Computern mit Windows eine Verbindung herstellen](with-oms.md#configure-test-devices-for-operations-management-suite-setup) .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-411">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="4e4f0-412">Stellen Sie sicher, dass der **SRS v2 – Microsoft OMS-Agent-Paket** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-412">Verify that the **SRS v2 – Microsoft OMS Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="4e4f0-413">Weitere Informationen zum Überwachen der Integrität der Bereitstellung v2 Skype Raum Systeme finden Sie unter [Planen von Skype Raum v2 systemverwaltung mit OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) und [Bereitstellen von Skype Raum v2 systemverwaltung mit OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-413">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

   11. <span data-ttu-id="4e4f0-414">**Kopie SRS v2 Konfigurationsdateien**: Dieser Schritt kopiert die erforderlichen Dateien von Setup und Konfiguration aus Skype Raum Systemen v2 Deployment Kit in der lokalen Festplatte.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-414">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="4e4f0-415">Keine Anpassung ist für diesen Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-415">No customization is required for this step.</span></span>
       -   <span data-ttu-id="4e4f0-416">Stellen Sie sicher, dass der **SRS v2 – SRS Anwendungspaket** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-416">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="4e4f0-417">**Install-SRSv2-OS-Updates**: in diesem Schritt wird alle obligatorisch mit der Bereitstellung der Skype Raum Systemen v2 erforderlichen Betriebssystemupdates bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-417">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="4e4f0-418">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-418">Do the following:</span></span>
       -   <span data-ttu-id="4e4f0-419">Überprüfen Sie [konfigurieren einen Skype Raum Systemen v2-Konsole](console.md) , um herauszufinden, welche Updates erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-419">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="4e4f0-420">Stellen Sie sicher, dass Ihre **SRS v2 – Paket mit OS Updates** alle erforderlichen Updates enthält.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-420">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="4e4f0-421">Stellen Sie sicher, dass der **SRS v2 – Paket mit OS Updates** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-421">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="4e4f0-422">Stellen Sie sicher, dass die PowerShell-Ausführungsrichtlinie **umgehen**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-422">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="4e4f0-423">**Computer neu starten**: Dieser Schritt startet den Computer neu, nachdem die obligatorische Betriebssystemupdates installiert worden sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-423">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="4e4f0-424">Keine Anpassung ist für diesen Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-424">No customization is required for this step.</span></span>

   14. <span data-ttu-id="4e4f0-425">**Konfigurieren der Windows-Komponenten**: in diesem Schritt werden die erforderlichen Windows-Features konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-425">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="4e4f0-426">Keine Anpassung ist für diesen Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-426">No customization is required for this step.</span></span>

   15. <span data-ttu-id="4e4f0-427">**Computer neu starten**: Dieser Schritt startet den Computer neu, nachdem die Windows-Features konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-427">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="4e4f0-428">Keine Anpassung ist für diesen Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-428">No customization is required for this step.</span></span>

   16. <span data-ttu-id="4e4f0-429">**Skype-Benutzer**: Dieser Schritt wird das lokale Skype-Konto verwendet, um automatisch bei Windows anmelden und starten Sie die Skype Raum Systemen v2-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-429">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="4e4f0-430">Dieser Schritt keine Softwarepaket zugeordnet haben, und keine Anpassung für die es erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-430">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="4e4f0-431">**Festlegen einrichten und Konfigurieren der SRS Anwendung**: in diesem Schritt Skype Raum Systemen v2 die Installation der Anwendung für den nächsten Start des Betriebssystems konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-431">**Set up and configure SRS application**: This step configures the Skype Room Systems v2 application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="4e4f0-432">Stellen Sie sicher, dass der **SRS v2 – SRS Setuppaket konfigurieren** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-432">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e4f0-433">Es ist sehr wichtig, dass die Task Sequence Schritte in der angegebenen Reihenfolge sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-433">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="4e4f0-434">Ändern der Reihenfolge der Schritte aus, oder konfigurieren zusätzliche Schritte möglicherweise die Bereitstellung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-434">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="4e4f0-435">**Festlegen einrichten und Konfigurieren der SRS Anwendung** Schritt muss der letzte Schritt in der Aufgabensequenz, andernfalls die Bereitstellung kann fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-435">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="4e4f0-436">Bereitstellung für die Abfolge der Vorgänge erstellen</span><span class="sxs-lookup"><span data-stu-id="4e4f0-436">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="4e4f0-437">Wählen Sie die Abfolge der Vorgänge aus, und wählen Sie dann auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-437">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="4e4f0-438">Wählen Sie auf **Durchsuchen** , um für die Bereitstellung Zielsammlung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-438">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="4e4f0-439">Wählen Sie **Alle unbekannten Computern** aus, und wählen Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-439">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="4e4f0-440">Wählen Sie **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-440">Select **Next**.</span></span>

5. <span data-ttu-id="4e4f0-441">Wählen Sie aus der Dropdownliste **Zweck** **verfügbar** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-441">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="4e4f0-442">Wählen Sie **nur Medien und PXE** in der Liste **die folgenden zur Verfügung stellen** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-442">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="4e4f0-443">Es ist sehr wichtig, dass **Zweck** auf **verfügbar**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-443">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="4e4f0-444">Stellen Sie sicher, dass der **Zweck** **nicht** auf **erforderlich**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-444">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="4e4f0-445">Stellen Sie außerdem sicher, dass Sie in **der folgenden zur Verfügung stellen** **nur Medien und PXE** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-445">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="4e4f0-446">Festlegen von diese Werte auf einen anderen Suchbegriff möglicherweise alle Computer mit dem Skype Raum Systeme Bereitstellungsabbild Wenn gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-446">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7. <span data-ttu-id="4e4f0-447">Geben Sie eine beliebige Zeitplan keine, und wählen Sie **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-447">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="4e4f0-448">Ändern Sie alles innerhalb des Abschnitts der **Benutzeroberfläche** nicht, und wählen Sie **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-448">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="4e4f0-449">Ändern Sie alles innerhalb des Abschnitts **Benachrichtigungen** nicht, und wählen Sie **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-449">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="4e4f0-450">Ändern Sie alles innerhalb des Abschnitts **Verteilungspunkte** nicht, und wählen Sie **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-450">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="4e4f0-451">Bestätigen Sie die Einstellungen, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-451">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="4e4f0-452">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-452">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="4e4f0-453">Überprüfen Sie und Problembehandlung bei der Lösung</span><span class="sxs-lookup"><span data-stu-id="4e4f0-453">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="4e4f0-454">Nachdem Sie die System Center Configuration Manager Task Sequences abgeschlossen haben, müssen Sie führen Sie einen Test ausführen, um zu überprüfen, ob die Abfolge der Vorgänge kann bereitstellen und Konfigurieren von Skype Raum Systemen v2 Einheiten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-454">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="4e4f0-455">Verbinden Sie das Testgerät mit dem Kabelnetzwerk mithilfe einer der unterstützten Ethernet-Adapter oder mit der Fläche andocken.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-455">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="4e4f0-456">Wenn PXE-Boot-Funktionalität für Ihre Umgebung nicht konfiguriert wurde, können Sie das Boot-Abbild auf die USB flash-Laufwerk [das Sie zuvor erstellt](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) von USB starten und eine Verbindung herstellen zu Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-456">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="4e4f0-457">Zugriff auf die Firmware und initiieren Sie PXE-Start:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-457">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="4e4f0-458">Stellen Sie sicher, dass das Gerät Fläche ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-458">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="4e4f0-459">Drücken Sie und halten Sie die **Lautstärke** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-459">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="4e4f0-460">Drücken und **halten** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-460">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="4e4f0-461">Nachdem das Gerät beginnt mit starten, lassen Sie die **Lautstärke** los.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-461">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="4e4f0-462">Wählen Sie die **Startkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-462">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="4e4f0-463">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-463">Do one of the following:</span></span>

        -   <span data-ttu-id="4e4f0-464">Wählen Sie **PXE-Start**, und ziehen Sie es an den Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-464">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="4e4f0-465">Alternativ können Sie führen Sie links auf den Netzwerkadapter, das Gerät sofort zu starten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-465">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="4e4f0-466">Dies wird nicht die Startreihenfolge auswirken.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-466">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="4e4f0-467">Wählen Sie das USB-Laufwerk, das die Startmedien enthält.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-467">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="4e4f0-468">Wählen Sie **Beenden**, und wählen Sie dann auf **Jetzt neu starten**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-468">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="4e4f0-469">Wenn Sie aufgefordert werden, wählen Sie **Enter** für Startdienst Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-469">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="4e4f0-470">Windows PE wird in den Arbeitsspeicher geladen, und der Task Sequence-Assistent wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-470">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="4e4f0-471">Wählen Sie auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-471">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="4e4f0-472">Wählen Sie die Abfolge der Vorgänge, die Sie zuvor importiert haben, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-472">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="4e4f0-473">Nachdem die Datenträgerkonfiguration angewendet wird, werden Sie aufgefordert, einen Computernamen für das Gerät angeben.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-473">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="4e4f0-474">Die Benutzeroberfläche wird eine empfohlene Computername basierend auf die Seriennummer des Geräts Surface Pro angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-474">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="4e4f0-475">Sie können entweder den vorgeschlagenen Namen übernehmen oder geben Sie einen neuen Anwendungspool.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-475">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="4e4f0-476">Befolgen Sie die Anweisungen auf dem Bildschirm Zuordnung Name ein.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-476">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="4e4f0-477">Wenn Sie **annehmen**auswählen, beginnt mit die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-477">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="4e4f0-478">Der Rest des Bereitstellungsprozesses erfolgt automatisch und nicht für jede weitere Benutzereingaben bitten.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-478">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="4e4f0-479">Nach Abschluss die Bereitstellungsreihenfolge für die Aufgabe Konfigurieren des Geräts sehen Sie die folgenden Konfigurationsbildschirm, die Sie zum Konfigurieren der Einstellungen der Skype Raum Systemen v2 aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-479">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Anfängliche Setupbildschirm für Skype Raum Systemen v2-Anwendung](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="4e4f0-481">Schließen Sie die Konsole Skype Raum Systeme v2 Surface Pro, und Konfigurieren der Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-481">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="4e4f0-482">Überprüfen Sie, dass die Funktionen in [Skype Raum Systemen v2 Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) aufgeführten auf dem Gerät bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-482">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="4e4f0-483">Um eine fehlerhafte Installation zu beheben, überprüfen Sie **die Masterprotokolldatei, in dem alle Schritte in einer Configuration Manager-Aufgabensequenz ausgeführt protokolliert** .</span><span class="sxs-lookup"><span data-stu-id="4e4f0-483">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="4e4f0-484">Die Masterprotokolldatei wird auf eine Reihe von Pfaden, je nach der Phase des Buildprozesses gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-484">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="4e4f0-485">Überprüfen Sie in der folgenden Tabelle, um den Pfad zu der Masterprotokolldatei zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-485">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="4e4f0-486">**Bereitstellungsphase**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-486">**Deployment phase**</span></span>                                                            | <span data-ttu-id="4e4f0-487">**Task Sequence Protokollpfad**</span><span class="sxs-lookup"><span data-stu-id="4e4f0-487">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="4e4f0-488">Windows PE, bevor Sie HDD-format</span><span class="sxs-lookup"><span data-stu-id="4e4f0-488">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="4e4f0-489">X:\\Windows\\Temp\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="4e4f0-489">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="4e4f0-490">Windows PE, nach HDD-format</span><span class="sxs-lookup"><span data-stu-id="4e4f0-490">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="4e4f0-491">C:\\_SMSTaskSequence\\Protokolle\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="4e4f0-491">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="4e4f0-492">Betriebssystem bereitgestellt werden, bevor der Konfigurations-Manager-Agent installiert wurde</span><span class="sxs-lookup"><span data-stu-id="4e4f0-492">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="4e4f0-493">c:\\_SMSTaskSequence\\Protokolle\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="4e4f0-493">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="4e4f0-494">Betriebssystem und den Konfigurations-Manager-Agent bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="4e4f0-494">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="4e4f0-495">%windir%\\System32\\Ccm\\Protokolle\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="4e4f0-495">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="4e4f0-496">Task Sequence Ausführung abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="4e4f0-496">Task sequence execution complete</span></span>                                                | <span data-ttu-id="4e4f0-497">%windir%\\System32\\Ccm\\Protokolle\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="4e4f0-497">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="4e4f0-498">Sie können wählen **F8** können Sie jederzeit während der Aufgabensequenz, um eine Befehlskonsole zu öffnen, und klicken Sie dann erhalten Sie Zugriff auf die Masterprotokolldatei.</span><span class="sxs-lookup"><span data-stu-id="4e4f0-498">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="4e4f0-499">Überprüfen Sie um PXE Boot-Problemen, die zwei Protokolldateien auf dem Server-Konfigurations-Manager, die speziell für PXE-Aktionen sind:</span><span class="sxs-lookup"><span data-stu-id="4e4f0-499">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="4e4f0-500">**Pxecontrol.log**, befindet sich im Installationsverzeichnis Protokolle Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="4e4f0-500">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="4e4f0-501">**Smspxe.log**, befindet sich im Verzeichnis der Konfigurations-Manager-Management Point (VA) logs</span><span class="sxs-lookup"><span data-stu-id="4e4f0-501">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="4e4f0-502">Eine vollständige Liste der Protokolldateien, die Sie zum Diagnostizieren Sie Ihre Installations Konfigurations-Manager verwenden können, finden Sie unter [System Center Configuration Manager-Protokolldateien](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="4e4f0-502">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
