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
description: In diesem Artikel erfahren Sie, wie Sie Skype for Business Cloud Connector Edition, eine minimale lokale Topologie zur Integration Ihrer lokalen VoIP-Infrastruktur mit Telefon System in Office 365 (Cloud PBX)-VoIP-Dienste in Skype for Business Online, konfigurieren können.
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779161"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="dd175-103">Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="dd175-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="dd175-104">In diesem Artikel erfahren Sie, wie Sie Skype for Business Cloud Connector Edition, eine minimale lokale Topologie zur Integration Ihrer lokalen VoIP-Infrastruktur mit Telefon System in Office 365 (Cloud PBX)-VoIP-Dienste in Skype for Business Online, konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="dd175-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="dd175-105">Bevor Sie beginnen, sollten Sie die Voraussetzungen in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dd175-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dd175-106">Die Schritte in diesem Thema gelten nur für Cloud Connector Edition 1.4.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="dd175-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="dd175-107">Wenn Sie noch nicht auf Cloud Connector Edition 2,1 aktualisiert haben, finden Sie weitere Informationen unter [Upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="dd175-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="dd175-108">Sie können die Installationsdatei von [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="dd175-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="dd175-109">Schritte zum Konfigurieren von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="dd175-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="dd175-110">In der folgenden Tabelle sind die Schritte aufgeführt, die Sie zum Installieren und Konfigurieren von Cloud Connector Edition benötigen:</span><span class="sxs-lookup"><span data-stu-id="dd175-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="dd175-111">**Schritt**</span><span class="sxs-lookup"><span data-stu-id="dd175-111">**Step**</span></span>|<span data-ttu-id="dd175-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dd175-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dd175-113">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="dd175-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="dd175-114">Laden Sie die Installationsdatei herunter, bereiten Sie Zertifikate vor, konfigurieren Sie Hyper-V, und nutzen Sie Ihre Umgebung für Ihre Cloud Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="dd175-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="dd175-115">Bereitstellen eines einzelnen Standorts in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="dd175-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="dd175-116">Erstellen Sie eine Website in ihrer Cloud Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="dd175-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="dd175-117">Bereitstellen mehrerer Websites in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="dd175-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="dd175-118">Fügen Sie Ihrer Bereitstellung Websites hinzu, und erfahren Sie mehr über die Unterschiede zwischen Einzel-und Multi-Site-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="dd175-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="dd175-119">Konfigurieren der Cloud Connector-Integration in Ihre Office 365 Organisation</span><span class="sxs-lookup"><span data-stu-id="dd175-119">Configure Cloud Connector integration with your Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="dd175-120">Fügen Sie DNS-Einträge hinzu, konfigurieren Sie Hybrid, richten Sie PSTN-Gateways ein, und aktivieren Sie Benutzer für das Telefon System in Office 365-Voicemail.</span><span class="sxs-lookup"><span data-stu-id="dd175-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="dd175-121">Überprüfen der Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="dd175-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="dd175-122">Stellen Sie sicher, dass Ihre Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="dd175-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="dd175-123">Upgrade auf eine neue Version von Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="dd175-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="dd175-124">Aktualisieren Sie die vorhandene Cloud Connector-Bereitstellung auf Version 2,1.</span><span class="sxs-lookup"><span data-stu-id="dd175-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="dd175-125">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="dd175-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="dd175-126">Ändern Sie die Einstellungen in Cloud Connector, nachdem Sie bereits bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="dd175-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="dd175-127">Bereitstellen der medienumgehung in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="dd175-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="dd175-128">Hier erfahren Sie, wie Sie die medienumgehung in Cloud Connector bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dd175-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="dd175-129">Referenz zu Cloud Connector-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="dd175-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="dd175-130">Erfahren Sie mehr über die PowerShell-Cmdlets, die in Cloud Connector verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd175-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="dd175-131">Problembehandlung bei der Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="dd175-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="dd175-132">Lösungen für häufige Probleme, die bei einer Cloud Connector-Bereitstellung auftreten.</span><span class="sxs-lookup"><span data-stu-id="dd175-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

