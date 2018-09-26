---
title: Aktualisieren von DNS-SRV-Einträgen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zum erfolgreichen Durchführen dieses Verfahrens sollten Sie auf dem Server oder Domäne als Mitglied der Gruppe Domänen-Admins oder ein Mitglied der Gruppe "DnsAdmins" angemeldet sein.
ms.openlocfilehash: f298db10f7030482b604734a1719756af4071ce2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027228"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="8b3dd-103">Aktualisieren von DNS-SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="8b3dd-103">Update DNS SRV records</span></span>

<span data-ttu-id="8b3dd-104">Zum erfolgreichen Durchführen dieses Verfahrens sollten Sie auf dem Server oder Domäne als Mitglied der Gruppe Domänen-Admins oder ein Mitglied der Gruppe "DnsAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="8b3dd-105">In diesem Thema wird beschrieben, wie die Datensätze Domain Name System (DNS) nach der Migration zu Skype für Business Server 2019 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="8b3dd-106">Nachdem alle Benutzer in Skype für Business Server 2019 verschoben wurden, jedoch vor dem vorversionspool oder dem Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge im internen DNS für jede SIP-Domäne aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="8b3dd-107">In diesem Verfahren wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="8b3dd-108">So konfigurieren Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="8b3dd-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="8b3dd-109">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="8b3dd-110">In der Konsolenstruktur für Ihre SIP-Domäne erweitern Sie **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in welche Skype für Business Server 2019 installiert ist, und navigieren Sie zur **_tcp** -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="8b3dd-111">Klicken Sie im rechten Bereich mit der rechten Maustaste **_sipinternaltls ein** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="8b3dd-112">Aktualisieren Sie unter **Host, der diesen Dienst anbietet**den Host FQDN So zeigen Sie auf die Skype für Business Server 2019 Pool ein.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="8b3dd-113">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="8b3dd-114">Um sicherzustellen, dass der FQDN des Front-End-Pool oder Standard Edition-Servers aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="8b3dd-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="8b3dd-115">Melden Sie sich an einem Clientcomputer in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="8b3dd-116">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="8b3dd-117">Klicken Sie im Feld **Öffnen** Geben Sie cmd ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="8b3dd-118">Geben Sie an der Eingabeaufforderung Nslookup _ \<FQDN des Front-End-Pools\> _ oder _ \<FQDN des Standard Edition-Servers\>_, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="8b3dd-119">Stellen Sie sicher, dass Sie eine Antwort erhalten, die für den FQDN in die entsprechenden IP-Adresse auflöst.</span><span class="sxs-lookup"><span data-stu-id="8b3dd-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

