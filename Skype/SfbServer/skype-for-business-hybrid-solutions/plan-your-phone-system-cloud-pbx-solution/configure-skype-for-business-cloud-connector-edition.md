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
ms.openlocfilehash: e30fcb4cad44bffed495f1191e5e5cae73bb18cc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358791"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="b1828-103">Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b1828-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="b1828-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="b1828-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="b1828-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="b1828-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="b1828-106">Hier erfahren Sie, wie Sie Skype for Business Cloud Connector Edition, eine minimale lokale Topologie, konfigurieren, um die Integration Ihrer lokalen VoIP-Infrastruktur mit Telefon System-VoIP-Diensten (Cloud PBX) in Skype for Business Online zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b1828-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="b1828-107">Bevor Sie beginnen, sollten Sie die Voraussetzungen in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b1828-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1828-108">Die Schritte in diesem Thema gelten nur für Cloud Connector Edition 1.4.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="b1828-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="b1828-109">Wenn Sie noch nicht auf Cloud Connector Edition 2,1 aktualisiert haben, finden Sie weitere Informationen unter [Upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b1828-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="b1828-110">Sie können die Installationsdatei von herunterladen [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="b1828-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="b1828-111">Schritte zum Konfigurieren von Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b1828-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="b1828-112">In der folgenden Tabelle sind die Schritte aufgeführt, die Sie zum Installieren und Konfigurieren von Cloud Connector Edition benötigen:</span><span class="sxs-lookup"><span data-stu-id="b1828-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="b1828-113">**Schritt**</span><span class="sxs-lookup"><span data-stu-id="b1828-113">**Step**</span></span>|<span data-ttu-id="b1828-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b1828-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b1828-115">Vorbereiten der Cloud Connector-Appliance</span><span class="sxs-lookup"><span data-stu-id="b1828-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="b1828-116">Laden Sie die Installationsdatei herunter, bereiten Sie Zertifikate vor, konfigurieren Sie Hyper-V, und nutzen Sie Ihre Umgebung für Ihre Cloud Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="b1828-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="b1828-117">Bereitstellen eines einzelnen Standorts in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b1828-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="b1828-118">Erstellen Sie eine Website in ihrer Cloud Connector-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="b1828-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="b1828-119">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b1828-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="b1828-120">Fügen Sie Ihrer Bereitstellung Websites hinzu, und erfahren Sie mehr über die Unterschiede zwischen Einzel-und Multi-Site-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="b1828-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="b1828-121">Konfigurieren der Cloud Connector-Integration in Ihre Microsoft 365-oder Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="b1828-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="b1828-122">Fügen Sie DNS-Einträge hinzu, konfigurieren Sie Hybrid, richten Sie PSTN-Gateways ein, und aktivieren Sie Benutzer für Voicemail für Telefonsysteme.</span><span class="sxs-lookup"><span data-stu-id="b1828-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="b1828-123">Überprüfen Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b1828-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b1828-124">Stellen Sie sicher, dass Ihre Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b1828-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="b1828-125">Upgrade auf eine neue Version von Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b1828-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="b1828-126">Aktualisieren Sie die vorhandene Cloud Connector-Bereitstellung auf Version 2,1.</span><span class="sxs-lookup"><span data-stu-id="b1828-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="b1828-127">Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b1828-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b1828-128">Ändern Sie die Einstellungen in Cloud Connector, nachdem Sie bereits bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b1828-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="b1828-129">Bereitstellen der medienumgehung in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b1828-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="b1828-130">Hier erfahren Sie, wie Sie die medienumgehung in Cloud Connector bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b1828-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="b1828-131">Cmdlet-Referenz für Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b1828-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="b1828-132">Erfahren Sie mehr über die PowerShell-Cmdlets, die in Cloud Connector verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1828-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="b1828-133">Problembehandlung bei Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b1828-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b1828-134">Lösungen für häufige Probleme, die bei einer Cloud Connector-Bereitstellung auftreten.</span><span class="sxs-lookup"><span data-stu-id="b1828-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

