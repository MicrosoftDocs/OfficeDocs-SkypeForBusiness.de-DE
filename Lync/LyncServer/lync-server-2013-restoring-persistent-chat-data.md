---
title: Wiederherstellen von Daten des beständigen Chats
TOCTitle: Wiederherstellen von Daten des beständigen Chats
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945649(v=OCS.15)
ms:contentKeyID: 52056451
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen von Daten des beständigen Chats

 

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Der Beständiger Chat-Chatroominhalt wird in der Beständiger Chat-Datenbank ("Mgc.mdf") gespeichert. Diese für das Unternehmen wichtigen Daten sollten regelmäßig gesichert werden. Neben dem Chatroominhalt werden in der Beständiger Chat-Datenbank auch Informationen zu den Prinzipalen (z. B. Benutzer und Benutzergruppen) sowie zu den Rollen und ihren Zugriffsberechtigungen für Chatrooms gespeichert.

Die Art der Wiederherstellung der Beständiger Chat-Daten hängt von der Methode ab, mit der Sie die Daten gesichert haben.

  - Wenn Sie SQL Server-Sicherungsverfahren verwendet haben, müssen Sie SQL Server-Wiederherstellungsverfahren verwenden.

  - Wenn Sie das **Export-CsPersistentChatData**-Cmdlet zum Sichern der Beständiger Chat-Daten verwendet haben, müssen Sie die Daten mit dem **Import-CsPersistentChatData**-Cmdlet wiederherstellen.

