---
title: Sicheres Messaging für Organisationen im Gesundheitswesen, die Microsoft Teams verwenden
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erfahren Sie hier, wie Sie eine Richtlinie für sicheres Messaging für Microsoft Teams anpassen können, die Lesebestätigungen und Benachrichtigungen mit hoher Priorität umfassen kann.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05a753873901d3faa4ae3446947c0b791b55c0b4531d9d03adf039a421c2f5a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308754"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Sicheres Messaging für Organisationen im Gesundheitswesen

Messagingrichtlinien werden verwendet, um zu steuern, welche Chat- und Kanalnachrichtenfunktionen für Benutzer in Microsoft Teams verfügbar sind. Sie sind Teil der allgemeinen Bereitstellung von Sicherem Messaging für Organisationen im Gesundheitswesen wie Krankenhäuser, Kliniken oder Arztpraxen, in denen es von entscheidender Bedeutung ist, dass eine Nachricht zeitnah erhalten und darauf reagiert wird, wie auch zu wissen, wann wichtige Nachrichten gelesen wurden.

Sie können die globale (organisationsweite) Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Messagingrichtlinien für die Benutzer in Ihrer Organisation erstellen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, weisen Sie sie einem Benutzer oder Benutzergruppen in Ihrer Organisation zu. Sie können z. B. festlegen, dass nur bestimmte Rollen (z. B. nur Arzt- und Pflegekräfte) diese Features verwenden dürfen und für andere Mitarbeiter (z. B. Hauspersonal und Küchenmitarbeiter) eine eingeschränkte Anzahl von Features verfügbar sind. Entscheiden Sie selbst, welche Anforderungen in Ihrer Organisation erfüllt werden sollen. Die vorliegenden Beispiele sind nur Vorschläge.

Die Richtlinien können auf einfache Weise im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) verwaltet werden: Melden Sie sich mit Administratoranmeldeinformationen an, und wählen Sie im linken Navigationsbereich **Messaging-Richtlinien** aus.

 ![Screenshot der Seite "Messaging-Richtlinien"](../../media/hc-messaging-policy-admin-center.png)

Um die bestehende standardmäßige Messaging-Richtlinie für Ihre Organisation zu bearbeiten, wählen Sie die Zeile **Global (organisationsweit Standard)** aus, und nehmen Sie dann die gewünschten Änderungen vor. Um eine neue benutzerdefinierte Nachrichtenrichtlinie zu erstellen, wählen Sie **Neue Richtlinie** und dann die gewünschten Einstellungen aus. Wenn Sie fertig sind, klicken Sie auf **Speichern**.

![Screenshot der Einstellungen für Messaging-Richtlinien](../../media/hc-messaging-policy.png)

Die folgenden Einstellungen sind für die Anwendung im Gesundheitswesen von besonderem Interesse und sollten beim Entwerfen einer benutzerdefinierten Richtlinie für das Gesundheitswesen berücksichtigt werden:

## <a name="read-receipts"></a>Lesebestätigungen

Durch Lesebestätigungen kann ein Absender einer Chatnachricht benachrichtigt werden, wenn diese vom Empfänger in persönlichen bzw. Gruppenchats mit höchstens 20 Personen gelesen wurde. Legen Sie mithilfe dieser Einstellung fest, ob Lesebestätigungen vom Benutzer gesteuert, für alle Benutzer aktiviert oder für alle Benutzer deaktiviert werden sollen. Lesebestätigungen für Nachrichten sind in Organisationen im Gesundheitswesen wichtig, da dadurch die Unsicherheit beseitigt wird, ob eine Nachricht gelesen wurde.

