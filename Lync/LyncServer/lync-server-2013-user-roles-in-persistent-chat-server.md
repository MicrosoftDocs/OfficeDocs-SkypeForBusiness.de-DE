---
title: Benutzerrollen in Persistent Chat Server
TOCTitle: Benutzerrollen in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49890700
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Benutzerrollen in Persistent Chat Server

 

_**Letztes Änderungsdatum des Themas:** 2015-03-19_

Server für beständigen Chat stellt das Konzept der zulässigen/abgelehnten Mitglieder bereit, das auf Beständiger Chat-Kategorien angewendet wird und mit dem gesteuert wird, wer auf Chatrooms in einer bestimmten Kategorie zugreifen kann.


> [!IMPORTANT]
> Der Begriff "Zulässige/Abgelehnte Mitglieder" in einer Kategorie ist nicht dasselbe wie die Rolle <STRONG>Mitglied</STRONG>, die auf einen Chatroom für beständigen Chat angewendet wird.<BR>Bei Suchen werden alle geöffneten und geschlossenen Chatrooms angezeigt, für die sich der Benutzer, der die Suche durchführt, in der Liste der zulässigen/abgelehnten Mitglieder befindet. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann.



Das primäre Grundprinzip für das Konzept der zulässigen/abgelehnten Mitglieder sind so genannte Chinesische Mauern. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen ethische Grenzen definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Wenn diese Einschränkung im System definiert ist, kann einem Chatroom kein Benutzer hinzugefügt werden, wenn die übergeordnete Kategorie dies verhindert.

Im Folgenden sind die vier Benutzerrollen für Server für beständigen Chat aufgeführt:

  - **Ersteller:** Benutzer, die zum Erstellen von Chatrooms berechtigt sind. Diese Benutzer befinden sich in der Liste **Ersteller** von bestimmten Kategorien. Sie können Chatrooms in dieser Kategorie erstellen, eine Mitgliedschaft gemäß dieser Kategorie zuweisen sowie Manager zum Verwalten von Chatrooms zuweisen. Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.
    

    > [!NOTE]
    > Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern.

    
    Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen, und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.

  - **Manager:** Benutzer, die die Eigenschaften eines Chatrooms verwalten. Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen). Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können. Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen). Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern. Nur der Beständiger Chat-Administrator kann die Kategorie ändern, nachdem der Chatroom erstellt wurde.
    

    > [!IMPORTANT]
    > Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt.



  - **Mitglied:** Benutzer, die Mitglieder eines Chatrooms sind. Diese Benutzer können die Chatrooms im Verzeichnis sehen (auch geheime Chatrooms) sowie den Chatroom abonnieren (einschließlich Metadatenoptionen wie nicht gelesene Nachrichten, Egofilter und Schlüsselwortlisten) und am Chatroom teilnehmen (Nachrichten senden, sofern es sich nicht um ein Auditorium handelt, in dem nur Referenten Nachrichten senden und Inhalte abrufen und suchen können). Benutzer, die keine Mitglieder des Chatrooms sind, können nach dem Chatroom suchen, wenn sie sich in der Liste der zulässigen Mitglieder befinden. Wenn Sie jedoch auf den Inhalt dieser Chatrooms zugreifen möchten, müssen Sie die Mitgliedschaft bei diesem Chatroom anfordern. (Im System sind keine Zugriffsanforderungen oder Genehmigungen integriert. Die Zugriffserteilung oder Genehmigung erfolgt per E-Mail, Telefon oder andere Formen des Kontakts.)

  - **Referent:** Benutzer, die Nachrichten in einem Auditorium senden können.

Bei den folgenden Rollen handelt es sich um Administratorrollen für Server für beständigen Chat:

  - **Beständiger Chat Administrator (CsPersistentChatAdministrator):** Dies ist eine neue rollenbasierte Zugriffssteuerungsrolle (RBAC-Rolle) zur Administration und Verwaltung von Server für beständigen Chat. Benutzer oder Sicherheitsgruppen mit der Rolle **CsPersistentChatAdministrator** können Server für beständigen Chat mithilfe von Windows PowerShell-Cmdlets im Remotemodus verwalten (d. h. von einem anderen Computer als dem Server für beständigen Chat aus). Server für beständigen Chat überprüft, ob der Beständiger Chat-Administrator Mitglied der lokalen Gruppe **RTC Local Administrators** auf dem Server für beständigen Chat-Front-End-Server ist.
    
    Benutzer mit der Rolle **CsPersistentChatAdministrator** können Chatrooms verwalten (alle Eigenschaften ändern, einschließlich Mitgliedschaft, Manager, Kategorien, Kennzeichnen von Chatrooms als deaktiviert) sowie Chatroomkategorien erstellen und verwalten, die definieren, wer Chatrooms erstellen und darauf zugreifen kann. Zudem können Administratoren Chatrooms als deaktiviert kennzeichnen und Chatrooms bereinigen, die nicht mehr aktiv sind. Administratoren unterliegen nicht den Einschränkungen, die für Ersteller oder zulässige Mitglieder gelten. Administratoren können jede Art von Chatroom erstellen und sich selbst als Mitglied beliebiger Chatrooms hinzufügen. Administratoren können auch die Beständiger Chat-Konfiguration (Pooleigenschaften, globale Einstellungen und Konformitätskonfiguration) ändern und verwalten sowie die Migration einer älteren Gruppenchatserver-Bereitstellung zum Lync Server 2013-Server für beständigen Chat planen und implementieren.

  - **Lync-Administrator:** Der Administrator für das gesamte Unternehmen, der für die Lync Server 2013-Bereitstellung verantwortlich ist.

  - **Operations Manager:** Benutzer, der für die täglichen Abläufe verantwortlich ist.

  - **Drittanbieterentwickler und Partner:** Drittanbieterentwickler erweitern das System und liefern insbesondere eine Lösung zum Errichten einer Chinesischen Mauer für Gruppenunterhaltungen. Zudem stellen sie Konformitätsunterstützung und -tools, Web- und mobile Clients sowie ein Framework für Bot-Entwicklung bereit.

