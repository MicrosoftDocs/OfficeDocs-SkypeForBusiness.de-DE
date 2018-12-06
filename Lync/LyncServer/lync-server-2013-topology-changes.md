---
title: 'Lync Server 2013: Topologieänderungen'
TOCTitle: Topologieänderungen
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49890860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologieänderungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Die Topologieanforderungen und Überlegungen für Lync Server 2013 unterscheiden sich von denen vorheriger Versionen. Die Unterschiede werden im folgenden Abschnitt erläutert.

## Neue Architektur der Front-End-Pools.

In Lync Server 2013 wurde die Architektur der Enterprise EditionFront-End-Pools in eine Architektur verteilter Systeme geändert.

Mit dieser neuen Architektur bildet die Back-End-Datenbank nicht mehr den Echtzeit-Datenspeicher in einem Pool. Die Informationen zu einem bestimmten Benutzer befinden sich auf drei Front-End-Servern im Pool. Für jeden Benutzer agiert ein Front-End-Server als Master für die Informationen des jeweiligen Benutzers und zwei weitere Front-End-Server dienen als Replikate. Wenn ein Front-End-Server ausfällt, wird ein anderer Front-End-Server, der als Replikat gedient hat, automatisch zum Master hochgestuft.

Dies passiert im Hintergrund und es ist nicht erforderlich, dass Administratoren wissen, welche Front-End-Server als Master für welche Benutzer agieren. Diese Verteilung des Datenspeichers verbessert die Leistung und Skalierbarkeit des Pools und beseitigt die einzelne Fehlerquelle, die ein einziger Back-End-Server bildet.

Der Back-End-Server dient als Sicherungsspeicher für Benutzer- und Konferenzdaten und stellt außerdem den primären Speicher für andere Datenbanken, wie die Reaktionsgruppendatenbank.

Diese Verbesserungen ziehen auch Änderungen bei der Planung und Wartung der Pools nach sich. Wir empfehlen die Aufnahme von mindestens drei Front-End-Servern in all Ihre Enterprise Edition- Front-End-Pools, um die vollständige Anzahl Replikate bereitzustellen, für die die Front-End-Pool-Architektur entwickelt wurde. Darüber hinaus müssen Sie beim Hinzufügen von Servern zum Front-End-Pool, beim Entfernen von Servern aus dem Pool und beim Aktualisieren von Servern im Pool bestimmte Verfahren einhalten. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

## Änderungen der Topologie der Serverrolle

Einige Serverrollen, die zuvor auf separaten Servern ausgeführt wurden, sind jetzt in der Front-End-Serverrolle zusammengefasst, was die Hardwarekosten senkt

  - In Lync Server 2013 ist der A/V-Konferenzserver immer mit dem Front-End-Server verbunden.

  - Die Front-Ends für die Überwachung und für die Archivierung sind jetzt mit dem Front-End-Server verbunden. Für die Überwachung und die Archivierung ist weiterhin eine separate Back-End-Datenbank erforderlich, die auf demselben Server wie die Back-End-Datenbank des Front-End-Pools verbunden oder auf separaten Back-End-Servern gehostet werden kann.

  - Server für beständigen Chat ist jetzt eine Serverrolle. In Microsoft Lync Server 2010 war Gruppenchatserver für Microsoft Lync Server 2010 eine vertrauenswürdige Anwendung eines Drittanbieters. In Lync Server 2013 ist die Server für beständigen Chat-Funktion mithilfe von drei neue Serverrollen implementiert:
    
      - **PersistentChatService :** Hauptdienst des Server für beständigen Chats, der als Front-End-Rolle implementiert ist
    
      - **PersistentChatStore :** Back-End-Serverrolle
    
      - **PersistentChatComplianceStore :** Back-End-Serverrolle Beständiger Chat-Konformität

