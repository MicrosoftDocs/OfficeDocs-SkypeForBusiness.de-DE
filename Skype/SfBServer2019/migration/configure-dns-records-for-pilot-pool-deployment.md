---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vor der Bereitstellung des pilotpools, müssen Sie die DNS-Host-A-Einträge für den pilotpool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens sollten Sie auf dem Server oder Domäne als Mitglied der Gruppe Domänen-Admins oder ein Mitglied der Gruppe "DnsAdmins" angemeldet sein.
ms.openlocfilehash: 23ac5e4f85dc0da560b4d288bbfad426298bf82e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238730"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="d3e99-104">Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung</span><span class="sxs-lookup"><span data-stu-id="d3e99-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="d3e99-105">Vor dem Bereitstellen des pilotpools, müssen Sie die DNS-Host-A-Einträge für den pilotpool aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d3e99-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="d3e99-106">Zum erfolgreichen Durchführen dieses Verfahrens sollten Sie auf dem Server oder Domäne als Mitglied der Gruppe Domänen-Admins oder ein Mitglied der Gruppe "DnsAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="d3e99-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="d3e99-107">So konfigurieren Sie DNS-Host-A-Einträge</span><span class="sxs-lookup"><span data-stu-id="d3e99-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="d3e99-108">Klicken Sie auf dem Server Domain Name System (DNS) klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d3e99-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="d3e99-109">Klicken Sie in der Konsolenstruktur für Ihre Domäne erweitern Sie **Forward-Lookupzonen**, und anschließend mit der Maustaste der Domäne, in der Skype für Business Server 2019 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3e99-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="d3e99-110">Klicken Sie auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="d3e99-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="d3e99-111">Klicken Sie auf **Name**, geben Sie den Hostnamen für die Skype für Business Server 2019 Pool (der Domänenname wird von der Zone, die der Datensatz ist in definiert und muss nicht als Teil des A-Eintrags eingegeben werden verwendet).</span><span class="sxs-lookup"><span data-stu-id="d3e99-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="d3e99-112">Klicken Sie auf **IP-Adresse**, und geben Sie die IP-Adresse für den Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="d3e99-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="d3e99-113">Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3e99-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="d3e99-114">Wenn Sie fertig sind, klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d3e99-114">When you are finished, click **Done**.</span></span>
    

