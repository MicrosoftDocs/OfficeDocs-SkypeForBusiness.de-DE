---
title: Bereitstellen von Microsoft Teams-Räumen mithilfe von System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Lesen Sie dieses Thema, um Informationen zum Bereitstellen von Microsoft Teams-Räumen in umfangreichen Bereitstellungen zu erhalten.
ms.openlocfilehash: 48a2ddbed8ca5909ca527f7db872c6fa74737610
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243421"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="a1165-103">Bereitstellen von Microsoft Teams-Räumen mithilfe von System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a1165-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="a1165-104">Dieser Artikel enthält alle erforderlichen Informationen zum Erstellen Ihrer Microsoft Teams rooms-Bereitstellungen mithilfe von System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a1165-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="a1165-105">Mit den einfach zu verwendenden Methoden, die von System Center Configuration Manager bereitgestellt werden, können Sie das Betriebs System und andere Anwendungen auf mehreren Zielgeräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a1165-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="a1165-106">Verwenden Sie den unten dargestellten Ansatz, der Sie durch Ihre Configuration Manager-Konfiguration führt, und passen Sie die Beispielpakete und Skripts an, die in diesem Leitfaden nach Bedarf für Ihre Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a1165-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Bereitstellungsprozess für Microsoft Teams rooms mithilfe von Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="a1165-108">Diese Lösung wurde nur mit Surface pro-basierten Bereitstellungen getestet.</span><span class="sxs-lookup"><span data-stu-id="a1165-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="a1165-109">Befolgen Sie die Richtlinien des Herstellers für Konfigurationen, die nicht auf Surface pro basieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="a1165-110">Überprüfen von Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a1165-110">Validate prerequisites</span></span>

