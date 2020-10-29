---
title: Sicheres Messaging für Organisationen des Gesundheitswesens mit Microsoft Teams
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
description: Hier erfahren Sie, wie Sie eine Richtlinie für sichere Nachrichten für Microsoft Teams anpassen, die Lesebestätigungen und Prioritäts Benachrichtigungen enthalten kann.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790627"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Sicheres Messaging für Organisationen im Gesundheitswesen

Nachrichtenrichtlinien werden verwendet, um zu steuern, welche Chat-und Kanal-Messaging Features für Benutzer in Microsoft Teams zur Verfügung stehen, und sind Teil der allgemeinen Bereitstellung von Secure Messaging für Organisationen im Gesundheitswesen wie Krankenhäuser, Kliniken oder Arztpraxen, in denen es entscheidend ist, wenn eine Nachricht aufgenommen und rechtzeitig bearbeitet wird, da Sie wissen, wann wichtige Nachrichten gelesen werden.

Sie können die Global (org-Wide Standard)-Richtlinie verwenden oder eine oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, weisen Sie Ihr einen Benutzer oder Gruppen von Benutzern in Ihrer Organisation zu. So können Sie beispielsweise festlegen, dass Sie nur bestimmten Aufgaben Rollen die Verwendung dieser Funktionen (vielleicht nur von Ärzten und Krankenschwestern) und anderen Mitarbeitern (wie dem Hausmeister oder Küchenpersonal) erlauben, um eine begrenzte Anzahl von Funktionen zu erhalten. Entscheiden Sie selbst, was Ihre Organisation braucht, die Anleitung hier ist höchstens ein Vorschlag.

Richtlinien können im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) einfach verwaltet werden, indem Sie sich mit Administratoranmeldeinformationen anmelden und im linken Navigationsbereich **Messaging Richtlinien** auswählen.

 ![Screenshot der Seite "Messaging Richtlinien"](../../media/hc-messaging-policy-admin-center.png)

Wenn Sie die vorhandene Standard-Messaging Richtlinie für Ihre Organisation bearbeiten möchten, klicken Sie auf **Global (org-Wide Standard)** , und nehmen Sie dann die gewünschten Änderungen vor. Wenn Sie eine neue benutzerdefinierte Nachrichten Richtlinie erstellen möchten, klicken Sie auf **Hinzufügen** , und wählen Sie dann Ihre Einstellungen aus. Wenn Sie fertig sind, wählen Sie **Speichern** aus.

![Screenshot der Nachrichtenrichtlinien Einstellungen](../../media/hc-messaging-policy.png)

Die folgenden Einstellungen sind für medizinische Anwendungen von besonderem Interesse und sollten beim Entwerfen einer benutzerdefinierten Richtlinie berücksichtigt werden, die im Feld "Gesundheitswesen" verwendet wird:

## <a name="read-receipts"></a>Lesebestätigungen

Lesebestätigungen können dem Absender einer Chatnachricht mitteilen, wann Ihre Nachricht vom Empfänger in 1:1 gelesen wurde, und Gruppen-Chats mit mindestens 20 Personen. Verwenden Sie diese Einstellung, um anzugeben, ob Lesebestätigungen vom Benutzer gesteuert werden, für jeden aktiviert oder für jeden deaktiviert sind. Lesebestätigungen für Nachrichten sind in Organisationen des Gesundheitswesens wichtig, da Sie ungewiss darüber entscheiden, ob eine Nachricht gelesen wurde.

Wählen Sie für Anwendungen im Gesundheitswesen entweder **Benutzer gesteuert** oder **ein für alle** aus. Beachten Sie, dass die einzige Möglichkeit zum Festlegen der Belege für den gesamten Mandanten bei Verwendung der Einstellung **für alle** für den gesamten Mandanten nur eine Messagingrichtlinie (die Standardrichtlinie mit dem Namen "Global (org-Wide Standard)") oder die Verwendung der gleichen Einstellungen für die Empfangsbestätigungen für alle Messagingrichtlinien im Mandanten ist. Das Feature „Lesebestätigungen“ ist am effektivsten, wenn das Feature **für alle aktiviert** ist.

