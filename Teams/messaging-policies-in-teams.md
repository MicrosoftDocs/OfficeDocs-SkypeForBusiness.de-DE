---
title: Verwalten von Messaging-Richtlinien in Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Erfahren Sie mehr über Messaging Richtlinien und wie Sie zum Steuern von Chatnachrichten in Teams verwendet werden können.
ms.openlocfilehash: 8a92ceea98d5f55c885a9fb59976dd571dba2b09
ms.sourcegitcommit: 1a768e470a9509139eeb24034def12630acb7914
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2019
ms.locfileid: "34915148"
---
# <a name="manage-messaging-policies-in-teams"></a>Verwalten von Messaging-Richtlinien in Teams

<!--- Add zone marker here--->

Mit Messagingrichtlinien wird gesteuert, welche Chat-und Kanal-Messaging Features für Benutzer in Microsoft Teams verfügbar sind. Sie können die Standardrichtlinie verwenden, die automatisch erstellt wird, oder Sie können eine oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen. Nachdem Sie eine Richtlinie erstellt haben, können Sie Sie einem Benutzer oder einer Gruppe von Benutzern in Ihrer Organisation zuweisen.

Standardmäßig wird eine Richtlinie mit dem Namen Global (org-Wide Standard) erstellt. Standardmäßig werden allen Benutzern in Ihrer Organisation diese Messagingrichtlinie zugewiesen. Sie können entweder Änderungen an dieser Richtlinie vornehmen oder eine oder mehrere benutzerdefinierte Richtlinien erstellen und Ihnen Benutzer zuweisen. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, können Sie zulassen oder verhindern, dass bestimmte Features für Ihre Benutzer verfügbar sind, und Sie dann einem oder mehreren Benutzern zuweisen, die die auf Sie angewendeten Einstellungen benötigen. 

## <a name="change-or-create-a-messaging-policy"></a>Ändern oder Erstellen einer Messagingrichtlinie

Sie können auf einfache Weise Messagingrichtlinien im Microsoft Teams Admin Center verwaltenhttp://admin.teams.microsoft.com) (indem Sie sich mit Administratoranmeldeinformationen anmelden und im linken Navigationsbereich **Messagingrichtlinien** auswählen. Wenn Sie die vorhandene Standard-Messagingrichtlinie für Ihre Organisation bearbeiten möchten, wählen Sie die **globale Zeile (org-Wide Standard)** aus, und nehmen Sie dann die gewünschten Änderungen vor. Wenn Sie eine neue benutzerdefinierte Nachrichten Richtlinie erstellen möchten, wählen Sie **neue Richt**Linie aus, geben Sie der neuen Richtlinie einen Namen, und wählen Sie dann Ihre Einstellungen aus. Wählen Sie **Speichern** aus, wenn Sie fertig sind.

Angenommen, Sie möchten sicherstellen, dass gesendete Nachrichten nicht gelöscht oder geändert werden. Erstellen Sie eine neue benutzerdefinierte Richtlinie mit dem Namen "gesendete Nachrichten beibehalten", und deaktivieren Sie die folgenden Einstellungen:

- Besitzer können gesendete Nachrichten löschen
- Benutzer können gesendete Nachrichten löschen
- Benutzer können gesendete Nachrichten bearbeiten

Weisen Sie die Richtlinie dann den Benutzern zu.

> [!NOTE] 
> Einem Benutzer kann immer nur eine Nachrichten Richtlinie zugewiesen werden.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Zuweisen einer Messagingrichtlinie zu einem Benutzer

