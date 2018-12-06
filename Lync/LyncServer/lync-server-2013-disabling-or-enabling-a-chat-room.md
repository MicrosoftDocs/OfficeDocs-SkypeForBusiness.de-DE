---
title: 'Lync Server 2013: Deaktivieren oder Aktivieren eines Chatrooms'
TOCTitle: Deaktivieren oder Aktivieren eines Chatrooms
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215883(v=OCS.15)
ms:contentKeyID: 49295605
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deaktivieren oder Aktivieren eines Chatrooms in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn das Thema eines Beständiger Chatrooms nicht mehr relevant ist, können Sie den Chatroom deaktivieren, damit er den Benutzern nicht mehr zur Verfügung steht. Wird ein Chatroom deaktiviert, dann werden alle Mitglieder vom Chatroom getrennt. Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten, und er wird auch nicht bei der Suche nach Chatrooms gefunden.

Ein deaktivierter Chatroom kann später von einem Administrator für Beständiger Chat wieder aktiviert werden. Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten. Wenn Sie den Chatroom also wieder aktivieren, müssen Sie die Einstellungen nicht manuell neu erstellen.

Wenn der Verlauf des Chatrooms gespeichert wird (das Speichern des Chatroomverlaufs ist eine optionale Einstellung in einer Kategorie, die für alle Chatrooms innerhalb dieser Kategorie gilt; standardmäßig wird der Verlauf gespeichert, was aber durch Deaktivieren der Option **Chatverlauf aktivieren** für diese Kategorie abgestellt werden kann), bleiben die Inhalte beim Deaktivieren des Chatrooms erhalten. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden.

Ausführliche Informationen zum Aktivieren und Deaktivieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Verwalten von Chatrooms" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Zum Deaktivieren eines Chatrooms verwenden Sie einen ähnlichen Befehl wie den folgenden:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Zum Aktivieren eines Chatrooms legen Sie die Eigenschaft "Disabled" auf "False" fest:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Beachten Sie, dass Chatrooms nicht über das Lync Server-Systemsteuerung aktiviert oder deaktiviert werden können.

Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Chatrooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

