---
title: 'Lync Server 2013: Überwachen der Netzwerkleistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Überwachen der Netzwerkleistung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-04-27_

Lync Server 2013 ist eine echt Zeit Kommunikationstechnologie, die stark vom Netzwerk abhängig ist, um die Kommunikation zwischen Benutzern zu ermöglichen – entweder durch Instant Messaging (im), Sprachanrufe oder Videokommunikation. Daher ist es wichtig, die Netzwerkleistung kontinuierlich zu überwachen, um sicherzustellen, dass die von einem Benutzer gewählte Kommunikations Modalität die bestmögliche Nutzung bietet.

Die Netzwerkleistung kann auf zwei Ebenen gemessen werden:

  - **Gesamtnetzwerkleistung**   diese Stufe der Leistungsmessung ermöglicht es einer Organisation, eine "Big-Picture"-Ansicht Ihres Netzwerks zu erstellen und wird in der Regel über Netzwerk Überwachungssysteme von Drittanbietern implementiert. Diese Systeme empfangen Leistungs-und Kapazitätsdaten von Remotenetzwerk Geräten wie Routern und werden im gesamten Netzwerk gewechselt, damit Administratoren die Integrität einer bestimmten Netzwerkkomponente zu jeder Tageszeit ermitteln können.

  - **Individuelle Serverleistung**   diese Ebene der Leistungsmessung ist auf einen bestimmten Server limitiert und unterstützt Administratoren bei der Messung der Netzwerkleistung eines bestimmten Servers, um entweder bei der Problembehandlung einer bestimmten Leistung zu helfen. Sie können die Leistung des jeweiligen Servers während eines bestimmten Zeitraums im Rahmen eines Kapazitäts Planungsprozesses abwägen oder bewerten.

Sie können das Netzwerk überwachen, indem Sie die in den folgenden Abschnitten beschriebenen Tools verwenden.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Tools zur allgemeinen Netzwerk Leistungsüberwachung

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager bietet eine End-to-End-Dienstverwaltung, die einfach angepasst und für verbesserte Dienstebenen in einer IT-Umgebung erweitert werden kann. Auf diese Weise können Operations-und IT-Verwaltungsteams Probleme erkennen und beheben, die sich auf die Integrität verteilter IT-Dienste auswirken. Die End-to-End-Dienstverwaltung ist nicht auf Microsoft-basierte Umgebungen beschränkt. Unterstützung für Webdienste für die Verwaltung (WS-Management), SNMP (Simple Network Management Protocol) und Partnerlösungen ermöglichen Systeme, die keine Microsoft-Betriebssysteme und-Hardware ausführen, um in System Center in die Dienstüberwachung einbezogen zu werden. Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 und Netzwerkverwaltungslösungen von Drittanbietern

**EMC Smarts**   EMC-Lösungen für Operations Manager unterstützen Sie bei der schnellen Behebung von Problemen, die sich auf die gesamten Serviceebenen auswirken. Durch die Verwendung von EMC-Lösungen für Operations Manager können Sie Ihre gesamte IT-Service-Kette mit einer integrierten, automatisierten Lösung managen und überwachen. Sie können die Ursachen von Problemen bei der Leistung und Verfügbarkeit einfach erkennen und schneller beheben, wodurch sich die Auswirkungen und Kosten verringern. Zu den wichtigsten Vorteilen gehören die folgenden:

  - Ein fortschrittliches, nutzerfreundliches Management konzentriert sich auf die Bereitstellung von strategischem geschäftlichen Nutzen, anstatt die verwirrenden Warnungen manuell zu sortieren und zu filtern.

  - **Schnellere Lösungen**   lösen IT-Probleme und reagieren auf geschäftliche Anforderungen schneller, wodurch sich die Wirkung und die Kosten verringern.

  - **Optimierte Vorgänge**   vermeiden IT-Komplexität durch Kombinieren mehrerer Verwaltungstools, Anwendungen und Terminals.

Weitere Informationen finden Sie hier:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Lösungen für Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Lösungen von Drittanbietern

