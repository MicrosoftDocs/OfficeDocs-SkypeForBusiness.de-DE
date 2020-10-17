---
title: 'Lync Server 2013: Benutzerrollen auf dem Server für beständigen Chat'
description: 'Lync Server 2013: Benutzerrollen im Server für beständigen Chat.'
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
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550851"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Benutzerrollen auf dem Server für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-03-19_

Der Server für beständigen Chat stellt das Konzept der zulässigen/abgelehnten Mitglieder bereit, das auf Kategorien für beständigen Chat angewendet wird, und steuert, wer auf Räume in einer bestimmten Kategorie zugreifen kann.

<div>


> [!IMPORTANT]  
> Zugelassene/abgelehnte Mitglieder in einer Kategorie sind nicht identisch mit einer <STRONG>Mitglieder Rolle,</STRONG> die für einen beständigen Chatroom gilt.<BR>Bei Suchen werden alle geöffneten und geschlossenen Chatrooms angezeigt, für die sich der Benutzer, der die Suche durchführt, in der Liste der zulässigen/abgelehnten Mitglieder befindet. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann.



</div>

Das primäre Grundprinzip für das Konzept der zulässigen/abgelehnten Mitglieder sind so genannte Chinesische Mauern. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen ethische Grenzen definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Wenn diese Einschränkung im System definiert ist, kann einem Chatroom kein Benutzer hinzugefügt werden, wenn die übergeordnete Kategorie dies verhindert.

Im folgenden sind die vier Benutzerrollen für beständigen Chat Server:

  - **Creator:** Benutzer mit Berechtigungen zum Erstellen von Chatrooms. Diese Benutzer befinden sich in der Liste der Ersteller bestimmter Kategorien: Sie können Chatrooms in dieser Kategorie erstellen, und Sie können auch eine Mitgliedschaft entsprechend der Kategorie zuweisen und Managern die Verwaltung des Chatrooms zuweisen. Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.
    
    <div>
    

    > [!NOTE]  
    > Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern.

    
    </div>
    
    Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen, und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.

  - **Manager:** Benutzer, die die Eigenschaften eines Chatrooms verwalten. Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen). Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können. Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen). Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern. Nur der Administrator für beständigen Chat kann die Kategorie ändern, nachdem der Chatroom erstellt wurde.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt.

    
    </div>

  - **Mitglied:** Benutzer, die Mitglied eines Chatrooms sind. Diese Benutzer können die Chatrooms im Verzeichnis sehen (auch wenn der Chatroom geheim ist) sowie den Chatroom abonnieren (einschließlich der Metadaten-Optionen wie ungelesene Nachrichten, Ego-Filter und Stichwortfilter) und am Chatroom teilnehmen (kann Beitrag, es sei denn, der Raum ist ein hörsaalraum, in dem nur Referenten Beiträge veröffentlichen, Inhalte abrufen und suchen können). Benutzer, die nicht Mitglied des Chatrooms sind, können nach dem Chatroom suchen, wenn Sie sich in der Liste zugelassene Mitglieder der Kategorie befinden, müssen jedoch den Zugriff auf diese Chatrooms anfordern, um auf Inhalte zuzugreifen. (Es gibt keinen Anforderungs Zugriff oder keine Genehmigungen, die in das System integriert sind; diese werden extern per e-Mail, Telefon oder anderen Kontaktformen ausgeführt.)

  - **Referent:** Benutzer, die in einem Auditorium-Raum Posten können.

<div>


> [!NOTE]  
> Mit dem Server für beständigen Chat können Benutzer Chatrooms für eine bestimmte Website erstellen und verwalten. Benutzer können Chatrooms jedoch nicht an anderen Standorten innerhalb derselben Topologie erstellen oder verwalten. Achten Sie darauf, die Ersteller und Manager für Chatrooms für alle Websites in Ihrer Organisation anzugeben.



</div>

Die folgenden Rollen sind Administratorrollen für den Server für beständigen Chat:

  - **Administrator für beständigen Chat ("cspersistentchatadministrator"):** Dies ist eine neue Rolle für die Role-Based Zugriffssteuerung, um den Server für beständigen Chat zu verwalten und zu verwalten. Benutzer oder Sicherheitsgruppen, die als "cspersistentchatadministrator" festgelegt sind, können den Server für beständigen Chat verwalten, indem Sie Windows PowerShell-Cmdlets Remote verwenden (also von einem anderen Computer als dem Server für beständigen Chat). Der Server für beständigen Chat überprüft, ob der Administrator für beständigen Chat Mitglied der lokalen Gruppe RTC Local Administrator auf dem Server für beständigen Chat ist Front-End-Server.
    
    Die "cspersistentchatadministrator"-Rolle kann Chatrooms verwalten (alle Eigenschaften einschließlich Mitgliedschaft, Manager, Kategorien, Kennzeichen von Räumen als deaktiviert) sowie Chatroom-Kategorien erstellen und verwalten, die definieren, wer Chatrooms erstellen und auf Sie zugreifen kann. Administratoren können Chatrooms auch als deaktiviert kennzeichnen und Chatrooms bereinigen, die nicht mehr aktiv sind. Administratoren unterliegen nicht den Einschränkungen der Ersteller oder zugelassenen Mitglieder. Administratoren können alle Arten von Chatrooms erstellen und sich selbst als Mitglied in Chatrooms hinzufügen. Administratoren können auch die Konfiguration beständiger Chats ändern und verwalten (Pooleigenschaften, globale Einstellungen und Kompatibilitäts Konfiguration), und Sie können auch die Migration von einer älteren Gruppen Chat Server-Bereitstellung zu beständiger Chat von lync Server 2013 Server planen und implementieren.

  - **Lync-Administrator:** Gesamtunternehmens Administrator für lync Server 2013, die für die Bereitstellung zuständig sind.

  - **Operations Manager:** Benutzer, der für die Verwaltung von alltäglichen Vorgängen verantwortlich ist.

  - **Drittanbieter-Entwickler und-Partner:** Drittanbieter erweitern das System, insbesondere die Bereitstellung einer ethischen Wandlösung für Gruppenunterhaltungen, Compliance-Support und-Tools, Web/Mobile-Clients und ein Framework für bot-Entwicklung.

</div>

<span> </span>

</div>

</div>

</div>

