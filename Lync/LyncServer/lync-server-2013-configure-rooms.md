---
title: 'Lync Server 2013: Konfigurieren von Chatrooms'
TOCTitle: Konfigurieren von Chatrooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205067(v=OCS.15)
ms:contentKeyID: 49294666
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Chatrooms in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Die Konfiguration von Beständiger Chat-Rooms wird im Allgemeinen von Benutzern oder anderen zentralen Teams mit Windows PowerShell-Befehlszeilenschnittstelle ausgeführt. Chatrooms werden normalerweise nicht von Administratoren verwaltet. Wenn Sie dennoch Chatrooms erstellen und verwalten müssen, können Sie Windows PowerShell-Befehlszeilenschnittstelle verwenden oder sich selbst als Mitglied zu einem Chatroom hinzufügen und den Lync 2013-Client verwenden.

Ausführliche Informationen zum Konfigurieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Chatroomverwaltung" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

## Verwalten von Daten in Chatrooms

Mit Server für beständigen Chat können Benutzer zusammenarbeiten, indem Sie Nachrichten in Beständiger Chat-Rooms veröffentlichen. Die Daten sind auf dem Server vorhanden, und die Mitglieder des Chatrooms können auf die Daten, einschließlich der Verlaufsdaten, zugreifen. Benutzer mit verschiedenen Rollen haben jedoch einen anderen Zugriff auf die persistenten Daten. Dies wird in der folgenden Liste beschrieben.

  - Administratoren können frühere Inhalte aus jedem Chatroom löschen (z. B. Inhalte, die vor einem bestimmen Datum veröffentlicht wurden), um zu verhindern, dass die Datenbanken zu groß werden. Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom ungeeignet sind.

  - Endbenutzer, einschließlich Autoren von Nachrichten, können keine Inhalte aus Chatrooms entfernen.

  - Chatroom-Manager können Chatrooms deaktivieren, aber nicht löschen. Nur Administratoren können Chatrooms löschen, nachdem diese erstellt wurden.

Wenn eine Nachricht gelöscht wird, kann diese Aktion nicht rückgängig gemacht werden. Wenn ein Beständiger Chat-Kompatibilitätsserver aktiviert wird, werden alte Nachrichten in der Kompatibilitätsdatenbank gespeichert.


> [!NOTE]
> Diese Datenverwendung des Chatrooms gilt für die Lync Server 2013-, Server für beständigen Chat-API Application, außer wenn die Administratorrolle involviert ist. Die Server für beständigen Chat-API kann nicht verwendet werden, um beliebige Administratorvorgänge auszuführen. Diese Vorgänge müssen Sie in der Lync Server-Verwaltungsshell ausführen.