*Verwendungsbeispiel ohne Lesebestätigungen:* Jakob Roth, ein Patient mit einem Höchstrisiko, wird zum Krankenhaus zugelassen.  Sofia Krause ist eine Krankenschwester, die als Teil des interdisziplinären Teams (IDT) von medizinischen Arbeitern, darunter verschiedene Spezialisten, als primärer Betreuer für diesen Patienten verantwortlich ist.  Sofia sendet e-Mails und andere Sofortnachrichten an eine Gruppe von Krankenschwestern und Ärzten, die eine Vielzahl von Messaging-Clients und-Apps verwenden, und erhält oft keine Antwort oder gibt an, ob eine Nachricht von Teammitgliedern gelesen wurde. Aufgrund von verworrenen Kommunikationsprozessen wird Jakobs Medikamenten nicht mehr verwendet und sein Krankenhausaufenthalt verlängert.

*Verwendungsbeispiel mit Lesebestätigungen:* Jakob Roth, ein Patient mit einem Höchstrisiko, wird zum Krankenhaus zugelassen.  Sofia Krause ist eine Krankenschwester, die als Teil des interdisziplinären Teams (IDT) von medizinischen Arbeitern, darunter verschiedene Spezialisten, als primärer Betreuer für diesen Patienten verantwortlich ist.  Sofia startet einen Gruppen-Chat mit einer Reihe von Ärzten und anderen Krankenschwestern, die mit dem Patienten zusammenarbeiten werden, um die Behandlung zu koordinieren und eine Notfall-Triage zu starten.  Die Krankenschwestern und Ärzte kommunizieren und Arbeiten über den Pflegeplan des Patienten während des Pflege Koordinationsprozesses zusammen.  Wichtige und dringende Nachrichten werden über 1:1 und Gruppen-Chat-Unterhaltungen gesendet. Sofia verwendet die Lese Bestätigungsfunktion, um festzustellen, ob Nachrichten, die Support anfordern, von den Ziel Ärzten oder Krankenschwestern zugestellt und gelesen werden. Jakobs Patientenergebnisse sind nahezu optimal und er geht früher nach Hause, weil sein Gesundheitsteam reibungslos kommuniziert.

## <a name="send-urgent-messages-using-priority-notifications"></a>Senden dringender Nachrichten mithilfe von Prioritäts Benachrichtigungen

Ein Benutzer kann eine Nachricht beim Senden von Chatnachrichten an andere Benutzer als *dringend* kennzeichnen. Dieses Feature hilft Krankenhausmitarbeitern, sich gegenseitig zu benachrichtigen, wenn ein kritischer Vorfall Ihre Aufmerksamkeit erfordert. Im Gegensatz zu normalen *wichtigen* Nachrichten werden Benutzer mit [Prioritäts Benachrichtigungen](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) alle zwei Minuten für bis zu 20 Minuten benachrichtigt, oder bis die Nachricht vom Empfänger abgeholt und gelesen wird, wobei die Wahrscheinlichkeit maximiert wird, dass die Nachricht rechtzeitig verarbeitet wird.

Ein Administrator kann die Möglichkeit für Benutzer, denen diese Richtlinie zugewiesen ist, zum Senden von Prioritäts Benachrichtigungen aktivieren oder deaktivieren. Dieses Feature ist standardmäßig aktiviert. Der Empfänger der Prioritäts Nachricht hat möglicherweise nicht die gleiche Messagingrichtlinie und hat keine Option zum Deaktivieren des Empfangens von Prioritäts Nachrichten. Für Anwendungen im Gesundheitswesen empfehlen wir, das Feature für mindestens einige Benutzer zu aktivieren, doch müssen Sie ermitteln, welche.

*Verwendungsbeispiel:* Sofia Krause gibt einen Patienten mit hoher Risikowahrscheinlichkeit, Jakob Roth, erneut ein. Manuela Carstens, Ärztin, ist die Ärztin für diesen Patienten.  Sofia sendet eine Nachricht an Manuela mithilfe einer Prioritäts Benachrichtigung, in der Sie um sofortige Hilfe bei der Selektierung von Jakob gebeten werden.  Manuelas Telefon erhält die Nachricht, aber Manuela spürte keine Vibrationen des Telefons und antwortet nicht. Teams benachrichtigt Manuela erneut und wird weiterhin ständig erneut benachrichtigt, bis Sie die Nachricht liest. Wenn Lesebestätigungen ebenfalls aktiviert sind, kann sich Sofia bewusst sein, dass die Nachricht von Manuela gelesen wurde, noch bevor Manuela sich entscheidet, wie Sie antworten möchten.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Messaging-Richtlinien in Teams](../../messaging-policies-in-teams.md)
- [Erste Schritte mit Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)
