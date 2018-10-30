---
title: Bewährte Methoden für den Server für beständigen Chat
TOCTitle: Bewährte Methoden für den Server für beständigen Chat
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398970(v=OCS.15)
ms:contentKeyID: 49295616
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bewährte Methoden für den Server für beständigen Chat

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Beim Erstellen von Kategorien und Beständiger Chatrooms und beim Festlegen des Bereichs und der Mitgliedschaft können die folgenden Tipps nützlich sein:

  - Wenn in Ihrem Unternehmen keine "Chinesische Mauer" notwendig ist, schränken Sie den Bereich in der Kategoriestruktur nicht ein. Nehmen Sie alle Benutzer in den Bereich einer Kategorie auf, und erstellen Sie alle Chatrooms in dieser Kategorie. Verwenden Sie dann nur Mitgliederlisten, um den Zugriff auf die einzelnen Chatrooms zu erteilen oder zu beschränken.

  - In den meisten Fällen sollten Sie zulassen, dass die Benutzer neue Chatrooms erstellen können. Dann können jederzeit Diskussionen über neue Themen aufgenommen werden. Dazu müssen die Listen **Creators** und **AllowedMembers** identisch sein. Wenn Sie jedoch nur einem zentralen Supportteam oder bestimmten Benutzern das Erstellen von Chatrooms erlauben möchten, sollte die Liste **Creators** die entsprechenden Benutzer enthalten.

  - Geben Sie für jeden Chatroom einen vollständigen Namen und eine zusammenfassende Beschreibung ein, damit die Benutzer den Chatroom innerhalb Ihrer Organisation richtig zuordnen können. Da die Benutzer den Kategorienamen nicht sehen können, wenn sie den Chatroom verwenden, hilft der Kategoriename den Benutzern nicht unbedingt, das vorgesehene Diskussionsforum für den Chatroom zu erkennen.

  - Sie können einen benutzerdefinierten Workflow zum Erstellen von Chatrooms verwenden, falls bestimmte Benennungskonventionen oder sonstige Zugriffssteuerungen oder Überprüfungen implementiert werden müssen. Bei der Konfiguration für den Beständiger Chat können Sie für **RoomManagementUrl** eine von Ihnen gehostete Lösung angeben. Wenn die Benutzer beispielsweise in ihrem Lync-Client auf **Einen Chatroom erstellen** klicken, können sie an Ihre benutzerdefinierte Lösung umgeleitet werden.

  - Sie können eine Vielzahl von Add-Ins erstellen, mit der Sie die Verwendung von Chatrooms optimieren können, indem andere Geschäftsdaten in Chatrooms eingebracht werden. Administratoren müssen die Add-Ins registrieren, die im System zulässig sein sollen. Chatroommanager und -ersteller können in der Liste der zulässigen Add-Ins die für ihre Chatrooms relevantesten Add-Ins auswählen.

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Kategorien, Chatrooms und Add-Ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)

