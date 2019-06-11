---
title: Grundlegendes zur Mitgliedschaft beim beständigen Chat
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e525d93e58e73304b9d3a26248418c88b5e9ea79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Grundlegendes zur Mitgliedschaft beim beständigen Chat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Der Benutzer Zugriff auf beständige Chatrooms wird von der Mitgliedschaft verwaltet. Benutzer müssen Mitglieder eines Chatrooms sein, um Nachrichten Posten und lesen zu können. Nur **Referenten** , die über eine bestimmte Zugehörigkeit zu Chatrooms verfügen, dürfen **Beiträge in Auditorium**-Chatrooms verwenden. Bei einem Auditorium handelt es sich um eine Art Chatroom (der andere ist **Normal**), in dem nur Referenten Beiträge Posten können und jeder lesen kann.

Darüber hinaus arbeiten beständige Chatrooms unter den Regeln einer Kategorie. Ausführliche Informationen zu Kategorien finden Sie unter [Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013 sowie in](lync-server-2013-managing-categories-rooms-and-add-ins.md)den Abschnitten "Funktionsweise der Kategorie" und "raumkategorie-Strategien" weiter unten in diesem Thema.

Ein beständiger Chat-Administrator kann Chatroom-Kategorien erstellen und verwalten. Im Rahmen des Erstellens und Verwaltens von Chatroom-Kategorien kann der Administrator für beständigen Chat Prinzipale (Active Directory-Domänendienste, Gruppen, Container und Benutzer) konfigurieren, die Zugriff auf Mitglieder oder Ersteller von Chatrooms einer bestimmten Kategorie haben.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory-Domänendienste und beständiger Chat

Der Server für beständigen Chat basiert auf Active Directory für den Pool interner beständiger Chat-Benutzer. Nach der Installation des beständigen Chats (Client) können Sie der Kategorie Raum Domänen von Benutzern und Benutzergruppen hinzufügen. Sie können diese Benutzer und Gruppen dann zur Mitgliedschaft in ihren Raumkategorien hinzufügen.

<div>


> [!IMPORTANT]  
> Sie müssen sicherstellen, dass keine doppelten Namen für Benutzer vorhanden sind, die Änderungen an Ihren beständigen Chatrooms vornehmen möchten. Wenn doppelte Benutzernamen vorhanden sind, ändern Sie Sie in verschiedene Namen, damit die Benutzer diese Änderungen nicht mehr vornehmen können. Wenn ein Benutzer in Active Directory doppelte Namen hat und versucht, Änderungen in seinen Räumen vorzunehmen, wird eine Fehlermeldung angezeigt, in der der Benutzer aufgefordert wird, den Administrator zur Lösung zu kontaktieren.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Funktionsweise von Kategorie-Scoping

Eine Kategorie gibt alle Benutzer und Gruppen an, die auf der Grundlage ihrer **AllowedMembers** -Eigenschaft Mitglieder in einer Mitgliederliste eines beständigen Chatrooms in dieser Kategorie sein können. Wenn Sie beispielsweise die **AllowedMembers** der Kategorie auf contoso.com festzulegen, können Sie eine beliebige Gruppe oder einen Benutzer bei *contoso* als Mitglied zu Chatrooms in dieser Kategorie hinzufügen. Wenn Sie das **AllowedMembers** für eine Kategorie auf *Sales*festzulegen, können nur Gruppen und Benutzer in dieser Verteilerliste als Mitglieder zu Chatrooms in dieser Kategorie hinzugefügt werden. Auf ähnliche Weise **** können Sie mit der Creators-Eigenschaft steuern, wer Chatrooms in dieser Kategorie erstellen kann. Nach dem Erstellen des Chatrooms kann jeder aus der **AllowedMembers** -Gruppe als **Manager** für laufende Verwaltungsvorgänge in den Räumen (beispielsweise Mitgliedschaftsänderungen und Genehmigungen) festgelegt werden.

Das Definieren von **AllowedMembers** und Erstellern für eine Kategorie bietet die folgenden Vorteile: ****

  - Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.

  - Ein Benutzer, der sich in **** der Liste der Ersteller befindet, kann neue Chatrooms in dieser Kategorie erstellen. Wenn Sie ein System implementieren möchten, bei dem eine begrenzte Anzahl von Mitarbeitern in der Organisation Chatrooms erstellen kann, kann dieses Steuerelement verwendet werden, um diese Anforderung zu erfüllen.

</div>

<div>

## <a name="room-category-strategies"></a>Strategien für Raumkategorien

Die **AllowedMembers** einer Kategorie müssen alle Benutzer umfassen, die in dieser Kategorie einen beliebigen beständigen Chatroom verwenden werden. Je nach Ihren Anforderungen, um Geschäftsdaten zu schützen und die angemessene Zugriffsebene zu gewährleisten, möchten Sie möglicherweise eine oder mehrere Kategorien definieren, um anzugeben, wer in Räumen suchen und daran teilnehmen kann. Wenn Sie nur einer bestimmten Gruppe von Benutzern (einem zentralen Helpdesk oder nur Vollzeit-Mitarbeitern) das Erstellen von Räumen gestatten möchten, können Sie die Ersteller einer Kategorie so einrichten, dass diese Anforderung erfüllt wird. ****

Kategorien können auch verwendet werden, um ethische Wände zu erstellen. Ethische Mauern verhindern einen Interessenkonflikt in einer Organisation. Beispielsweise kann ein Administrator Chatrooms in einer Kategorie nur für Händler erstellen, während Chatrooms in einer anderen Kategorie nur von Analysten verwendet werden können.

<div>


> [!NOTE]  
> In lync Server 2013, beständiger Chat Server, wird der Zugriff auf Verbundbenutzer nicht unterstützt. Wenn in früheren Versionen des beständigen Chat Servers Chats von Verbundbenutzern vorhanden sind, werden Sie migriert. Die Verbundbenutzer werden als deaktivierte Prinzipale hinzugefügt.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Einschränken der Mitglieder auf Benutzergruppen

Wenn Sie einer Kategorie eine Domäne hinzufügen, stehen die Benutzergruppen, deren Gruppenobjekte in dieser Domäne enthalten sind, für Sie zur Verfügung, damit Sie Sie als Mitglieder von Räumen in dieser Kategorie angeben können.

Wir empfehlen, dass Sie in der Regel Active Directory-Container wie Domänen und Organisationseinheiten verwenden, um **AllowedMembers** und Creators einer Kategorie zu definieren. **** Sie können Objekte aus einer beliebigen Domäne zu einer **AllowedMembers** - **** oder Creators-Liste hinzufügen. Den Räumen unter dieser Kategorie können nur Objekte in der **AllowedMembers** -oder **Creators** -Liste hinzugefügt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

