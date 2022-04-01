---
title: Kommunikationskonformität mit Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Learning zur Kommunikationskonformität, die Teil der Insider-Risikolösungslösung ist, aus der Perspektive Microsoft Teams (dies ist Teil der M365 Communication Compliance-Funktionalität).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33a2f72307b82fa4264f264e0f98a4d0aed45ae4
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592840"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Kommunikationskonformität mit Microsoft Teams

Kommunikationskonformität ist eine Insider-Risikolösung in Microsoft 365, die Ihnen hilft, Kommunikationsrisiken zu minimieren, indem Sie unsachgemäße Nachrichten in Ihrer Organisation erkennen, erfassen und auf diese Weise agieren können.

Im Microsoft Teams hilft Kommunikationskonformität dabei, die folgenden [](/microsoft-365/compliance/communication-compliance-feature-reference) Arten unangemessener Inhalte in Teams-Kanälen, privaten Teams-Kanälen oder 1:1- und Gruppenchats zu identifizieren:

- Anstößige, anstößige und beleidigende Sprache
- Bilder für Erwachsene, Racy und Gory
- Freigeben vertraulicher Informationen

Weitere Informationen zur Kommunikationskonformität und zum Konfigurieren von Richtlinien für Ihre Organisation finden Sie unter Kommunikationskonformität [in Microsoft 365](/microsoft-365/compliance/communication-compliance). Informationen zu Abonnements Microsoft 365 die Kommunikationskonformität enthalten, finden Sie unter [Insider-Risikolösungen](/microsoft-365/compliance/insider-risk-solution-overview#communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Verwenden von Kommunikationskonformität in Microsoft Teams

Kommunikationskonformität und Microsoft Teams sind eng integriert und können dazu beitragen, Kommunikationsrisiken in Ihrer Organisation zu minimieren. Nachdem Sie Ihre ersten Richtlinien für Kommunikationskonformität konfiguriert haben, können Sie unangemessene Nachrichten Microsoft Teams und Inhalte aktiv verwalten, die automatisch in Benachrichtigungen gekennzeichnet werden.

### <a name="getting-started"></a>Erste Schritte

Die ersten Schritte mit Kommunikationskonformität in Microsoft Teams beginnen mit [](/microsoft-365/compliance/communication-compliance-plan) der Planung und Erstellung vordefinierter oder benutzerdefinierter Richtlinien zur Identifizierung unangemessener Benutzeraktivitäten in Teams-Kanälen oder in 1:1- und Gruppen. Denken Sie daran, dass Sie im [Rahmen](/microsoft-365/compliance/communication-compliance-configure) des Konfigurationsprozesses einige Berechtigungen und grundlegende Voraussetzungen konfigurieren müssen.

Teams Administratoren können Richtlinien zur Kommunikationskonformität auf den folgenden Ebenen konfigurieren:

- **Benutzerebene**: Richtlinien auf dieser Ebene gelten für einen einzelnen Teams Benutzer oder können auf alle Benutzer Teams in Ihrer Organisation angewendet werden. Diese Richtlinien umfassen Nachrichten, die diese Benutzer in 1:1- oder Gruppenchats senden können. Die Chatkommunikation für die Benutzer wird automatisch auf allen Microsoft Teams, in denen die Benutzer Mitglied sind, überwacht.
- **Teams**: Richtlinien auf dieser Ebene gelten für einen Microsoft Teams Kanal, einschließlich eines privaten Kanals. Diese Richtlinien decken nur Nachrichten ab, die nur in Teams Kanal gesendet werden.

### <a name="report-a-concern-in-microsoft-teams"></a>Melden von Bedenken in Microsoft Teams

Die *Option "* Bedenken melden" in Teams-Nachrichten ist standardmäßig aktiviert und kann über Teams Messaging-Richtlinien im [Teams Admin Center gesteuert werden](/microsoftteams/manage-teams-in-modern-portal). Dadurch können die Benutzer in Ihrer Organisation unangemessene Nachrichten zur Überprüfung durch Die Prüfer der Kommunikationskonformität für die Richtlinie übermitteln. Weitere Informationen zu Nachrichten, die von Benutzern gemeldet werden, in Der Compliance für Kommunikationen finden Sie unter [Richtlinien zur Kommunikationskonformität](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Bericht über das Menü "Bedenken"](./media/communication-compliance-report-a-concern-full-menu.png)

Nach dem Übermitteln der Nachricht zur Überprüfung erhält der Benutzer eine Bestätigung des Absendens im Microsoft Teams. Diese Benachrichtigung wird anderen Teilnehmern des Chats nicht angezeigt.

![Melden Sie die Bestätigung eines Problem.](./media/communication-compliance-report-a-concern.png)

Die Benutzer in Ihrer Organisation erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Bearbeiten Sie die Einstellungen in der globalen Richtlinie, oder erstellen und weisen Sie mindestens eine benutzerdefinierte Richtlinie zu, um dieses Feature zu aktivieren oder zu deaktivieren. Weitere Informationen finden Sie unter [Verwalten von Messagingrichtlinien in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Unangemessene Nachrichten in Microsoft Teams

Nachdem Sie Ihre Richtlinien konfiguriert und Kommunikations-Compliance-Benachrichtigungen für Microsoft Teams-Nachrichten erhalten haben, ist es an der Zeit, dass Complianceprüfer in Ihrer Organisation auf diese Nachrichten reagieren. Dies umfasst auch Nachrichten, die Benutzer gemeldet haben, wenn diese für Ihre Organisation aktiviert sind. Prüfer können zum Schutz Ihrer Organisation beitragen, indem sie Kommunikations-Compliance-Benachrichtigungen überprüfen und gekennzeichnete Nachrichten aus der Ansicht in Microsoft Teams.

![Entfernen Sie eine Nachricht in Teams.](./media/communication-compliance-remove-teams-message.png)

Entfernte Nachrichten und Inhalte werden durch Benachrichtigungen für Anzeigende ersetzt, die erläutern, dass die Nachricht oder der Inhalt entfernt wurde und welche Richtlinie für das Entfernen gilt. Der Absender der entfernten Nachricht oder des entfernten Inhalts wird ebenfalls über den Bzw. die Entfernungsstatus benachrichtigt und mit dem ursprünglichen Nachrichteninhalt für den Kontext im Zusammenhang mit dem Entfernen bereitgestellt. Der Absender kann auch die spezielle Richtlinienbedingung anzeigen, die für das Entfernen von Nachrichten gilt.

Beispiel für Richtlinientipp des Absenders:

![Richtlinientipp für Absender.](./media/communication-compliance-warning-1.png)

Beispiel für richtlinienbenachrichtigung des Absenders:

![Richtlinienbedingungsinformationen für Absender.](./media/communication-compliance-warning-2.png)

Beispiel für einen Richtlinientipp des Empfängers:

![Richtlinientipp für Empfänger.](./media/communication-compliance-warning-3.png)