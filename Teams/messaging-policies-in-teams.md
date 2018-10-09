---
title: Was sind die Richtlinien in Teams Messaging?
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
ms.openlocfilehash: 7b9cb8a6a5c30806d44f5056e4dee0de79823841
ms.sourcegitcommit: c6b62a64d198fe18ae53cf849d125c5143053456
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25453794"
---
# <a name="what-are-messaging-policies-in-teams"></a>Was sind die Richtlinien in Teams Messaging?

Messaging-Richtlinien dienen zum Steuern, welche Chat und Channel messaging-Funktionen für Benutzer in Microsoft-Teams verfügbar sind. Sie können die Standardrichtlinie, die erstellt wird, oder erstellen Sie eine oder mehrere benutzerdefinierte messaging Richtlinien für die Personen in Ihrer Organisation. Nachdem Sie eine Richtlinie erstellen, weisen es einem Benutzer oder Gruppen von Benutzern in Ihrer Organisation Sie.

Richtlinien können auf einfache Weise verwaltet werden, in der Verwaltungskonsole Teams (http://admin.teams.microsoft.com) von **Messaging-Richtlinien** im linken Navigationsbereich klicken und sich mit Administratoranmeldeinformationen anmelden. Um die vorhandene Standardrichtlinie für Ihre Organisation zu bearbeiten, wählen Sie die Zeile **Global (Org geltende Standard)** , und klicken Sie auf **Bearbeiten**. Um eine neue messaging-Richtlinie zu erstellen, klicken Sie auf **neue Richtlinie**.

![Messagingrichtlinien in Teams](media/messaging-policies.png)

Die verfügbaren Einstellungen für die Richtlinie werden nachfolgend beschrieben: 

- **Websitebesitzer können gesendete Nachrichten löschen**  Verwenden Sie diese Einstellung, um Besitzer Nachrichten löschen, die Benutzer im Chat senden lassen.
- **Benutzer können gesendete Nachrichten löschen** Verwenden Sie diese Einstellung, damit Benutzer Nachrichten löschen, die sie im Chat senden.
- **Benutzer können gesendete Nachrichten bearbeiten** Verwenden Sie diese Einstellung, damit Benutzer die Nachrichten zu bearbeiten, die sie im Chat senden.
- **Lesebestätigungen** Verwenden Sie diese Einstellung an, ob Lese-Empfangsbestätigungen Benutzer gesteuert, für alle Benutzer aktiviert oder deaktiviert werden.
- **Chat**  Aktivieren Sie diese Einstellung, wenn die Benutzer in Ihrer Organisation die Teams app verwenden, um mit anderen Teilnehmern zu chatten können sollen.
- **Verwendung Giphys Unterhaltungen**  Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Giphys einschließen. Giphy ist ein online-Datenbank und die Suchmaschine, mit dem Benutzer suchen und Freigeben von animierte GIF-Dateien. Jede Giphy wird eine Content Bewertung zugewiesen.
- **Giphy zum Bewerten** 
    - **Keine Einschränkung** Dies bedeutet, dass Ihre Benutzer alle Giphys in Chats unabhängig von der zum Bewerten einfügen können.
    - **Moderater**  Dies bedeutet, dass Ihre Benutzer in Chats Giphys Einfügen jedoch einigermaßen aus Versender nicht jugendfreier Inhalte eingeschränkt werden.
    - **Strict**  Dies bedeutet, dass Ihre Benutzer in Chats Giphys Einfügen jedoch unbedingt aus Versender nicht jugendfreier Inhalte eingeschränkt werden.
- **Verwendung Memes Unterhaltungen** Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Memes einschließen. 
- **Verwendung Aufkleber Unterhaltungen** Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Aufkleber einschließen.
- **Zulassen von URL-Vorschau** Verwenden Sie diese Einstellung, um die automatische URL Anzeigen der Vorschau aktiviert oder deaktiviert in Nachrichten zu aktivieren.
- **Übersetzen von Nachrichten durch Benutzer zulassen** Aktivieren Sie diese Einstellung Benutzer Teams Nachrichten automatisch in die Sprache, die durch ihre persönliche Sprachoptionen für Office 365 angegebenen übersetzen können.

Wenn Sie eine benutzerdefinierte Richtlinie an Messaging erstellt haben, werden es nur aktive für einen Benutzer wenn diese Richtlinie, die einem Benutzer zugewiesen ist.  Um eine benutzerdefinierte Richtlinie für einen Benutzer in der Verwaltungskonsole Teams zuzuweisen, klicken Sie im linken Navigationsbereich auf **Benutzer** , wählen Sie den Benutzer, dem Sie die Richtlinie zuweisen möchten, und wählen Sie dann auf **Bearbeiten** , klicken Sie unter **Richtlinien zugewiesen**.

### <a name="related-topics"></a>Verwandte Themen
[Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)