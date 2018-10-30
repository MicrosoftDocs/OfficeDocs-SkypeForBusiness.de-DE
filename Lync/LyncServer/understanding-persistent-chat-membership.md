---
title: Grundlegendes zur Mitgliedschaft beim beständigen Chat
TOCTitle: Grundlegendes zur Mitgliedschaft beim beständigen Chat
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398730(v=OCS.15)
ms:contentKeyID: 49294736
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grundlegendes zur Mitgliedschaft beim beständigen Chat

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Der Benutzerzugriff auf Chatrooms in Beständiger Chat wird über die Mitgliedschaft verwaltet. Ein Benutzer muss Mitglied eines Chatrooms sein, um Nachrichten zu veröffentlichen und zu lesen. Nur **Referenten** mit einer festgelegten Zugehörigkeit zu Chatrooms können in **Auditoriumchatrooms veröffentlichen**. Ein Auditorium ist ein Chatroomtyp (der andere Typ ist **Normal**), in dem ausschließlich Referenten veröffentlichen und alle anderen lesen können.

Darüber hinaus unterliegen Chatrooms in Beständiger Chat den Regeln einer Kategorie. Ausführliche Informationen zu Kategorien finden Sie unter [Verwalten von Kategorien, Chatrooms und Add-Ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md) und in den Abschnitten "Funktionsweise der Mitgliedschaft in Kategorien" und "Strategien für Chatroomkategorien" im weiteren Verlauf dieses Themas.

Ein Beständiger Chat-Administrator kann Chatroomkategorien erstellen und verwalten. Im Rahmen des Erstellens und Verwaltens von Chatroomkategorien kann der Beständiger Chat-Administrator Prinzipale ( Active Directory-Domänendienste-Gruppen, -Container und -Benutzer) konfigurieren, die als Mitglieder oder Ersteller von Chatrooms in einer bestimmten Kategorie Zugriff haben.

## Active Directory-Domänendienste und Beständiger Chat

Server für beständigen Chat nutzt die Active Directory-Dienste für den Pool interner Benutzer von Beständiger Chat. Nach der Installation von Beständiger Chat (Client) können Sie dem Bereich der Chatrooms Domänen von Benutzern und Benutzergruppen hinzufügen. Sie können dann die Benutzer und Gruppen zur Mitgliedschaft Ihrer Chatroomkategorien hinzufügen.


> [!IMPORTANT]
> Sie müssen sicherstellen, dass für Benutzer, die Änderungen an ihren Chatrooms in Beständiger Chat vornehmen möchten, keine doppelten Namen vorhanden sind. Falls doppelte Benutzernamen vorhanden sind, ändern Sie diese in andere Namen, um die Sperrung der Änderungen durch diese Benutzer aufzuheben. Wenn ein Benutzer in Active Directory doppelte Namen hat und Änderungen an seinen Chatrooms durchführen will, wird eine Fehlermeldung angezeigt, die den Benutzer auffordert, sich für die Lösung an den Administrator zu wenden.



## Funktionsweise von Bereichen in Kategorien

Eine Kategorie gibt alle Benutzer und Gruppen an, die auf der Grundlage ihrer Eigenschaft **AllowedMembers** Mitglied in einer Mitgliederliste eines Chatrooms in Beständiger Chat in dieser Kategorie sein können. Wenn Sie beispielsweise für die Eigenschaft **AllowedMembers** der Kategorie contoso.com festlegen, können Sie beliebige Gruppen oder Benutzer zu *Contoso* als Mitglied von Chatrooms in dieser Kategorie festlegen. Wenn Sie für die Eigenschaft **AllowedMembers** einer Kategorie *Sales* festlegen, können nur Gruppen und Benutzer dieser Verteilerliste als Mitglieder von Chatrooms in dieser Kategorie festgelegt werden. Ähnlich können Sie mit der Eigenschaft **Creators** steuern, wer Chatrooms in der Kategorie erstellen kann. Nachdem der Chatroom erstellt wurde, können alle Mitglieder der Gruppe **AllowedMembers** als **Manager** für laufende Verwaltungsvorgänge für die Chatrooms festgelegt werden (z. B. Änderungen der Mitgliedschaft und Genehmigungen).

Das Definieren von **AllowedMembers** und **Creators** für eine Kategorie hat folgende Vorteile:

  - Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.

  - Ein Benutzer, der in der Liste **Creators** vorhanden ist, kann in der Kategorie neue Chatrooms erstellen. Falls Sie ein System implementieren möchten, in dem nur eine beschränkt Anzahl Mitarbeiter der Organisation Chatrooms erstellen kann, können Sie dies nach diesem Verfahren realisieren.

## Strategien für Chatroomkategorien

Zu den **AllowedMembers** einer Kategorie müssen alle Benutzer gehören, die einen Chatroom in Beständiger Chat in der jeweiligen Kategorie benutzen. Abhängig von Ihren Anforderungen im Hinblick auf den Schutz von Geschäftsdaten und zur Sicherstellung der passenden Zugriffsebene können Sie eine oder mehrere Kategorien definieren, um festzulegen, wer in Chatrooms suchen und sich beteiligen kann. Wenn Sie nur einer bestimmten Gruppe von Benutzern (zentraler Helpdesk oder ausschließlich Vollzeitkräfte) erlauben möchten, Chatrooms zu erstellen, können Sie die **Creators** einer Kategorie entsprechend festlegen.

Kategorien können auch eingesetzt werden, um chinesische Mauern zu errichten. Chinesische Mauern verhindern das Auftreten von Interessenkonflikten in einer Organisation. Ein Administrator kann z. B. Chatrooms in einer Kategorie erstellen, die nur für Händler vorgesehen ist, während die Chatrooms in einer anderen Kategorie ausschließlich durch Analysten genutzt werden können.


> [!NOTE]
> In Lync Server 2013, Server für beständigen Chat wird kein Zugriff von Partnerbenutzern unterstützt. Sofern Chats von Partnerbenutzern in früheren Versionen von Server für beständigen Chat vorhanden sind, werden diese migriert. Die Partnerbenutzer werden als deaktivierte Prinzipale hinzugefügt.



## Beschränken der Mitglieder auf Benutzergruppen

Wenn Sie eine Domäne zu einer Kategorie hinzufügen, können Sie die Benutzergruppen, deren Gruppenobjekte in dieser Domäne enthalten sind, als Mitglieder von Chatrooms in der Kategorie festlegen.

Es empfiehlt sich in der Regel, Active Directory-Container, wie Domänen und Organisationseinheiten, zu verwenden, um die **AllowedMembers** und **Creators** einer Kategorie zu definieren. Zur Liste der **AllowedMembers** oder der **Creators** können Objekte aus beliebigen Domänen hinzugefügt werden. Ausschließlich Objekte, die in der Liste **AllowedMembers** oder **Creators** enthalten sind, können zu Chatrooms der entsprechenden Kategorie hinzugefügt werden.

