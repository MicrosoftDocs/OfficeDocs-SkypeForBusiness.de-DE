---
title: Verwalten von Nachrichtenrichtlinien in Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Nachrichtenrichtlinien, und wie Sie diese zur Steuerung der Chat-Nachrichten in Teams nutzen können.
ms.openlocfilehash: f760fdf196bdeecf14e432445e619c968f66c081
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096119"
---
# <a name="manage-messaging-policies-in-teams"></a>Verwalten von Nachrichtenrichtlinien in Teams

<!--- Add zone marker here--->

Nachrichtenrichtlinien werden genutzt, um zu steuern, welche Chat- und Nachrichtenkanalfunktionen den [Benutzern (Besitzern und Mitgliedern)](assign-roles-permissions.md) in Microsoft Teams zur Verfügung stehen. Sie können die globale (standardmäßig organisationsweit geltende) Richtlinie verwenden, oder benutzerdefinierte Richtlinien erstellen und diese gezielt zuweisen.

Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie können die Einstellungen in der globalen Richtlinie bearbeiten oder eine oder mehrere benutzerdefinierte Richtlinien erstellen und zuweisen, um bestimmte Features ein- und auszustellen.

## <a name="create-a-custom-messaging-policy"></a>Erstellen einer benutzerdefinierten Nachrichtenrichtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Nachrichtenrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie die gewünschten Einstellungen aus.
5. Klicken Sie auf **Speichern**.

Angenommen, Sie möchten sicherstellen, dass gesendete Nachrichten nicht gelöscht oder geändert werden können. Erstellen Sie dann eine neue benutzerdefinierte Richtlinie namens „Gesendete Nachrichten aufbewahren“ und deaktivieren Sie die folgenden Einstellungen:

- Besitzer können gesendete Nachrichten löschen
- Benutzer können gesendete Nachrichten löschen
- Benutzer können gesendete Nachrichten bearbeiten

Weisen Sie dann die Richtlinie den Benutzern zu.

## <a name="edit-a-messaging-policy"></a>Bearbeiten einer Nachrichtenrichtlinie

Sie können die globale Standardrichtlinie oder eine von Ihnen erstellte benutzerdefinierte Richtlinie jederzeit bearbeiten. 

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Nachrichtenrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie nun die gewünschten Änderungen vor.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Weisen Sie eine benutzerdefinierte Nachrichtenrichtlinie einem Benutzer zu

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Einem Benutzer kann jeweils nur eine Nachrichtenrichtlinie zugewiesen werden.

> [!NOTE]
> Sie können eine Richtlinie nicht löschen, solange Sie Benutzern zugewiesen ist. Sie müssen allen betroffenen Benutzern erst eine andere Richtlinie zuweisen, bevor Sie die ursprüngliche Richtlinie löschen können.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Nachrichtenrichtlinie – Einstellungen

Dies sind die Nachrichteneinstellungen, die Sie konfigurieren können.

