---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
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
description: Vor dem Bereitstellen des pilotpools müssen Sie den DNS-Host A-Einträge für den Pilot Pool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754055"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="d5cc8-104">Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung</span><span class="sxs-lookup"><span data-stu-id="d5cc8-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="d5cc8-105">Vor dem Bereitstellen des pilotpools müssen Sie den DNS-Host A-Einträge für den Pilot Pool aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="d5cc8-106">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="d5cc8-107">So konfigurieren Sie DNS-Hosteinträge (A)</span><span class="sxs-lookup"><span data-stu-id="d5cc8-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="d5cc8-108">Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="d5cc8-109">Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Skype for Business Server 2019 installiert wird.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="d5cc8-110">Klicken Sie auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="d5cc8-111">Klicken Sie auf **Name**, geben Sie den Hostnamen für den Skype for Business Server Pool 2019 (der Domänen Name wird von der Zone angenommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).</span><span class="sxs-lookup"><span data-stu-id="d5cc8-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="d5cc8-112">Klicken Sie auf **IP-Adresse**, und geben Sie dann die IP-Adresse für die Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="d5cc8-113">Klicken Sie auf **Host hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="d5cc8-114">Klicken Sie abschließend auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d5cc8-114">When you are finished, click **Done**.</span></span>
    

