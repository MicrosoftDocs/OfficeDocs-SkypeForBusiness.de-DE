---
title: Migrieren eines XMPP-Partnerverbunds
TOCTitle: Migrieren eines XMPP-Partnerverbunds
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49890792
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren eines XMPP-Partnerverbunds

 

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Frühere Versionen von Office Communications Server enthielten ein XMPP-Gateway (Extensible Messaging and Presence Protocol), das als separate Serverrolle bereitgestellt wurde, um einen Verbund mit XMPP-Bereitstellungen zu ermöglichen. In Lync Server 2013 kann die XMPP-Funktionalität als Feature bereitgestellt werden. Die XMPP-Funktionalität wird in zwei Schritten installiert: als XMPP-Proxy, der auf dem Lync Server 2013-Edgeserver ausgeführt wird, und als XMPP-Gateway, das auf dem Lync Server 2013-Front-End-Server ausgeführt wird.

Aus der Migrationsperspektive betrachtet, kann ein Office Communications Server 2007 R2-Benutzerkonto in einem Lync Server 2013-Pool verschoben werden und weiterhin das Office Communications Server 2007 R2-XMPP-Gateway verwenden. Dies ist jedoch nur möglich, wenn der XMPP-Verbundpartner nicht unter Lync Server 2013 konfiguriert ist.

Zusammengefasst lässt sich sagen, dass bei Bereitstellung von Office Communications Server mit dem Office Communications Server 2007 R2-XMPP-Gateway und Aktivierung von XMPP-Verbund für bestehende Office Communications Server 2007 R2-Benutzer wie folgt vorgegangen werden muss, um den XMPP-Verbund nach Lync Server 2013 zu migrieren:

1.  Stellen Sie einen Lync Server 2013-Pool bereit.

2.  Stellen Sie einen Lync Server 2013-Edgeserver bereit.

3.  Übertragen Sie alle Benutzer in den Lync Server 2013-Pool.

4.  Erstellen Sie XMPP-Zugriffsrichtlinien und -Zertifikate für den Edgeserver.

5.  Aktivieren Sie den XMPP-Verbund in Lync Server 2013. 

6.  Aktualisieren Sie die DNS-Einträge so, dass diese auf den Lync Server 2013-XMPP-Gateway verweisen.

