---
title: Verwenden von überwachten Chats
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über überwachte Chats in Microsoft Teams-Besprechungen.
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506678"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Überwachte Chats in Microsoft Teams

Bildungseinrichtungen stellen einen sicheren und gesunden digitalen Raum für Schüler/Studenten zur Verfügung. Der digitale Bereich umfasst E-Mails, Onlinebesprechungen und Anrufe sowie Messaging in Teams. Um unangemessenes Nachrichtenverhalten zu verhindern, deaktivieren viele Schulen privaten Chat in Teams. Leider wird durch das Deaktivieren des Chats auch die Möglichkeit für Lehrer blockiert, die Schüler privat für personalisiertes Lernen zu erreichen. Wenn der Chat deaktiviert ist, können Die Kursteilnehmer nicht zu Lehrkräften gelangen, wenn sie die Nachrichten lieber nicht öffentlich in Kursteams posten möchten.

Überwachter Chat ermöglicht es designierten Lehrkräften, Chats mit Kursteilnehmern zu initiieren und schüler/studenten am Starten neuer Chats zu sperren, es sei denn, ein geeigneter Lehrer ist anwesend. Wenn die Chatüberwachung aktiviert ist, dürfen Vorgesetzte keine Chats verlassen, und andere Teilnehmer dürfen sie nicht entfernen, um sicherzustellen, dass Chats, an denen Schüler/Studenten beteiligt sind, ordnungsgemäß überwacht werden.

