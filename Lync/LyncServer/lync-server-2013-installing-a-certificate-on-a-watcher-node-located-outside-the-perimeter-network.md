---
title: 'Lync Server 2013: Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b82dcdfd5cc5f7ec00b92c333acbe107a8ec519
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks von lync Server 2013 befindet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

System Center Operations Manager-Agents, die in einem Umkreisnetzwerk ausgeführt werden (beispielsweise eine lync Server Edgeserver) außerhalb des Unternehmens (beispielsweise ein externer synthetischer Transaktionsmonitor Knoten) oder über eine Active Directory-Domänendienstee Vertrauensgrenze hinaus möglicherweise erfordert die Konfiguration eines System Center Operations Manager-Gatewayservers. Diese Serverrolle ermöglicht es Agents, die keine Vertrauensstellung mit dem Root Management Server haben, Warnungen auszulösen. Ausführliche Informationen finden Sie unter "Managing Gateway Servers in Operations Manager 2007" in der TechNet-Bibliothek von System Center [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703)Operations Manager unter.

Wenn Sie einen Agent an einem dieser Speicherorte bereitstellen, müssen Sie außerdem ein Zertifikat anfordern und konfigurieren, mit dem der Watcher-Knoten Warnungen an System Center Operations Manager senden kann. Um dieses Verfahren zu vereinfachen, hat das Operations Manager-Team eine Reihe an Dienstprogrammen erstellt, mit denen Sie den richtigen Typ des Zertifikats anfordern und auf dem Computer mit dem Watcher-Knoten installieren können. Ausführliche Informationen zum Herunterladen dieser Dienstprogramme finden Sie im Blog-Artikel "certificates for Non-Domain Joined Agents Made Easy with Certificate Generation [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421)Wizard" unter.

</div>

<span> </span>

</div>

</div>

</div>

