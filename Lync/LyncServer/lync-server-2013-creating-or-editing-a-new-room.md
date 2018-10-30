---
title: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Chatrooms'
TOCTitle: Erstellen oder Bearbeiten eines neuen Chatrooms
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215880(v=OCS.15)
ms:contentKeyID: 49295044
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Bearbeiten eines neuen Chatrooms in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-19_

Die Konfiguration von Chatrooms für Chats vom Typ Beständiger Chat erfolgt im Allgemeinen durch die Benutzer; ein Administrator für Chats vom Typ Beständiger Chat konfiguriert oder verwaltet normalerweise keine Chatrooms. Die Windows PowerShell-Cmdlets zum Verwalten von Chatrooms sind für **CsPersistentChatAdministrator**-Administratoren verfügbar.

Benutzer, die in einer bestimmten Kategorie **Ersteller** sind, können den Lync-Client zum Erstellen und Verwalten von Chatrooms verwenden. Benutzer, die für einen bestimmten Chatroom als Manager bestimmt wurden, können den Chatroom auch fortlaufend verwalten, indem sie beispielsweise dessen Eigenschaften oder Mitgliedschaften bearbeiten.


> [!TIP]
> Administratoren für Chats vom Typ Beständiger Chat können auch Ersteller sein, und sie unterliegen nicht den für die Ersteller festgelegten Einschränkungen.



Wenn Sie Administrator für Chats vom Typ Beständiger Chat sind, können Sie optional eine Benutzerschnittstelle zum Erstellen und Verwalten von Chatrooms verwenden, anstatt Windows PowerShell-Cmdlets zu verwenden. Führen Sie dazu für einen Administrator eine SIP-Aktivierung für einen Server für beständigen Chat aus, und verwenden Sie dann den Lync-Client zum Erstellen und Verwalten von Chatrooms.

Wenn Sie einen benutzerdefinierten Chatroom-Verwaltungsworkflow für Ihre Benutzer erstellen möchten, können Sie die Eigenschaft **RoomManagementUrl** für Ihre Server für beständigen Chat-Konfiguration so festlegen, dass Benutzer vom Lync-Client zu Ihrer benutzerdefinierten Lösung umgeleitet werden.

Ausführliche Informationen zum Konfigurieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Chatroomverwaltung" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Chatrooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

