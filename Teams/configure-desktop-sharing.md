---
title: Konfigurieren Sie die Desktopfreigabe in Microsoft-Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Konfigurieren Sie eine besprechungsrichtlinie, damit die Benutzer ihren Desktop in Teams Chats oder Besprechungen freigeben können
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202501"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Konfigurieren Sie die Desktopfreigabe in Microsoft-Teams
============================================

Desktopfreigabe kann Benutzer eine Bildschirm oder app während einer Besprechung oder Chat darstellen. Administratoren können Bildschirmfreigabe in Microsoft-Teams können Benutzer einen ganzen Bildschirm, einer app oder eine Datei freizugeben, konfigurieren. Sie können anderen Benutzern erteilen oder Steuerung anfordern, PowerPoint-Freigabe ermöglichen, ein Whiteboard hinzuzufügen und freigegebene Notizen zulassen. Sie können auch konfigurieren, ob anonyme oder externe Benutzer Steuerung des freigegebenen Bildschirms anfordern können.

So konfigurieren die Bildschirmfreigabe, erstellen Sie eine neue Richtlinie für Besprechungen und weisen Sie es den Benutzern, den Sie verwalten möchten.

In der Microsoft-Teams & Skype für Business Admin Center:

1. Wählen Sie **Besprechungen** > **Besprechungsrichtlinien**.

    ![Wählen Sie Besprechungsrichtlinien](media/configure-desktop-sharing-image1.png)

2. Wählen Sie auf der Seite **Besprechungsrichtlinien** **neue Richtlinie**aus.

    ![Wählen Sie neue Richtlinie](media/configure-desktop-sharing-image2.png)

3. Geben Sie Ihre Richtlinie einen eindeutigen Titel, und geben Sie eine kurze Beschreibung ein.

4. Wählen Sie unter **gemeinsame Nutzung von Inhalten**aus der Dropdown Liste einer **Bildschirmfreigabe Modus** :

   - **Gesamten Bildschirm** – können Benutzer ihren gesamten Desktop freigeben.
   - **Einzelne Anwendung** – ermöglicht Benutzern Grenzwert Bildschirmfreigabe auf eine einzelne aktive Anwendung.
   - **Disabled** – deaktiviert Bildschirmfreigabe.

    ![Wählen Sie einen Modus für die Bildschirmfreigabe](media/configure-desktop-sharing-image3.png)

5. Aktivieren Sie oder Deaktivieren der folgenden Einstellungen:

    - **Ermöglichen ein Teilnehmers zu gewähren oder Anfordern der Steuerung** – können Mitglieder des Teams gewähren oder Anfordern der Steuerung des Desktops der Referent oder der Anwendung.
    - Gäste können **einen externen Teilnehmer zu gewähren oder Anfordern der Steuerung zulassen** – und externe (Verbundbenutzer) gewähren oder Anfordern der Steuerung des Desktops oder der Anwendung der Referent.
    - **Zulassen von PowerPoint-Freigabe** - können Benutzer Besprechungen erstellen, mit denen PowerPoint-Präsentationen hochgeladen und gemeinsam genutzt werden können.
    - **Whiteboard zulassen** – ermöglicht dem Benutzer, die ein Whiteboard zu teilen.
    - **Freigegebene Notizen zulassen** – ermöglicht Benutzern das freigegebene Notizen machen.

6. Klicken Sie auf **Speichern**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Verwenden von PowerShell zum Konfigurieren des freigegebenen Desktops

Sie können auch das Cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) zur Steuerung der Desktopfreigabe verwenden. Festlegen Sie die folgenden Parameter:

- Beschreibung
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Erfahren Sie mehr über die Verwendung des CsTeamsMeetingPolicy-Cmdlets](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

