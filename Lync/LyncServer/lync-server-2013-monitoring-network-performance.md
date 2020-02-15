---
title: 'Lync Server 2013: Überwachen der Netzwerkleistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524499737ae1e52a36a80fbc636f005b687a6a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Überwachen der Netzwerkleistung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-04-27_

Lync Server 2013 ist eine echt Zeit Kommunikationstechnologie, die in hohem Maße auf das Netzwerk angewiesen ist, um die Kommunikation zwischen Benutzern zu ermöglichen – entweder über Sofortnachrichten (Chat), Sprachanrufe oder Videokommunikation. Es ist daher wichtig, die Netzwerkleistung kontinuierlich zu überwachen, um sicherzustellen, dass die gewählte Kommunikations Modalität eines Benutzers die bestmögliche Erfahrung bietet.

Die Netzwerkleistung kann auf zwei Ebenen gemessen werden:

  - **Gesamtnetzwerkleistung**   diese Leistungsmessung ermöglicht es einer Organisation, eine "Big-Picture"-Ansicht Ihres Netzwerks zu erstellen, die in der Regel über Netzwerk Überwachungssysteme von Drittanbietern implementiert wird. Auf diesen Systemen werden Leistungs-und Kapazitätsdaten von Remotenetzwerk Geräten wie Router empfangen und im Netzwerk umgeschaltet, sodass Administratoren zu jeder Tageszeit die Integrität einer bestimmten Netzwerkkomponente bestimmen können.

  - **Einzelne Serverleistung**   diese Leistungsmessung ist auf einen bestimmten Server limitiert und unterstützt Administratoren bei der Bewertung der Netzwerkleistung eines bestimmten Servers, um entweder bei der Behandlung eines bestimmten Leistungsproblems behilflich zu sein oder um die Leistung des jeweiligen Servers über einen bestimmten Zeitraum im Rahmen eines Kapazitäts Planungsprozesses zu messen.

Sie können das Netzwerk überwachen, indem Sie die in den folgenden Abschnitten beschriebenen Tools verwenden.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Tools für die allgemeine Überwachung der Netzwerkleistung

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager bietet eine End-to-End-Dienstverwaltung, die einfach angepasst und für verbesserte Dienstebenen in einer IT-Umgebung erweitert werden kann. Auf diese Weise können Betriebs-und IT-Verwaltungsteams Probleme identifizieren und beheben, die sich auf die Integrität verteilter IT-Dienste auswirken. Die End-to-End-Dienstverwaltung ist nicht auf Microsoft-basierte Umgebungen beschränkt. Unterstützung für Webdienste für Verwaltung (WS-Management), SNMP (Simple Network Management Protocol) und Partnerlösungen ermöglichen Systemen, die Microsoft-Betriebssysteme und-Hardware nicht ausführen, die in der Dienstüberwachung in System Center enthalten sein sollen. Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 und Netzwerkverwaltungslösungen von Drittanbietern

**EMC Smarts**   EMC-Lösungen für Operations Manager unterstützen Sie bei der schnellen Lösung von Problemen, die sich auf die gesamte Serviceebene auswirken. Durch die Verwendung von EMC Lösungen für Operations Manager können Sie Ihre gesamte IT-Servicekette mit einer integrierten, automatisierten Lösung verwalten und überwachen. Sie können die Ursachen von Problemen mit der Leistung und der Verfügbarkeit leicht erkennen und schneller beheben, wodurch Effekte und Kosten reduziert werden. Zu den wichtigsten Vorteilen zählen folgende:

  - Fortschrittliches, einfach zu bedienendes Management konzentrieren Sie sich auf die Bereitstellungeines strategischen Geschäftswerts anstelle von manueller Sortierung und Filterung verwirrender Warnungen.

  - **Schnellere Lösungen**   lösen IT-Probleme und reagieren schneller auf geschäftliche Anforderungen und reduzieren Wirkung und Kosten.

  - **Optimierte Vorgänge**   vermeiden IT-Komplexität durch die Kombination mehrerer Verwaltungstools, Anwendungen und Terminals.

Weitere Informationen finden Sie hier:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Lösungen für Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Lösungen von Drittanbietern

