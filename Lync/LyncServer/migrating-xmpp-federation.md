---
title: Migrieren eines XMPP-Partnerverbunds
TOCTitle: Migrieren eines XMPP-Partnerverbunds
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49890909
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren eines XMPP-Partnerverbunds

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

In früheren Versionen von Lync Server und Office Communications Server stand ein XMPP-Gateway (Extensible Messaging and Presence Protocol) zur Verfügung, das als separate Serverrolle bereitgestellt werden konnte, um den Verbund mit XMPP-Bereitstellungen zuzulassen. In Lync Server 2013 kann die XMPP-Funktionalität als Funktion bereitgestellt werden. Die XMPP-Funktionalität wird in zwei Teilen installiert: als ein XMPP-Proxy, der auf dem Lync Server 2013-Edgeserver ausgeführt wird, und das XMPP-Gateway, das auf dem Lync Server 2013-Front-End-Server ausgeführt wird.

Auf Migrationsebene kann ein Lync Server-Benutzerkonto in einen Lync Server 2013-Pool verschoben werden und weiterhin den bestehenden XMPP-Gateway verwenden. Dies ist nur möglich, wenn der XMPP-Verbundpartner nicht in Lync Server 2013 konfiguriert ist.

Zusammengefasst lässt sich sagen, dass bei Bereitstellung von Lync Server 2010 mit dem Office Communications Server 2007 R2-XMPP-Gateway und Aktivierung von XMPP-Verbund für bestehende Lync Server 2010-Benutzer wie folgt vorgegangen werden muss, um den XMPP-Verbund nach Lync Server 2013 zu migrieren:

1.  Stellen Sie einen Lync Server 2013-Pool bereit.

2.  Stellen Sie einen Lync Server 2013-Edgeserver bereit.

3.  Verschieben Sie alle Benutzer in den Lync Server 2013-Pool

4.  Erstellen Sie XMPP-Zugriffsrichtlinien und -Zertifikate für den Edgeserver.

5.  Aktivieren Sie den XMPP-Verbund in Lync Server 2013. 

6.  Aktualisieren Sie die DNS-Einträge so, dass diese auf den Lync Server 2013-XMPP-Gateway verweisen.