Wenn Sie eine benutzerdefinierte Messagingrichtlinie erstellen, ist Sie nur für einen Benutzer aktiv, wenn die Richtlinie dem Benutzer zugewiesen ist. Wenn Sie einem Benutzer eine benutzerdefinierte Richtlinie zuweisen möchten, wechseln Sie zum Microsoft Teams Admin Center, wählen Sie im linken Navigationsbereich die Option **Benutzer** aus, und wählen Sie den Benutzer aus, dem Sie die Richtlinie zuweisen möchten. Wählen Sie auf der Seite des Benutzers neben **zugewiesene Richtlinien**die Option **Bearbeiten** aus. Wählen Sie dann im Bereich **Benutzerrichtlinien bearbeiten** unter **Nachrichten Richtlinie**die Messagingrichtlinie aus der Dropdownliste aus, und wählen Sie **Speichern**aus. Sie können die Einstellungen auch in der Liste der Benutzer bearbeiten. Wählen Sie dazu den Benutzer aus, indem Sie links neben dem Anzeigenamen des Benutzers klicken. Wählen Sie **Einstellungen bearbeiten**aus. Wählen Sie dann im Bereich **Bearbeitungseinstellungen** unter **Nachrichten Richtlinie**die Richtlinie aus der Dropdownliste aus, und wählen Sie dann **Speichern**aus.

Wenn Sie eine Richtlinie auf mehrere Benutzer anwenden, wählen Sie die einzelnen Benutzer aus, indem Sie links neben dem Benutzernamen klicken, und wählen Sie dann **Einstellungen bearbeiten**aus. Wählen Sie im Bereich **Bearbeitungseinstellungen** unter **Nachrichten Richtlinie**die Richtlinie aus der Dropdownliste aus, und wählen Sie dann **Speichern**aus.

Sie können eine Messagingrichtlinie auch einem oder mehreren Benutzern wie folgt zuweisen:

1. Wechseln Sie zu den **Microsoft Teams Admin Center** > -**Nachrichtenrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten**aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.

> [!NOTE]
> Sie können eine Richtlinie nicht löschen, wenn Benutzer ihr zugewiesen sind. Sie müssen zunächst allen betroffenen Benutzern eine andere Richtlinie zuweisen, und Sie können dann die ursprüngliche Richtlinie löschen.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Nachrichtenrichtlinien Einstellungen

Verwenden Sie die folgenden Einstellungen, um die globale Messagingrichtlinie zu ändern oder eine neue benutzerdefinierte Richtlinie zu erstellen:

- **Besitzer können gesendete Nachrichten löschen**  Verwenden Sie diese Einstellung, damit Besitzer Nachrichten löschen können, die Benutzer im Chat gesendet haben.
- **Benutzer können gesendete Nachrichten löschen** Verwenden Sie diese Einstellung, damit Benutzer Nachrichten, die Sie im Chat gesendet haben, löschen können.
- **Benutzer können gesendete Nachrichten bearbeiten** Verwenden Sie diese Einstellung, damit Benutzer die Nachrichten bearbeiten können, die Sie im Chat gesendet haben.
- **Lesebestätigungen** Verwenden Sie diese Einstellung, um anzugeben, ob Lesebestätigungen vom Benutzer gesteuert werden, für jeden aktiviert oder für jeden deaktiviert sind. Die Standardeinstellung ist Benutzer gesteuert. 
    - **Benutzer gesteuert** Das bedeutet, dass Benutzer entscheiden können, ob Lesebestätigungen ein-oder ausgeschaltet werden sollen. Die Standardeinstellung in der APP ist aktiviert. Benutzer können Sie dann deaktivieren.
    - **Für jeden** frei Dies bedeutet, dass jeder im Mandanten das Feature aktiviert hat, ohne die Option zum Deaktivieren. 
    - **Für jeden frei** Dies bedeutet, dass das Feature deaktiviert ist und niemand im Mandanten Lesebestätigungen hat, und dass es nicht aktiviert werden kann. 
<a name="bkchat"> </a>

