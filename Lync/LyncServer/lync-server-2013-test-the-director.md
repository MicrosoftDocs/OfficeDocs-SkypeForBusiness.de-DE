---
title: 'Lync Server 2013: Testen des Directors'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8fbb19ac08886c7603d3b1d60ae3946f7bde32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="17c02-102">Testen des Directors in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17c02-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17c02-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="17c02-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="17c02-104">Zu diesem Zeitpunkt haben Sie einen Director oder einen Directorpool konfiguriert, Ihre DNS-SRV-Einträge (Domain Name System) verweisen Clients jedoch noch immer an die Anmeldung über einen Pool- oder einen Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="17c02-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="17c02-105">Bevor Sie den DNS-Eintrag so ändern, dass lync 2013 Clients sich automatisch mit dem Director anmelden, testen Sie einen Client, indem Sie ihn manuell an den Director richten.</span><span class="sxs-lookup"><span data-stu-id="17c02-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="17c02-106">So testen Sie die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="17c02-106">To test the deployment</span></span>

1.  <span data-ttu-id="17c02-107">Melden Sie sich an dem Computer an, auf dem Sie die lync Server-Systemsteuerung mit einem Domänenkonto installiert haben, das Teil der **CSAdministrator** -Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="17c02-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="17c02-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="17c02-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17c02-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="17c02-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17c02-110">Klicken Sie im Navigationsbereich auf **Topologie**, und vergewissern Sie sich in der Spalte **Status** , dass ein grüner Server mit einem Pfeil ( ![Serversymbol mit grünem Pfeil](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server Symbol mit grünem Pfeil")) für Ihren Director oder Directorpool vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="17c02-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="17c02-111">Verbinden Sie zwei Clientcomputer, auf denen der lync Server 2013-Client installiert ist, und melden Sie sich mit einem anderen Benutzerkonto an, das für lync Server 2013 für jeden Computer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17c02-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="17c02-112">Klicken Sie auf einem der Clientcomputer auf das Menü **Optionen**, wählen Sie die Einstellungsgruppe **Persönlich** aus, klicken Sie auf **Erweitert**, dann auf **Manuelle Konfiguration**, und legen Sie dann die Option **Interner Servername oder IP-Adresse** auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Directors oder Directorpools ein.</span><span class="sxs-lookup"><span data-stu-id="17c02-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="17c02-113">Melden Sie sich bei beiden Clients an, und stellen Sie sicher, dass die Anmeldung auf dem Client, der sich über den Director anmeldet, erfolgreich verläuft. Beachten Sie den Anwesenheitsstatus des anderen Benutzers, und prüfen Sie, ob beide Sofortnachrichten austauschen können.</span><span class="sxs-lookup"><span data-stu-id="17c02-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

