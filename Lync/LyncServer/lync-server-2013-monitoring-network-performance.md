---
title: 'Lync Server 2013: Überwachen der Netzwerkleistung'
TOCTitle: Überwachen der Netzwerkleistung
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn720923(v=OCS.15)
ms:contentKeyID: 62240045
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überwachen der Netzwerkleistung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 ist eine Echzeitkommunikationstechnologie, die stark vom Netzwerk abhängig ist, um die Kommunikation zwischen Benutzern zu ermöglichen – über Chat, Sprachanrufe oder Videokommunikation. Daher ist es wichtig, die Netzwerkleistung kontinuierlich zu überwachen und sicherzustellen, dass die von einem Benutzer ausgewählte Kommunikationsmodalität die bestmögliche Erfahrung bereitstellt.

Die Netzwerkleistung kann auf zwei Ebenen gemessen werden:

  - **Allgemeine Netzwerkleistung**   Die Leistungsmessung auf dieser Ebene ermöglicht einer Organisation, eine allgemeine Übersicht über das Netzwerk zu erstellen, und wird in der Regel über Netzwerküberwachungssysteme von Drittanbietern bereitgestellt. Diese Systeme erhalten Leistungs- und Kapazitätsdaten von Remotenetzwerkgeräten wie Routern und Switches im gesamten Netzwerk, damit Administratoren jederzeit die Integrität einer beliebigen Netzwerkkomponente ermitteln können.

  - **Individuelle Serverleistung**   Die Leistungsmessung auf dieser Ebene ist auf einen bestimmten Server begrenzt und unterstützt Administratoren dabei, die Netzwerkleistung eines bestimmten Servers zu beurteilen, um entweder ein bestimmtes Leistungsproblem zu beheben oder die Leistung des entsprechenden Servers über einen gewissen Zeitraum im Rahmen eines Kapazitätsplanungsprozesses abzuschätzen.

Sie können das Netzwerk mit den in den folgenden Abschnitten beschriebenen Tools überwachen.

## Tools für die allgemeine Netzwerkleistungsüberwachung

## System Center Operations Manager 2012

System Center Operations Manager bietet eine End-to-End-Dienstverwaltung, die einfach angepasst und verwaltet werden kann, um verbesserte Servicelevel in einer IT-Umgebung bereitzustellen. Damit können Betriebs- und IT-Verwaltungsteams Probleme ermitteln und lösen, die sich auf die Integrität verteilter IT-Dienste auswirken. Die End-to-End-Dienstverwaltung ist nicht auf Microsoft-basierte Umgebungen beschränkt. Durch die Unterstützung für Webdienste für die Verwaltung (WS-Management), SNMP (Simple Network Management Protocol) und Partnerlösungen können Systeme, auf denen keine Betriebssysteme von Microsoft ausgeführt werden, und Hardware in die Dienstüberwachung in System Center Operations Manager 2012 eingeschlossen werden.

## System Center Operations Manager 2012 und Netzwerkverwaltungslösungen von Drittanbietern

**EMC Smarts**   Mithilfe von Lösungen von EMC für Operations Manager können Sie schnell Probleme beheben, die sich auf Servicelevel auswirken. Mit den Lösungen von EMC für Operations Manager können Sie Ihre gesamte IT-Dienstkette mit einer integrierten und automatisierten Lösung verwalten und überwachen. Sie können auf einfache Weise die Ursachen von Leistungs- und Verfügbarkeitsproblemen ermitteln und sie schneller beheben, sodass Auswirkungen und Kosten reduziert werden. Sie profitieren von den folgenden Hauptvorteilen:

  - Erweiterte, benutzerfreundliche Verwaltung   Konzentrieren Sie sich auf die Bereitstellung eines strategischen geschäftlichen Nutzens statt auf die manuelle Sortierung und Filterung von verwirrenden Warnungen.

  - **Schnellere Problembehebung**   Lösen Sie IT-Probleme und reagieren Sie schneller auf geschäftliche Anforderungen, um Aufwand und Kosten zu reduzieren.

  - **Rationalisierter Betrieb**   Vermeiden Sie IT-Komplexität, indem Sie mehrere Verwaltungstools, Anwendungen und Terminals kombinieren.

Weitere Informationen finden Sie unter:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Lösungen für Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

## Lösungen von Drittanbietern

