---
title: 'Lync Server 2013: Löschen eines Chatrooms oder einer Kategorie'
TOCTitle: Löschen eines Chatrooms oder einer Kategorie
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215881(v=OCS.15)
ms:contentKeyID: 49295082
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines Chatrooms oder einer Kategorie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Chatrooms für Chats vom Typ Beständiger Chat können gelöscht werden. Wenn ein Chatroom nicht mehr verwendet wird, können Sie ihn deaktivieren. Ausführliche Informationen dazu finden Sie unter [Deaktivieren oder Aktivieren eines Chatrooms in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Administratoren für Chats vom Typ Beständiger Chat können eine Abfrage nach deaktivierten Chatrooms ausführen und die Chatrooms mithilfe des Windows PowerShell-Cmdlets **Remove-CsPersistentChatRoom** regelmäßig und endgültig löschen.

Kategorien können gelöscht werden. Zum Löschen einer Kategorie müssen Sie jedoch zunächst alle Chatrooms in dieser Kategorie löschen oder die Chatrooms in eine neue Kategorie verschieben, sodass eine leere Kategorie für die Löschung übrig bleibt. Der Server vom Typ Server für beständigen Chat lässt nicht zu, dass sie eine Kategorie löschen, die Chatrooms enthält. Ausführliche Informationen dazu finden Sie unter [Verschieben eines Chatrooms von einer Kategorie in eine andere in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Einzelheiten zum Löschen leerer Kategorien mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Chatroomverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Ausführliche Informationen zu Chatrooms und Kategorien finden Sie unter [Konfigurieren von Chatrooms in Lync Server 2013](lync-server-2013-configure-rooms.md) und [Konfigurieren von Kategorien in Lync Server 2013](lync-server-2013-configure-categories.md) in der Bereitstellungsdokumentation.

