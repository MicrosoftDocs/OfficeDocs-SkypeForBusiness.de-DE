---
title: 'Lync Server 2013: Überprüfen der System Einstellungen für Domänennamen für den Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Überprüfen von System Einstellungen für den Domänennamen für den Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-02_

Zur Unterstützung des vom DNS-Lastenausgleich verwendeten FQDN müssen Sie DNS bereitstellen, um den Pool-FQDN (wie pool01.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.). Sie sollten nur die IP-Adressen der Server einbeziehen, die derzeit bereitgestellt werden.

Wenn Sie den DNS-Lastenausgleich für die Edge-Pools verwenden, sind zusätzlich die folgenden DNS-Einträge erforderlich:

  - Für den lync Server Access Edge-Dienst müssen Sie einen Eintrag für jeden Server im Pool besitzen. Jeder Eintrag muss den FQDN des lync Server Access-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse des lync Server Access Edge-Diensts auf einem der Edgeserver im Pool auflösen.

  - Für den lync Server Web Conferencing Edge-Dienst müssen Sie einen Eintrag für jeden Server im Pool besitzen. Jeder Eintrag muss den FQDN des lync Server Web Conferencing Edge-Diensts (beispielsweise webconf.contoso.com) in die IP-Adresse des lync Server Web Conferencing Edge-Diensts auf einem der Edgeserver im Pool auflösen.

  - Für den lync Server-Audio/Video-Edgedienst muss für jeden Server im Pool ein Eintrag vorhanden sein. Jeder Eintrag muss den FQDN des lync Server-Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des lync Server-Audio/Video-Edgedienst auf einem der Edgeserver im Pool auflösen.

  - Wenn Sie den DNS-Lastenausgleich auf der internen Schnittstelle des Edge-Pools verwenden möchten, müssen Sie einen DNS-Eintrag hinzufügen, der den internen FQDN des Edge-Pools in die IP-Adresse jedes Servers im Pool auflöst.

Verwenden Sie das Nslookup-Tool, um zu überprüfen, ob DNS die richtigen Werte für den DNS-Lastenausgleich zurückgibt. Wenn Sie alle Werte für einen DNS-Eintrag mit nslookup zurückgeben möchten, sollten Sie den folgenden Befehl ausführen:

`nslookup <FQDN >`

Sie führen diesen Befehl für jeden FQDN aus, der in der Konfiguration des DNS-Lastenausgleichs verwendet wird, um zu überprüfen, ob alle Daten Satz Sätze für den DNS-Lastenausgleich alle korrekten Einträge zurückgegeben haben.

</div>

<span> </span>

</div>

</div>

</div>

