---
title: Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Informationen Sie zum Konfigurieren von Skype für Business Cloud Connector Edition, eine minimale lokalen Topologie zum Aktivieren der Integration von Ihrer lokalen VoIP-Infrastruktur in Telefonsystem in Office 365 (Cloud, PBX) VoIP-Dienste in Skype für Business Online.
ms.openlocfilehash: 3872bf212d3a0a12f5fc63eb62930cfb20314f13
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885636"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="5e570-103">Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="5e570-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="5e570-104">Informationen Sie zum Konfigurieren von Skype für Business Cloud Connector Edition, eine minimale lokalen Topologie zum Aktivieren der Integration von Ihrer lokalen VoIP-Infrastruktur in Telefonsystem in Office 365 (Cloud, PBX) VoIP-Dienste in Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="5e570-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="5e570-105">Bevor Sie beginnen, sollten Sie die erforderlichen Komponenten in [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="5e570-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5e570-106">Die Schritte in diesem Thema gelten nur für Cloud Connector Edition 1.4.1 und höher. </span><span class="sxs-lookup"><span data-stu-id="5e570-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="5e570-107">Wenn Sie noch nicht auf die Cloud Connector Edition 2.1 aktualisiert haben, finden Sie unter [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5e570-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="5e570-108">Sie können die Installationsdatei aus herunterladen [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="5e570-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="5e570-109">Schritte zum Konfigurieren von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="5e570-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="5e570-110">In der folgenden Tabelle finden Sie eine Auflistung der notwendigen Schritte zum Installieren und Konfigurieren von Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="5e570-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="5e570-111">**Schritt**</span><span class="sxs-lookup"><span data-stu-id="5e570-111">**Step**</span></span>|<span data-ttu-id="5e570-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5e570-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5e570-113">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="5e570-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="5e570-114">Laden Sie die Installationsdatei, Zertifikate, Konfigurieren von Hyper-V und bereiten Sie Ihre Umgebung für die Bereitstellung von Cloud-Connector.</span><span class="sxs-lookup"><span data-stu-id="5e570-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="5e570-115">Bereitstellen eines einzelnen Standorts in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5e570-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="5e570-116">Erstellen Sie in Ihrer Cloud Connector-Bereitstellung einen Standort.</span><span class="sxs-lookup"><span data-stu-id="5e570-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="5e570-117">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5e570-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="5e570-118">Fügen Sie Ihrer Bereitstellung Standorte hinzu, und informieren Sie sich über die Unterschiede zwischen der Bereitstellung mit einem einzelnen Standort und mit mehreren Standorten.</span><span class="sxs-lookup"><span data-stu-id="5e570-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="5e570-119">Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="5e570-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="5e570-120">Fügen Sie DNS-Einträge hinzu, erstellen Sie eine Hybridkonfiguration, richten Sie PSTN-Gateways ein, und aktivieren Sie Benutzer für Voicemail im Telefonsystem in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e570-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="5e570-121">Überprüfen der Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5e570-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="5e570-122">Stellen Sie sicher, dass Ihre Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5e570-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="5e570-123">Aktualisieren auf eine neue Version von Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5e570-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="5e570-124">Aktualisieren Sie die vorhandene Cloud Connector-Bereitstellung auf Version 2.1.</span><span class="sxs-lookup"><span data-stu-id="5e570-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="5e570-125">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5e570-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="5e570-126">Ändern Sie Einstellungen in der Cloud Connector, nachdem es bereits bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5e570-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="5e570-127">Die medienumgehung in der Cloud Connector Edition bereitstellen</span><span class="sxs-lookup"><span data-stu-id="5e570-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="5e570-128">Hier erfahren Sie, wie Sie die Medienumgehung in Cloud Connector bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5e570-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="5e570-129">Cmdlet-Referenz für Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5e570-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="5e570-130">Erfahren Sie mehr über die in Cloud Connector verwendeten PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5e570-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="5e570-131">Problembehandlung bei Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5e570-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="5e570-132">Lösungen zu häufig auftretende Probleme mit einer Cloud-Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5e570-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

