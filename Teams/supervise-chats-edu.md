---
title: Verwenden überwachter Chats
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über überwachte Chats in Microsoft Teams Besprechungen.
ms.openlocfilehash: 0d2b727ab28577e8d7d9ed6d935afeab38560d94
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749001"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Überwachen von Chats in Microsoft Teams

Bildungseinrichtungen bieten Schülern und Studenten einen sicheren und gesunden digitalen Bereich. Der digitale Bereich umfasst E-Mails, Onlinebesprechungen und -anrufe sowie Messaging in Teams. Um unangemessenes Nachrichtenverhalten zu verhindern, deaktivieren viele Schulen den privaten Chat in Teams. Unglücklicherweise blockiert das Deaktivieren des Chats auch die Möglichkeit für Lehrer, Schüler privat zum personalisierten Lernen zu erreichen. Wenn der Chat deaktiviert ist, können die Kursteilnehmer Lehrer nicht erreichen, wenn sie es vorziehen, die Nachrichten nicht öffentlich in Kursteams zu veröffentlichen.

Durch einen überwachten Chat können bestimmte Lehrkräfte Chats mit Kursteilnehmern initiieren und Schüler/Studierende am Starten neuer Chats sperren, es sei denn, eine geeignete Lehrkraft ist anwesend. Wenn die Chatüberwachung aktiviert ist, dürfen Supervisor keine Chats verlassen, und andere Teilnehmer dürfen sie nicht entfernen, um sicherzustellen, dass Chats, die Schüler/Studierende beteiligt, ordnungsgemäß überwacht werden.

