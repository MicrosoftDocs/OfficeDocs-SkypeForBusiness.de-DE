---
title: Überprüfen der legacy-Umgebung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Müssen Sie vor der Bereitstellung von Skype für Business Server 2019 zusammen, um sicherzustellen, dass legacy-Diensten konfiguriert und gestartet wurden. Es ist wichtig, identifizieren wichtige Dienste und Features, die in der vorgängerumgebung vor der Bereitstellung einer Skype für Business Server 2019 pilotpool vorhanden sind. Vor der Bereitstellung von Microsoft Skype für Business Server 2019 XMPP zusammen mit einer Vorversion XMPP-Bereitstellung, müssen Sie überprüfen, ob der Vorversion XMPP-Dienste gestartet und konfiguriert wurden, und Bestimmen der Verbundpartner die Vorversion XMPP-Konfiguration ist Sie unterstützen.
ms.openlocfilehash: d6e4585e127009117345d1220458196b5b461b6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030427"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="d5778-105">Überprüfen der Vorversionen Umgebung</span><span class="sxs-lookup"><span data-stu-id="d5778-105">Verify the legacy environment</span></span>

<span data-ttu-id="d5778-106">Müssen Sie vor der Bereitstellung von Skype für Business Server 2019 zusammen, um sicherzustellen, dass legacy-Diensten konfiguriert und gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="d5778-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="d5778-107">Es ist wichtig, identifizieren wichtige Dienste und Features, die in der Vorversion Umgebung vor der Bereitstellung einer Skype für Business Server 2019 pilotpool vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d5778-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="d5778-108">Vor der Bereitstellung von Microsoft Skype für Business Server 2019 XMPP zusammen mit einer Vorversion XMPP-Bereitstellung, müssen Sie sicherstellen, dass die Vorversion XMPP-Dienste gestartet und konfiguriert wurden, und Bestimmen der Partner die Vorversion XMPP federated Konfiguration wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d5778-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="d5778-109">Überprüfen der Bereitstellung die Vorgängerversion umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d5778-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="d5778-110">Sicherstellen, dass die legacy-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="d5778-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="d5778-111">Überprüfen der Topologie und Benutzer</span><span class="sxs-lookup"><span data-stu-id="d5778-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="d5778-112">Überprüfen der Partnerverbund- und edgeservereinstellungen</span><span class="sxs-lookup"><span data-stu-id="d5778-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="d5778-113">Überprüfen der XMPP-Dienste und Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="d5778-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="d5778-114">Stellen Sie sicher, dass legacy-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="d5778-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="d5778-115">Navigieren Sie aus der Vorversion Front-End-Server zum Applet verwaltungstools\dienste.</span><span class="sxs-lookup"><span data-stu-id="d5778-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="d5778-116">Stellen Sie sicher, dass die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d5778-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Liste der Dienste, die auf Front-End-Server ausgeführt werden.](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="d5778-118">Überprüfen der vorversionstopologie in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d5778-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d5778-119">Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="d5778-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="d5778-120">Öffnen Sie die Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d5778-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d5778-121">Wählen Sie **Topologie**aus.</span><span class="sxs-lookup"><span data-stu-id="d5778-121">Select **Topology**.</span></span> <span data-ttu-id="d5778-122">Stellen Sie sicher, dass die verschiedenen Server in Ihrer Bereitstellung der Vorversion aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d5778-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Topologieseite in der Systemsteuerung steuern](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="d5778-124">Überprüfen von legacybenutzern in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d5778-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d5778-125">Öffnen Sie die Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d5778-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d5778-126">Wählen Sie **Benutzer**aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d5778-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="d5778-127">Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** auf den Pool der Vorgängerversion für jeden aufgeführten Benutzer zeigt.</span><span class="sxs-lookup"><span data-stu-id="d5778-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Systemsteuerung Auflisten von Benutzern](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="d5778-129">Überprüfen Sie die Einstellungen für legacy Edge und Verbund</span><span class="sxs-lookup"><span data-stu-id="d5778-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="d5778-130">Starten Sie Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="d5778-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="d5778-131">Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus.</span><span class="sxs-lookup"><span data-stu-id="d5778-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="d5778-132">Wählen Sie einen Dateinamen ein, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.</span><span class="sxs-lookup"><span data-stu-id="d5778-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="d5778-133">Erweitern Sie den Knoten Vorversion installiert, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d5778-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="d5778-134">Wählen Sie den Websiteknoten, und stellen Sie sicher, dass ein **Zuweisung der partnerverbundroute Route** Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d5778-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Topologie-Generator Partnerverbundroute des Standorts](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="d5778-136">Wählen Sie den Standard Edition-Server oder Enterprise Edition-Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="d5778-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="d5778-137">Bestimmen Sie, ob für Medien unter **Zuordnungen**ein edgepool konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d5778-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Topologie-Generator mit Servern und pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="d5778-139">Wählen Sie den edgepool aus, und identifizieren Sie, ob unter **Auswahl für nächsten Hop**ein nächster hoppool konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d5778-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Topologie-Generator Auswahl für nächsten hop](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="d5778-141">Legacy XMPP-Verbundpartner Konfiguration überprüfen</span><span class="sxs-lookup"><span data-stu-id="d5778-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="d5778-142">Die XMPP-vorversionsserver zum Applet verwaltungstools\dienste navigieren.</span><span class="sxs-lookup"><span data-stu-id="d5778-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="d5778-143">Stellen Sie sicher, dass der Office Communications Server-XMPP-Gateway-Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d5778-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server-XMPP-Gatewaydienst](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

