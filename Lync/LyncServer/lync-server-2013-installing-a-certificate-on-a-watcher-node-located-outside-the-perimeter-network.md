---
title: 'Lync Server 2013: Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1479ffdd7f6652b96f3015e047194d76bf1e8978
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="76817-102">Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks von lync Server 2013 befindet</span><span class="sxs-lookup"><span data-stu-id="76817-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76817-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="76817-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="76817-104">System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (wie einem lync Server-Edgeserver) ausgeführt werden, außerhalb des Unternehmens (beispielsweise ein externer synthetischer Transaktions Überwachungsknoten) oder über eine Vertrauensgrenze für Active Directory-Domänendienste verfügen, können erfordert die Konfiguration eines System Center Operations Manager-Gatewayservers.</span><span class="sxs-lookup"><span data-stu-id="76817-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="76817-105">Mit dieser Serverrolle können Agents, die nicht über eine Vertrauensstellung mit dem Stammverwaltungsserver verfügen, Benachrichtigungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="76817-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="76817-106">Ausführliche Informationen finden Sie unter "Verwalten von Gatewayservern in Operations Manager 2007" in der TechNet-Bibliothek für System [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)Center Operations Manager unter.</span><span class="sxs-lookup"><span data-stu-id="76817-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="76817-107">Wenn Sie einen Agenten an einem dieser Speicherorte bereitstellen, müssen Sie auch ein Zertifikat anfordern und konfigurieren, das dem Watcher-Knoten die Möglichkeit gibt, Benachrichtigungen an System Center Operations Manager zu senden.</span><span class="sxs-lookup"><span data-stu-id="76817-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="76817-108">Zur Vereinfachung dieses Prozesses hat das Operations Manager-Team einen Satz von Dienstprogrammen erstellt, mit denen Sie den richtigen Zertifikattyp auf dem Watcher-Knoten Computer anfordern und installieren können.</span><span class="sxs-lookup"><span data-stu-id="76817-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="76817-109">Informationen zum Herunterladen dieser Dienstprogramme finden Sie im Blog Artikel unter "Abrufen von Zertifikaten für nicht-Domänen verbundene Agents, die mit dem Assistenten für die [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)Zertifikatgenerierung vereinfacht wurden".</span><span class="sxs-lookup"><span data-stu-id="76817-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

