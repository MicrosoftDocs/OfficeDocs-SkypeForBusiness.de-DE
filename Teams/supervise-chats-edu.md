---
title: Verwenden von überwachten Chats
author: DaniEASmith
ms.author: danismith
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
description: Erfahren Sie mehr über überwachte Chats in Microsoft Teams-Besprechungen.
ms.collection:
- M365-collaboration
ms.openlocfilehash: 5cee0678e48a0fcdeb340b90e95981c3b1759f83
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271470"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Überwachte Chats in Microsoft Teams

Bildungseinrichtungen bieten Studierenden einen sicheren und gesunden digitalen Raum. Der digitale Raum umfasst E-Mails, Onlinebesprechungen und Anrufe sowie Nachrichten in Teams. Um unangemessenes Messagingverhalten zu verhindern, deaktivieren viele Schulen den privaten Chat in Teams. Leider blockiert das Deaktivieren des Chats auch die Möglichkeit für Lehrkräfte, sich privat an Schüler zu wenden, um personalisiertes Lernen zu ermöglichen. Wenn der Chat deaktiviert ist, können die Schüler/Studenten lehrer nicht erreichen, wenn sie es vorziehen, die Nachrichten nicht öffentlich in Kursteams zu posten.

Beaufsichtigter Chat ermöglicht es bestimmten Lehrkräften, Chats mit Kursteilnehmern zu initiieren, und blockiert Die Kursteilnehmer daran, neue Chats zu starten, es sei denn, eine entsprechende Lehrkraft ist vorhanden. Wenn die Chatüberwachung aktiviert ist, dürfen Aufsichtspersonen Chats nicht verlassen, und andere Teilnehmer dürfen sie nicht entfernen, um sicherzustellen, dass Chats, an denen Schüler beteiligt sind, ordnungsgemäß überwacht werden.

