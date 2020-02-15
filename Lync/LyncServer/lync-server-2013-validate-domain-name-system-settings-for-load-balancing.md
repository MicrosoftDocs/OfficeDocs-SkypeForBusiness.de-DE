---
title: 'Lync Server 2013: Überprüfen der System Einstellungen des Domänennamens für den Lastenausgleich'
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
ms.openlocfilehash: 3cc1766ad11a5a6b7933d95b2c3e1182ff8ffc6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Validieren von Domänennamen-System Einstellungen für den Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-02_

Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. pool01.contoso.com) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Schließen Sie nur die IP-Adressen von Servern ein, die gegenwärtig bereitgestellt sind.

Außerdem sind die folgenden DNS-Einträge erforderlich, wenn Sie den DNS-Lastenausgleich für die Edge-Pools verwenden:

  - Für die lync Server Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des lync Server Zugriffs-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse der lync Server Zugriffs-Edgedienst auf einem der Edgeserver im Pool auflösen.

  - Für die lync Server Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des lync Server Webkonferenz-Edgedienst (beispielsweise webconf.contoso.com) in die IP-Adresse der lync Server Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.

  - Für den lync Server Audio/Video-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des lync Server Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des lync Server Audio/Video Edge-Diensts auf einem der Edgeserver im Pool auflösen.

  - Wenn Sie den DNS-Lastenausgleich für die interne Schnittstelle des Edgepool verwenden möchten, müssen Sie einen DNS-Eintrag hinzufügen, der den internen FQDN des Edgepool in die IP-Adresse jedes Servers im Pool auflöst.

Um zu überprüfen, ob DNS die korrekten Werte für den DNS-Lastenausgleich zurückgibt, sollten Sie das Nslookup-Tool verwenden. Wenn Sie alle Werte für einen DNS-Eintrag mit nslookup zurückgeben möchten, führen Sie den folgenden Befehl aus:

`nslookup <FQDN >`

Sie führen diesen Befehl für jeden FQDN aus, der in der Konfiguration des DNS-Lastenausgleichs verwendet wurde, um zu überprüfen, ob alle Datensätze für den DNS-Lastenausgleich alle korrekten Einträge zurückgegeben haben.

</div>

<span> </span>

</div>

</div>

</div>