**HP Network Management Center (zuvor bekannt als HP OpenView)**   [HP Network Management Center](https://h10078.www1.hp.com/cda/hpms/display/main/hpms_content.jsp?zn=bto%26cp=1-11-15-119_4000_100__) bietet eine integrierte Fehler- und Leistungsverwaltung, um die Netzwerkverfügbarkeit und -leistung zu verbessern. Network Management Center ist Teil der automatisierten Netzwerkverwaltungslösung von HP, die Fehler-, Leistungs-, Konfigurations- und Änderungsverwaltung vereint.

**Netzwerkverwaltungs- und -automatisierungsprodukte von Cisco**   Cisco bietet mehrere Verwaltungsprodukte für Unternehmen, darunter CiscoWorks LAN Management Solution und Cisco Network Analysis Module, die dazu beitragen, die betriebliche Effizienz zu verbessern und Netzwerkausfallzeiten zu reduzieren. Zusätzliche Daten zu diesen Produkten finden Sie auf der Website von Cisco unter [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).

Simple Network Management Protocol (SNMP)   SNMP ist ein Netzwerkverwaltungsstandard, der eine Strategie für die Verwaltung von TCP/IP-Netzwerken definiert. Mithilfe von SNMP können Sie Konfigurations- und Statusinformationen über das Netzwerk erfassen und die Informationen für die Ereignisüberwachung an einen designierten Computer senden. Dieses standardbasierte Netzwerkverwaltungsprotokoll verwendet eine verteilte Architektur mit den folgenden Komponenten:

  - Mehrere verwaltete Knoten, jeweils mit einer SNMP-Entität, die als Agent bezeichnet wird und Remotezugriff auf die Verwaltungsinstrumentation bereitstellt

  - Mindestens eine SNMP-Entität, die als Manager bezeichnet wird und auf der Verwaltungsanwendungen zum Überwachen und Steuern verwalteter Elemente ausgeführt werden. Verwaltete Elemente sind Geräte wie Hosts, Router und so weiter. Diese werden überwacht und gesteuert, indem auf ihre Verwaltungsinformationen zugegriffen wird.

  - Ein Verwaltungsprotokoll, SNMP, wird verwendet, um Verwaltungsinformationen zwischen den Verwaltungsstationen und -Agents zu kommunizieren. Verwaltungsinformationen beziehen sich auf eine Sammlung verwalteter Objekte, die in einem virtuellen Informationsspeicher namens Management Information Base (MIB) gespeichert sind.


> [!NOTE]
> Beispiele für Netzwerküberwachungslösungen von Drittanbietern sind oben bereitgestellt. Diese Liste ist nicht ausschließlich und Microsoft bevorzugt keine bestimmte Anbieterlösung. Lassen Sie sich von einem Netzwerkdienstanbieter und/oder Ihrem entsprechenden Technologieanbieter beraten, um die beste Netzwerküberwachungslösung für Ihre Organisation zu ermitteln.



## Tools für die Überwachung der Netzwerkleistung einzelner Server

## System Center Operations Manager 2012

System Center Operations Manager 2012 ermöglicht Administratoren das Anzeigen der Netzwerkleistung einzelner Server über das Windows Server 2012 Management Pack: Das Windows Server Management Pack enthält ein „Leistungs“-Management Pack, mit dem Administratoren die Netzwerkadapterleistung und Adapterintegrität überwachen können.

## Windows-Netzwerkmonitor

Ermöglicht das Erfassen, Anzeigen und Analysieren des Ressourceneinsatzes auf einem Server und misst den Netzwerkdatenverkehr. Der Netzwerkmonitor überwacht ausschließlich die Netzwerkaktivität. Durch Erfassen und Analysieren von Netzwerkdaten und Verwenden der Daten mit Leistungsprotokollen können Sie die Netzwerkauslastung bestimmen, Netzwerkprobleme erkennen und zukünftige Netzwerkanforderungen prognostizieren.

Weitere Informationen zum Netzwerkmonitor 3.4, zum Installieren und Konfigurieren des Netzwerkmonitors sowie zum Erfassen und Analysieren von Daten finden Sie in der folgenden Sitzung: Übersicht über Netzwerkmonitor 3.3. Zusätzliche Informationen finden Sie im Blog zum Netzwerkmonitor unter: <http://blogs.technet.com/b/netmon/>.