- **Besitzer können gesendete Nachrichten löschen**: Verwenden Sie diese Einstellung, damit Besitzer Nachrichten löschen können, die von Benutzern im Chat gesendet wurden.
- **Benutzer können gesendete Nachrichten löschen**: Verwenden Sie diese Einstellung, damit Benutzer Nachrichten löschen können, die sie im Chat gesendet haben.
- **Benutzer können gesendete Nachrichten bearbeiten**: Verwenden Sie diese Einstellung, damit Benutzer Nachrichten bearbeiten können, die sie im Chat gesendet haben.
- **Lesebestätigungen**: Lesebestätigungen ermöglichen es dem Absender einer Chatnachricht, benachrichtigt zu werden, wenn die Nachricht vom Empfänger in 1:1-Chats und Gruppenchats mit höchstens 20 Personen gelesen wurde. Lesebestätigungen für Nachrichten nehmen die Ungewissheit, ob eine Nachricht gelesen wurde und verbessern so die Kommunikation im Team. Beachten Sie, dass in eDiscovery-Berichten keine Lesebestätigungen erfasst werden.  
    - **Benutzergesteuert**: Das bedeutet, dass Benutzer entscheiden können, ob Sie die Funktion „Lesebestätigungen“ aktivieren oder deaktivieren möchten. Die Standardeinstellung in der App ist „aktiviert“. Benutzer können Sie dann auf „deaktiviert“ ändern.
    - **Für alle aktiviert**: Das bedeutet, dass das Feature für jeden im Mandanten aktiviert ist und nicht deaktiviert werden kann. Achten Sie darauf, dass bei Verwendung der Einstellung **Für alle aktiviert** die einzige Möglichkeit zum Festlegen von Bestätigungen für den gesamten Mandanten darin besteht, nur eine Nachrichtenrichtlinie für den gesamten Mandanten zu nutzen (die Standardrichtlinie namens "Global (organisationsweiter Standard)) oder alle Nachrichtenrichtlinien im Mandanten dieselben Einstellungen für Bestätigungen verwenden zu lassen. Das Feature „Lesebestätigungen“ ist am effektivsten, wenn das Feature **für alle aktiviert** ist.
    - **Für alle deaktiviert**: Das bedeutet, dass das Feature für jeden im Mandanten deaktiviert ist und dass niemand im Mandanten Lesebestätigungen erhält. Auch kann das Feature nicht aktiviert werden.
<a name="bkchat"> </a>

- **Chat**: Aktivieren Sie diese Einstellung, wenn Sie möchten, dass die Benutzer in Ihrer Organisation mithilfe der Teams-App mit anderen Personen chatten können.
- **Giphys in Unterhaltungen verwenden**: Wenn Sie diese Funktion aktivieren, können Benutzer Giphys in Chats mit anderen Personen verwenden. Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen. Jedem Giphy wird eine Inhaltsbewertung zugewiesen. Beachten Sie bitte, dass Sie zusätzlich zum Aktivieren dieser Einstellung auch [Optional Connected Experiences](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) aktivieren müssen, damit Sie in Unterhaltungen Giphys hinzufügen können.
- **Giphy-Inhaltsklassifikation**
    - **Keine Einschränkung**: Das bedeutet, dass Ihre Benutzer beliebige Giphys in Chats einfügen können – unabhängig von ihrer Inhaltsbewertung.
    - **Moderat**: Das bedeutet, dass Benutzer Giphys in Chats einfügen können, der Zugriff auf nicht jugendfreie Inhalte aber moderat eingeschränkt wird.
    - **Streng**: Das bedeutet, dass Benutzer Giphys in Chats einfügen können, der Zugriff auf nicht jugendfreie Inhalte aber streng eingeschränkt wird.
- **Memes in Unterhaltungen verwenden**: Wenn Sie diese Funktion aktivieren, können Benutzer Memes in Chats mit anderen Personen verwenden.
- **Sticker in Unterhaltungen verwenden**: Wenn Sie diese Funktion aktivieren, können Benutzer Sticker in Chats mit anderen Personen verwenden.
- **URL-Vorschau zulassen**: Verwenden Sie diese Einstellung, um die automatische URL-Vorschau in Nachrichten zu aktivieren bzw. zu deaktivieren.
- **Übersetzung von Nachrichten durch Benutzer zulassen**: Wenn diese Funktion aktiviert ist, können Benutzer Microsoft Teams-Nachrichten automatisch in die Sprache übersetzen lassen, die in ihren persönlichen Spracheinstellungen für Microsoft 365 oder Office 365 festgelegt ist.
- **Plastischen Reader zum Anzeigen von Nachrichten zulassen**: Aktivieren Sie diese Einstellung, damit Benutzer Nachrichten in einem Microsoft Plastischen Reader anzeigen können. Plastischer Reader ist ein Lerntool, das zur Verbesserung der Lesbarkeit von Text eine Vollbildansicht bietet.
- **Senden von Prioritätsbenachrichtigungen**: Wenn Sie diese Funktion aktivieren, können Benutzer Nachrichten über [Prioritätsbenachrichtigungen senden](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Prioritätsbenachrichtigungen informieren Benutzer alle 2 Minuten innerhalb eines Zeitraums von 20 Minuten, oder bis Nachrichten, die als *dringend* markiert wurden, vom Benutzer aufgerufen und gelesen wurden, um eine möglichst zeitnahe Bearbeitung zu ermöglichen.
- **Aufnahme von Sprachnachrichten** 
  > [!Important]
  > Sprachnachrichten werden in eDiscovery-Berichten nicht erfasst.
    - **In Chats und Kanälen zugelassen**: Das bedeutet, dass Benutzer sowohl in Chats als auch in Kanälen Sprachnachrichten hinterlassen können.
    - **Nur in Chats zugelassen**: Das bedeutet, dass Benutzer in Chats, nicht aber in Kanälen Sprachnachrichten hinterlassen können.
    - **Deaktiviert**: Das bedeutet, dass Benutzer keine Sprachnachrichten in Chats oder Kanälen erstellen können.  
- **Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen**: Aktivieren Sie diese Einstellung, um die bevorzugten Kanäle an den oberen Rand des Bildschirms für mobile Geräte zu verschieben, damit ein Benutzer nicht scrollen muss, um Sie zu finden.
- **Einem Benutzer das Entfernen von Benutzern aus einem Gruppenchat gestatten**: Aktivieren Sie diese Einstellung, damit ein Benutzer andere Benutzer aus einem Gruppenchat entfernen kann. Mithilfe dieses Features können Sie mit einer kleineren Gruppe von Personen chatten, ohne den Chatverlauf zu verlieren.
- **Aktivieren Sie vorgeschlagene Antworten**  Aktivieren Sie diese Einstellung, um vorgeschlagene Antworten für Chatnachrichten zu aktivieren.

> [!NOTE]
> Einige dieser Einstellungen, z. B. die Verwendung von Giphys, können auch auf Teamebene von Teambesitzern und auf privater Kanalebene von den Besitzern dieser privaten Kanäle konfiguriert werden.

### <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](assign-roles-permissions.md)