Wählen Sie für die Anwendung im Gesundheitswesen entweder **Benutzergesteuert** oder **Für alle aktiviert**. Achten Sie darauf, dass bei Verwendung der Einstellung **Für alle aktiviert** die einzige Möglichkeit zum Festlegen von Bestätigungen für den gesamten Mandanten darin besteht, nur eine Messaging-Richtlinie für den gesamten Mandanten zu nutzen (die Standardrichtlinie namens "Global (organisationsweiter Standard)), oder in allen Messaging-Richtlinien im Mandanten dieselben Einstellungen für Bestätigungen festzulegen. Das Feature "Lesebestätigungen" ist am effektivsten, wenn die Option **Für alle aktiviert** ist.

*Beispiel für eine Verwendung ohne Lesebestätigungen:* Jakob Rot, ein Patient mit hohem Risiko, wird aufgenommen.  Sofia Krause ist eine Pflegekraft, die dem interdisziplinären Team von medizinischen Mitarbeitern angehört, zu dem verschiedene Spezialisten zählen. Sie wird als für diesen Patienten zuständige primäre Pflegekraft festgelegt.  Sofia sendet E-Mails und Chatnachrichten an eine Reihe von Pflegekräften und Ärzten, die eine Vielzahl von Nachrichtenclients und Apps nutzen, und erhält häufig keine Antwort oder Hinweise darauf, ob eine Nachricht von Teammitgliedern gelesen wurde. Aufgrund verworrener Kommunikationsprozesse wird Jakob Rots Medikation falsch angewendet, wodurch sich sein Krankenhausaufenthalt verlängert.

*Beispiel für eine Verwendung mit Lesebestätigungen:* Jakob Rot, ein Patient mit hohem Risiko, wird aufgenommen.  Sofia Krause ist eine Pflegekraft, die dem interdisziplinären Team von medizinischen Mitarbeitern angehört, zu dem verschiedene Spezialisten zählen. Sie wird als für diesen Patienten zuständige primäre Pflegekraft festgelegt.  Sofia beginnt einen Gruppenchat mit einer Reihe von Ärzten und Pflegekräften, die den Patienten betreuen werden, um die Pflege zu koordinieren, und startet eine Notfall-Triage.  Pflegekräfte und Ärzte tauschen sich aus und arbeiten während des gesamten Behandlungsplans am Pflegeplan des Patienten zusammen.  Wichtige und dringliche Nachrichten werden über persönliche und Gruppenchats gesendet. Sofia verwendet die Lesebestätigungsfunktion, um zu erfahren, ob Nachrichten mit Unterstützungsanfragen von den empfangenden Ärzten bzw. Pflegekräften empfangen und gelesen wurden. Jakob Rots Behandlungsergebnisse sind fast optimal, und er kann früher nach Hause gehen, weil sein Gesundheitsteam reibungslos kommuniziert.

## <a name="send-urgent-messages-using-priority-notifications"></a>Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden

Beim Senden von Chatnachrichten an andere kann ein Benutzer eine Nachricht als *dringend* kennzeichnen. Dieses Feature hilft Mitarbeitern in Kliniken, sich gegenseitig zu warnen, wenn ein kritischer Vorfall ihre Aufmerksamkeit erfordert. Im Gegensatz zu normalen *wichtigen* Nachrichten informieren [Benachrichtigungen mit hoher Priorität](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) Benutzer alle 2 Minuten für einen Zeitraum von 20 Minuten, oder bis die Nachricht vom Empfänger geöffnet und gelesen wird. Dadurch wird die Wahrscheinlichkeit einer zeitnahen Bearbeitung erhöht.

Ein Administrator kann die Möglichkeit zum Senden von Benachrichtigungen mit hoher Priorität für Benutzer aktivieren oder deaktivieren, denen diese Richtlinie zugewiesen ist. Diese Funktion ist standardmäßig aktiviert. Für den Empfänger einer Nachricht mit hoher Priorität gilt u. U. nicht dieselbe Messaging-Richtlinie, und er hat u. U. keine Möglichkeit, den Empfang solcher Nachrichten zu deaktivieren. Bei der Anwendung im Gesundheitswesen empfehlen wir, das Feature mindestens für einige Benutzer zu aktivieren, die jedoch von Ihnen ermittelt werden müssen.

*Verwendungsbeispiel:* Sofia Krause nimmt einen Patienten mit hohem Risiko, Jakob Rot, erneut auf. Manuela Karsten ist die für diesen Patienten zuständige Ärztin.  Sofia Krause sendet eine Nachricht mittels einer Benachrichtigung mit hoher Priorität an Manuela Karsten mit der Bitte um sofortige Hilfe bei der Triage von Jakob Rot.  Manuela Karsten erhält die Nachricht auf ihrem Smartphone, hat das Vibrieren des Telefons jedoch nicht bemerkt, und antwortet deshalb nicht. Microsoft Teams benachrichtigt Manuela Karsten erneut und wird damit fortfahren, bis sie die Nachricht liest. Wenn auch Lesebestätigungen aktiviert sind, weiß Sofia Krause, dass die Nachricht von Manuela Karsten gelesen wurde, noch bevor Letztere entschieden hat, was sie antworten soll.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Messaging-Richtlinien in Microsoft Teams](../../messaging-policies-in-teams.md)
- [Erste Schritte mit Microsoft Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)
