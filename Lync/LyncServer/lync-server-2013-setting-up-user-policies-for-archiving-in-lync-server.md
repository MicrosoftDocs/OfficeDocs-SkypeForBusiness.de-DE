---
title: Einrichten von Benutzerrichtlinien für die Archivierung in Lync Server
TOCTitle: Einrichten von Benutzerrichtlinien für die Archivierung in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204742(v=OCS.15)
ms:contentKeyID: 49293425
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Benutzerrichtlinien für die Archivierung in Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Für die Aktivierung bzw. Deaktivierung der Archivierung für bestimmte Benutzer, die unter Lync Server 2013 verwaltet werden, ist das Erstellen und Konfigurieren von mindestens einer Benutzerrichtlinie sowie das Anwenden der entsprechenden Richtlinie für bestimmte Benutzer oder Benutzergruppen erforderlich. Benutzerrichtlinien setzen Standortrichtlinien und globale Richtlinien außer Kraft, jedoch nur für Benutzer, die unter Lync Server 2013 verwaltet werden.

Benutzer werden immer unter Lync Server verwaltet. Ist die Microsoft Exchange-Integration aktiviert, müssen die Archivierungsrichtlinien der Benutzer mit Postfächern unter Microsoft Exchange Server 2013 nicht unter Lync Server verwalten werden. Diese Benutzer mit der Archivierungsfunktion werden mit dem Exchange-Compliance-Archiv verwaltet.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich zur Hierarchie für globale, standortbezogene und benutzerbezogene Richtlinien, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.


> [!NOTE]
> Wenn Sie für Ihre Bereitstellung die Microsoft Exchange-Integration aktiviert haben, wird mithilfe von Richtlinien des Exchange-Compliance-Archivs gesteuert, ob die Archivierung für die unter Exchange 2013 verwalteten Benutzer aktiviert wird. Die Archivierung für diese Benutzer erfordert, dass für ihre Postfächer das Compliance-Archiv festgelegt wird. Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A>.<BR>Geben Sie in den Archivierungskonfigurationen erst alle erforderlichen Optionen ein, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen</A>.



## In diesem Abschnitt

  - [Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in Lync Server](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Anwenden einer Lync Server-Archivierungsrichtlinie auf einen Benutzer](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

