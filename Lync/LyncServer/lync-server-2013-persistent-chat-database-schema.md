---
title: 'Lync Server 2013: Datenbankschema für beständigen Chat'
TOCTitle: Datenbankschema für beständigen Chat
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558653(v=OCS.15)
ms:contentKeyID: 49294081
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Datenbankschema für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-18_

In diesem Artikel wird das Schema der Datenbank für Beständiger Chat in der Lync Server 2013- Kommunikationssoftware dokumentiert.

Die Beständiger Chat-Datenbank bezieht sich auf die Datenbank, die den Lync Server 2013-Back-End-Serverrollen **PersistentChatStore** (entsprechend der mgc-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp-Datenbank) entspricht. Durch die Veröffentlichung dieses Schemas können Sie Abfragen erstellen und erhalten Einblick in das Erstellen hilfreicher Berichte zur Verwendung der Chatfunktion, zu aktiven Räumen, Benutzern mit den meisten Beiträgen usw.


> [!IMPORTANT]
> Wir behalten uns das Recht zur Weiterentwicklung dieses Schemas vor. Microsoft übernimmt keinerlei Garantie für eine dauerhafte vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema.



Halten Sie sich an folgende bewährte Methoden:

  - Anweisungen vom Typ "SELECT\* //" werden nicht unterstützt, da die Größe der Spaltenliste zunehmen kann.

  - Es werden keine benutzergenerierten Schemaänderungen unterstützt.

  - Auch Schreibvorgänge werden nicht unterstützt.

  - Testen Sie alle Abfragen, die Sie erstellen, mit Datenbanken ähnlicher Größe, um sicherzustellen, dass die Leistung der Abfragen Ihren Anforderungen entspricht.

## In diesem Abschnitt

  - [Liste der Tabellen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Ausführliche Informationen zur Tabelle für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Beispieldatenbankabfragen für beständigen Chat für Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

