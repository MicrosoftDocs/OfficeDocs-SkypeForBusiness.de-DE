---
title: Verwenden überwachter Chats für Mandanten ohne Bildungseinrichtung
author: SerdarSoysal
ms.author: serdars
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
description: Informieren Sie sich über überwachte Chats für Mandanten ohne Bildungseinrichtung in Microsoft Teams Besprechungen.
---

# <a name="supervised-chats-for-non-educational-tenants"></a>Überwachen von Chats für Mandanten ohne Bildungseinrichtung

Der überwachte Chat ermöglicht festgelegten Vorgesetzten, Chats mit allen Personen in ihrer Organisation zu initiieren und blockiert das Starten neuer Chats für Benutzer, sofern kein geeigneter Vorgesetzter vorhanden ist. Wenn die Chatüberwachung aktiviert ist, dürfen Die Vorgesetzten keine Chats verlassen, und andere Teilnehmer dürfen sie nicht entfernen, um sicherzustellen, dass Chats mit eingeschränkten Benutzern ordnungsgemäß überwacht werden.

Diese Einschränkungen werden nur auf neue private Chats angewendet, die erstellt werden, nachdem der überwachte Chat vollständig aktiviert wurde. Sie gelten nicht für vorhandene private Chats, Besprechungschats oder Kanäle.

Der überwachte Chat ist auf die Anforderungen von Bildungseinrichtungen zugeschnitten, steht aber auch für Mandanten ohne Bildungseinrichtung zur Verfügung.

> [!NOTE]
> Der überwachte Chat schützt neue Chats, die nach dem Erzwingen des Features erstellt wurden. Vorhandene Chats werden nicht geschützt.

## <a name="enable-supervised-chat"></a>Aktivieren eines überwachten Chats

> [!NOTE]
> Stellen Sie sicher, dass Sie Chatberechtigungsrollen und die rollenbasierten Chat-Berechtigungsrichtlinien einrichten, bevor Sie Chat für Ihre Einrichtung aktivieren, um unerwünschten eingeschränkten Benutzerzugriff auf nicht überwachte Chats zu vermeiden.

**Definieren von Chatberechtigungsrollen für jeden Benutzer in Ihrer Umgebung**

Damit der überwachte Chat wie erwartet funktioniert, muss jedem Benutzer in Ihrer Umgebung die richtige Chatberechtigungsrolle zugewiesen werden. Es gibt drei Rollen, die ein Benutzer zugewiesen haben kann:

- Vollständige Berechtigungen: Diese Rolle sollte den Chat-Supervisorn in Ihrer Umgebung zugewiesen werden. Sie können Chats mit jedem Benutzer in Ihrer Umgebung starten. Von Benutzern mit vollständigen Berechtigungen wird erwartet, dass sie die Chats beaufsichtigen, an den sie teilnehmen. Sie können Chats, die sie starten, oder Chats, die sie in Partnerbenutzern überwacht, nicht verlassen oder aus ihnen entfernen.

- Eingeschränkte Berechtigungen: Diese Rolle eignet sich ideal für Mitarbeiter, die nur eingeschränkten Benutzern zugriffen dürfen. Sie können Chats mit allen oder eingeschränkten Benutzern, aber nicht mit eingeschränkten Benutzern starten. Wenn ein Benutzer mit voll berechtigten Berechtigungen einen Chat mit einem eingeschränkten Benutzer beginnt, können nur eingeschränkte Benutzer zur Unterhaltung teilnehmen. Dieser Zugriff erfolgt, weil ein Benutzer mit vollständigen Berechtigungen anwesend ist, um die Zusammenarbeit zwischen eingeschränkten und eingeschränkten Benutzern zu beaufsichtigen.

- Eingeschränkte Berechtigungen: Diese Rolle eignet sich ideal für Benutzer, die überwacht werden müssen. Sie können nur Chats mit Benutzern starten, die über vollständige Berechtigungen verfügen. Sie können an jeder Unterhaltung teilnehmen, zu der ein Benutzer mit vollständigen Berechtigungen eingeladen wird. In Partnerchat-Fällen können eingeschränkte Benutzer nur von benutzern mit vollständigen Berechtigungen zu Chats hinzugefügt werden, die vom Mandanten des eingeschränkten Benutzers kommen.

Wenn Sie die Chatberechtigungsrolle Ihrer Benutzer festlegen möchten, verwenden Sie die Berechtigungsrichtlinie chatten, die in den Optionen für Messagingrichtlinien im Teams-Verwaltungsportal zu finden ist. Sie können PowerShell verwenden, um Rollen mithilfe der Richtlinie ChatPermissionRole mit den Werten "Full", "Limited" oder "Restricted" zu definieren. Diese Richtlinie befindet sich unter [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).

Rollen können Gäste in Ihrem Mandanten nicht zugewiesen werden. Gästen wird die eingeschränkte Rolle zugewiesen.

## <a name="allow-supervised-chat"></a>Zulassen eines überwachten Chats

Überwachter Chat ist für Ihren Mandanten standardmäßig deaktiviert. Nachdem Sie **Chat-Berechtigungsrollen** für Ihre Benutzer festgelegt haben,  >  können Sie den überwachten Chat innerhalb Ihres Mandanten aktivieren **,** indem Sie zu Organisationsweite Einstellungen Teams Einstellungen und Festlegen der Berechtigungsrichtlinie für rollenbasierte Chats auf Ein **festlegen.** Sie können auch PowerShell verwenden, um den überwachten Chat zu aktivieren, indem Sie AllowRoleBasedChatPermissions auf True festlegen. Dieses Cmdlet befindet sich unter [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).

Überwachter Chat muss für alle Benutzer im Mandanten aktiviert sein und kann nicht nur für einen Teil Ihrer Benutzer aktiviert werden.

**Aktivieren des Chats**

Aktivieren Sie chatten für alle Ihre Benutzer, indem Sie die im Admin Center Teams Chat-Richtlinie verwenden.

**Beibehalten überwachter Chats**

Nachdem der überwachte Chat aktiviert wurde, müssen Sie einige Schritte unternehmen, um sicherzustellen, dass die Chats in Ihrer Umgebung überwacht bleiben:

- Weisen Sie allen neuen Benutzern, die Ihrem Mandanten beitreten, die entsprechenden Rollen zu. Standardmäßig wird Benutzern eine eingeschränkte Rolle zugewiesen.

- Wenn ein Benutzer mit vollständigen Berechtigungen einen Mandanten verlässt oder aus ihm entfernt wird, bleiben die von ihm überwachten Chats unbeaufsichtigt. Bevor Sie den ursprünglichen Benutzer entfernen, stellen Sie sicher, dass diesen Unterhaltungen ein anderer Benutzer mit vollständigen Berechtigungen hinzugefügt wird, damit der Chat überwacht bleiben kann. Nachdem der ursprüngliche Vorgesetzte entfernt wurde, können neue Teilnehmer der Unterhaltung nicht mehr hinzugefügt werden, aktuelle Teilnehmer können jedoch weiterhin kommunizieren.
