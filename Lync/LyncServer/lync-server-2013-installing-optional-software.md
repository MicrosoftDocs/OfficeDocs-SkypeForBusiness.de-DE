---
title: 'Lync Server 2013: Installieren von optionaler Software'
TOCTitle: Installieren von optionaler Software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615032(v=OCS.15)
ms:contentKeyID: 52056421
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von optionaler Software in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Das Microsoft Lync Server 2013, Planungstool dient zum Exportieren von Daten nach Microsoft Excel und Microsoft Visio. Wenngleich diese Anwendungen nicht für die Ausführung des Planungstools erforderlich sind, bieten sie einen erheblichen Nutzen für die Bereitstellung und Dokumentation Ihres Entwurfs.

## Optionale Software

## Microsoft Excel

Beim Exportieren Ihres Entwurfs nach Microsoft Excel wird ein Bericht in Form einer Tabelle mit sieben Registerkarten erstellt:

  - Zusammenfassung - Zeigt Informationen zur Standortkonfiguration an, u. a. Benutzeranzahl, Kapazitätseinstellungen und Serverprofilinformationen.

  - Hardwareprofil - Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind (einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle). Die Anzahl und die empfohlenen Spezifikationen für die Serverkomponenten sind auch enthalten. Darüber hinaus ist jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.

  - Portanforderungen - Zeigt einen Bericht zu allen aktivierten Ports sowie die Zuordnung zum Domain Name System-Lastenausgleich (DNS-LB) und zu Hardwaregeräten zum Lastenausgleich (HLB) an. Sie sollten diesen Bericht zum Planen der Konfiguration von Firewall sowie DNS-Lastenausgleich und Hardwaregeräten zum Lastenausgleich verwenden.

  - Zusammenfassungsbericht - Zeigt die allgemeine Zusammenfassung der Einstellungen an, die erforderlich sind, um das Edgeserver-Netzwerk einzurichten.

  - Zertifikatbericht - Zeigt den Antragstellernamen und die alternativen Antragstellernamen für die Zertifikate an, die zum Ausführen der Edgeserver erforderlich sind.

  - Firewallbericht - Zeigt die Quell- und Zielports und die IP-Adressen für sowohl externe als auch interne Schnittstellten an.

  - DNS-Bericht - Zeigt den vollqualifizierten Domänennamen (FQDN) und die IP/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.

## Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:


> [!NOTE]
> Wenn Ihr Entwurf so groß ist, dass mehr als drei Front-End-Server erforderlich sind, wird für Front-End-Pool, Front-End-Server, für den Computer mit SQL Server, IP-Adressen und FQDNs eine zusätzliche Seite erstellt.



  - Globale Topologie - Diagramm der konfigurierten Lync Server 2013-Standorte.

  - Registerkarte "Standortname" - Zeigt die Topologie der Standortkonfiguration mit Edgeserver, Firewall, Telefonfestnetz (PSTN) mit Gateways und die interne Serverbereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, darunter Front-End-Pools, SQL Server-basierten Server, Active Directory-Domänendienste, Directors, Exchange Unified Messaging-Server, Exchange-Postfachserver, Office Web Apps-Server, Vermittlungsserver und Server für beständigen Chat.

  - Edge-Netzwerkdiagramm - Diagramm zur Darstellung der Edgeserverkonfiguration mit den zugeordneten IP-Adressen und vollqualifizierten Domänennamen (FQDNs). DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Zusätzlich werden Directors und Front-End-Server oder Front-End-Pools mit zugeordnetem DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich sowie die zugewiesenen IP-Adressen (das Planungstool unterstützt sowohl IPv4- als auch IPv6-Adressen) und FQDNs dargestellt.

## Siehe auch

#### Aufgaben

[Installieren des Planungstools in Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)