Diese Einschränkungen gelten nur für neue private Chats, die erstellt werden, nachdem der überwachte Chat vollständig aktiviert wurde. Sie gelten nicht für vorhandene private Chats, Besprechungschats oder Kanäle. Weitere Informationen zu bewährten Methoden für Besprechungschats, Kanalsicherheit und Die Sicherheit von Kursteilnehmern finden Sie unter Schützen von Kursteilnehmern [während der Verwendung von Teams.](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> Überwachter Chat schützt neue Chats, die nach dem Erzwingen des Features erstellt wurden.  Vorhandene Chats werden nicht geschützt.

## <a name="review-use-cases-for-supervised-chats"></a>Überprüfen von Verwendungsfällen für überwachte Chats

Die folgenden Beispiele sind Beschreibungen, wann ein überwachter Chat erforderlich ist.

- Eine 1.1-Nachnutzung mit einem Pädagogen, wenn kursteilnehmer es nicht bequem haben, öffentlich Fragen zu teilen oder zu stellen.

- Lehrkräfte, die sich mit 1.1 an einen Kursteilnehmer zu einer Aufgabe, einer kürzlich durchgeführten Kursinteraktion (oder einem Fehlenden) oder einem anderen Thema weiterbilden.

- Schülergruppendiskussionen, die von einem Lehrer überwacht werden.

- Zulassen, dass nicht lehrende Mitarbeiter in einer überwachten Umgebung mit Kursteilnehmern chatten.

## <a name="enable-supervised-chat"></a>Aktivieren des überwachten Chats

> [!Note]
> Stellen Sie sicher, dass Sie Chatberechtigungsrollen und die rollenbasierten Chatberechtigungsrichtlinien einrichten, bevor Sie chats für Ihre Bildungseinrichtung aktivieren, um unerwünschten Zugriff von Kursteilnehmern auf nicht überwachte Chats zu vermeiden.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definieren von Chatberechtigungsrollen für jeden Benutzer in Ihrer Umgebung

Damit überwachter Chat wie erwartet funktioniert, muss jedem Benutzer in Ihrer Umgebung die richtige Chatberechtigungsrolle zugewiesen werden. Es gibt drei Rollen, die ein Benutzer zugewiesen haben kann:

- *Vollständige Berechtigungen* – Diese Rolle eignet sich ideal für Lehrkräfte, die Vollzugriff auf Schüler/Studenten und andere Mitarbeiter haben sollten. Sie können chatten mit jedem Benutzer in Ihrer Umgebung beginnen. Benutzer mit vollständigen Berechtigungen sollen die Chats überwachen, an der sie teilnehmen. Sie können Chats, die sie starten, oder Chats, die sie in Partnerdächern überwacht, nicht verlassen oder aus chatten entfernen.

- *Eingeschränkte Berechtigungen* – Diese Rolle eignet sich ideal für Mitarbeiter, die nur beaufsichtigten Zugriff auf Schüler/Studenten und Vollzugriff auf andere Mitarbeiter und Lehrkräfte haben sollten. Sie können Chats mit allen vollständigen oder eingeschränkten Benutzern beginnen, aber sie können keine Chats mit eingeschränkten Benutzern starten. Wenn ein Benutzer mit vollständigen Berechtigungen einen Chat mit einem eingeschränkten Benutzer beginnt, können eingeschränkte Benutzer in die Unterhaltung mit einberaumt werden. Dieser Zugriff erfolgt, weil ein Benutzer mit vollständigen Berechtigungen vorhanden ist, um die Zusammenarbeit zwischen eingeschränkten und eingeschränkten Benutzern zu überwachen.

- *Eingeschränkte Berechtigungen* – Diese Rolle eignet sich ideal für Kursteilnehmer, die überwacht werden müssen. Sie können nur Chats mit Benutzern starten, die über vollständige Berechtigungen verfügen. Sie können an jeder Unterhaltung teilnehmen, zu der ein Benutzer mit vollständigen Berechtigungen eingeladen wird. In Verbundchatfällen können eingeschränkte Benutzer nur von einem Benutzer mit vollständigen Berechtigungen, der aus dem Mandanten des eingeschränkten Benutzers kommt, zu Chats hinzugefügt werden.

Verwenden Sie zum Festlegen der Chatberechtigungsrolle Ihrer Benutzer die Rollenrichtlinie Chatberechtigungen, die sich in den Optionen für Die Messagingrichtlinie im Teams-Administratorportal befindet.   Sie können PowerShell verwenden, um Rollen mithilfe der ChatPermissionRole-Richtlinie mit den Werten "Voll", "Eingeschränkt" oder "Eingeschränkt" zu definieren. Diese Richtlinie befindet sich unter CsTeamsMessagingPolicy.

Weitere Informationen zum Festlegen. Teams-Richtlinien finden Sie unter Teams-Richtlinien und -Richtlinienpakete für Bildungseinrichtungen und Zuweisen von Richtlinien zu großen Gruppen von Benutzerleitfäden.

Rollen können Gästen in Ihrem Mandanten nicht zugewiesen werden. Gästen wird die eingeschränkte Rolle zugewiesen.

### <a name="allow-supervised-chat"></a>Überwachten Chat zulassen

Überwachter Chat ist für Ihren Mandanten standardmäßig deaktiviert. Nachdem Sie Chatberechtigungsrollen für Ihre Benutzer festgelegt haben, können Sie überwachten Chat innerhalb Ihres Mandanten aktivieren, indem Sie zu **Organisationsweite** Einstellungen Teams-Einstellungen und Festlegen der rollenbasierten Chatberechtigungsrichtlinie &gt;  auf *Ein gehen.*  Sie können powerShell auch verwenden, um überwachten Chat zu aktivieren, indem Sie AllowRoleBasedChatPermissions auf True festlegen. Dieses Cmdlet befindet sich unter CsTeamsClientConfiguration.

Überwachter Chat muss für alle Benutzer im Mandanten aktiviert sein und kann nicht nur für einen Teil ihrer Benutzer aktiviert werden.

### <a name="enable-chat"></a>Chat aktivieren

Aktivieren Sie chatten für alle Benutzer mithilfe der vorhandenen Chatrichtlinie, die im Teams Admin Center verfügbar ist.

## <a name="maintain-supervised-chats"></a>Verwalten überwachter Chats

Nachdem überwachte Chats anfänglich aktiviert wurden, müssen Sie einige Schritte unternehmen, um sicherzustellen, dass die Chats in Ihrer Umgebung überwacht bleiben:

- Weisen Sie allen neuen Benutzern, die Ihrem Mandanten beitreten, geeignete Rollen zu. Standardmäßig wird Benutzern eine eingeschränkte Rolle zugewiesen.

- Wenn ein Benutzer mit vollständigen Berechtigungen einen Mandanten verlässt oder aus diesem entfernt wird, bleiben die von ihm überwachten Chats unbeaufsichtigt. Stellen Sie vor dem Entfernen des ursprünglichen Benutzers sicher, dass diesen Unterhaltungen ein anderer Benutzer mit vollständigen Berechtigungen hinzugefügt wird, damit der Chat überwacht werden kann. Nachdem der ursprüngliche Vorgesetzte entfernt wurde, können der Unterhaltung keine neuen Teilnehmer hinzugefügt werden, aber die aktuellen Teilnehmer können weiterhin kommunizieren.

## <a name="related-topics"></a>Verwandte Themen

[Überwachte Chats für Teams in Ausbildung](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
