---
title: Überprüfen der Legacyumgebung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Bevor Sie Skype for Business Server 2019 in einem koexistenzstatus bereitstellen, müssen Sie sicherstellen, dass ältere Dienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features, die in ihrer Vorgänger Umgebung vorhanden sind, vor der Bereitstellungeines Skype for Business Server 2019-pilotpools zu identifizieren. Bevor Sie Microsoft Skype for Business Server 2019 XMPP im koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die vorhandenen XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751677"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="04b7e-105">Überprüfen der Vorgänger Umgebung</span><span class="sxs-lookup"><span data-stu-id="04b7e-105">Verify the legacy environment</span></span>

<span data-ttu-id="04b7e-106">Bevor Sie Skype for Business Server 2019 in einem koexistenzstatus bereitstellen, müssen Sie sicherstellen, dass ältere Dienste konfiguriert und gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="04b7e-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="04b7e-107">Es ist wichtig, wichtige Dienste und Features in ihrer Legacyumgebung vor der Bereitstellungeines Skype for Business Server 2019-pilotpools zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="04b7e-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="04b7e-108">Bevor Sie Microsoft Skype for Business Server 2019 XMPP im koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie sicherstellen, dass die vorhandenen XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="04b7e-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="04b7e-109">Die Überprüfung Ihrer Legacy-Bereitstellung umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="04b7e-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="04b7e-110">Überprüfen, ob die Legacy Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="04b7e-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="04b7e-111">Überprüfen der Topologie und der Benutzer</span><span class="sxs-lookup"><span data-stu-id="04b7e-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="04b7e-112">Überprüfen der Einstellungen für den Verbund und den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="04b7e-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="04b7e-113">Überprüfen der XMPP-Dienste und Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="04b7e-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="04b7e-114">Überprüfen, ob ältere Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="04b7e-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="04b7e-115">Navigieren Sie in der Legacy Front-End-Server zum Applet für administrative verwaltungstools\dienste..</span><span class="sxs-lookup"><span data-stu-id="04b7e-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="04b7e-116">Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="04b7e-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Liste der auf Front-End-Server ausgeführten Dienste](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="04b7e-118">Überprüfen der Legacy Topologie in Skype for Business Server Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="04b7e-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="04b7e-119">Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="04b7e-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="04b7e-120">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="04b7e-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04b7e-121">Wählen Sie **Topologie** aus.</span><span class="sxs-lookup"><span data-stu-id="04b7e-121">Select **Topology**.</span></span> <span data-ttu-id="04b7e-122">Stellen Sie sicher, dass die verschiedenen Server in Ihrer Legacy Bereitstellung aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="04b7e-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![System Steuerungs Topologie (Seite)](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="04b7e-124">Überprüfen von älteren Benutzern in Skype for Business Server Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="04b7e-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="04b7e-125">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="04b7e-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="04b7e-126">Wählen Sie **Benutzer**aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04b7e-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="04b7e-127">Stellen Sie sicher, dass die Spalte **Registrierungspool** für jeden aufgelisteten Benutzer auf den Legacy Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="04b7e-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Systemsteuerung, die Benutzer auflistet](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="04b7e-129">Überprüfen der Legacy-Edge-und Verbund Einstellungen</span><span class="sxs-lookup"><span data-stu-id="04b7e-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="04b7e-130">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="04b7e-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="04b7e-131">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="04b7e-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="04b7e-132">Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem Dateityp default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="04b7e-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="04b7e-133">Erweitern Sie den Knoten Legacy installs, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04b7e-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="04b7e-134">Wählen Sie den Knoten Website aus, und stellen Sie sicher, dass ein **Standort Verbund-Routen Zuordnungs** Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="04b7e-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Topologie-Generator, Standort Verbund Route](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="04b7e-136">Wählen Sie den Front-End-Pool Standard Edition-Server oder Enterprise Edition aus.</span><span class="sxs-lookup"><span data-stu-id="04b7e-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="04b7e-137">Bestimmen Sie, ob ein Edgepool für Medien unterhalb von **Zuordnungen**konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="04b7e-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Topologie-Generator mit Servern und Pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="04b7e-139">Wählen Sie die Edgepool aus, und bestimmen Sie, ob ein nächster Hop-Pool unterhalb der **nächsten Hop-Auswahl**konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="04b7e-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Topologie-Generator, Auswahl des nächsten Hops](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="04b7e-141">Überprüfen der Vorgänger Konfiguration für XMPP-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="04b7e-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="04b7e-142">Navigieren Sie auf dem XMPP-Vorversionsserver zum Applet Verwaltungstools\Dienste.</span><span class="sxs-lookup"><span data-stu-id="04b7e-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="04b7e-143">Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist.</span><span class="sxs-lookup"><span data-stu-id="04b7e-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP-Gatewaydienst](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

