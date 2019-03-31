---
title: Erste Schritte mit Secure Messaging für Unternehmen aus dem Gesundheitswesen
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erste Schritte mit Secure Messaging für Unternehmen aus dem Gesundheitswesen
ms.openlocfilehash: 58e19cd5f8e39e05b2b2178bcf4062260546e509
ms.sourcegitcommit: 355bcdafa58b6349bb6bc771054f4c9c91387a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013774"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Erste Schritte mit Secure Messaging für Unternehmen aus dem Gesundheitswesen

Messaging-Richtlinien dienen zum Steuern, welche Chat und Channel messaging-Funktionen für Benutzer in Microsoft-Teams verfügbar sind und sind Bestandteil der gesamten Bereitstellung von Secure Messaging für das Gesundheitswesen wie Krankenhäuser, Clinics oder Arzt des Büros, wobei eine Nachricht aufgenommene und dem in kurzer Zeit eine Aktion ausgeführt ist wichtig, wie wichtige Nachrichten beim Lesen sind bekannt ist.

Sie können die Standardrichtlinie verwenden oder einen oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen. Nachdem Sie eine Richtlinie erstellen, weisen es einem Benutzer oder Gruppen von Benutzern in Ihrer Organisation Sie. Sie können beispielsweise nur bestimmte Rollen Auftrag auf diese Features (vielleicht Ärzten und nur Pflegepersonal) und andere Mitarbeiter (wie die Mitarbeiter Hausmeister- oder Küche) verwenden, um eine geringerem Funktionssatz abzurufen zulassen. Für sich selbst entscheiden, welche Anforderungen Ihrer Organisation befindet, sind höchstens einen Vorschlag.

