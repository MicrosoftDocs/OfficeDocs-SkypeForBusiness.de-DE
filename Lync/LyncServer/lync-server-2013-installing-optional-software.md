---
title: 'Lync Server 2013: Installieren einer optionalen Software'
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
ms.openlocfilehash: a493fed33fff897ea2cccc2a89c0d55c5b8a8097
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Installieren von optionaler Software in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Das Planungs Tool für Microsoft lync Server 2013 ist für den Export nach Microsoft Excel und Microsoft Visio vorgesehen. Obwohl diese Anwendungen nicht für den Betrieb des Planungstools erforderlich sind, fügen Sie der Bereitstellung und Dokumentation Ihres Entwurfs einen erheblichen Mehrwert hinzu.

<div>

## <a name="optional-software"></a>Optionale Software

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

Beim Exportieren Ihres Entwurfs nach Microsoft Excel wird ein Bericht in Form einer Tabelle mit sieben Registerkarten erstellt:

  - Zusammenfassung - Zeigt Informationen zur Standortkonfiguration an, u. a. Benutzeranzahl, Kapazitätseinstellungen und Serverprofilinformationen.

  - Hardwareprofil - Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind (einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle). Die Anzahl und die empfohlenen Spezifikationen für die Serverkomponenten sind auch enthalten. Darüber hinaus ist jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.

  - Portanforderungen - Zeigt einen Bericht zu allen aktivierten Ports sowie die Zuordnung zum Domain Name System-Lastenausgleich (DNS-LB) und zu Hardwaregeräten zum Lastenausgleich (HLB) an. Sie sollten diesen Bericht zum Planen der Konfiguration von Firewall sowie DNS-Lastenausgleich und Hardwaregeräten zum Lastenausgleich verwenden.

  - Zusammenfassungsbericht – zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten Ihres Edge-Server-Netzwerks erforderlich sind.

  - Zertifikat Bericht – zeigt den Namen des Antragstellers und des Subjekts an, die für die erforderlichen Zertifikate erforderlich sind, damit die Edgeserver ausgeführt werden.

  - Firewallbericht - Zeigt die Quell- und Zielports und die IP-Adressen für sowohl externe als auch interne Schnittstellten an.

  - DNS-Bericht - Zeigt den vollqualifizierten Domänennamen (FQDN) und die IP/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

<div>


> [!NOTE]  
> Wenn Ihr Entwurf groß genug ist, um mehr als drei Front-End-Server zu erfordern, wird eine zusätzliche Seite für den Front-End-Pool, Front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.



</div>

  - Globale Topologie – Diagramm der konfigurierten lync Server 2013-Websites.

  - Registerkarte "Website Name" – zeigt die Topologie der Websitekonfiguration mit Edgeserver, Firewall, PSTN (Public Switched Telephone Network) mit Gateways und der internen Server Bereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich der Front-End-Pools, SQL Server-basierten Servern, Active Directory-Domänendiensten, Directors, Exchange Unified Messaging (um)-Servern, Exchange-Postfachservern, Office Web Apps-Servern, Vermittlungsserver und persistente Chat Server.

  - Edge-Netzwerkdiagramm – Diagramm, in dem die Edgeserver-Konfiguration mit zugehörigen IP-Adressen und FQDNs erläutert wird. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden Directors und der Front-End-Server oder der Front-End-Pool mit zugeordneter DNS lb oder HLB und der zugewiesenen IP-Adresse (das Planungs Tool unterstützt IPv4-und IPv6-Adressen) und dem FQDN angezeigt.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Installieren des Planungstools in Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

