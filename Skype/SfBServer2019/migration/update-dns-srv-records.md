---
title: Aktualisieren von DNS SRV-Einträgen
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
description: Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753267"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="58c9c-103">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="58c9c-103">Update DNS SRV records</span></span>

<span data-ttu-id="58c9c-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="58c9c-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="58c9c-105">In diesem Thema wird beschrieben, wie Sie die Domain Name System (DNS) Datensätze nach der Migration zu Skype for Business Server 2019 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="58c9c-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="58c9c-106">Nachdem alle Benutzer auf Skype for Business Server 2019 verschoben wurden, aber bevor der ältere Pool oder Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="58c9c-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="58c9c-107">Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="58c9c-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="58c9c-108">So konfigurieren Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="58c9c-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="58c9c-109">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="58c9c-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="58c9c-110">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der Skype for Business Server 2019 installiert ist, und navigieren Sie zur Einstellung **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="58c9c-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="58c9c-111">Klicken Sie im rechten Bereich mit der rechten Maustaste auf **_sipinternaltls** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="58c9c-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="58c9c-112">Aktualisieren Sie unter Host, der **diesen Dienst anbietet**den Host-FQDN so, dass er auf den Skype for Business Server 2019-Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="58c9c-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="58c9c-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c9c-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="58c9c-114">So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="58c9c-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="58c9c-115">Melden Sie sich an einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="58c9c-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="58c9c-116">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="58c9c-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="58c9c-117">Geben Sie im Feld **Öffnen** den Befehl cmd ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c9c-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="58c9c-118">Geben Sie an der Eingabeaufforderung nslookup _\<FQDN of the Front End pool\>_ oder _\<FQDN of the Standard Edition server\>_ ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="58c9c-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="58c9c-119">Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="58c9c-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

