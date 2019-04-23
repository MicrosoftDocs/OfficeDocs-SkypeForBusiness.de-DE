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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Informationen Sie zu Richtlinien für Messaging und wie sie Chat in Teams messaging steuern verwendet werden können.
ms.openlocfilehash: 20c1354f168b5476733c95b49d3344364b8a6008
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959458"
---
# <a name="manage-messaging-policies-in-teams"></a>Verwalten von Messaging-Richtlinien in Teams

<!--- Add zone marker here--->

Messaging-Richtlinien dienen zum Steuern, welche Chat und Channel messaging-Funktionen für Benutzer in Microsoft-Teams verfügbar sind. Sie können die Standardrichtlinie, die automatisch erstellt wird, oder erstellen Sie eine oder mehrere benutzerdefinierte messaging Richtlinien für die Personen in Ihrer Organisation. Nachdem Sie eine Richtlinie erstellt haben, können Sie es auf einen Benutzer oder eine Gruppe von Benutzern in Ihrer Organisation zuweisen.

Standardmäßig wird eine Richtlinie mit dem Namen Global (Org geltende Standard) erstellt. Alle Benutzer in Ihrer Organisation werden standardmäßig diese messaging Richtlinie zugewiesen werden. Sie können entweder Änderungen an dieser Richtlinie vornehmen oder einen oder mehrere benutzerdefinierte Richtlinien erstellen und Benutzer zuweisen. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, können Sie zulassen oder verhindern, dass bestimmte Features wird für die Benutzer verfügbar und weisen Sie es für einen oder mehrere Benutzer, die die Einstellungen angewendet wird, benötigen. 

## <a name="change-or-create-a-messaging-policy"></a>Ändern Sie oder erstellen Sie eine Richtlinie messaging

