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
ms.openlocfilehash: 10cd31639445fab6138ea77cb40a03d727ecce12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks von lync Server 2013 befindet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (wie einem lync Server-Edgeserver) ausgeführt werden, außerhalb des Unternehmens (beispielsweise ein externer synthetischer Transaktions Überwachungsknoten) oder über eine Vertrauensgrenze für Active Directory-Domänendienste verfügen, können erfordert die Konfiguration eines System Center Operations Manager-Gatewayservers. Mit dieser Serverrolle können Agents, die nicht über eine Vertrauensstellung mit dem Stammverwaltungsserver verfügen, Benachrichtigungen auslösen. Ausführliche Informationen finden Sie unter "Verwalten von Gatewayservern in Operations Manager 2007" in der TechNet-Bibliothek für System [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)Center Operations Manager unter.

Wenn Sie einen Agenten an einem dieser Speicherorte bereitstellen, müssen Sie auch ein Zertifikat anfordern und konfigurieren, das dem Watcher-Knoten die Möglichkeit gibt, Benachrichtigungen an System Center Operations Manager zu senden. Zur Vereinfachung dieses Prozesses hat das Operations Manager-Team einen Satz von Dienstprogrammen erstellt, mit denen Sie den richtigen Zertifikattyp auf dem Watcher-Knoten Computer anfordern und installieren können. Informationen zum Herunterladen dieser Dienstprogramme finden Sie im Blog Artikel unter "Abrufen von Zertifikaten für nicht-Domänen verbundene Agents, die mit dem Assistenten für die [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)Zertifikatgenerierung vereinfacht wurden".

</div>

<span> </span>

</div>

</div>

</div>

