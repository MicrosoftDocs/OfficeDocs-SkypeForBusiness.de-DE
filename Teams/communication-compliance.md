---
title: Kommunikationscompliance mit Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informationen zur Kommunikationscompliance, Teil des Insider-Risikolösungssatzes, aus der Sicht von Microsoft Teams (dies ist Teil der M365-Kommunikationscompliance-Funktionalität).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01b51694b22d44ace9980f2b98fdb89a9150a12d
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240744"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Kommunikationscompliance mit Microsoft Teams

Microsoft Purview-Kommunikationscompliance ist eine Insider-Risikolösung in Microsoft 365, die Ihnen hilft, Kommunikationsrisiken zu minimieren, indem Sie unangemessene Nachrichten in Ihrer Organisation erkennen, erfassen und darauf reagieren können.

Für Microsoft Teams hilft die Kommunikationscompliance dabei, die [folgenden Arten](/microsoft-365/compliance/communication-compliance-feature-reference) unangemessener Inhalte in Teams-Kanälen, privaten Teams-Kanälen oder in 1:1- und Gruppenchats zu identifizieren:

- Anstößige, profane und belästigende Sprache
- Erwachsene, rassige und gory Bilder
- Freigabe vertraulicher Informationen

Weitere Informationen zur Kommunikationscompliance und zum Konfigurieren von Richtlinien für Ihre Organisation finden [Sie unter "Informationen zur Kommunikationscompliance"](/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Verwenden der Kommunikationscompliance in Microsoft Teams

Kommunikationscompliance und Microsoft Teams sind eng integriert und können dazu beitragen, Kommunikationsrisiken in Ihrer Organisation zu minimieren. Nachdem Sie Ihre ersten Richtlinien für die Kommunikationscompliance konfiguriert haben, können Sie unangemessene Microsoft Teams-Nachrichten und -Inhalte, die automatisch in Warnungen gekennzeichnet werden, aktiv verwalten.

### <a name="getting-started"></a>Erste Schritte

Die ersten Schritte mit der Kommunikationscompliance in Microsoft Teams beginnen mit der [Planung](/microsoft-365/compliance/communication-compliance-plan) und Erstellung vordefinierter oder benutzerdefinierter Richtlinien, um unangemessene Benutzeraktivitäten in Teams-Kanälen oder in 1:1- und Gruppen zu identifizieren. Denken Sie daran, dass Sie im Rahmen des Konfigurationsprozesses einige Berechtigungen und grundlegende Voraussetzungen [konfigurieren](/microsoft-365/compliance/communication-compliance-configure) müssen.

Teams-Administratoren können Kommunikationscompliancerichtlinien auf den folgenden Ebenen konfigurieren:

- **Benutzerebene**: Richtlinien auf dieser Ebene gelten für einen einzelnen Teams-Benutzer oder können auf alle Teams-Benutzer in Ihrer Organisation angewendet werden. Diese Richtlinien decken Nachrichten ab, die diese Benutzer möglicherweise in 1:1- oder Gruppenchats senden. Die Chatkommunikation für die Benutzer wird automatisch in allen Microsoft Teams überwacht, in denen die Benutzer Mitglied sind.
- **Teams-Ebene**: Richtlinien auf dieser Ebene gelten für einen Microsoft Teams-Kanal, einschließlich eines privaten Kanals. Diese Richtlinien decken nur Nachrichten ab, die im Teams-Kanal gesendet werden.

### <a name="report-a-concern-in-microsoft-teams"></a>Melden eines Anliegens in Microsoft Teams

>[!NOTE]
>Die Verfügbarkeit von vom Benutzer gemeldeten Nachrichten für Organisationen, die lizenziert sind und [Kommunikationscompliance](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) verwenden, und Microsoft Teams begann im Mai 2022. Dieses Feature wird bis zum 31. August 2022 für alle Organisationen verfügbar sein, die bis Juli 2022 lizenziert sind und kommunikationscompliance verwenden. Für Organisationen, die nach Juli 2022 mit der Verwendung der Kommunikationscompliance beginnen, kann die Verfügbarkeit von vom Benutzer gemeldeten Nachrichtenrichtlinien bis zu 30 Tage ab dem Datum der Lizenzierung und der ersten Verwendung der Kommunikationscompliance dauern.

Die Option *"Bedenken melden* " in internen Teams-Chatnachrichten ist standardmäßig aktiviert und kann über Teams-Messagingrichtlinien im [Teams Admin Center](/microsoftteams/manage-teams-in-modern-portal) gesteuert werden. Auf diese Weise können Benutzer in Ihrer Organisation unangemessene interne Chatnachrichten zur Überprüfung durch Kommunikationscomplianceprüfer für die Richtlinie übermitteln. Weitere Informationen zu vom Benutzer gemeldeten Nachrichten in der Kommunikationscompliance finden Sie unter [Kommunikationscompliancerichtlinien](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Melden eines Menüs "Bedenken".](./media/communication-compliance-report-a-concern-full-menu.png)

Nachdem die Nachricht zur Überprüfung übermittelt wurde, erhält der Benutzer eine Bestätigung der Übermittlung in Microsoft Teams. Anderen Teilnehmern des Chats wird diese Benachrichtigung nicht angezeigt.

![Melden Sie eine Bestätigung des Anliegens.](./media/communication-compliance-report-a-concern.png)

Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Bearbeiten Sie die Einstellungen in der globalen Richtlinie, oder erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien zu, um dieses Feature zu aktivieren oder zu deaktivieren. Weitere Informationen finden Sie unter [Verwalten von Messagingrichtlinien in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Reagieren auf unangemessene Nachrichten in Microsoft Teams

Nachdem Sie Ihre Richtlinien konfiguriert und Benachrichtigungen zur Kommunikationscompliance für Microsoft Teams-Nachrichten erhalten haben, ist es an der Zeit, dass Complianceprüfer in Ihrer Organisation auf diese Nachrichten reagieren. Dies schließt auch vom Benutzer gemeldete Nachrichten ein, wenn sie für Ihre Organisation aktiviert sind. Prüfer können Ihre Organisation schützen, indem sie Warnungen zur Kommunikationscompliance überprüfen und gekennzeichnete Nachrichten aus der Ansicht in Microsoft Teams entfernen.

![Entfernen einer Nachricht in Teams.](./media/communication-compliance-remove-teams-message.png)

Entfernte Nachrichten und Inhalte werden durch Benachrichtigungen für Benutzer ersetzt, die erklären, dass die Nachricht oder der Inhalt entfernt wurde und welche Richtlinie auf das Entfernen anwendbar ist. Der Absender der entfernten Nachricht oder des entfernten Inhalts wird auch über den Entfernungsstatus benachrichtigt und mit dem ursprünglichen Nachrichteninhalt für den Kontext im Zusammenhang mit seiner Entfernung bereitgestellt. Der Absender kann auch die spezifische Richtlinienbedingung anzeigen, die für das Entfernen von Nachrichten gilt.

Beispiel für einen Richtlinientipp, der vom Absender angezeigt wird:

![Richtlinientipp für Absender.](./media/communication-compliance-warning-1.png)

Beispiel für eine Richtlinienbenachrichtigung, die vom Absender angezeigt wird:

![Richtlinienbedingungsinformationen für Absender.](./media/communication-compliance-warning-2.png)

Beispiel für einen Richtlinientipp, der vom Empfänger angezeigt wird:

![Richtlinientipp für Empfänger.](./media/communication-compliance-warning-3.png)