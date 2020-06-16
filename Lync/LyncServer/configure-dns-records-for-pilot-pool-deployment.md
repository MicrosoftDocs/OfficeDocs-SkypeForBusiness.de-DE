---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f8c04773c31e60e5faa8fd9df2b1e08331f5c7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="590e1-102">Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung</span><span class="sxs-lookup"><span data-stu-id="590e1-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="590e1-103">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="590e1-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="590e1-104">Vor dem Bereitstellen des lync Server 2013-pilotpools müssen Sie den DNS-Host A-Einträge für den Pilot Pool aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="590e1-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="590e1-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="590e1-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="590e1-106">**So konfigurieren Sie DNS-Hosteinträge (A)**</span><span class="sxs-lookup"><span data-stu-id="590e1-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="590e1-107">Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="590e1-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="590e1-108">Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="590e1-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="590e1-109">Klicken Sie auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="590e1-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="590e1-110">Klicken Sie auf **Name**, geben Sie den Hostnamen für den lync Server 2013 Pool ein (der Domänen Name wird von der Zone angenommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).</span><span class="sxs-lookup"><span data-stu-id="590e1-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="590e1-111">Klicken Sie auf **IP-Adresse**, geben Sie die IP-Adresse für die Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="590e1-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="590e1-112">Klicken Sie auf **Host hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="590e1-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="590e1-113">Klicken Sie abschließend auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="590e1-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