- **Chat**  Aktivieren Sie diese Einstellung, wenn Benutzer in Ihrer Organisation in der Lage sein sollen, die Teams-App zum chatten mit anderen Personen zu verwenden.
- **Verwenden von Giphys in Unterhaltungen**  Wenn Sie diese Option aktivieren, können Benutzer Giphys in Chat Unterhaltungen mit anderen Personen einbeziehen. Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen. Jedem Giphy wird eine Inhaltsbewertung zugewiesen.
- **Giphy-Inhaltsbewertung** 
    - **Keine Einschränkung** Das bedeutet, dass Ihre Benutzer unabhängig von der Inhaltsbewertung in der Lage sind, beliebige Giphy in Chats einzufügen.
    - Mittel **mäßig**  Das bedeutet, dass Ihre Benutzer in der Lage sein werden, Giphys in Chats einzufügen, die aber von Erwachseneninhalten moderat eingeschränkt werden.
    - **Strenge**  Das bedeutet, dass Ihre Benutzer in der Lage sein werden, Giphys in Chats einzufügen, die jedoch strikt von Erwachseneninhalten eingeschränkt werden.
- **Verwenden von Memen in Konversationen** Wenn Sie diese Option aktivieren, können Benutzer Meme in Chat Unterhaltungen mit anderen Personen einbeziehen. 
- **Verwenden von Aufklebern in Konversationen** Wenn Sie diese Option aktivieren, können Benutzer Aufkleber in Chat Unterhaltungen mit anderen Personen einbeziehen.
- **URL-Vorschau zulassen** Verwenden Sie diese Einstellung, um die automatische URL-Vorschau in Nachrichten ein-oder auszuschalten.
- **Zulassen, dass Benutzer Nachrichten übersetzen** Aktivieren Sie diese Einstellung, damit Benutzer Teams-Nachrichten automatisch in die Sprache übersetzen können, die in Ihren persönlichen Spracheinstellungen für Office 365 angegeben ist.
- **Ermöglichen des immersiven Readers zum Anzeigen von Nachrichten** Aktivieren Sie diese Einstellung, damit Benutzer Nachrichten in Microsoft immersive Reader anzeigen können. Der immersive Reader ist ein Lerntool, mit dem Sie die Lesbarkeit von Text verbessern können.
- **Benutzer können Prioritäts Benachrichtigungen senden** Wenn Sie diese Option aktivieren, können Benutzer eine Nachricht senden, die Prioritäts Benachrichtigungen verwendet. Prioritäts Benachrichtigungen benachrichtigen Benutzer wiederholt über einen Zeitraum von 20 Minuten, oder bis Nachrichten vom Empfänger abgeholt und gelesen werden, sodass die Wahrscheinlichkeit maximiert wird, dass die Nachricht aufgenommen und rechtzeitig bearbeitet wird.   [!INCLUDE [pri-message-offer](includes/pri-message-offer.md)]
- **Erstellen von Sprachnachrichten** 
    - **Erlaubt in Chats und Kanälen** Das bedeutet, dass Benutzer Sprachnachrichten sowohl in Chats als auch in Kanälen hinterlassen können.
    - **Nur in Chats zulässig** Das bedeutet, dass Benutzer Sprachnachrichten in Chats, aber nicht in Kanälen hinterlassen können.
    - **Deaktiviert** Das bedeutet, dass Benutzer keine Sprachnachrichten in Chats oder Kanälen erstellen können.  
- **Auf mobilen Geräten: Anzeigen von bevorzugten Kanälen über den letzten Chats** Aktivieren Sie diese Einstellung, um die bevorzugten Kanäle an den oberen Rand des Bildschirms des mobilen Geräts zu verschieben, damit ein Benutzer nicht scrollen muss, um ihn zu finden. 
- **Zulassen, dass ein Benutzer Benutzer aus einem Gruppen-Chat entfernt** Aktivieren Sie diese Einstellung, damit ein Benutzer andere Benutzer aus einem Gruppen-Chat entfernen kann. Mit dieser Funktion können Sie einen Chat mit einer kleineren Gruppe von Personen fortsetzen, ohne das Chat-Protokoll zu verlieren.

### <a name="related-topics"></a>Verwandte Themen
[Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