HP **Network Management Center (bisher als HP OpenView bezeichnet)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) bietet integriertes Fehler-und Leistungs Management zur Verbesserung der Netzwerkverfügbarkeit und-Leistung. Network Management Center ist Teil der HP Automated Network Management-Lösung, die Fehler-, Leistungs-, Konfigurations-und Änderungsverwaltung vereint.

**Cisco-Netzwerkmanagement-und Automatisierungsprodukte**   für das Unternehmen bietet Cisco mehrere Verwaltungsprodukte, einschließlich CiscoWorks LAN-Verwaltungslösung und Cisco-Netzwerkanalyse Modul, um die betriebliche Effizienz zu verbessern und die Ausfallzeit des Netzwerks zu verringern. Weitere Informationen zu diesen Produkten finden Sie auf der Cisco-Website unter [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).

SNMP (Simple Network Management Protocol) Simple Network Management Protocol (SNMP) ist ein Netzwerkverwaltungsstandard, der eine Strategie für die Verwaltung von TCP/IP-Netzwerken definiert. SNMP ermöglicht es Ihnen, Konfigurations-und Statusinformationen zum Netzwerk zu erfassen und die Informationen an einen bestimmten Computer für die Ereignisüberwachung zu senden. Dieses standardbasierte Netzwerkverwaltungsprotokoll verwendet eine verteilte Architektur, die Folgendes umfasst:

  - Mehrere verwaltete Knoten mit jeweils einer SNMP-Entität, die als Agent bezeichnet wird und den Remotezugriff auf Verwaltungsinstrumentation ermöglicht.

  - Mindestens eine SNMP-Entität, die als Manager bezeichnet wird und Verwaltungsanwendungen zum Überwachen und Steuern verwalteter Elemente ausführt. Verwaltete Elemente sind Geräte wie Hosts, Router usw. Sie werden durch Zugriff auf Ihre Verwaltungsinformationen überwacht und gesteuert.

  - Ein Verwaltungsprotokoll, SNMP, wird verwendet, um Verwaltungsinformationen zwischen den Verwaltungsstationen und Agents zu kommunizieren. Verwaltungsinformationen bezieht sich auf eine Sammlung von verwalteten Objekten, die in einem virtuellen Informationsspeicher mit dem Namen "Management Information Base (MIB)" Leben.

<div>


> [!NOTE]  
> Beispiele für Netzwerk Überwachungslösungen von Drittanbietern werden oben bereitgestellt. Diese Liste ist nicht endgültig, und Microsoft favorisiert keine bestimmte Anbieter Lösung. Wenden Sie sich an einen Netzwerkdienstanbieter und ihren jeweiligen Technologieanbieter, um die beste Netzwerküberwachungslösung für Ihre Organisation zu ermitteln.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Tools zum Überwachen der einzelnen Server Netzwerkleistung

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

Mit System Center Operations Manager 2012 können Administratoren die Netzwerkleistung einzelner Server über das Windows Server 2012 Management Pack anzeigen: das Windows Server-Betriebssystem-Management Pack enthält ein Management Pack für die Leistung Dadurch können Administratoren die Leistung von Netzwerkadaptern und die Adapter Integrität überwachen.

</div>

<div>

## <a name="windows-network-monitor"></a>Windows-Netzwerk Monitor

Sammelt, zeigt, analysiert die Ressourcennutzung auf einem Server und misst den Netzwerkdatenverkehr. Netzwerkmonitor überwacht ausschließlich die Netzwerkaktivität. Durch das erfassen und Analysieren von Netzwerkdaten und die Verwendung dieser Daten mit Leistungsprotokollen können Sie die Netzwerkauslastung ermitteln, Netzwerkprobleme identifizieren und zukünftige Netzwerkanforderungen prognostizieren.

Weitere Informationen zu Netzwerkmonitor 3,4 und Informationen zum Installieren und Konfigurieren des Netzwerkmonitors sowie zum Erfassen und Analysieren von Daten finden Sie in dieser Sitzung: Network Monitor 3,3 Overview. Überprüfen Sie außerdem den [Blog Netzwerk Monitor](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

