---
title: 'Lync Server 2013: Verschieben eines Chatrooms von einer Kategorie in eine andere'
TOCTitle: Verschieben eines Chatrooms von einer Kategorie in eine andere
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215877(v=OCS.15)
ms:contentKeyID: 49294539
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben eines Chatrooms von einer Kategorie in eine andere in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wir empfehlen, die Kategorie eines Beständiger Chat-Rooms nicht zu ändern, nachdem der Chatroom erstellt wurde. Wenn der Chatroom-Manager jedoch über **Creator**-Berechtigungen in einer anderen Kategorie verfügt, kann er den Room von einer Kategorie in eine andere verschieben. Der Room wird hierbei weder gelöscht noch neu erstellt. Es wird lediglich die Zuordnung in der Datenbank geändert.

Chatroomkategorien sollten eher selten geändert werden. Eine Kategorie legt die erlaubte Mitgliedschaft für einen Chatroom fest. Wenn also der Chatroom in eine andere Kategorie verschoben wird, werden alle Systemzugriffssteuerungslisten (SACLs) gelöscht, die von der neuen Kategorie nicht unterstützt werden. Wenn beispielsweise ein Benutzer Mitglied eines Chatrooms war und nun kein **AllowedMember** der neuen Kategorie mehr ist, wird die Mitgliedschaft für den Chatroom geändert und der Benutzer aus diesem entfernt.

Ausführliche Informationen zum Verschieben eines Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie im Abschnitt "Manage Rooms" unter [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Chatrooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

