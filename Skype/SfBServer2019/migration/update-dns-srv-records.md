---
title: Aktualisieren von DNS SRV-Einträgen
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
description: Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812773"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="21578-103">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="21578-103">Update DNS SRV records</span></span>

<span data-ttu-id="21578-104">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="21578-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="21578-105">In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) nach der Migration zu Skype for Business Server 2019 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="21578-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="21578-106">Nachdem alle Benutzer in Skype for Business Server 2019 verschoben wurden, aber bevor der Legacy Pool oder Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="21578-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="21578-107">Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="21578-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="21578-108">So konfigurieren Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="21578-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="21578-109">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="21578-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="21578-110">Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der Skype for Business Server 2019 installiert ist, und navigieren Sie zur **_tcp** -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="21578-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="21578-111">Klicken Sie im rechten Bereich mit der rechten Maustaste auf **_sipinternaltls** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="21578-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="21578-112">Aktualisieren Sie im Host, der **diesen Dienst anbietet**, den FQDN des Hosts so, dass er auf den Skype for Business Server 2019-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="21578-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="21578-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21578-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="21578-114">So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="21578-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="21578-115">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="21578-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="21578-116">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="21578-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="21578-117">Geben Sie im Feld **Öffnen** den Befehl cmd ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21578-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="21578-118">Geben Sie an der Eingabeaufforderung nslookup _ \<-FQDN des Front-End\> -Pools_ oder _ \<den FQDN des Standard\>Edition-Servers_ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="21578-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="21578-119">Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="21578-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