Sie können auf einfache Weise verwalten Messagingrichtlinien in der Verwaltungskonsole von Microsoft-Teams (http://admin.teams.microsoft.com) , sich mit Administratoranmeldeinformationen anmelden und **Messaging Richtlinien** im linken Navigationsbereich. Um die Richtlinie für Ihre Organisation für den vorhandenen Nachrichtentransport zu bearbeiten, wählen Sie die Zeile **Global (Org geltende Standard)** , und nehmen Sie dann die Änderungen vor. Um eine neue benutzerdefinierte messaging-Richtlinie zu erstellen, wählen Sie **neue Richtlinie**, benennen Sie der neuen Richtlinie, und wählen Sie dann die Einstellungen aus. Wählen Sie **Speichern** aus, wenn Sie fertig sind.

Angenommen Sie, dass Sie sicherstellen möchten, die Nachrichten gelöscht oder geändert werden nicht gesendet. Sie erstellen eine neue benutzerdefinierte Richtlinie mit dem Namen "Gesendete Nachrichten beibehalten" und deaktivieren Sie die folgenden Einstellungen:

- Websitebesitzer können gesendete Nachrichten löschen.
- Benutzer können gesendete Nachrichten löschen.
- Benutzer können gesendete Nachrichten bearbeiten.

Klicken Sie dann den Benutzern zuweisen der Richtlinie.

> [!NOTE] 
> Ein Benutzer kann nur eine messaging-Richtlinie zu einem Zeitpunkt zugewiesen werden.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Zuweisen einer Richtlinie auf messaging für einen Benutzer

Wenn Sie eine benutzerdefinierte Richtlinie an messaging erstellen, werden es nur für einen Benutzer active, wenn die Richtlinie für den Benutzer zugewiesen ist. Wenn eine benutzerdefinierte Richtlinie an, die einem Benutzer zuweisen möchten, wechseln Sie in Microsoft-Teams, Admin Center, wählen **Benutzer** im linken Navigationsbereich, und wählen den Benutzer, dem Sie die Richtlinie zuweisen möchten. Wählen Sie der Benutzer auf Seite **Bearbeiten** , neben **Richtlinien zugewiesen**. Klicken Sie dann im Bereich **Richtlinien für Benutzer bearbeiten** unter **Messaging Policy**wählen Sie die messaging-Richtlinie aus der Dropdown-Liste, und wählen Sie **Speichern**aus. Sie können auch die Einstellungen aus der Liste der Benutzer bearbeiten. Wählen Sie den Benutzer dazu, indem Sie auf der linken Seite des Anzeigenamen des Benutzers auf. Wählen Sie **Einstellungen bearbeiten**. Klicken Sie dann im Bereich **Einstellungen bearbeiten** unter **Messaging Policy**, wählen Sie die Richtlinie aus der Dropdownliste aus, und wählen Sie dann auf **Speichern**.

Wenn Sie eine Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie jeden Benutzer aus, indem Sie links neben den Benutzernamen ein, und wählen Sie dann auf **Bearbeiten**. Klicken Sie im Bereich **Einstellungen bearbeiten** unter **Messaging-Richtlinie**wählen Sie die Richtlinie aus der Dropdown-Liste, und wählen Sie dann auf **Speichern**.

Sie können einen oder mehrere Benutzer auch wie folgt eine messaging-Richtlinie zuweisen:

1. Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **Messaging Richtlinien**.
2. Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.
3. Wählen Sie **Benutzer verwalten**.
4. Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.
5. Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.

> [!NOTE]
> Eine Richtlinie kann nicht gelöscht werden, wenn Benutzer zugewiesen sind. Sie müssen zuerst eine andere Richtlinie für alle betroffenen Benutzer zuweisen, und klicken Sie dann können Sie die ursprüngliche Richtlinie löschen.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Richtlinie für Textnachrichten

Verwenden Sie die folgenden Einstellungen zum Ändern der globalen Richtlinie messaging oder erstellen eine neue benutzerdefinierte Richtlinie an:

- **Websitebesitzer können gesendete Nachrichten löschen**  Verwenden Sie diese Einstellung Besitzer Nachrichten löschen können, die Benutzer in Chat gesendet.
- **Benutzer können gesendete Nachrichten löschen** Verwenden Sie diese Einstellung, damit Benutzer Nachrichten löschen, die sie im Chat gesendet.
- **Benutzer können gesendete Nachrichten bearbeiten** Verwenden Sie diese Einstellung, damit Benutzer die Nachrichten zu bearbeiten, die sie im Chat gesendet.
- **Lesebestätigungen** Verwenden Sie diese Einstellung an, ob Lese-Empfangsbestätigungen Benutzer gesteuert, für alle Benutzer aktiviert oder deaktiviert werden.
<a name="bkchat"> </a>

- **Chat**  Aktivieren Sie diese Einstellung, wenn die Benutzer in Ihrer Organisation die Teams app verwenden, um mit anderen Teilnehmern zu chatten können sollen.
- **Verwendung Giphys Unterhaltungen**  Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Giphys einschließen. Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen. Jedem Giphy wird eine Inhaltsbewertung zugewiesen.
- **Giphy zum Bewerten** 
    - **Keine Einschränkung** Dies bedeutet, dass Ihre Benutzer alle Giphy in Chats unabhängig von der zum Bewerten einfügen können.
    - **Moderater**  Dies bedeutet, dass Ihre Benutzer in Chats Giphys einfügen können, aber einigermaßen aus Versender nicht jugendfreier Inhalte eingeschränkt werden.
    - **Strict**  Dies bedeutet, dass Ihre Benutzer Giphys in Chats einfügen können, aber unbedingt aus Versender nicht jugendfreier Inhalte eingeschränkt werden.
- **Verwendung Memes Unterhaltungen** Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Memes einschließen. 
- **Verwendung Aufkleber Unterhaltungen** Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Aufkleber einschließen.
- **Zulassen von URL-Vorschau** Verwenden Sie diese Einstellung, um die automatische URL Anzeigen der Vorschau aktiviert oder deaktiviert in Nachrichten zu aktivieren.
- **Übersetzen von Nachrichten durch Benutzer zulassen** Aktivieren Sie diese Einstellung Benutzer Teams Nachrichten automatisch in die Sprache, die durch ihre persönliche Sprachoptionen für Office 365 angegebenen übersetzen können.
- **Zulassen von fesselnden Leser für die Anzeige von Nachrichten** Aktivieren dieser Einstellung können Benutzer anzeigen von Nachrichten in Microsoft fesselnden Reader. Fesselnden Reader ist ein Learning-Tool, das eine Vollbild-Lesemodus wünschen, um die Lesbarkeit des Texts erhöhen bereitstellt.
- **Benutzer können Benachrichtigungen Priorität senden** Wenn Sie diese aktivieren, können Benutzer die Priorität der Nachricht angeben.
- **Erstellung von VoIP-Nachricht** 
    - **Zulässige in Chats und Kanäle** Dies bedeutet, dass Benutzer Sprachnachrichten in Chats und Kanäle lassen können.
    - **Zulässige in nur chats** Dies bedeutet, dass Benutzer Sprachnachrichten in Chats, jedoch nicht in den Kanälen lassen können.
    - **Deaktiviert** Dies bedeutet, dass Benutzer nicht Sprachnachrichten in Chats oder Kanäle erstellen können.  
- **Auf mobilen Geräten anzeigen bevorzugte Kanäle über aktuelle chats** Aktivieren Sie diese Einstellung, um die bevorzugte Kanäle in im oberen Bereich des Bildschirms mobilen Gerät zu verschieben, damit ein Benutzer nicht muss, um einen Bildlauf durchführen, um sie zu finden. 
- **Ein Benutzer entfernen Sie Benutzer aus einer Gruppenchat zulassen** Aktivieren Sie diese Einstellung auf um einen Benutzer, die andere Benutzer aus einer Gruppenchat entfernen zu lassen. Dieses Feature können Sie einen Chat mit einer kleineren Gruppe von Personen weiter ohne Verlust des Chatverlaufs.

### <a name="related-topics"></a>Verwandte Themen
[Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
