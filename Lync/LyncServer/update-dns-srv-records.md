---
title: Aktualisieren von DNS SRV-Einträgen
description: Aktualisieren von DNS-SRV-Einträgen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579591"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="66765-103">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="66765-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66765-104">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="66765-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="66765-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="66765-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="66765-106">In diesem Thema wird beschrieben, wie Sie die Domain Name System (DNS) Datensätze nach der Migration zu lync Server 2013 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="66765-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="66765-107">Nachdem alle Benutzer in lync Server 2013 verschoben wurden, aber bevor der Legacy lync Server 2010-Pool oder-Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="66765-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="66765-108">Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="66765-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="66765-109">**So konfigurieren Sie einen DNS-SRV-Eintrag**</span><span class="sxs-lookup"><span data-stu-id="66765-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="66765-110">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="66765-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="66765-111">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der lync Server 2013 installiert ist, und navigieren Sie zur \*\* \_ TCP\*\* -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="66765-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="66765-112">Klicken Sie im rechten Bereich mit der rechten Maustaste auf \*\* \_ sipinternaltls\*\* , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="66765-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="66765-113">Aktualisieren Sie unter Host, der **diesen Dienst anbietet**den Host-FQDN so, dass er auf den lync Server 2013 Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="66765-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="66765-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="66765-114">Click **OK**.</span></span>

<span data-ttu-id="66765-115">**So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann**</span><span class="sxs-lookup"><span data-stu-id="66765-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="66765-116">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="66765-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="66765-117">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="66765-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="66765-118">Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="66765-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="66765-119">Geben Sie an der Eingabeaufforderung **nslookup** \<FQDN of the Front End pool\> oder \<FQDN of the Standard Edition server\> ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="66765-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="66765-120">Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="66765-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

