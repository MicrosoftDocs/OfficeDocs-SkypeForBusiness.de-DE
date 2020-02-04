---
title: 'Lync Server 2013: Benutzerrollen im beständigen Chat Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771eac8e5c8ff1c72bfb2ce64d9b6c04853b30a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Benutzerrollen im Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-03-19_

Der Server für beständigen Chat bietet das Konzept der zugelassenen/abgelehnten Mitglieder, das auf beständige Chatkategorien und Steuerelemente angewendet wird, die auf Räume in einer bestimmten Kategorie zugreifen können.

<div>


> [!IMPORTANT]  
> Zulässige/abgelehnte Mitglieder in einer Kategorie ist nicht mit einer <STRONG>Mitglieds</STRONG> Rolle identisch, die für einen beständigen Chatroom gilt.<BR>In suchen werden alle geöffneten und geschlossenen Chatrooms angezeigt, für die der Benutzer, der die Suche ausführt, in der Liste zugelassene/abgelehnte Mitglieder aufgeführt ist. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann.



</div>

Das primäre Argument für das Konzept der zugelassenen/verweigerten Mitglieder sind ethische Mauern. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen Chinesische Mauern definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Wenn diese Einschränkung in das System vorgesehen ist, ist es nicht möglich, einen Benutzer als Mitglied des Chatrooms hinzuzufügen, wenn die übergeordnete Kategorie Dies verhindert.

Im folgenden werden die vier Benutzerrollen beständiger Chat Server:

  - **Creator:** Benutzer, die über die Berechtigung zum Erstellen von Chatrooms verfügen. Diese Benutzer befinden sich in der Liste der Ersteller bestimmter Kategorien: Sie können Chatrooms in dieser Kategorie erstellen, und Sie können auch Mitgliedschaften entsprechend der Kategorie zuweisen und Managern zuweisen, dass Sie den Chatroom verwalten möchten. Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.
    
    <div>
    

    > [!NOTE]  
    > Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern.

    
    </div>
    
    Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.

  - **Manager:** Benutzer, die die Eigenschaften eines Chatrooms verwalten. Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen). Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können. Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen). Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern. Nur der Administrator des beständigen Chats kann die Kategorie nach dem Erstellen des Chatrooms ändern.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt.

    
    </div>

  - **Mitglied:** Benutzer, die Mitglieder eines Chatrooms sind. Diese Benutzer können die Chatrooms im Verzeichnis (auch wenn der Chatroom geheim ist) sehen sowie den Chatroom abonnieren (einschließlich metadateneinstellungen wie ungelesene Nachrichten, Ego-Filter und Keyword-Filter) und am Chatroom teilnehmen (kann Posten, es sei denn, der Raum ist ein Hörsaal Raum, in dem nur Referenten Beiträge Posten, Inhalte abrufen und suchen können. Benutzer, die keine Mitglieder des Chatrooms sind, können nach dem Chatroom suchen, wenn Sie sich in der Liste der zulässigen Mitglieder der Kategorie befinden, müssen aber Zugriff auf die Teilnahme an diesen Chatrooms anfordern, um auf Inhalte zugreifen zu können. (Es sind keine Zugriffs-oder Genehmigungsanfragen in das System integriert; diese werden extern per e-Mail, Telefon oder anderen Kontaktarten durchgeführt.)

  - **Referent:** Benutzer, die in einem Auditorium-Chatroom Posten können

<div>


> [!NOTE]  
> Der beständige Chat Server ermöglicht Benutzern, Chatrooms für eine bestimmte Website zu erstellen und zu verwalten. Benutzer können Chatrooms jedoch nicht auf anderen Websites innerhalb derselben Topologie erstellen oder verwalten. Stellen Sie sicher, dass Sie für alle Websites in Ihrer Organisation Chatroom-Ersteller und-Manager angeben.



</div>

Die folgenden Rollen sind Administratorrollen für den Server für beständigen Chat:

  - **Administrator für beständigen Chat (CsPersistentChatAdministrator):** Hierbei handelt es sich um eine neue rollenbasierte zugriffssteuerungsrolle, um den Server für beständigen Chat zu verwalten und zu verwalten. Benutzer oder Sicherheitsgruppen, die als CsPersistentChatAdministrator bezeichnet werden, können beständigen Chat Server mithilfe von Windows PowerShell-Cmdlets remote verwalten (also von einem anderen Computer als dem beständigen Chat Server). Der beständige Chat Server überprüft, ob der Administrator des beständigen Chats Mitglied der lokalen Gruppe RTC Local Administrator auf dem Front-End-Server des beständigen Chats ist.
    
    Die CsPersistentChatAdministrator-Rolle kann Chatrooms verwalten (alle Eigenschaften wie Mitgliedschaft, Manager, Kategorien, als deaktiviert kennzeichnen) sowie Chatrooms erstellen und verwalten, die definieren, wer Chatrooms erstellen und darauf zugreifen kann. Administratoren können Chatrooms auch als deaktiviert kennzeichnen und Chatrooms bereinigen, die nicht mehr aktiv sind. Administratoren unterliegen nicht den Einschränkungen des Erstellers oder der zulässigen Mitglieder. Administratoren können jede Art von Chatroom erstellen und sich selbst als Mitglied zu einem Chatroom hinzufügen. Administratoren können auch die Konfiguration beständiger Chats ändern und verwalten (Pooleigenschaften, globale Einstellungen und Kompatibilitäts Konfiguration) und auch die Migration von einer älteren Gruppen-Chat Server Bereitstellung in lync Server 2013 beständigen Chat planen und implementieren. Server.

  - **Lync-Administrator:** Gesamtunternehmens Administrator für lync Server 2013, der für die Bereitstellung verantwortlich ist.

  - **Operations Manager:** Der Benutzer, der für die Verwaltung von alltäglichen Vorgängen verantwortlich ist.

  - **Drittanbieter-Entwickler und-Partner:** Entwickler von Drittanbietern erweitern das System, insbesondere die Bereitstellung einer ethischen Wandlösung für Gruppenunterhaltungen, Compliance-Unterstützung und Tools, Web/Mobile-Clients und ein Framework für die bot-Entwicklung.

</div>

<span> </span>

</div>

</div>

</div>

