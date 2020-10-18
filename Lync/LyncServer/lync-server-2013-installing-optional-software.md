---
title: 'Lync Server 2013: Installieren von optionaler Software'
description: 'Lync Server 2013: Installieren von optionaler Software.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7423c0d54b762fb4af7cedc8d7ba8745fd94bdf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573911"
---
# <a name="installing-optional-software-in-lync-server-2013"></a>Installieren von optionaler Software in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Das Planungs Tool für Microsoft lync Server 2013 wurde für den Export in Microsoft Excel und Microsoft Visio entwickelt. Diese Anwendungen sind zwar für den Betrieb des Planungstools nicht erforderlich, fügen jedoch für die Bereitstellung und Dokumentation Ihres Entwurfs einen erheblichen Mehrwert hinzu.

<div>

## <a name="optional-software"></a>Optionale Software

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

Wenn Sie Ihren Entwurf in Microsoft Excel exportieren, wird ein Bericht erstellt, in dem sieben Registerkarten im Arbeitsblatt angezeigt werden:

  - Zusammenfassung – zeigt Informationen zur Websitekonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Server Profilinformationen.

  - Hardwareprofil – Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind (einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle). Die Menge und die empfohlenen Spezifikationen für die Server Komponenten sind ebenfalls enthalten. Darüber hinaus wird jeder Server durch die Website definiert, um eine vollständige Darstellung der Server Anforderungen nach Standort bereitzustellen.

  - Ports Requirements – zeigt einen Bericht über alle aktivierten Ports sowie die Zuordnung zu Domänennamen System-Lastenausgleich (DNS lb) und Hardwarelastenausgleichs (HLB) an. Verwenden Sie diesen Bericht, um Ihre Firewall-und DNS-lb-und HLB-Konfigurationen zu planen.

  - Zusammenfassender Bericht – zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten Ihres Edgeserver Netzwerks erforderlich sind.

  - Certificates Report – zeigt den Antragstellernamen und die alternativen Antragstellernamen an, die für die für die Ausführung der Edgeserver erforderlichen Zertifikate erforderlich sind.

  - Firewallbericht – zeigt die Quell-und Zielports sowie IP-Adressen sowohl für externe als auch für interne Schnittstellen an.

  - DNS-Bericht – zeigt den vollqualifizierten Domänennamen (FQDN) und die IP/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

<div>


> [!NOTE]  
> Wenn Ihr Entwurf groß genug ist, um mehr als drei Front-End-Server zu erfordern, wird eine zusätzliche Seite für die Front-End-Pool, die Front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.



</div>

  - Globale Topologie – Diagramm der konfigurierten lync Server 2013 Websites.

  - Registerkarte "Website Name" – zeigt die Standort Konfigurationstopologie mit Edgeserver, einer Firewall, einem PSTN (Public Switched Telephone Network) und Gateways sowie der internen Server Bereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich der Front-End-Pools, SQL Server basierten Servern, Active Directory-Domänendienste, Directors, Exchange Unified Messaging (um) Servern, Exchange-Postfachservern, Office-webapps-Servern, Vermittlungsservern und Servern für beständigen Chat.

  - Edge-Netzwerkdiagramm – Diagramm, in dem die Edgeserver Konfiguration mit zugeordneten IP-Adressen und FQDNs erläutert wird. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden Directors und die Front-End-Server oder Front-End-Pool mit zugeordneten DNS lb oder HLB und der zugewiesenen IP-Adresse (das Planungs Tool unterstützt sowohl IPv4-als auch IPv6-Adressen) und FQDN angezeigt.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Installieren des Planungstools in lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