**HP Network Management Center (vormals als HP OpenView bezeichnet)** Das    [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) bietet integriertes Fehler-und Leistungs Management, um die Netzwerkverfügbarkeit und-Leistung zu verbessern. Network Management Center ist Teil der automatischen HP-Netzwerkverwaltungslösung, die Fehler-, Leistungs-, Konfigurations-und Änderungsverwaltung vereint.

**Cisco-Netzwerkmanagement-und-Automatisierungsprodukte**   für das Unternehmen bietet Cisco verschiedene Verwaltungsprodukte, einschließlich der CiscoWorks-LAN-Verwaltungslösung und des Cisco-Netzwerkanalyse Moduls, um die operative Effizienz zu verbessern und reduzieren Sie die Netzwerkausfälle. Weitere Informationen zu diesen Produkten finden Sie auf der Cisco-Website unter [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).

SNMP (Simple Network Management Protocol, SNMP) ist ein Netzwerkverwaltungsstandard, der eine Strategie für die Verwaltung von TCP/IP-Netzwerken definiert. SNMP ermöglicht Ihnen, Konfigurations-und Statusinformationen über das Netzwerk zu erfassen und die Informationen an einen festgelegten Computer zur Ereignisüberwachung zu senden. Dieses standardbasierte Netzwerkverwaltungsprotokoll verwendet eine verteilte Architektur, die Folgendes umfasst:

  - Mehrere verwaltete Knoten mit einer SNMP-Entität, die als Agent bezeichnet wird und Remotezugriff auf die Verwaltungsinstrumentation bietet.

  - Mindestens eine SNMP-Entität, die als Manager bezeichnet wird und Verwaltungsanwendungen ausführt, um verwaltete Elemente zu überwachen und zu steuern. Verwaltete Elemente sind Geräte wie Hosts, Router usw. Sie werden überwacht und kontrolliert, indem Sie auf Ihre Verwaltungsinformationen zugreifen.

  - Ein Verwaltungsprotokoll, SNMP, wird verwendet, um Verwaltungsinformationen zwischen den Verwaltungsstationen und Agents zu kommunizieren. Verwaltungsinformationen bezieht sich auf eine Sammlung verwalteter Objekte, die in einem virtuellen Informationsspeicher (Management Information Base, MIB) enthalten sind.

<div>


> [!NOTE]  
> Oben finden Sie Beispiele für Netzwerk Überwachungslösungen von Drittanbietern. Diese Liste ist nicht endgültig, und Microsoft bevorzugt keine spezifische Anbieter Lösung. Erkundigen Sie sich bei einem Netzwerkdienstanbieter und ihrem jeweiligen Technologieanbieter, wie Sie die beste Netzwerküberwachungslösung für Ihre Organisation ermitteln können.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Tools zum Überwachen der einzelnen Server Netzwerkleistung

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

Mit System Center Operations Manager 2012 können Administratoren die Netzwerkleistung einzelner Server über das Windows Server 2012-Management Pack anzeigen: das Windows Server-Betriebssystem-Management Pack enthält ein Management Pack für die Leistung Damit können Administratoren die Leistung des Netzwerkadapters und den Adapterstatus überwachen.

</div>

<div>

## <a name="windows-network-monitor"></a>Windows-Netzwerk Monitor

Sammelt, zeigt, analysiert die Ressourcennutzung auf einem Server und misst den Netzwerkdatenverkehr. Netzwerkmonitor überwacht ausschließlich die Netzwerkaktivität. Durch die Erfassung und Analyse von Netzwerkdaten und die Verwendung dieser Daten mit Leistungsprotokollen können Sie die Netzwerkauslastung ermitteln, Netzwerkprobleme identifizieren und zukünftige Netzwerkanforderungen Vorhersagen.

Weitere Informationen zu Netzwerkmonitor 3,4 und Informationen zum Installieren und Konfigurieren des Netzwerkmonitors sowie zum Aufzeichnen und Analysieren von Daten finden Sie in dieser Sitzung: Übersicht über den Netzwerkmonitor 3,3. Überprüfen Sie außerdem den [Blog des Netzwerkmonitors](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