Diese Einschränkungen gelten nur für neue private Chats, die erstellt werden, nachdem der überwachte Chat vollständig aktiviert wurde. Sie gelten nicht für vorhandene private Chats, Besprechungschats oder Kanäle. Weitere Informationen zu bewährten Methoden für Besprechungschats, Kanalsicherheit und Die Sicherheit von Kursteilnehmern finden Sie unter ["Schützen von Kursteilnehmern während der Verwendung von Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)".

> [!Note]
> Der überwachte Chat schützt neue Chats, die nach der Durchsetzung des Features erstellt wurden.  Vorhandene Chats werden nicht geschützt.

## <a name="review-use-cases-for-supervised-chats"></a>Überprüfen von Anwendungsfällen für überwachte Chats

Die folgenden Beispiele sind Beschreibungen, wann ein überwachter Chat erforderlich ist.

- Eine 1.1-Nachbereitung mit einem Dozenten, wenn Die Schüler/Studenten sich nicht damit vertraut machen, öffentlich Fragen zu stellen oder freizugeben.

- Lehrkräfte erreichen 1.1 an einen Kursteilnehmer über eine Aufgabe, kürzliche Kursinteraktion (oder fehlendes) oder anderes Thema.

- Diskussionen zu Schülergruppen, die von einer Lehrkraft überwacht werden.

- Zulassen, dass Nicht-Lehrpersonal in einer beaufsichtigten Umgebung mit Kursteilnehmern chatten kann.

## <a name="enable-supervised-chat"></a>Aktivieren des überwachten Chats

> [!Note]
> Stellen Sie sicher, dass Sie Chatberechtigungsrollen und die rollenbasierten Chatberechtigungsrichtlinien einrichten, bevor Sie den Chat für Ihre Bildungseinrichtung aktivieren, um unerwünschten Schülerzugriff auf nicht überwachte Chats zu vermeiden.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definieren von Chatberechtigungsrollen für jeden Benutzer in Ihrer Umgebung

Damit der überwachte Chat erwartungsgemäß funktioniert, muss jedem Benutzer in Ihrer Umgebung die richtige Chatberechtigungsrolle zugewiesen werden. Es gibt drei Rollen, die einem Benutzer zugewiesen werden können:

- *Vollständige Berechtigungen* – Diese Rolle ist ideal für Lehrkräfte, die vollzugriff auf Schüler/Studenten und andere Mitarbeiter haben sollten. Sie können Chats mit jedem Benutzer in Ihrer Umgebung starten. Benutzer mit vollständigen Berechtigungen werden erwartet, dass sie die Chats überwachen, an denen sie teilnehmen. Sie können Chats, die sie starten, oder Chats, die sie in Verbundmandanten überwachen, nicht verlassen oder daraus entfernt werden.

- *Eingeschränkte Berechtigungen* – Diese Rolle ist ideal für Mitarbeiter, die nur überwachten Zugriff auf Schüler/Studenten und vollumfänglichen Zugriff auf andere Mitarbeiter und Lehrkräfte haben sollten. Sie können Chats mit allen vollständigen oder eingeschränkten Benutzern starten, aber keine Chats mit eingeschränkten Benutzern starten. Wenn ein Benutzer mit vollständigen Berechtigungen einen Chat mit einem eingeschränkten Benutzer beginnt, können eingeschränkte Benutzer in die Unterhaltung gebracht werden. Dieser Zugriff geschieht, weil ein Benutzer mit vollständigen Berechtigungen anwesend ist, um die Zusammenarbeit zwischen eingeschränkten und eingeschränkten Benutzern zu überwachen.

- *Eingeschränkte Berechtigungen* – Diese Rolle ist ideal für Schüler/Studenten, die überwacht werden müssen. Sie können nur Chats mit Benutzern starten, die über vollständige Berechtigungen verfügen. Sie können an allen Unterhaltungen teilnehmen, zu denen ein Benutzer mit vollständigen Berechtigungen beginnt und zu der er dann eingeladen wird. In Verbundchatfällen können eingeschränkte Benutzer nur von einem Benutzer mit vollständigen Berechtigungen, der aus dem Mandanten des eingeschränkten Benutzers stammt, zu Chats hinzugefügt werden.

Verwenden Sie zum Festlegen der Chatberechtigungsrolle Ihrer Benutzer die  **Chatberechtigungsrollenrichtlinie**, die Sie in Ihren Messaging-Richtlinienoptionen im Teams-Administratorportal finden. Sie können PowerShell verwenden, um Rollen mithilfe der ChatPermissionRole-Richtlinie mit den Werten "Full", "Limited" oder "Restricted" zu definieren. Diese Richtlinie befindet sich unter "CsTeamsMessagingPolicy".

Weitere Informationen zum Festlegen. Teams-Richtlinien sehen Teams-Richtlinien und Richtlinienpakete für Bildungseinrichtungen und Zuweisen von Richtlinien zu großen Gruppen von Benutzerhandbüchern.

Rollen können Gästen in Ihrem Mandanten nicht zugewiesen werden. Gästen wird die eingeschränkte Rolle zugewiesen.

### <a name="allow-supervised-chat"></a>Beaufsichtigten Chat zulassen

Der überwachte Chat ist für Ihren Mandanten standardmäßig deaktiviert. Nachdem Sie Chatberechtigungsrollen für Ihre Benutzer festgelegt haben, können Sie den überwachten Chat in Ihrem Mandanten aktivieren, indem Sie zu **den** **Teams-Teams-Einstellungen** &gt; wechseln und die Richtlinien für **rollenbasierte Chatberechtigungen** auf *"Ein*" festlegen. Sie können powerShell auch verwenden, um den überwachten Chat zu aktivieren, indem Sie AllowRoleBasedChatPermissions auf "True" festlegen. Dieses Cmdlet befindet sich unter "CsTeamsClientConfiguration".

Der überwachte Chat muss für alle Benutzer im Mandanten aktiviert sein und kann nicht nur für einen Teil Ihrer Benutzer aktiviert werden.

### <a name="enable-chat"></a>Chat aktivieren

Aktivieren Sie den Chat für alle Ihre Benutzer mithilfe der vorhandenen Chatrichtlinie, die im Teams Admin Center verfügbar ist.

## <a name="maintain-supervised-chats"></a>Verwalten von überwachten Chats

Nachdem der überwachte Chat anfänglich aktiviert wurde, müssen Sie einige Schritte ausführen, um sicherzustellen, dass die Chats in Ihrer Umgebung überwacht werden:

- Weisen Sie allen neuen Benutzern, die Ihrem Mandanten beitreten, die entsprechenden Rollen zu. Benutzern wird standardmäßig eine eingeschränkte Rolle zugewiesen.

- Wenn ein Benutzer mit vollständigen Berechtigungen einen Mandanten verlässt oder daraus entfernt wird, bleiben die Chats, die er beaufsichtigt hat, unbeaufsichtigt. Bevor Sie den ursprünglichen Benutzer entfernen, stellen Sie sicher, dass diesen Unterhaltungen ein anderer Benutzer mit vollständigen Berechtigungen hinzugefügt wird, damit der Chat überwacht bleiben kann. Nachdem der ursprüngliche Vorgesetzte entfernt wurde, können neue Teilnehmer nicht mehr zur Unterhaltung hinzugefügt werden, aber die aktuellen Teilnehmer können weiterhin kommunizieren.

## <a name="related-topics"></a>Verwandte Themen

[Überwachte Chats für Teams in Bildungseinrichtungen](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
