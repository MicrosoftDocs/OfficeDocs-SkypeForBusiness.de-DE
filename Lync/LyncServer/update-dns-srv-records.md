---
title: Aktualisieren von DNS SRV-Einträgen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e171e821d2fcf5c773321ada3a5b107b28314699
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="6f238-102">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="6f238-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f238-103">_**Letztes Änderungsdatum des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="6f238-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="6f238-104">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="6f238-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="6f238-105">In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) nach der Migration zu lync Server 2013 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6f238-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="6f238-106">Nachdem alle Benutzer nach lync Server 2013 verschoben wurden, aber bevor der Legacy lync Server 2010-Pool oder-Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6f238-106">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="6f238-107">Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="6f238-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="6f238-108">**So konfigurieren Sie einen DNS-SRV-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="6f238-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="6f238-109">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6f238-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="6f238-110">Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der lync Server 2013 installiert ist, und navigieren Sie zur \*\* \_TCP\*\* -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="6f238-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="6f238-111">Klicken Sie im rechten Bereich mit der rechten Maustaste auf \*\* \_sipinternaltls\*\* , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="6f238-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="6f238-112">Aktualisieren Sie im Host, der **diesen Dienst anbietet**, den FQDN des Hosts so, dass er auf den lync Server 2013-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="6f238-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="6f238-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f238-113">Click **OK**.</span></span>

<span data-ttu-id="6f238-114">**So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann**</span><span class="sxs-lookup"><span data-stu-id="6f238-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="6f238-115">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="6f238-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="6f238-116">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6f238-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="6f238-117">Geben Sie im Feld **Öffnen** den **Befehl cmd**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f238-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="6f238-118">Geben Sie an der Eingabeaufforderung **nslookup** \<-FQDN des Front-End\> - \<Pools oder den FQDN des Standard\>Edition-Servers ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6f238-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="6f238-119">Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6f238-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

