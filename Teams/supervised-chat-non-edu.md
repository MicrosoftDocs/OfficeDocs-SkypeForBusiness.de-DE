---
title: Verwenden von beaufsichtigten Chats für Nicht-Bildungsmandanten
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Erfahren Sie mehr über überwachte Chats für Nicht-Bildungsmandanten in Microsoft Teams-Besprechungen.
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6f499845f77ededf47fa907961624081197b65b1
ms.sourcegitcommit: 2d873e774c1a1182326e22e5de6ee5df4d50f41e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2022
ms.locfileid: "67446768"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Überwachte Chats für Nicht-Bildungsmandanten

Beaufsichtigter Chat ermöglicht es designierten Aufsichtspersonen, Chats mit beliebigen Personen in ihrer Organisation zu initiieren, und sperrt eingeschränkte Benutzer daran, neue Chats zu starten, es sei denn, ein geeigneter Vorgesetzter ist anwesend. Wenn die Chatüberwachung aktiviert ist, dürfen Aufsichtspersonen Chats nicht verlassen, und andere Teilnehmer dürfen sie nicht entfernen, um sicherzustellen, dass Chats, an denen eingeschränkte Benutzer beteiligt sind, ordnungsgemäß überwacht werden.

Diese Einschränkungen gelten nur für neue private Chats, die erstellt werden, nachdem der überwachte Chat vollständig aktiviert wurde. Sie gelten nicht für vorhandene private Chats, Besprechungschats oder Kanäle.

Der überwachte Chat ist auf die Anforderungen von Bildungseinrichtungen zugeschnitten, steht aber auch für Nicht-Bildungsmandanten zur Verfügung.

> [!NOTE]
> Der überwachte Chat schützt neue Chats, die nach der Durchsetzung des Features erstellt wurden. Vorhandene Chats werden nicht geschützt.

## <a name="enable-supervised-chat"></a>Aktivieren des überwachten Chats

> [!NOTE]
> Stellen Sie sicher, dass Sie Chatberechtigungsrollen und die rollenbasierten Chatberechtigungsrichtlinien einrichten, bevor Sie den Chat für Ihre Einrichtung aktivieren, um unerwünschten eingeschränkten Benutzerzugriff auf nicht überwachte Chats zu vermeiden.

**Definieren Sie Chatberechtigungsrollen für jeden Benutzer in Ihrer Umgebung**:

Damit der überwachte Chat erwartungsgemäß funktioniert, muss jedem Benutzer in Ihrer Umgebung die richtige Chatberechtigungsrolle zugewiesen werden. Es gibt drei Rollen, die einem Benutzer zugewiesen werden können:

- Vollständige Berechtigungen: Diese Rolle sollte den Chatverantwortlichen in Ihrer Umgebung zugewiesen werden. Sie können Chats mit jedem Benutzer in Ihrer Umgebung starten. Benutzer mit vollständigen Berechtigungen werden erwartet, dass sie die Chats überwachen, an denen sie teilnehmen. Sie können Chats, die sie starten, oder Chats, die sie in Verbundmandanten überwachen, nicht verlassen oder daraus entfernt werden.

- Eingeschränkte Berechtigungen: Diese Rolle eignet sich ideal für Mitarbeiter, die nur überwachten Zugriff auf eingeschränkte Benutzer haben sollten. Sie können Chats mit allen vollständigen oder eingeschränkten Benutzern starten, aber keine Chats mit eingeschränkten Benutzern starten. Wenn ein Benutzer mit vollständigen Berechtigungen einen Chat mit einem eingeschränkten Benutzer beginnt, können eingeschränkte Benutzer in die Unterhaltung gebracht werden. Dieser Zugriff geschieht, weil ein Benutzer mit vollständigen Berechtigungen anwesend ist, um die Zusammenarbeit zwischen eingeschränkten und eingeschränkten Benutzern zu überwachen.

- Eingeschränkte Berechtigungen: Diese Rolle eignet sich ideal für Benutzer, die überwacht werden müssen. Sie können nur Chats mit Benutzern starten, die über vollständige Berechtigungen verfügen. Sie können an jeder Unterhaltung teilnehmen, zu der ein Benutzer mit vollständigen Berechtigungen eingeladen wird. In Verbundchatfällen können eingeschränkte Benutzer nur von einem Benutzer mit vollständigen Berechtigungen, der aus dem Mandanten des eingeschränkten Benutzers stammt, zu Chats hinzugefügt werden.

Verwenden Sie zum Festlegen der Chatberechtigungsrolle Ihrer Benutzer die **Chatberechtigungsrollenrichtlinie** , die Sie in Ihren Messaging-Richtlinienoptionen im Teams-Administratorportal finden. Sie können PowerShell verwenden, um Rollen mithilfe der ChatPermissionRole-Richtlinie mit den Werten "Full", "Limited" oder "Restricted" zu definieren. Diese Richtlinie befindet sich unter ["CsTeamsMessagingPolicy"](/powershell/module/skype/set-csteamsmessagingpolicy).

Rollen können Gästen in Ihrem Mandanten nicht zugewiesen werden. Gästen wird die eingeschränkte Rolle zugewiesen.

## <a name="allow-supervised-chat"></a>Beaufsichtigten Chat zulassen

Der überwachte Chat ist für Ihren Mandanten standardmäßig deaktiviert. Nachdem Sie Chatberechtigungsrollen für Ihre Benutzer festgelegt haben, können Sie den überwachten Chat in Ihrem Mandanten aktivieren, indem Sie zu **Teams** \> **Teams-Einstellungen** wechseln und die Richtlinien für **rollenbasierte Chatberechtigungen** auf **"Ein**" festlegen. Sie können powerShell auch verwenden, um den überwachten Chat zu aktivieren, indem Sie AllowRoleBasedChatPermissions auf "True" festlegen. Dieses Cmdlet befindet sich unter ["CsTeamsClientConfiguration"](/powershell/module/skype/set-csteamsclientconfiguration).

Der überwachte Chat muss für alle Benutzer im Mandanten aktiviert sein und kann nicht nur für einen Teil Ihrer Benutzer aktiviert werden.

**Chat aktivieren**:

Aktivieren Sie den Chat für alle Ihre Benutzer mithilfe der vorhandenen Chatrichtlinie, die im Teams Admin Center verfügbar ist.

**Verwalten von überwachten Chats**:

Nachdem der überwachte Chat anfänglich aktiviert wurde, müssen Sie einige Schritte ausführen, um sicherzustellen, dass die Chats in Ihrer Umgebung überwacht werden:

- Weisen Sie allen neuen Benutzern, die Ihrem Mandanten beitreten, die entsprechenden Rollen zu. Benutzern wird standardmäßig eine eingeschränkte Rolle zugewiesen.

- Wenn ein Benutzer mit vollständigen Berechtigungen einen Mandanten verlässt oder daraus entfernt wird, bleiben die Chats, die er beaufsichtigt hat, unbeaufsichtigt. Bevor Sie den ursprünglichen Benutzer entfernen, stellen Sie sicher, dass diesen Unterhaltungen ein anderer Benutzer mit vollständigen Berechtigungen hinzugefügt wird, damit der Chat überwacht bleiben kann. Nachdem der ursprüngliche Vorgesetzte entfernt wurde, können neue Teilnehmer nicht mehr zur Unterhaltung hinzugefügt werden, aber die aktuellen Teilnehmer können weiterhin kommunizieren.
