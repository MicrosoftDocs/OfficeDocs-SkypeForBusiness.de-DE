---
title: Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition
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
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Hier erfahren Sie, wie Sie Skype for Business Cloud Connector Edition, eine minimale lokale Topologie, konfigurieren, um die Integration Ihrer lokalen VoIP-Infrastruktur mit Telefon System-VoIP-Diensten (Cloud PBX) in Skype for Business Online zu ermöglichen.
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219515"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1c14e-103">Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1c14e-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="1c14e-104">Hier erfahren Sie, wie Sie Skype for Business Cloud Connector Edition, eine minimale lokale Topologie, konfigurieren, um die Integration Ihrer lokalen VoIP-Infrastruktur mit Telefon System-VoIP-Diensten (Cloud PBX) in Skype for Business Online zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1c14e-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="1c14e-105">Bevor Sie beginnen, sollten Sie die Voraussetzungen in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1c14e-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1c14e-106">Die Schritte in diesem Thema gelten nur für Cloud Connector Edition 1.4.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="1c14e-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="1c14e-107">Wenn Sie noch nicht auf Cloud Connector Edition 2,1 aktualisiert haben, finden Sie weitere Informationen unter [Upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1c14e-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="1c14e-108">Sie können die Installationsdatei von herunterladen [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="1c14e-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1c14e-109">Schritte zum Konfigurieren von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1c14e-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="1c14e-110">In der folgenden Tabelle sind die Schritte aufgeführt, die Sie zum Installieren und Konfigurieren von Cloud Connector Edition benötigen:</span><span class="sxs-lookup"><span data-stu-id="1c14e-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="1c14e-111">**Schritt**</span><span class="sxs-lookup"><span data-stu-id="1c14e-111">**Step**</span></span>|<span data-ttu-id="1c14e-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1c14e-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1c14e-113">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="1c14e-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="1c14e-114">Laden Sie die Installationsdatei herunter, bereiten Sie Zertifikate vor, konfigurieren Sie Hyper-V, und nutzen Sie Ihre Umgebung für Ihre Cloud Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="1c14e-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-115">Bereitstellen eines einzelnen Standorts in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1c14e-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="1c14e-116">Erstellen Sie eine Website in ihrer Cloud Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="1c14e-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-117">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1c14e-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="1c14e-118">Fügen Sie Ihrer Bereitstellung Websites hinzu, und erfahren Sie mehr über die Unterschiede zwischen Einzel-und Multi-Site-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="1c14e-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-119">Konfigurieren der Cloud Connector-Integration in Ihre Microsoft 365-oder Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="1c14e-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="1c14e-120">Fügen Sie DNS-Einträge hinzu, konfigurieren Sie Hybrid, richten Sie PSTN-Gateways ein, und aktivieren Sie Benutzer für Voicemail für Telefonsysteme.</span><span class="sxs-lookup"><span data-stu-id="1c14e-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-121">Überprüfen Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1c14e-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1c14e-122">Stellen Sie sicher, dass Ihre Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="1c14e-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-123">Upgrade auf eine neue Version von Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1c14e-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="1c14e-124">Aktualisieren Sie die vorhandene Cloud Connector-Bereitstellung auf Version 2,1.</span><span class="sxs-lookup"><span data-stu-id="1c14e-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-125">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1c14e-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1c14e-126">Ändern Sie die Einstellungen in Cloud Connector, nachdem Sie bereits bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1c14e-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-127">Bereitstellen der medienumgehung in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1c14e-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="1c14e-128">Hier erfahren Sie, wie Sie die medienumgehung in Cloud Connector bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c14e-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-129">Cmdlet-Referenz für Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1c14e-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="1c14e-130">Erfahren Sie mehr über die PowerShell-Cmdlets, die in Cloud Connector verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c14e-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1c14e-131">Problembehandlung bei Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1c14e-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1c14e-132">Lösungen für häufige Probleme, die bei einer Cloud Connector-Bereitstellung auftreten.</span><span class="sxs-lookup"><span data-stu-id="1c14e-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

