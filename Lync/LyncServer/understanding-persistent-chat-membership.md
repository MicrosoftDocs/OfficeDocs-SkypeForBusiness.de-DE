---
title: Grundlegendes zur Mitgliedschaft im beständigen Chat
description: Grundlegendes zur Mitgliedschaft in beständigen Chat.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0d26ea56552d8906ab9a5cf216a7026868017
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579601"
---
# <a name="understanding-persistent-chat-membership"></a>Grundlegendes zur Mitgliedschaft im beständigen Chat

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Der Benutzer Zugriff auf beständige Chatrooms wird durch die Mitgliedschaft verwaltet. Benutzer müssen Mitglied eines Chatrooms sein, um Nachrichten Posten und lesen zu können. Nur **Referenten** , die über eine bestimmte Zugehörigkeit mit Chatrooms verfügen, können das **Posting in Auditorium**-Chatrooms verwenden. Ein Auditorium ist eine Art Chatroom (der andere ist **Normal**), wo nur Referenten Posten können und jeder lesen kann.

Darüber hinaus werden die Räume für beständigen Chatrooms unter den Regeln einer Kategorie ausgeführt. Ausführliche Informationen zu Kategorien finden Sie unter [Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)sowie in den Abschnitten "How Category Scoping Works" und "Room category Strategies" weiter unten in diesem Thema.

Ein Administrator für beständigen Chat kann Chat Raumkategorien erstellen und verwalten. Im Rahmen der Erstellung und Verwaltung von Chatroom-Kategorien kann der Administrator für beständigen Chat Prinzipale (Active Directory-Domänendienste Gruppen, Container und Benutzer) konfigurieren, die Zugriff auf Mitglieder oder Ersteller von Chatrooms einer bestimmten Kategorie haben.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory-Domänendienste und beständiger Chat

Der Server für beständigen Chat basiert auf Active Directory für den Pool interner persistent Chat-Benutzer. Nachdem Sie den beständigen Chat (Client) installiert haben, können Sie der raumkategorie Domänen von Benutzern und Benutzergruppen hinzufügen. Sie können dann die Benutzer und Gruppen zur Mitgliedschaft Ihrer Chatroomkategorien hinzufügen.

<div>


> [!IMPORTANT]  
> Sie müssen sicherstellen, dass für Benutzer, die Änderungen an Ihren beständigen Chatrooms vornehmen möchten, keine doppelten Namen vorhanden sind. Falls doppelte Benutzernamen vorhanden sind, ändern Sie diese in andere Namen, um die Sperrung der Änderungen durch diese Benutzer aufzuheben. Wenn ein Benutzer in Active Directory doppelte Namen aufweist und versucht, Änderungen in den/den-Räumen vorzunehmen, wird eine Fehlermeldung angezeigt, in der der Benutzer aufgefordert wird, den Administrator zur Lösung zu kontaktieren.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Funktionsweise von Bereichen in Kategorien

Eine Kategorie gibt alle Benutzer und Gruppen an, die in einer Mitgliedschaftsliste eines beständigen Chatrooms in dieser Kategorie basierend auf der **AllowedMembers** -Eigenschaft Mitglieder sein können. Wenn Sie beispielsweise die **AllowedMembers** der Kategorie auf contoso.com festlegen, können Sie eine beliebige Gruppe oder einen Benutzer bei *contoso* als Mitglied zu Chatrooms in dieser Kategorie hinzufügen. Wenn Sie für die Eigenschaft **AllowedMembers** einer Kategorie *Sales* festlegen, können nur Gruppen und Benutzer dieser Verteilerliste als Mitglieder von Chatrooms in dieser Kategorie festgelegt werden. Ähnlich können Sie mit der Eigenschaft **Creators** steuern, wer Chatrooms in der Kategorie erstellen kann. Nachdem der Chatroom erstellt wurde, können alle Mitglieder der Gruppe **AllowedMembers** als **Manager** für laufende Verwaltungsvorgänge für die Chatrooms festgelegt werden (z. B. Änderungen der Mitgliedschaft und Genehmigungen).

Das Definieren von **AllowedMembers** und **Creators** für eine Kategorie hat folgende Vorteile:

  - Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.

  - Ein Benutzer, der in der Liste **Creators** vorhanden ist, kann in der Kategorie neue Chatrooms erstellen. Falls Sie ein System implementieren möchten, in dem nur eine beschränkt Anzahl Mitarbeiter der Organisation Chatrooms erstellen kann, können Sie dies nach diesem Verfahren realisieren.

</div>

<div>

## <a name="room-category-strategies"></a>Strategien für Chatroomkategorien

Das **AllowedMembers** einer Kategorie muss alle Benutzer einschließen, die in dieser Kategorie einen beliebigen beständigen Chatroom verwenden sollen. Abhängig von Ihren Anforderungen im Hinblick auf den Schutz von Geschäftsdaten und zur Sicherstellung der passenden Zugriffsebene können Sie eine oder mehrere Kategorien definieren, um festzulegen, wer in Chatrooms suchen und sich beteiligen kann. Wenn Sie nur einer bestimmten Gruppe von Benutzern (zentraler Helpdesk oder ausschließlich Vollzeitkräfte) erlauben möchten, Chatrooms zu erstellen, können Sie die **Creators** einer Kategorie entsprechend festlegen.

Kategorien können auch eingesetzt werden, um chinesische Mauern zu errichten. Chinesische Mauern verhindern das Auftreten von Interessenkonflikten in einer Organisation. Ein Administrator kann z. B. Chatrooms in einer Kategorie erstellen, die nur für Händler vorgesehen ist, während die Chatrooms in einer anderen Kategorie ausschließlich durch Analysten genutzt werden können.

<div>


> [!NOTE]  
> In lync Server 2013 Server für beständigen Chat wird der Zugriff auf Partnerverbund Benutzer nicht unterstützt. Wenn in früheren Versionen des Servers für beständigen Chat Chats von Verbundbenutzern vorhanden sind, werden diese migriert. Die Partnerbenutzer werden als deaktivierte Prinzipale hinzugefügt.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Beschränken der Mitglieder  auf Benutzergruppen

Wenn Sie eine Domäne zu einer Kategorie hinzufügen, können Sie die Benutzergruppen, deren Gruppenobjekte in dieser Domäne enthalten sind, als Mitglieder von Chatrooms in der Kategorie festlegen.

In der Regel wird empfohlen, Active Directory Container wie Domänen und Organisationseinheiten zum Definieren der **AllowedMembers** und **Ersteller**einer Kategorie zu verwenden. Zur Liste der **AllowedMembers** oder der **Creators** können Objekte aus beliebigen Domänen hinzugefügt werden. Ausschließlich Objekte, die in der Liste **AllowedMembers** oder **Creators** enthalten sind, können zu Chatrooms der entsprechenden Kategorie hinzugefügt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

