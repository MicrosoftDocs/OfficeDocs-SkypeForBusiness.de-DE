---
title: Überprüfen der Legacyumgebung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vor der Bereitstellung von Skype for Business Server 2019 in einem Koexistenzmodus müssen Sie überprüfen, ob Legacy Dienste konfiguriert und gestartet wurden. Vor der Bereitstellungeines Skype for Business Server 2019-pilotpools ist es wichtig, die wichtigsten Dienste und Features zu identifizieren, die in ihrer Legacyumgebung vorhanden sind. Bevor Sie Microsoft Skype for Business Server 2019 xmpp in einem koexistenzstatus mit einer Legacy-XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die Legacy-XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welchen Verbundpartner die Legacy-XMPP-Konfiguration ist stützen.
ms.openlocfilehash: 34c9ecbc4fe9863c09b2648145ff46c1628ef655
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812693"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="e68ca-105">Überprüfen der Legacyumgebung</span><span class="sxs-lookup"><span data-stu-id="e68ca-105">Verify the legacy environment</span></span>

<span data-ttu-id="e68ca-106">Vor der Bereitstellung von Skype for Business Server 2019 in einem Koexistenzmodus müssen Sie überprüfen, ob Legacy Dienste konfiguriert und gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="e68ca-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="e68ca-107">Es ist wichtig, wichtige Dienste und Features zu identifizieren, die in ihrer Legacyumgebung vorhanden sind, bevor Sie einen Skype for Business Server 2019-Pilot Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e68ca-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="e68ca-108">Bevor Sie Microsoft Skype for Business Server 2019 xmpp in einem koexistenzstatus mit einer Legacy-XMPP-Bereitstellung bereitstellen, müssen Sie sicherstellen, dass die Legacy-XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welchen Partner das Legacy-XMPP die Konfiguration unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e68ca-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="e68ca-109">Die Überprüfung Ihrer Legacy Bereitstellung umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e68ca-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="e68ca-110">Überprüfen, ob die Legacy Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="e68ca-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="e68ca-111">Überprüfen der Topologie und der Benutzer</span><span class="sxs-lookup"><span data-stu-id="e68ca-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="e68ca-112">Überprüfen der Einstellungen für den Verbund und den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e68ca-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="e68ca-113">Überprüfen von XMPP-Diensten und Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="e68ca-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="e68ca-114">Überprüfen, ob Legacy Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="e68ca-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="e68ca-115">Navigieren Sie vom Legacy-Front-End-Server zum Applet administrative Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="e68ca-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e68ca-116">Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e68ca-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Liste der Dienste, die auf dem Front-End-Server ausgeführt werden](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e68ca-118">Überprüfen der Legacy Topologie in der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e68ca-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e68ca-119">Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="e68ca-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="e68ca-120">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="e68ca-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e68ca-121">Wählen Sie **Topologie**aus.</span><span class="sxs-lookup"><span data-stu-id="e68ca-121">Select **Topology**.</span></span> <span data-ttu-id="e68ca-122">Überprüfen Sie, ob die verschiedenen Server in Ihrer Legacy Bereitstellung aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="e68ca-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Seite "System Steuerungs Topologie"](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e68ca-124">Überprüfen von Legacy Benutzern in der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e68ca-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e68ca-125">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="e68ca-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e68ca-126">Wählen Sie **Benutzer**aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e68ca-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="e68ca-127">Überprüfen Sie, ob die Spalte des **registrierungspools** auf den Legacy Pool für jeden aufgelisteten Benutzer verweist.</span><span class="sxs-lookup"><span data-stu-id="e68ca-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Control Panel-Auflistung der Benutzer](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="e68ca-129">Überprüfen von Legacy Edge-und Federation-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e68ca-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="e68ca-130">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="e68ca-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="e68ca-131">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**.</span><span class="sxs-lookup"><span data-stu-id="e68ca-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="e68ca-132">Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.</span><span class="sxs-lookup"><span data-stu-id="e68ca-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="e68ca-133">Erweitern Sie den Knoten Legacy Installationen, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e68ca-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="e68ca-134">Wählen Sie den Websiteknoten aus, und überprüfen Sie, ob ein **Standort Verbund-Routen Zuordnungs** Wert festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e68ca-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Topologie-Generator, Website Verbund Route](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="e68ca-136">Wählen Sie den Standard Edition-Server oder Enterprise Edition-Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="e68ca-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="e68ca-137">Ermitteln Sie, ob ein Edge-Pool für Medien unter **Zuordnungen**konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="e68ca-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Topologie-Generator mit Servern und Pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="e68ca-139">Wählen Sie den Edge-Pool aus, und ermitteln Sie, ob unterhalb des nächsten Hop- **Auswahlbereichs**ein nächster Hop-Pool konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e68ca-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Topologie-Generator, Auswahl des nächsten Hops](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="e68ca-141">Überprüfen der Konfiguration von Legacy-XMPP-Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="e68ca-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="e68ca-142">Navigieren Sie vom Legacy-XMPP-Server zum Administrator Tools\Services-Applet.</span><span class="sxs-lookup"><span data-stu-id="e68ca-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e68ca-143">Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewayserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e68ca-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server-XMPP-Gatewaydienst](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

