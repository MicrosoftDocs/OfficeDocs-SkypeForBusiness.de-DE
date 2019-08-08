---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c9bc007eda604ce4894497db4a6ef334315d28
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="df91c-102">Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung</span><span class="sxs-lookup"><span data-stu-id="df91c-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df91c-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="df91c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="df91c-104">Vor der Bereitstellung des lync Server 2013-pilotpools müssen Sie den DNS-Host einen Eintrag für den Pilot Pool aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="df91c-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="df91c-105">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie mindestens als Mitglied der Gruppe Domänen-Admins oder als Mitglied der DnsAdmins-Gruppe bei dem Server oder der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="df91c-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="df91c-106">**So konfigurieren Sie DNS-Host A-Einträge**</span><span class="sxs-lookup"><span data-stu-id="df91c-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="df91c-107">Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="df91c-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="df91c-108">Erweitern Sie in der Konsolenstruktur für Ihre Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert wird.</span><span class="sxs-lookup"><span data-stu-id="df91c-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="df91c-109">Klicken Sie auf **neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="df91c-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="df91c-110">Klicken Sie auf **Name**, geben Sie den Hostnamen für den Pool ein (der Domänen Name wird aus der Zone übernommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).</span><span class="sxs-lookup"><span data-stu-id="df91c-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="df91c-111">Klicken Sie auf **IP-Adresse**, und geben Sie die IP-Adresse für den Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="df91c-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="df91c-112">Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="df91c-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="df91c-113">Wenn Sie fertig sind, klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="df91c-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

