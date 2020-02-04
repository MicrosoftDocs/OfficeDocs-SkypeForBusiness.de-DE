---
title: Aktualisieren von DNS SRV-Einträgen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 927bdab6721583fd744f68969a852f29ba478027
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="fca6b-102">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="fca6b-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fca6b-103">_**Letztes Änderungsdatum des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="fca6b-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="fca6b-104">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="fca6b-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="fca6b-105">In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) nach der Migration zu lync Server 2013 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fca6b-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="fca6b-106">Nachdem alle Benutzer nach lync Server 2013 verschoben wurden, aber bevor der Legacy Office Communications Server 2007 R2-Pool oder-Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fca6b-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="fca6b-107">Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="fca6b-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="fca6b-108">**So konfigurieren Sie einen DNS-SRV-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="fca6b-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="fca6b-109">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fca6b-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="fca6b-110">Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der lync Server 2013 installiert ist, und navigieren Sie zur \*\* \_TCP\*\* -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="fca6b-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="fca6b-111">Klicken Sie im rechten Bereich mit der rechten Maustaste auf \*\* \_sipinternaltls\*\* , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="fca6b-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="fca6b-112">Aktualisieren Sie im Host, der **diesen Dienst anbietet**, den FQDN des Hosts so, dass er auf den lync Server 2013-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="fca6b-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="fca6b-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fca6b-113">Click **OK**.</span></span>

<span data-ttu-id="fca6b-114">**So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann**</span><span class="sxs-lookup"><span data-stu-id="fca6b-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="fca6b-115">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="fca6b-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="fca6b-116">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fca6b-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="fca6b-117">Geben Sie im Feld **Öffnen** den **Befehl cmd**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fca6b-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="fca6b-118">Geben Sie an der Eingabeaufforderung **nslookup** \<-FQDN des Front-End\> - \<Pools oder den FQDN des Standard\>Edition-Servers ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fca6b-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="fca6b-119">Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="fca6b-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