<span data-ttu-id="a1165-111">Stellen Sie zum Bereitstellen von Microsoft Teams-Räumen mit Configuration Manager sicher, dass Sie die folgenden Voraussetzungen und Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1165-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="a1165-112">System Center-Konfigurations-Manager-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1165-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="a1165-113">Die System Center Configuration Manager-Version muss mindestens 1706 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="a1165-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="a1165-114">Wir empfehlen die Verwendung von 1710 oder höher.</span><span class="sxs-lookup"><span data-stu-id="a1165-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="a1165-115">Schauen Sie sich die [Unterstützung für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) an, um mehr über die Windows 10-Versionen zu erfahren, die von Configuration Manager unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a1165-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="a1165-116">Es muss eine unterstützte Version von Windows Assessment und Deployment Kit (ADK) für Windows 10 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="a1165-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="a1165-117">Sehen Sie sich die Versionen von [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) an, die Sie in verschiedenen Versionen von Configuration Manager verwenden können, und stellen Sie sicher, dass Ihre Bereitstellung die richtige Version enthält.</span><span class="sxs-lookup"><span data-stu-id="a1165-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="a1165-118">Den Standortsystemservern muss die Verteilungspunktrolle zugewiesen worden sein, und die Startabbilder sollten für [PXE-Unterstützung (Preboot Execution Environment)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) aktiviert werden, um Netzwerk initiierte Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a1165-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="a1165-119">Wenn die PXE-Unterstützung nicht aktiviert ist, können Sie für Ihre Bereitstellungen [startfähige Medien](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1165-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="a1165-120">Ein Netzwerkzugriffskonto muss so konfiguriert sein, dass es neue Bereitstellungsszenarien für Computer (Bare Metal) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1165-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="a1165-121">Wenn Sie mehr über die Konfiguration eines Netzwerkzugriffskontos erfahren möchten, lesen Sie [Verwalten von Konten für den Zugriff auf Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="a1165-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="a1165-122">Wir empfehlen, dass Sie die [Multicastunterstützung](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)aktivieren, wenn Sie wahrscheinlich dasselbe Microsoft Teams rooms-Bild gleichzeitig auf mehreren Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a1165-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="a1165-123">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="a1165-123">Networking requirements</span></span>

-   <span data-ttu-id="a1165-124">Ihr Netzwerk sollte über einen DHCP-Server (Dynamic Host Configuration Protocol) verfügen, der für die automatische IP-Adress Verteilung an die Subnetze konfiguriert ist, in denen die Microsoft Teams rooms-Einheiten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a1165-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1165-125">Die DHCP-Leasingdauer muss auf einen Wert gesetzt werden, der länger als die Dauer der Bild Bereitstellung ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="a1165-126">Andernfalls schlägt die Bereitstellung möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="a1165-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="a1165-127">Ihr Netzwerk, einschließlich Switches und virtuellen LANs (VLANs), sollte so konfiguriert werden, dass es PXE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1165-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="a1165-128">Weitere Informationen zur IP-Helper-und PXE-Konfiguration finden Sie bei Ihrem Netzwerkanbieter.</span><span class="sxs-lookup"><span data-stu-id="a1165-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="a1165-129">Wenn die PXE-Unterstützung nicht aktiviert ist, können Sie auch [startfähige Medien](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) für Ihre Bereitstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1165-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1165-130">Bei Surface pro-Geräten wird das Booten vom Netzwerk (PXE-Start) nur unterstützt, wenn Sie einen Ethernet-Adapter oder eine Docking-Station von Microsoft verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1165-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="a1165-131">Ethernet-Adapter von Drittanbietern unterstützen keinen PXE-Start mit Surface pro.</span><span class="sxs-lookup"><span data-stu-id="a1165-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="a1165-132">Weitere Informationen finden Sie unter [Ethernet-Adapter und Surface-Bereitstellung](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="a1165-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="a1165-133">Konfigurieren von System Center Configuration Manager für die Betriebs System Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a1165-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="a1165-134">In diesem Artikel wird davon ausgegangen, dass Sie bereits über eine gesunde System Center Configuration Manager-Bereitstellung verfügen und nicht alle erforderlichen Schritte zum Bereitstellen und Konfigurieren von Configuration Manager von Grund auf detailliert ausführen.</span><span class="sxs-lookup"><span data-stu-id="a1165-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="a1165-135">Die [Dokumentation und die Konfigurationsanleitungen](https://docs.microsoft.com/sccm/) im System Center Configuration Manager sind eine hervorragende Ressource; Wenn Sie Configuration Manager noch nicht bereitgestellt haben, empfehlen wir, mit diesen Ressourcen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a1165-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="a1165-136">Verwenden Sie die folgenden Anweisungen, um zu überprüfen, ob die OSD-Features (Operating System Deployment) ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="a1165-137">Überprüfen und Aktualisieren des Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="a1165-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="a1165-138">Wechseln Sie in der Configuration Manager-Konsole zu **Administrator** \> **Updates und-Wartung**.</span><span class="sxs-lookup"><span data-stu-id="a1165-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="a1165-139">Überprüfen Sie den installierten Build und die anwendbaren Updates, die noch nicht installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1165-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="a1165-140">Überprüfen des [Supports für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Wenn Sie Ihre Bereitstellung aktualisieren müssen, wählen Sie das Update aus, das Sie installieren möchten, und wählen Sie dann **herunterladen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="a1165-141">Nachdem der Download abgeschlossen ist, wählen Sie das Update aus, und wählen Sie dann **Update Pack installieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="a1165-142">Konfigurieren von Verteilungspunkten zur Unterstützung von PXE und Multicast</span><span class="sxs-lookup"><span data-stu-id="a1165-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="a1165-143">Wechseln Sie in der Configuration Manager-Konsole zu **Verwaltungs** \> **Verteilungspunkten**.</span><span class="sxs-lookup"><span data-stu-id="a1165-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="a1165-144">Wählen Sie den Verteilungspunktserver aus, der für die Bereitstellung von Microsoft Teams rooms dient, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="a1165-145">Wählen Sie die Registerkarte **PXE** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="a1165-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="a1165-146">Aktivieren der PXE-Unterstützung für Clients</span><span class="sxs-lookup"><span data-stu-id="a1165-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="a1165-147">Diesem Verteilungspunkt gestatten, auf eingehende PXE-Anforderungen zu reagieren</span><span class="sxs-lookup"><span data-stu-id="a1165-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="a1165-148">Unterstützung für unbekannte Computer aktivieren</span><span class="sxs-lookup"><span data-stu-id="a1165-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="a1165-149">*Optional:* Wenn Sie die Multicastunterstützung aktivieren möchten, wählen Sie die Registerkarte **Multicast** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="a1165-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="a1165-150">Aktivieren von Multicast zum gleichzeitigen Senden von Daten an mehrere Clients</span><span class="sxs-lookup"><span data-stu-id="a1165-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="a1165-151">Konfigurieren des UDP-Portbereichs gemäß den Empfehlungen Ihres Netzwerkteams</span><span class="sxs-lookup"><span data-stu-id="a1165-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="a1165-152">Konfigurieren des Netzwerkzugriffskontos</span><span class="sxs-lookup"><span data-stu-id="a1165-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="a1165-153">Wechseln Sie in der Configuration Manager-Konsole zu den **Verwaltungs** \> **Website-Konfigurations** \> **Websites**, und wählen Sie dann die Website aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="a1165-154">Wählen Sie in der Gruppe **Einstellungen** die Option **Software Verteilung**für **Websitekomponenten** \> konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="a1165-155">Wählen Sie die Registerkarte **Netzwerkzugriffskonto** aus. richten Sie mindestens ein Konto ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="a1165-156">Die Konten benötigen keine besonderen Rechte, mit Ausnahme des **Zugriffs auf diesen Computer vom Netzwerk aus** direkt auf dem Verteilungspunktserver.</span><span class="sxs-lookup"><span data-stu-id="a1165-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="a1165-157">Ein generisches Domänenbenutzerkonto ist angemessen.</span><span class="sxs-lookup"><span data-stu-id="a1165-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="a1165-158">Weitere Informationen finden Sie unter [Verwalten von Konten für den Zugriff auf Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="a1165-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="a1165-159">Konfigurieren eines Startabbilds</span><span class="sxs-lookup"><span data-stu-id="a1165-159">Configure a boot image</span></span>

1.  <span data-ttu-id="a1165-160">Wechseln Sie in der Configuration Manager-Konsole zu den **Start**Abbildern des **Software Bibliothek** \> - **Betriebssystems** \> .</span><span class="sxs-lookup"><span data-stu-id="a1165-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="a1165-161">Wählen Sie **Startabbild (x64)** aus, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="a1165-162">Wählen Sie die Registerkarte **Datenquelle** aus, und aktivieren Sie **Dieses Startabbild auf dem PXE-fähigen Verteilungspunkt bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="a1165-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="a1165-163">Wählen Sie die Registerkarte **optionale Komponenten** aus, um erforderliche Komponenten zu installieren:</span><span class="sxs-lookup"><span data-stu-id="a1165-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="a1165-164">Wählen Sie das Stern Symbol aus, und suchen Sie nach **HTML (WinPE-HTA)** .</span><span class="sxs-lookup"><span data-stu-id="a1165-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="a1165-165">Wählen Sie **OK** aus, um dem Startabbild HTML-Anwendungsunterstützung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a1165-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="a1165-166">*Optional:* Um die Bereitstellungsumgebung anzupassen, wählen Sie die Registerkarte **Anpassung** aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="a1165-167">Aktivieren Sie die **Befehlsunterstützung (nur testen)** , wenn Sie während der Bereitstellung auf eine Eingabeaufforderung zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="a1165-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="a1165-168">Wenn diese Option aktiviert ist, können Sie eine Eingabeaufforderung starten, indem Sie **F8** zu einem beliebigen Zeitpunkt während der Bereitstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="a1165-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="a1165-169">Sie können auch ein benutzerdefiniertes Hintergrundbild angeben, das während der Bereitstellung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1165-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="a1165-170">Wenn Sie ein Bild festlegen möchten, aktivieren **Sie die Option geben Sie die benutzerdefinierte Hintergrund Bilddatei an (UNC-Pfad** , und wählen Sie den Hintergrund aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="a1165-171">Wenn Sie dazu aufgefordert werden, wählen Sie **Ja** aus, und verteilen Sie das aktualisierte Startabbild an Ihre Verteilungspunkte.</span><span class="sxs-lookup"><span data-stu-id="a1165-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="a1165-172">Weitere Informationen finden Sie unter [Verwalten von Startabbildern mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="a1165-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="a1165-173">Sie können ein startbares USB-Medium erstellen, um auf Tasksequenz basierte Configuration Manager-Bereitstellungen für Umgebungen zu initiieren, die keine PXE-Unterstützung haben.</span><span class="sxs-lookup"><span data-stu-id="a1165-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="a1165-174">Das startbare Medium enthält nur das Startabbild, optionale prestart-Befehle und die erforderlichen Dateien sowie Configuration Manager-Binärdateien, um das Booten in Windows PE zu unterstützen und die Verbindung mit Configuration Manager für den restlichen Bereitstellungsprozess herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a1165-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="a1165-175">Weitere Informationen finden Sie unter [Erstellen von Start](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)baren Medien.</span><span class="sxs-lookup"><span data-stu-id="a1165-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="a1165-176">Erstellen von Configuration Manager-Paketen</span><span class="sxs-lookup"><span data-stu-id="a1165-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1165-177">Die erforderliche Betriebssystemversion für jede Version des SRS-Installationsprogramms ändert sich mit jeder MSI-Version.</span><span class="sxs-lookup"><span data-stu-id="a1165-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="a1165-178">Wenn Sie die beste Version des Betriebssystems für eine bestimmte MSI-Datei ermitteln möchten, führen Sie das Setupskript für die Konsole einmal aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="a1165-179">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mithilfe von System Center Configuration Manager](room-systems-scale.md).</span><span class="sxs-lookup"><span data-stu-id="a1165-179">To learn more, see [Deploy Microsoft Teams Rooms by using System Center Configuration Manager](room-systems-scale.md).</span></span>

<span data-ttu-id="a1165-180">Configuration Manager erfordert eine Reihe von Paketen zum Bereitstellen und Konfigurieren der Microsoft Teams rooms-Einheiten.</span><span class="sxs-lookup"><span data-stu-id="a1165-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="a1165-181">Sie müssen die folgenden Pakete erstellen und konfigurieren und dann an die Configuration Manager-Standortsysteme verteilen, denen die Verteilungspunkt-Serverrolle zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a1165-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="a1165-182">**Paket Name**</span><span class="sxs-lookup"><span data-stu-id="a1165-182">**Package name**</span></span>                     | <span data-ttu-id="a1165-183">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a1165-183">**Type**</span></span>               | <span data-ttu-id="a1165-184">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a1165-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="a1165-185">SRS v2-SRS-Anwendungspaket</span><span class="sxs-lookup"><span data-stu-id="a1165-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="a1165-186">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-186">Software package</span></span>       | <span data-ttu-id="a1165-187">Paket für das Microsoft Teams Room Deployment Kit</span><span class="sxs-lookup"><span data-stu-id="a1165-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="a1165-188">SRS v2 – Sysprep-Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="a1165-189">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-189">Software package</span></span>       | <span data-ttu-id="a1165-190">Paket für die benutzerdefinierte unbeaufsichtigte XML-Datei zum Konfigurieren von Microsoft Teams-Zimmereinheiten</span><span class="sxs-lookup"><span data-stu-id="a1165-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="a1165-191">SRS v2-Set-SRSComputerName-Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="a1165-192">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-192">Software package</span></span>       | <span data-ttu-id="a1165-193">Paket für die HTML-Anwendung (HTA), um während der Bereitstellung einen Computernamen zuzuweisen</span><span class="sxs-lookup"><span data-stu-id="a1165-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="a1165-194">SRS v2 – Konfigurieren des SRS-Setups</span><span class="sxs-lookup"><span data-stu-id="a1165-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="a1165-195">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-195">Software package</span></span>       | <span data-ttu-id="a1165-196">Paket zum Konfigurieren der Bereitstellung der Microsoft Teams rooms-App</span><span class="sxs-lookup"><span data-stu-id="a1165-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="a1165-197">SRS v2-Betriebssystem Updates-Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="a1165-198">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-198">Software package</span></span>       | <span data-ttu-id="a1165-199">Paket zum Bereitstellen obligatorischer Betriebssystemupdates</span><span class="sxs-lookup"><span data-stu-id="a1165-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="a1165-200">SRS v2-Stammzertifikat Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="a1165-201">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-201">Software package</span></span>       | <span data-ttu-id="a1165-202">Optional – Paket zum Bereitstellen des Stammzertifikats (nicht erforderlich für Domänen verbundene Einheiten)</span><span class="sxs-lookup"><span data-stu-id="a1165-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="a1165-203">SRS V2 – Paket für Microsoft-Überwachungs-Agents</span><span class="sxs-lookup"><span data-stu-id="a1165-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="a1165-204">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-204">Software package</span></span>       | <span data-ttu-id="a1165-205">Optional – Paket zum Bereitstellen und Konfigurieren des Microsoft Operations Management Suite-Agents</span><span class="sxs-lookup"><span data-stu-id="a1165-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="a1165-206">SRS v2 – WinPE-Hintergrund Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="a1165-207">Software Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-207">Software package</span></span>       | <span data-ttu-id="a1165-208">Paket für das benutzerdefinierte Hintergrundbild, das für Start Bilder verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="a1165-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="a1165-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1165-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="a1165-210">Betriebssystemabbild</span><span class="sxs-lookup"><span data-stu-id="a1165-210">Operating system image</span></span> | <span data-ttu-id="a1165-211">Paket für die Installationsdatei des Betriebssystems (install. wim)</span><span class="sxs-lookup"><span data-stu-id="a1165-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="a1165-212">Surface pro</span><span class="sxs-lookup"><span data-stu-id="a1165-212">Surface Pro</span></span>                          | <span data-ttu-id="a1165-213">Treiberpaket</span><span class="sxs-lookup"><span data-stu-id="a1165-213">Driver package</span></span>         | <span data-ttu-id="a1165-214">Paket für die Gerätetreiber und Firmware für Microsoft Surface pro</span><span class="sxs-lookup"><span data-stu-id="a1165-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="a1165-215">Surface pro 4</span><span class="sxs-lookup"><span data-stu-id="a1165-215">Surface Pro 4</span></span>                        | <span data-ttu-id="a1165-216">Treiberpaket</span><span class="sxs-lookup"><span data-stu-id="a1165-216">Driver package</span></span>         | <span data-ttu-id="a1165-217">Paket für die Gerätetreiber und Firmware für Microsoft Surface pro 4</span><span class="sxs-lookup"><span data-stu-id="a1165-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="a1165-218">Weitere Informationen finden Sie unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="a1165-218">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="a1165-219">Erstellen von Ordnern für die Paketquelldateien</span><span class="sxs-lookup"><span data-stu-id="a1165-219">Create folders for the package source files</span></span>

<span data-ttu-id="a1165-220">Configuration Manager erfordert, dass Paketquelldateien in einer bestimmten Ordnerstruktur organisiert werden, wenn Sie zum ersten Mal erstellt und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1165-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="a1165-221">Erstellen Sie die folgende Ordnerstruktur auf der System Center Configuration Manager-Website für die Zentraladministration oder auf der primären Website oder auf einer Serverfreigabe, die Sie zum Hosten von Paketquelldateien verwenden:</span><span class="sxs-lookup"><span data-stu-id="a1165-221">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="a1165-222">SRS V2 – Paket für Microsoft-Überwachungs-Agents</span><span class="sxs-lookup"><span data-stu-id="a1165-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="a1165-223">SRS v2-Betriebssystem Updates-Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="a1165-224">SRS v2-Stammzertifikat Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="a1165-225">SRS v2-Set-SRSComputerName-Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="a1165-226">SRS v2-SRS-Anwendungspaket</span><span class="sxs-lookup"><span data-stu-id="a1165-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="a1165-227">SRS v2 – Konfigurieren des SRS-Setups</span><span class="sxs-lookup"><span data-stu-id="a1165-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="a1165-228">SRS v2 – Sysprep-Paket</span><span class="sxs-lookup"><span data-stu-id="a1165-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="a1165-229">Treiber</span><span class="sxs-lookup"><span data-stu-id="a1165-229">Drivers</span></span>
    -   <span data-ttu-id="a1165-230">Surface pro</span><span class="sxs-lookup"><span data-stu-id="a1165-230">Surface Pro</span></span>
    -   <span data-ttu-id="a1165-231">Surface pro 4</span><span class="sxs-lookup"><span data-stu-id="a1165-231">Surface Pro 4</span></span>
-   <span data-ttu-id="a1165-232">Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="a1165-232">Operating Systems</span></span>
    -   <span data-ttu-id="a1165-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1165-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="a1165-234">Sie können auch die ZIP-Datei [herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) und verwenden, die die Ordnerstruktur für die Pakete, die erforderlichen Skripts und die zu verwendende Tasksequenz Vorlage enthält, die Sie importieren müssen.</span><span class="sxs-lookup"><span data-stu-id="a1165-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="a1165-235">Erstellen des Überwachungs-Agent-Pakets</span><span class="sxs-lookup"><span data-stu-id="a1165-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="a1165-236">Laden Sie den Überwachungs- <https://go.microsoft.com/fwlink/?LinkId=828603>Agent von herunter.</span><span class="sxs-lookup"><span data-stu-id="a1165-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="a1165-237">Extrahieren Sie das Paket in den Ordner **SRS v2-Microsoft-Überwachungs-Agent-Paket** , indem Sie ein Eingabeaufforderungsfenster öffnen und **MMASetup-amd64. exe/c:** an der Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="a1165-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="a1165-238">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="a1165-239">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="a1165-240">Name<strong>: SRS V2 – Paket für Microsoft-Überwachungs-Agents</strong></span><span class="sxs-lookup"><span data-stu-id="a1165-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="a1165-241">Hersteller<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="a1165-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="a1165-242">Version<strong>: 8.1.11081.0</strong> (geben Sie die Version der heruntergeladenen Installationsdatei ein)</span><span class="sxs-lookup"><span data-stu-id="a1165-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="a1165-243">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-Microsoft-Überwachungs-Agent-Paket** Ordner ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="a1165-244">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="a1165-245">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="a1165-246">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="a1165-247">Erstellen des Betriebssystemupdates-Pakets</span><span class="sxs-lookup"><span data-stu-id="a1165-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="a1165-248">Erstellen Sie im Ordner **SRS v2-OS Updates Package** ein neues PowerShell-Skript mit dem Namen **install-SRSv2-OS-Updates. ps1**.</span><span class="sxs-lookup"><span data-stu-id="a1165-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="a1165-249">Kopieren Sie das Skript unten in das **install-SRSv2-OS-Updates. ps1** -Skript.</span><span class="sxs-lookup"><span data-stu-id="a1165-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="a1165-250">Alternativ können Sie das install-SRSv2-OS-Updates. ps1-Skript [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a1165-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="a1165-251">Laden Sie die obligatorischen Windows Update-Pakete in denselben Ordner herunter.</span><span class="sxs-lookup"><span data-stu-id="a1165-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a1165-252">Zu dem Zeitpunkt, zu dem dieser Artikel veröffentlicht wurde, war nur [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="a1165-253">Aktivieren Sie das Kontrollkästchen [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md), um festzustellen, ob andere Updates erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="a1165-254">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="a1165-255">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="a1165-256">Name: **SRS v2 – Betriebssystem Updates-Paket**</span><span class="sxs-lookup"><span data-stu-id="a1165-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="a1165-257">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a1165-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="a1165-258">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a1165-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="a1165-259">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-OS-Updatepaket** Ordner ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="a1165-260">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="a1165-261">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="a1165-262">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="a1165-263">Erstellen des Stammzertifikat Pakets (optional)</span><span class="sxs-lookup"><span data-stu-id="a1165-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="a1165-264">Sie erstellen dieses Paket, um das Stammzertifikat für Geräte zu verteilen, die nicht mit einer Active Directory-Domäne verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="a1165-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="a1165-265">Erstellen Sie dieses Paket nur, wenn die folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="a1165-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="a1165-266">Ihre Bereitstellung umfasst lokales lync oder Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a1165-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="a1165-267">Microsoft Teams rooms-Einheiten sind so konfiguriert, dass Sie in einer Arbeitsgruppe statt in einem Domänenmitglied funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="a1165-268">Kopieren Sie das Stammzertifikat in den Ordner **SRS v2 – Stammzertifikat Paket** .</span><span class="sxs-lookup"><span data-stu-id="a1165-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="a1165-269">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="a1165-270">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="a1165-271">Name: **SRS v2 – Stammzertifikat Paket**</span><span class="sxs-lookup"><span data-stu-id="a1165-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="a1165-272">Hersteller: *Name Ihrer Organisation*</span><span class="sxs-lookup"><span data-stu-id="a1165-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="a1165-273">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a1165-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="a1165-274">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum Ordner **SRS v2 – Stammzertifikat Paket** ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="a1165-275">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="a1165-276">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="a1165-277">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="a1165-278">Erstellen des Microsoft Teams Room Deployment Kit-Pakets</span><span class="sxs-lookup"><span data-stu-id="a1165-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="a1165-279">Laden Sie die neueste Version des **Microsoft Teams rooms Deployment Kit** von <https://go.microsoft.com/fwlink/?linkid=851168>herunter, und installieren Sie Sie auf einer Workstation.</span><span class="sxs-lookup"><span data-stu-id="a1165-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="a1165-280">Kopieren Sie den Inhalt von **C\\: Program Files (x86\\) Skype Room System Deployment Kit** in den Ordner **SRS v2-SRS-Anwendungspaket** .</span><span class="sxs-lookup"><span data-stu-id="a1165-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="a1165-281">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="a1165-282">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="a1165-283">Name: **SRS v2 – SRS-Anwendungspaket**</span><span class="sxs-lookup"><span data-stu-id="a1165-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="a1165-284">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a1165-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="a1165-285">Version: **3.1.104.0** (geben Sie die Version der heruntergeladenen Installationsdatei ein)</span><span class="sxs-lookup"><span data-stu-id="a1165-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="a1165-286">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-SRS-Anwendungspaket** Ordner ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="a1165-287">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="a1165-288">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="a1165-289">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="a1165-290">Erstellen des Aufgabenpakets "Computername"</span><span class="sxs-lookup"><span data-stu-id="a1165-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="a1165-291">Erstellen Sie im **Paketordner SRS v2-Set-SRSComputerName** eine neue HTML-Anwendung mit dem Namen **Set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="a1165-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="a1165-292">Kopieren Sie das folgende Skript in die **Set-SRSComputerName. HTA** -Datei.</span><span class="sxs-lookup"><span data-stu-id="a1165-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="a1165-293">Alternativ können Sie die Set-SRSComputerName. HTA-Datei [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a1165-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="a1165-294">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="a1165-295">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="a1165-296">Name: **SRS v2-Set-SRSComputerName-Paket**</span><span class="sxs-lookup"><span data-stu-id="a1165-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="a1165-297">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a1165-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="a1165-298">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a1165-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="a1165-299">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-Set-SRSComputerName-Paket** Ordner ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="a1165-300">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="a1165-301">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="a1165-302">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="a1165-303">Erstellen des Sysprep-Pakets</span><span class="sxs-lookup"><span data-stu-id="a1165-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="a1165-304">Erstellen Sie im Ordner **SRS v2 – Sysprep-Paket** eine neue XML-Datei mit dem Namen Unattend **. XML** .</span><span class="sxs-lookup"><span data-stu-id="a1165-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="a1165-305">Kopieren Sie den folgenden Text in die Datei **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="a1165-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="a1165-306">Alternativ können Sie die Datei "Unattend. xml" [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a1165-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="a1165-307">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="a1165-308">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="a1165-309">Name: **SRS v2 – Sysprep-Paket**</span><span class="sxs-lookup"><span data-stu-id="a1165-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="a1165-310">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a1165-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="a1165-311">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a1165-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="a1165-312">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum Ordner **SRS v2 – Sysprep-Paket** ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="a1165-313">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="a1165-314">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="a1165-315">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="a1165-316">Erstellen des Windows 10 Enterprise-Pakets</span><span class="sxs-lookup"><span data-stu-id="a1165-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="a1165-317">Besorgen Sie sich ein Windows 10 Enterprise x64-Medium, und kopieren Sie die Datei " **install. wim** " in den **\\Windows 10 Enterprise** -Ordner der Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="a1165-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="a1165-318">Wechseln Sie in der Configuration Manager-Konsole zu den Betriebs **System**Abbildern der **Software Bibliothek** \> \*\*\*\* \> , und wählen Sie dann **Betriebssystemabbild hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="a1165-319">Geben Sie den Pfad zu der soeben kopierten **install. wim** -Datei an, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="a1165-320">Aktualisieren Sie das Feld **Version** so, dass es der Buildnummer des Windows 10 Enterprise-Bilds entspricht, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="a1165-321">Überprüfen Sie die Seite **Details** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="a1165-322">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-322">Select **Close**.</span></span>

<span data-ttu-id="a1165-323">Weitere Informationen finden Sie unter [Verwalten von Betriebssystemabbildern mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="a1165-323">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="a1165-324">Erstellen von Surface pro-Gerätetreiberpaketen</span><span class="sxs-lookup"><span data-stu-id="a1165-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="a1165-325">Microsoft Teams Rooms wird sowohl für Surface pro als auch Surface pro 4 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1165-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="a1165-326">Sie müssen für jedes Surface pro-Modell, das Sie in Ihrer Umgebung haben, ein Treiberpaket erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1165-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1165-327">Die Treiber müssen mit dem Windows 10 Enterprise Build und der Microsoft Teams Room Deployment Kit-Version kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="a1165-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="a1165-328">Weitere Informationen finden Sie unter [herunterladen der neuesten Firmware und Treiber für Surface-Geräte](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) und [Konfigurieren einer Konsole](console.md).</span><span class="sxs-lookup"><span data-stu-id="a1165-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="a1165-329">Laden Sie die neuesten Treiber und Firmware herunter.</span><span class="sxs-lookup"><span data-stu-id="a1165-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="a1165-330">Für Surface pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="a1165-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="a1165-331">Für Surface pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="a1165-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="a1165-332">Extrahieren Sie den heruntergeladenen Treiber und die Firmware.</span><span class="sxs-lookup"><span data-stu-id="a1165-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="a1165-333">Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie an der Eingabeaufforderung einen der folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="a1165-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="a1165-334">Wechseln Sie in der Configuration Manager-Konsole zu den Treibern der **Software Bibliothek** \> - **Betriebssysteme** \> \*\*\*\*, und wählen Sie dann **Treiber importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="a1165-335">Wählen Sie **alle Treiber importieren im folgenden Netzwerkpfad (UNC)** aus, wählen Sie den Quellordner aus (beispielsweise\\C\\:\\_Sources Driver Surface pro), und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="a1165-336">Wählen Sie auf der Seite **Geben Sie die Details für die importierten Treiber** an alle aufgeführten Treiber aus, und wählen Sie dann **Diese Treiber aktivieren aus, und ermöglichen Sie es Computern, Sie zu installieren**.</span><span class="sxs-lookup"><span data-stu-id="a1165-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="a1165-337">Wählen Sie **Kategorien**aus, erstellen Sie eine neue Kategorie, die dem Oberflächenmodell entspricht, wählen Sie **OK**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="a1165-338">Wählen Sie **neues Paket**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="a1165-339">Geben Sie den Paketnamen an, der dem Surface pro-Modell entspricht, geben Sie einen Ordnerpfad zum Speichern der Treiberpaketdateien ein, wählen Sie **OK**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="a1165-340">Stellen Sie sicher, dass auf der Seite **Start Bilder** keine Startabbilder ausgewählt sind, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="a1165-341">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-341">Select **Close**.</span></span>

11. <span data-ttu-id="a1165-342">Wechseln Sie zu den Treibern der **Software Bibliothek** \> - **Betriebssysteme** \> \*\*\*\*, wählen Sie Ordner \*\* \> erstellen\*\*aus, und geben Sie einen Ordnernamen ein, der dem Surface pro-Modell entspricht, für das Sie die Treiber gerade importiert haben.</span><span class="sxs-lookup"><span data-stu-id="a1165-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="a1165-343">Verschieben Sie alle importierten Treiber in den neu erstellten Ordner, um die Navigation und den Vorgang zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a1165-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="a1165-344">Wiederholen Sie diese Schritte für andere Surface pro-Modelle, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="a1165-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="a1165-345">Weitere Informationen finden Sie unter [Verwalten von Treibern in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="a1165-345">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="a1165-346">Konfigurationspaket "Microsoft Teams-Chatrooms erstellen"</span><span class="sxs-lookup"><span data-stu-id="a1165-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="a1165-347">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="a1165-348">Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a1165-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="a1165-349">Name: **SRS v2 – Konfigurieren des SRS-Setup Pakets**</span><span class="sxs-lookup"><span data-stu-id="a1165-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="a1165-350">Hersteller: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a1165-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="a1165-351">Version: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a1165-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="a1165-352">Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-Setup-** Ordner ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="a1165-353">Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="a1165-354">Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="a1165-355">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="a1165-356">Verteilen von Configuration Manager-Paketen</span><span class="sxs-lookup"><span data-stu-id="a1165-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="a1165-357">Alle Pakete müssen an die Server verteilt werden, denen die Verteilungspunktrolle in der Configuration Manager-Hierarchie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a1165-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="a1165-358">Führen Sie die folgenden Anweisungen aus, um die Paketverteilung zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="a1165-359">Softwarepakete verteilen.</span><span class="sxs-lookup"><span data-stu-id="a1165-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="a1165-360">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**.</span><span class="sxs-lookup"><span data-stu-id="a1165-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="a1165-361">Wählen Sie alle Softwarepakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a1165-362">Überprüfen Sie die Liste der Pakete, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a1165-363">Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilungspunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a1165-364">Wählen Sie **weiter**aus, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="a1165-365">Treiberpakete verteilen.</span><span class="sxs-lookup"><span data-stu-id="a1165-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="a1165-366">Wechseln Sie in der Configuration Manager-Konsole zu den **Treiberpaketen**für **Software Bibliothek** \> - **Betriebssysteme** \> .</span><span class="sxs-lookup"><span data-stu-id="a1165-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="a1165-367">Wählen Sie alle Treiberpakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a1165-368">Überprüfen Sie die Liste der Pakete, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a1165-369">Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilungspunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a1165-370">Wählen Sie **weiter**aus, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="a1165-371">Verteilen von Betriebssystempaketen</span><span class="sxs-lookup"><span data-stu-id="a1165-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="a1165-372">Wechseln Sie in der Configuration Manager-Konsole zu den \*\*\*\* \> **Betriebssystem**Abbildern der **Software Bibliothek** \> .</span><span class="sxs-lookup"><span data-stu-id="a1165-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="a1165-373">Wählen Sie alle Betriebssystem Bilder aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a1165-374">Überprüfen Sie die Liste der Pakete, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a1165-375">Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilungspunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a1165-376">Wählen Sie **weiter**aus, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="a1165-377">Die Paketverteilung kann abhängig von der Paketgröße, der Configuration Manager-Hierarchie, der Anzahl der Verteilungspunktserver und der in Ihrem Netzwerk verfügbaren Bandbreite einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="a1165-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="a1165-378">Alle Pakete müssen verteilt werden, bevor Sie mit der Bereitstellung einer Microsoft Teams rooms-Einheit beginnen können.</span><span class="sxs-lookup"><span data-stu-id="a1165-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="a1165-379">Sie können den Status Ihrer Paketverteilung in der Configuration Manager-Konsole überprüfen, indem \*\*\*\* \> Sie auf den **Inhaltsstatus**des **Verteilungsstatus** \> überwachen wechseln.</span><span class="sxs-lookup"><span data-stu-id="a1165-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="a1165-380">Tasksequenzen für Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a1165-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="a1165-381">Sie verwenden Tasksequenzen mit System Center Configuration Manager, um die Schritte zum Bereitstellen eines Betriebs System Abbilds auf einem Zielcomputer zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-381">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="a1165-382">Wenn Sie eine Microsoft Teams rooms-Einheit auf automatisierte Weise bereitstellen möchten, erstellen Sie eine Tasksequenz, die auf das Startabbild verweist, das zum Starten des Microsoft Teams Room-Zielcomputers, des Windows 10 Enterprise-Betriebssystemabbilds, das Sie installieren möchten, und allen andere zusätzliche Inhalte wie andere Anwendungen oder Softwareupdates.</span><span class="sxs-lookup"><span data-stu-id="a1165-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="a1165-383">Importieren der Beispiel Tasksequenz</span><span class="sxs-lookup"><span data-stu-id="a1165-383">Import the sample task sequence</span></span>

<span data-ttu-id="a1165-384">Sie können eine Beispiel Tasksequenz herunterladen und auf einfache Weise importieren und an Ihre Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="a1165-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="a1165-385">[**Laden**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) Sie die Beispiel Tasksequenz herunter, und kopieren Sie die heruntergeladene ZIP-Datei an einen freigegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a1165-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="a1165-386">Wechseln Sie in der Configuration Manager-Konsole zu den **Tasksequenzen** **Software Library** \> **Operating Systems** \> , und wählen Sie dann **Tasksequenz importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="a1165-387">Wählen Sie **Durchsuchen**aus, wechseln Sie zum Speicherort des freigegebenen Ordners, den Sie in Schritt 1 verwendet haben, wählen Sie die **Microsoft Teams Room Deployment (en-US). zip** -Datei aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="a1165-388">Legen Sie **Aktion** auf **neu erstellen**, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="a1165-389">Bestätigen Sie die Einstellungen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="a1165-390">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="a1165-391">Überprüfen Sie, ob die Verweis Pakete ordnungsgemäß mit jedem Tasksequenzschritt verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="a1165-392">Wählen Sie die importierte Tasksequenz aus, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="a1165-393">Der Task Sequenz-Editor wird geöffnet und zeigt jeden sequenziellen Schritt an, den Sie für die Bereitstellung und Konfiguration einer Microsoft Teams rooms-Einheit benötigen.</span><span class="sxs-lookup"><span data-stu-id="a1165-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="a1165-394">Durchlaufen Sie die einzelnen Schritte, und führen Sie die empfohlenen Updates aus:</span><span class="sxs-lookup"><span data-stu-id="a1165-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="a1165-395">**Neustart in Windows PE**: dieser Schritt wird neu gestartet und dann der Computer in Windows PXE gestartet.</span><span class="sxs-lookup"><span data-stu-id="a1165-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="a1165-396">Für diesen Schritt sind keine Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="a1165-397">**Partition Disk 0 – UEFI**: dieser Schritt löscht die Datenträgerkonfiguration und erstellt Partitionen basierend auf den konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a1165-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="a1165-398">Wir empfehlen, dass Sie an diesem Schritt keine Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a1165-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="a1165-399">**SRS-Computer Name einrichten**: dieser Schritt umfasst eine HTML-Anwendung, um eine Benutzeroberfläche bereitzustellen, um einen Computer Namen für die Einheit Microsoft Teams rooms während der Bereitstellung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="a1165-400">Dies ist ein optionaler Schritt, der aber nur deaktiviert werden kann, wenn Sie die Computer Namensgebung in einem anderen Prozess verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="a1165-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="a1165-401">Überprüfen Sie, ob das Paket **SRS v2-Set-SRSComputerName** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="a1165-402">Wenn dies nicht der Fall ist, wechseln Sie zum Paket, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="a1165-403">**Betriebssystem anwenden**: dieser Schritt gibt das Betriebssystemabbild an, das bereitgestellt werden soll, und die zu verwendende Antwortdatei für die unbeaufsichtigte Sysprep.</span><span class="sxs-lookup"><span data-stu-id="a1165-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="a1165-404">Überprüfen Sie, ob die richtige Abbilddatei für das Windows 10 Enterprise-Betriebssystem ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="a1165-405">Stellen Sie sicher, dass die **Verwendung einer Antwortdatei für eine unbeaufsichtigte oder Sysprep für eine benutzerdefinierte Installation** aktiviert ist und das **SRS v2-Sysprep-Paket** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="a1165-406">Stellen Sie außerdem sicher, dass der **Dateiname** auf **Unattend. XML**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="a1165-407">**Windows-Einstellungen übernehmen**: dieser Schritt sammelt Informationen zur Windows-Installation.</span><span class="sxs-lookup"><span data-stu-id="a1165-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="a1165-408">Stellen Sie Lizenzierungs-und Registrierungsinformationen bereit, einschließlich des Product Keys, des Kennworts für das lokale Administratorkonto und der Zeitzone (je nach Ihren Anforderungen).</span><span class="sxs-lookup"><span data-stu-id="a1165-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="a1165-409">**Netzwerkeinstellungen übernehmen**: mit diesem Schritt können Sie eine Arbeitsgruppe oder einen Active Directory-Domänennamen und eine Organisationseinheit angeben.</span><span class="sxs-lookup"><span data-stu-id="a1165-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="a1165-410">Informationen zu empfohlenen Aktionen, die Sie beim Bereitstellen von Microsoft Teams rooms-Einheiten als Mitglieder einer Actve-Verzeichnisdomäne ausführen müssen, finden Sie unter [Überlegungen zu Skype Room System Domain Joining](domain-joining-considerations.md) .</span><span class="sxs-lookup"><span data-stu-id="a1165-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="a1165-411">**Anwenden von Treibern:** Dieser Schritt und seine unter Schritte werden verwendet, um anwendbare Gerätetreiber und Firmware basierend auf dem von Ihnen verwendeten Surface pro-Modell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a1165-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="a1165-412">Aktualisieren Sie die einzelnen Schritte, um das entsprechende Treiberpaket anzugeben, das dieser Bereitstellung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="a1165-413">Jedes Treiberpaket ist so konfiguriert, dass es die Windows-Verwaltungsinstrumentation (WMI)-Filter nutzt, um relevante Treiber und Firmware basierend auf dem Surface pro-Hersteller und-Modell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a1165-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="a1165-414">Wir empfehlen dringend, dass Sie die Konfiguration dieser Treiber nicht ändern, da die Bereitstellung andernfalls möglicherweise fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a1165-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="a1165-415">**Einrichten von Windows und Configuration Manager**: dieser Schritt stellt den Configuration Manager-Client bereit und konfiguriert ihn.</span><span class="sxs-lookup"><span data-stu-id="a1165-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="a1165-416">Aktualisieren Sie diesen Schritt, um das integrierte Configuration Manager-Client Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a1165-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="a1165-417">**Installieren des Stammzertifikats**: mit diesem Schritt wird das Stammzertifikat für nicht-Domänen verbundene Geräte verteilt und ist daher standardmäßig optional und deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1165-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="a1165-418">Aktivieren Sie diesen Schritt, wenn Sie ein Stammzertifikat für die Microsoft Teams-Zimmereinheiten bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="a1165-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="a1165-419">Wenn Sie diesen Schritt ausführen müssen, stellen Sie sicher, dass das **SRS v2 – Stammzertifikat Paket** und die Deaktivierung der **64-Bit-Dateisystem Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="a1165-420">**Installieren und Konfigurieren des Überwachungs-Agents**: mit diesem Schritt wird die 64-Bit-Version des Microsoft Azure Monitor-Agents installiert und der Agent so konfiguriert, dass eine Verbindung mit Ihrem Protokollanalyse Arbeitsbereich hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a1165-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="a1165-421">Dieser Schritt ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1165-421">This step is disabled by default.</span></span> <span data-ttu-id="a1165-422">Aktivieren Sie diesen Schritt nur, wenn Sie den Überwachungs-Agent verwenden möchten, um den Status Ihrer Microsoft Teams-Zimmereinheiten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a1165-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="a1165-423">Bearbeiten Sie diesen Schritt, und aktualisieren Sie die Befehlszeilenparameter, um die **Arbeitsbereichs-ID** und den **Arbeitsbereichs Schlüssel**anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a1165-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="a1165-424">Weitere Informationen zum Abrufen der Arbeitsbereichs-ID der Operations Management Suite und des Primärschlüssels finden Sie unter [Konfigurieren von Testgeräten für die Azure-Überwachung](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .</span><span class="sxs-lookup"><span data-stu-id="a1165-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="a1165-425">Vergewissern Sie sich, dass das **SRS v2 – Microsoft Monitoring Agent-Paket** und die Deaktivierung der **64-Bit-Dateisystem Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="a1165-426">Weitere Informationen zum Überwachen der Integrität Ihrer Microsoft Teams rooms-Bereitstellung finden Sie unter [Planen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-plan.md), [Bereitstellen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-deploy.md) und [Verwalten von Microsoft Teams Räume Geräte mit Azure Monitor](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="a1165-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="a1165-427">**Kopieren von SRS v2-Konfigurationsdateien**: dieser Schritt kopiert die erforderlichen Setup-und Konfigurationsdateien aus dem Microsoft Teams rooms Deployment Kit auf die lokale Festplatte.</span><span class="sxs-lookup"><span data-stu-id="a1165-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="a1165-428">Für diesen Schritt sind keine Anpassungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="a1165-429">Vergewissern Sie sich, dass das **SRS v2-SRS-Anwendungspaket** und die Deaktivierung der **64-Bit-Dateisystem Umleitung** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="a1165-430">**Installieren-SRSv2-OS-Updates**: in diesem Schritt werden alle obligatorischen Betriebssystemupdates bereitgestellt, die für die Microsoft Teams rooms-Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="a1165-431">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a1165-431">Do the following:</span></span>
       -   <span data-ttu-id="a1165-432">Aktivieren Sie das Kontrollkästchen [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md) , um festzustellen, welche Updates erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="a1165-433">Überprüfen Sie, ob Ihr **SRS v2 – OS-Updatepaket** alle erforderlichen Updates enthält.</span><span class="sxs-lookup"><span data-stu-id="a1165-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="a1165-434">Überprüfen Sie, ob das **Paket SRS v2 – Betriebssystem Updates** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="a1165-435">Überprüfen Sie, ob die PowerShell-Ausführungsrichtlinie auf **Bypass**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="a1165-436">**Computer neu starten**: mit diesem Schritt wird der Computer neu gestartet, nachdem die obligatorischen Betriebssystemupdates installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1165-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="a1165-437">Für diesen Schritt sind keine Anpassungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="a1165-438">**Konfigurieren von Windows-Komponenten**: in diesem Schritt werden die erforderlichen Windows-Features konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a1165-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="a1165-439">Für diesen Schritt sind keine Anpassungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="a1165-440">**Computer neu starten**: mit diesem Schritt wird der Computer neu gestartet, nachdem die Windows-Features konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1165-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="a1165-441">Für diesen Schritt sind keine Anpassungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="a1165-442">**Lokalen Skype-Nutzer hinzufügen**: mit diesem Schritt wird das lokale Skype-Konto erstellt, das für die automatische Anmeldung bei Windows und das Starten der Microsoft Teams rooms-Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1165-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="a1165-443">Diesem Schritt ist kein Softwarepaket zugeordnet, und es ist keine Anpassung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1165-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="a1165-444">**Einrichten und Konfigurieren von SRS-Anwendungen**: dieser Schritt konfiguriert die Anwendungsinstallation von Microsoft Teams rooms für den nächsten Start des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="a1165-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="a1165-445">Vergewissern Sie sich, dass das SRS **v2 – Setup-Paket** für die SRS-Konfiguration und die **64-Bit-Dateisystem Umleitung deaktiviert** sind.</span><span class="sxs-lookup"><span data-stu-id="a1165-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1165-446">Es ist sehr wichtig, dass die Tasksequenzschritte in der angegebenen Reihenfolge ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a1165-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="a1165-447">Wenn Sie die Reihenfolge der Schritte ändern oder zusätzliche Schritte konfigurieren, kann dies die Bereitstellung unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="a1165-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="a1165-448">Das **Einrichten und Konfigurieren des SRS-Anwendungs** Schritts muss der letzte Schritt in der Tasksequenz sein, da andernfalls möglicherweise die Bereitstellung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a1165-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="a1165-449">Erstellen einer Bereitstellung für die Tasksequenz</span><span class="sxs-lookup"><span data-stu-id="a1165-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="a1165-450">Wählen Sie die Tasksequenz aus, und wählen Sie **Bereitstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="a1165-451">Wählen Sie **Durchsuchen** aus, um die Zielsammlung für die Bereitstellung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a1165-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="a1165-452">Wählen Sie **alle unbekannten Computer** aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="a1165-453">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-453">Select **Next**.</span></span>

5. <span data-ttu-id="a1165-454">Wählen Sie in der \*\*\*\* Dropdownliste Purpose **available (verfügbar** ) aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="a1165-455">Wählen Sie **nur Medien und PXE** in der Liste in der **folgenden Liste verfügbar machen** aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="a1165-456">Es ist sehr wichtig, \*\*\*\* dass Purpose auf **available**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="a1165-457">Stellen Sie sicher, dass der **Zweck** **nicht** auf **erforderlich**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="a1165-458">Stellen Sie außerdem sicher, dass Sie **nur Medien und PXE** in der **folgenden verfügbar machen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="a1165-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="a1165-459">Wenn diese Werte auf etwas anderes festgelegt werden, kann dies dazu führen, dass alle Computer beim Booten das Bereitstellungs Bild von Microsoft Teams rooms erhalten.</span><span class="sxs-lookup"><span data-stu-id="a1165-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="a1165-460">Geben Sie keinen Zeitplan an, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="a1165-461">Ändern Sie im Abschnitt **Benutzerfreundlichkeit** nichts, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="a1165-462">Ändern Sie im Abschnitt **Benachrichtigungen** nichts, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="a1165-463">Ändern Sie im Abschnitt Verteilungs **Punkte** nichts, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="a1165-464">Bestätigen Sie die Einstellungen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="a1165-465">Wählen Sie **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="a1165-466">Überprüfen und Problembehandlung der Lösung</span><span class="sxs-lookup"><span data-stu-id="a1165-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="a1165-467">Nachdem Sie die Tasksequenzen des System Center Configuration Manager abgeschlossen haben, müssen Sie einen Testlauf durchführen, um zu überprüfen, ob die Tasksequenz Microsoft Teams-Zimmereinheiten bereitstellen und konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="a1165-467">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="a1165-468">Verbinden Sie das Test Gerät mit dem kabelgebundenen Netzwerk, indem Sie einen der unterstützten Ethernet-Adapter verwenden oder die Surface-Docking-Station verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1165-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="a1165-469">Wenn die PXE-Start Funktionalität für Ihre Umgebung nicht konfiguriert wurde, können Sie das Startabbild auf dem USB-Stick verwenden, den [Sie zuvor erstellt](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) haben, um von USB zu booten und mit Configuration Manager zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="a1165-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="a1165-470">Zugreifen auf die Firmware und Initiieren des PXE-Starts:</span><span class="sxs-lookup"><span data-stu-id="a1165-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="a1165-471">Stellen Sie sicher, dass das Surface-Gerät ausgeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="a1165-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="a1165-472">Drücken Sie die **Lautstärke** Taste und halten Sie sie gedrückt.</span><span class="sxs-lookup"><span data-stu-id="a1165-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="a1165-473">Drücken Sie die **Power** -Taste, und lassen Sie sie los.</span><span class="sxs-lookup"><span data-stu-id="a1165-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="a1165-474">Nachdem das Gerät gestartet wurde, lassen Sie die **Lautstärke** Taste los.</span><span class="sxs-lookup"><span data-stu-id="a1165-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="a1165-475">Wählen Sie **Startkonfiguration**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="a1165-476">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a1165-476">Do one of the following:</span></span>

        -   <span data-ttu-id="a1165-477">Wählen Sie **PXE-Start**aus, und ziehen Sie den Mauszeiger an den Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="a1165-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="a1165-478">Sie können aber auch nach links auf dem Netzwerkadapter wischen, um sofort auf das Gerät zu booten.</span><span class="sxs-lookup"><span data-stu-id="a1165-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="a1165-479">Dies wirkt sich nicht auf die Startreihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="a1165-480">Wählen Sie das USB-Flashlaufwerk aus, das die Startmedien enthält.</span><span class="sxs-lookup"><span data-stu-id="a1165-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="a1165-481">Wählen Sie **Beenden**und dann **jetzt neu starten**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="a1165-482">Wenn Sie dazu aufgefordert werden, wählen Sie für den Netzwerkstart Dienst **Enter** aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="a1165-483">Windows PE wird in den Arbeitsspeicher geladen, und der Task Sequenz-Assistent wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="a1165-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="a1165-484">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="a1165-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="a1165-485">Wählen Sie die zuvor importierte Tasksequenz aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a1165-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="a1165-486">Nachdem die Datenträgerkonfiguration angewendet wurde, werden Sie aufgefordert, einen Computernamen für das Gerät anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a1165-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="a1165-487">Auf der Benutzeroberfläche wird ein empfohlener Computername basierend auf der Seriennummer des Surface pro-Geräts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1165-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="a1165-488">Sie können entweder den vorgeschlagenen Namen akzeptieren oder einen neuen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="a1165-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="a1165-489">Folgen Sie den Anweisungen auf dem Bildschirm Computername-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="a1165-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="a1165-490">Wenn Sie **annehmen**auswählen, beginnt die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a1165-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="a1165-491">Der restliche Bereitstellungsprozess ist automatisch und fordert keine weitere Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="a1165-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="a1165-492">Nachdem die Bereitstellungstasksequenz die Konfiguration des Geräts abgeschlossen hat, wird der folgende Konfigurationsbildschirm angezeigt, in dem Sie aufgefordert werden, die Anwendungseinstellungen für Microsoft Teams Rooms zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Bildschirm ' Initial Setup ' für die Microsoft Teams rooms-Anwendung](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="a1165-494">Schließen Sie das Surface pro an die Microsoft Teams rooms-Konsole an, und konfigurieren Sie die Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a1165-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="a1165-495">Überprüfen Sie, ob die in [Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) -Chatrooms aufgeführten Funktionen auf dem bereitgestellten Gerät funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="a1165-496">Wenn Sie eine fehlerhafte Installation beheben möchten, überprüfen Sie die Datei **"smsts. log** , in der alle in einer Configuration Manager-Tasksequenz ausgeführten Schritte protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="a1165-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="a1165-497">Die Datei "" smsts. log "wird je nach Phase des Buildprozesses in einer Reihe von Pfaden gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1165-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="a1165-498">Überprüfen Sie die folgende Tabelle, um den Pfad zur Datei "" smsts. log "zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a1165-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="a1165-499">**Bereitstellungsphase**</span><span class="sxs-lookup"><span data-stu-id="a1165-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="a1165-500">**Task Sequenzprotokoll Pfad**</span><span class="sxs-lookup"><span data-stu-id="a1165-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="a1165-501">WinPE, vor dem Festplattenformat</span><span class="sxs-lookup"><span data-stu-id="a1165-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="a1165-502">X:\\Windows\\Temp\\smstslog\\"smsts. log</span><span class="sxs-lookup"><span data-stu-id="a1165-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="a1165-503">WinPE, nach Festplattenformat</span><span class="sxs-lookup"><span data-stu-id="a1165-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="a1165-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\"smsts. log</span><span class="sxs-lookup"><span data-stu-id="a1165-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="a1165-505">Betriebssystem, das vor der Installation des Configuration Manager-Agents bereitgestellt wurde</span><span class="sxs-lookup"><span data-stu-id="a1165-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="a1165-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\"smsts. log</span><span class="sxs-lookup"><span data-stu-id="a1165-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="a1165-507">Betriebssystem und bereitgestellter Configuration Manager-Agent</span><span class="sxs-lookup"><span data-stu-id="a1165-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="a1165-508">% windir%\\System32\\ccm\\-\\Protokolle\\Smstslog "smsts. log</span><span class="sxs-lookup"><span data-stu-id="a1165-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="a1165-509">Ausführung der Task Sequenz abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="a1165-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="a1165-510">% windir%\\System32\\ccm\\-\\Protokolle "smsts. log</span><span class="sxs-lookup"><span data-stu-id="a1165-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="a1165-511">Sie können **F8** während der Tasksequenz zu einem beliebigen Zeitpunkt auswählen, um eine Befehlskonsole zu öffnen, und dann Zugriff auf die Datei "" smsts. log "erhalten.</span><span class="sxs-lookup"><span data-stu-id="a1165-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="a1165-512">Wenn Sie Probleme mit dem PXE-Start beheben möchten, überprüfen Sie die beiden Protokolldateien auf dem Configuration Manager-Server, die für PXE-Aktionen spezifisch sind:</span><span class="sxs-lookup"><span data-stu-id="a1165-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="a1165-513">**Pxecontrol. log**, befindet sich im Configuration Manager-Installationsprotokoll Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="a1165-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="a1165-514">**"SMSPXE. log**, befindet sich im Configuration Manager-Verwaltungspunkt (MP)-Protokollverzeichnis</span><span class="sxs-lookup"><span data-stu-id="a1165-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="a1165-515">Eine vollständige Liste der Protokolldateien, die Sie zur weiteren Problembehandlung bei der Installation von Configuration Manager verwenden können, finden Sie unter [Protokolldateien in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="a1165-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