Diese Einschränkungen werden nur auf neue private Chats angewendet, die erstellt werden, nachdem der überwachte Chat vollständig aktiviert wurde. Sie gelten nicht für vorhandene private Chats, Besprechungschats oder Kanäle. Weitere Informationen zu den bewährten Methoden für Besprechungschat, Kanalsicherheit und die Sicherheit von Kursteilnehmern finden Sie unter Gewährleisten der Sicherheit von Kursteilnehmern bei der [Verwendung Teams.](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> Der überwachte Chat schützt neue Chats, die nach dem Erzwingen des Features erstellt wurden.  Vorhandene Chats werden nicht geschützt.

## <a name="review-use-cases-for-supervised-chats"></a>Überprüfen von Verwendungsfällen für überwachte Chats

In den folgenden Beispielen wird beschrieben, wann ein überwachter Chat erforderlich ist.

- Eine 1.1-Nach anschluss an einen Lehrer oder Dozenten, wenn es den Schülern/Studenten nicht möglich ist, Fragen öffentlich frei zu geben oder zu stellen.

- Lehrkräfte haben 1.1 mit einem Kursteilnehmer zu einer Aufgabe, einer kürzlich durchgeführten Kursinteraktion (oder fehlender) oder einem anderen Thema kontaktiert.

- Von einem Lehrer/Dozent überwachte Diskussionen in Kursteilnehmergruppen.

- Lassen Sie nicht unterrichtende Mitarbeiter in einer überwachten Umgebung mit Kursteilnehmern chatten.

## <a name="enable-supervised-chat"></a>Aktivieren eines überwachten Chats

> [!Note]
> Stellen Sie sicher, dass Sie Chatberechtigungsrollen und die rollenbasierten Chat-Berechtigungsrichtlinien einrichten, bevor Sie Chats für Ihre Bildungseinrichtung aktivieren, um unerwünschten Zugriff von Kursteilnehmern auf nicht überwachte Chats zu vermeiden.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definieren von Chatberechtigungsrollen für jeden Benutzer in Ihrer Umgebung

Damit der überwachte Chat wie erwartet funktioniert, muss jedem Benutzer in Ihrer Umgebung die richtige Chatberechtigungsrolle zugewiesen werden. Es gibt drei Rollen, die ein Benutzer zugewiesen haben kann:

- *Vollständige Berechtigungen* – Diese Rolle eignet sich ideal für Lehrkräfte, die Vollzugriff auf Kursteilnehmer und andere Mitarbeiter haben sollten. Sie können Chats mit jedem Benutzer in Ihrer Umgebung starten. Von Benutzern mit vollständigen Berechtigungen wird erwartet, dass sie die Chats beaufsichtigen, an den sie teilnehmen. Sie können Chats, die sie starten, oder Chats, die sie in Partnerbenutzern überwacht, nicht verlassen oder aus ihnen entfernen.

- *Eingeschränkte* Berechtigungen – Diese Rolle eignet sich ideal für Mitarbeiter, die nur den Zugriff auf Schüler/Studierende überwachen und vollzugriff auf andere Mitarbeiter und Lehrkräfte haben sollten. Sie können Chats mit allen oder eingeschränkten Benutzern, aber nicht mit eingeschränkten Benutzern starten. Wenn ein Benutzer mit voll berechtigten Berechtigungen einen Chat mit einem eingeschränkten Benutzer beginnt, können nur eingeschränkte Benutzer zur Unterhaltung teilnehmen. Dieser Zugriff erfolgt, weil ein Benutzer mit vollständigen Berechtigungen anwesend ist, um die Zusammenarbeit zwischen eingeschränkten und eingeschränkten Benutzern zu beaufsichtigen.

- *Eingeschränkte* Berechtigungen: Diese Rolle eignet sich ideal für Schüler/Studierende, die überwacht werden müssen. Sie können nur Chats mit Benutzern starten, die über vollständige Berechtigungen verfügen. Sie können an jeder Unterhaltung teilnehmen, zu der ein Benutzer mit vollständigen Berechtigungen eingeladen wird. In Partnerchat-Fällen können eingeschränkte Benutzer nur von benutzern mit vollständigen Berechtigungen zu Chats hinzugefügt werden, die vom Mandanten des eingeschränkten Benutzers kommen.

Verwenden Sie zum Festlegen der Chatberechtigungsrolle Ihrer Benutzer die Rollenrichtlinie Chatberechtigungen, die in den Optionen für Messagingrichtlinien im Teams-Administratorportal zu finden ist.   Sie können PowerShell verwenden, um Rollen mithilfe der Richtlinie ChatPermissionRole mit den Werten "Full", "Limited" oder "Restricted" zu definieren. Diese Richtlinie befindet sich unter CsTeamsMessagingPolicy.

Weitere Informationen zum Festlegen. Teams Richtlinien finden sie Teams Richtlinienpakete für Bildungseinrichtungen und Zuweisen von Richtlinien zu großen Gruppen von Benutzerhandbüchern.

Rollen können Gäste in Ihrem Mandanten nicht zugewiesen werden. Gästen wird die eingeschränkte Rolle zugewiesen.

### <a name="allow-supervised-chat"></a>Zulassen eines überwachten Chats

Überwachter Chat ist für Ihren Mandanten standardmäßig deaktiviert. Nachdem Sie Chat-Berechtigungsrollen für Ihre Benutzer festgelegt haben, können Sie den **überwachten** Chat innerhalb Ihres Mandanten aktivieren, indem Sie zu Teams &gt; **Teams-Einstellungen** und die Richtlinie rollenbasierte Chatberechtigungen auf Ein *festlegen.*  Sie können auch PowerShell verwenden, um den überwachten Chat zu aktivieren, indem Sie AllowRoleBasedChatPermissions auf True festlegen. Dieses Cmdlet befindet sich unter CsTeamsClientConfiguration.

Überwachter Chat muss für alle Benutzer im Mandanten aktiviert sein und kann nicht nur für einen Teil Ihrer Benutzer aktiviert werden.

### <a name="enable-chat"></a>Aktivieren des Chats

Aktivieren Sie chatten für alle Ihre Benutzer, indem Sie die im Admin Center Teams Chat-Richtlinie verwenden.

## <a name="maintain-supervised-chats"></a>Beibehalten überwachter Chats

Nachdem der überwachte Chat aktiviert wurde, müssen Sie einige Schritte unternehmen, um sicherzustellen, dass die Chats in Ihrer Umgebung überwacht bleiben:

- Weisen Sie allen neuen Benutzern, die Ihrem Mandanten beitreten, die entsprechenden Rollen zu. Standardmäßig wird Benutzern eine eingeschränkte Rolle zugewiesen.

- Wenn ein Benutzer mit vollständigen Berechtigungen einen Mandanten verlässt oder aus ihm entfernt wird, bleiben die von ihm überwachten Chats unbeaufsichtigt. Bevor Sie den ursprünglichen Benutzer entfernen, stellen Sie sicher, dass diesen Unterhaltungen ein anderer Benutzer mit vollständigen Berechtigungen hinzugefügt wird, damit der Chat überwacht bleiben kann. Nachdem der ursprüngliche Vorgesetzte entfernt wurde, können neue Teilnehmer der Unterhaltung nicht mehr hinzugefügt werden, aktuelle Teilnehmer können jedoch weiterhin kommunizieren.

## <a name="related-topics"></a>Verwandte Themen

[Überwachen von Chats für Teams in Bildungseinrichtungen](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