Richtlinien können auf einfache Weise in der [Microsoft-Teams, Administrationscenter](http://admin.teams.microsoft.com) verwaltet werden, indem Sie sich mit Administratoranmeldeinformationen anmelden und **Messaging Richtlinien** im linken Navigationsbereich.

 ![Messagingrichtlinien in Teams](../../media/messaging-policies-image1.png)

Um die vorhandenen Messaging-Standardrichtlinie für Ihre Organisation zu bearbeiten, klicken Sie auf die Zeile **Global (Org geltende Standard)** , und nehmen Sie dann die Änderungen vor. Um eine neue benutzerdefinierte messaging-Richtlinie zu erstellen, klicken Sie auf **neue Richtlinie** , und wählen Sie Ihre Einstellungen aus. Wählen Sie **Speichern** aus, wenn Sie fertig sind.

![Gesundheitswesen messaging Richtlinieneinstellungen](../../media/hc-message-policy.png)

Die folgenden Einstellungen sind besonders interessant für aus dem Gesundheitswesen Applikationen und sollten beim Entwerfen einer benutzerdefinierten Richtlinie an im Feld aus dem Gesundheitswesen verwendet berücksichtigt werden:

- ![Nummer eins](../../media/sfbcallout1.png) **lesebestätigungen** lesebestätigungen ermöglicht es dem Absender einer Nachricht Chat wissen, wann die Nachricht vom Empfänger gelesen wurde. Verwenden Sie diese Einstellung an, ob Lese-Empfangsbestätigungen gesteuert, für alle Benutzer aktiviert oder deaktiviert für jeden Benutzer. Die Nachricht gelesen, dass Empfangsbestätigungen in Unternehmen aus dem Gesundheitswesen eine wichtige Rolle spielen, da sie nicht eindeutig zu gibt an, ob eine Nachricht gelesen wurde entfernt.

  Wählen Sie aus dem Gesundheitswesen Anwendungsmöglichkeiten **Benutzer gesteuert** oder **für alle Benutzer aktiviert**. Beachten Sie, dass bei Verwendung die Einstellung **für alle Benutzer aktiviert** die einzige Möglichkeit zum Festlegen der Einnahmen für den gesamten Mandanten ist haben nur eine messaging-Richtlinie für den gesamten Mandanten (die Standardrichtlinie mit dem Namen "Global (Org geltende Standard)") oder alle messaging haben Richtlinien im Mandanten verwendet die gleichen Einstellungen für Einnahmen.

  > [!NOTE]
  > Beim Lesen verwendeten Einnahmen in eine große Gruppe chat (mit mehr als 100 Benutzer, beispielsweise), die Bestätigung Nachrichten die tatsächlichen Nachrichten überlasten und zu Chat zu Frustration führen können. Dies ist etwas Sie Benutzer aufmerksam zu machen müssen. Eine kleinere Gruppenchat (vielleicht 20 Benutzer oder weniger) dieses Feature besser nutzt.

 *Verwendungsbeispiel ohne lesebestätigungen:* Jakob Roth, ein Patient hohem Risiko wird an das Krankenhaus zugelassen.Sofia Krause handelt es sich um eine im Rahmen der Kommunikation zwischen disziplinarische Team (IDT) von medizinischen Mitarbeiter, einschließlich von anderen Experten arbeiten Pflegekraft als primärer Vorsicht Koordinator für diesen Patienten zugewiesen ist.  Sofia sendet-e-Mails und anderen Sofortnachrichten an eine Gruppe Pflegepersonal und Ärzten, die eine Vielzahl von messaging-Clients und apps verwenden und häufig abgerufen, keine Antwort oder die Angabe, ob eine Nachricht von Teammitgliedern gelesen wurde. Aufgrund von komplizierte Kommunikationsprozesse Jakob Medikament unzufriedenen wird und seine Nacht wurde erweitert.

  *Beispiel für die Verwendung mit lesebestätigungen:* Jakob Roth, ein Patient hohem Risiko wird an das Krankenhaus zugelassen.Sofia Krause handelt es sich um eine im Rahmen der Kommunikation zwischen disziplinarische Team (IDT) von medizinischen Mitarbeiter, einschließlich von anderen Experten arbeiten Pflegekraft als primärer Vorsicht Koordinator für diesen Patienten zugewiesen ist.  Sofia startet einen Gruppenchat mit einem Satz von Ärzten und andere Pflegepersonal, arbeiten mit den Patienten bei koordiniert und startet eine Notfall Ursachenanalyse.Die Pflegepersonal und Ärzten kommunizieren und zusammenarbeiten über den Patienten bei Plan über den gesamten Prozess Koordinierung Vorsicht.  Wichtige und dringende Nachrichten werden über 1:1 und Group Chat Unterhaltungen gesendet. Sofia verwendet die lesebestätigungen Funktionalität feststellen, wenn Nachrichten gesendet Anfordern von Unterstützung übermittelt und durch das gezielte Ärzten oder Pflegepersonal gelesen werden. Jakob Patienten Ergebnisse sind in der Nähe optimale, und er wechselt home schneller, da seine Vorsicht Team reibungslos kommuniziert.

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

- ![Nummer zwei](../../media/sfbcallout2.png) **Benutzer Priorität Benachrichtigungen senden können** mit dieser Einstellung können Benutzer Priorität Chatnachrichten an andere Benutzer senden können. Dieses Feature verbessert Personal voneinander zu warnen, wenn ein wichtiger Vorfall seine Aufmerksamkeit erfordern. Im Gegensatz zu regulären "important" Nachrichten Priorität Benachrichtigungen wiederholt benachrichtigen Sie Benutzer für einen Zeitraum von 20 Minuten oder bis Nachrichten aufgenommen werden, und Lesen Sie durch den Empfänger maximieren die Wahrscheinlichkeit, dass die Nachricht aufgenommene und dem in kurzer Zeit eine Aktion ausgeführt wird.

  Ein Administrator kann aktivieren oder deaktivieren die Möglichkeit für Benutzer, denen diese Richtlinie zugewiesen, Priorität Benachrichtigungen senden. Die Standardeinstellung ist deaktiviert. Der Empfänger der Nachricht Priorität verfügen nicht über die gleichen für Messagingrichtlinien und keine Option zum Empfang von Nachrichten mit Priorität zu deaktivieren. Aus dem Gesundheitswesen handelt es wird empfohlen, das Feature für mindestens einige Benutzer aktivieren, jedoch müssen Sie zu bestimmen, welche.

  *Verwendungsbeispiel:* Sofia Krause ist mit hohem Risiko Patienten Jakob Roth readmitting. Manuela Carstens, ein Arzt ist die primäre Vorsicht Arzt für diesen Patienten.  Sofia sendet eine Nachricht an Manuela als Ursachenanalyse von Jakob 'Hohe Priorität' und sofortige benötigen Hilfe markiert.  Manuelas Telefons die Nachricht empfängt, aber Manuela nicht der Meinung sind die Telefon Vibration und antwortet nicht. Teams erneut Manuela benachrichtigt und weiterhin permanenten erneut benachrichtigen, bis er die Nachricht liest. Wenn gelesenen Empfangsbestätigungen auch aktiviert sind, Sofia bewusst sein kann, dass die Nachricht vom Manuela gelesen wurde, entscheidet auch vor Manuela wie reagiert.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Messaging-Richtlinien in Teams](../../messaging-policies-in-teams.md)
- [Erste Schritte mit Teams für Unternehmen aus dem Gesundheitswesen](teams-in-hc.md)
