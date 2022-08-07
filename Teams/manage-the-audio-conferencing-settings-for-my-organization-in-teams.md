---
title: Verwalten von Audiokonferenzeinstellungen
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Weitere Informationen finden Sie in den Schritten von Microsoft Teams zum Zuweisen einer Lizenz für Einwahlkonferenzen und einer Konferenz-ID zu einem Benutzer und vielen anderen Einstellungen für Einwahlkonferenzen.
ms.openlocfilehash: 4bfb813b6e7b472ad7a9ab58e6403b92f60fd039
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271220"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams.

Möglicherweise ist es für Sie einfacher, alle Audiokonferenzeinstellungen für Microsoft Teams an einem zentralen Ort anzuzeigen.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Audiokonferenzlizenz

> [!NOTE]
> Sie können keine Lizenzen mithilfe von Teams zuweisen. Sie müssen die Microsoft 365 Admin Center verwenden. Siehe [Zuweisen von Microsoft Teams-Add-On-Lizenzen](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="to-assign-a-license-for-a-user"></a>To assign a license for a user

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.

2. Wechseln Sie in der linken Navigationsleiste des **Microsoft 365 Admin Center** zu **"** > **Aktive Benutzer**", und wählen Sie dann den Oder die Benutzer aus der Liste der verfügbaren Benutzer aus.

    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**.  
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.

4. Aktivieren Sie auf der Seite " **Produktlizenzen** " **audiokonferenzen** , und klicken Sie dann auf **"Speichern"**. Weitere Informationen zur Lizenzierung finden [Sie unter Microsoft Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

   > [!NOTE]
   > Nachdem Sie die Lizenz zugewiesen haben, wird Microsoft möglicherweise zunächst nicht in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall entweder beim Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren von E-Mails, die an Audiokonferenzbenutzer gesendet werden

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>Aktivieren oder Deaktivieren mithilfe des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Aktivieren oder deaktivieren Sie im **Einstellungsbereich "Brücke** " das **automatische Senden von E-Mails an Benutzer, wenn sich ihre Einwahleinstellungen ändern**.

4. Klicken Sie auf **Speichern**.

### <a name="enable-or-disable-using-windows-powershell"></a>Aktivieren oder Deaktivieren mithilfe von Windows PowerShell

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .
  
## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>Zurücksetzen der Besprechungskonferenz-ID mithilfe des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer**", und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurücksetzen**.  

3. Klicken Sie im Fenster " **Konferenz-ID zurücksetzen?"** auf **"Zurücksetzen"**. Eine Konferenz-ID wird automatisch erstellt, und eine E-Mail wird an den Benutzer mit der neuen Konferenz-ID gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. It's enabled by default.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es vorkommen, dass ein Benutzer diese nicht verwenden möchte und Sie diese auf eine bestimmte Zahl festlegen möchten, oder ihre Benutzer sich nicht mehr erinnern können oder ihre Konferenz-ID verloren haben.

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>Zurücksetzen der PIN eines Konferenzorganisators mithilfe des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer**", und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen** auf " **PIN zurücksetzen"** und dann auf **"Zurücksetzen"**.
  
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt.
  
Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>Senden einer E-Mail über das Microsoft Teams Admin Center

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer**", und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen** auf **Konferenzinformationen per E-Mail senden**.

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>Festlegen von Telefonnummern für Einladungen über das Microsoft Teams Admin Center

Weitere Informationen finden [Sie unter Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Sie können Telefonnummern auch festlegen, indem Sie sie der *TeamsAudioconferencingpolicy* hinzufügen und die Richtlinie Ihren Benutzern zuweisen. Gebührenpflichtige und gebührenfreie Telefonnummern, die der Richtlinie hinzugefügt wurden, haben Vorrang vor den Telefonnummern, die über den Einstellungsbereich für Audiokonferenzen einzeln für Benutzer festgelegt werden. Wenn der *Teamsaudioconferencingpolicy* keine Telefonnummern hinzugefügt werden, wird die über den Einstellungsbereich für Audiokonferenzen individuell für Benutzer festgelegte Telefonnummer in Microsoft Teams-Besprechungsanfragen angezeigt. [Die Richtlinieneinstellungen für Audiokonferenzen für gebührenpflichtige und gebührenfreie Telefonnummern](audio-conferencing-toll-free-numbers-policy.md) enthalten weitere Informationen.

## <a name="choose-audio-conferencing-bridge-settings"></a>Auswählen der Einstellungen für die Audiokonferenzbrücke

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>Festlegen der Besprechungserfahrung, wenn Anrufer über das Microsoft Teams Admin Center an einer Besprechung teilnehmen

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).

    Dies ist standardmäßig aktiviert. Wenn Sie diese Option deaktivieren, werden Benutzer, die der Besprechung bereits beigetreten sind, standardmäßig nicht benachrichtigt, wenn jemand die Besprechung betritt oder verlässt.

4. Wählen Sie unter **Ankündigungstyp "Ein-/Ausstieg**" entweder **"Töne** " oder " **Namen" oder "Telefonnummern**" aus.

    Wenn Sie **"Namen" oder "Telefonnummern**" auswählen, können Sie auch die Option "Anrufer bitten" aktivieren oder deaktivieren, **ihren Namen aufzuzeichnen, bevor Sie an der Besprechung teilnehmen**.
    > [!NOTE]
    > Standardmäßig können externe Teilnehmer die Telefonnummern der eingewählten Teilnehmer nicht sehen. Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden).
5. Klicken Sie auf **Speichern**.

Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
### <a name="set-the-pin-length-for-meetings"></a>Festlegen der Länge der PIN für Besprechungen

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Geben Sie im **Einstellungsbereich "Brücke** " die gewünschte Anzahl von Ziffern für die PIN in der **Pinlängenliste** ein, und klicken Sie dann auf **"Speichern"**.

    Die PIN muss aus 4 bis 12 Ziffern bestehen. The default is 5.

Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Aktivieren oder deaktivieren Sie im **Einstellungsbereich "Brücke** " das **automatische Senden von E-Mails an Benutzer, wenn sich ihre Audiokonferenzeinstellungen ändern**.

4. Klicken Sie auf **Speichern**.

    Sie können dem Benutzer auch E-Mails mit den Audiokonferenzeinstellungen senden, indem Sie zu den Audiokonferenzeigenschaften des Benutzers wechseln und auf **Konferenzinformationen per E-Mail senden** klicken.

    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Anzeigen und Festlegen der primären (Standard-) und sekundären (alternativen) Sprachen auf einer Audiokonferenzbrücke

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>Anzeigen der primären und sekundären Sprachen mithilfe des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **"Bearbeiten"**.

3. Wählen Sie die gewünschten Sprachen unter **"Standardsprache** " und **"Alternative Sprachen" (optional)** aus.

4. Klicken Sie auf **Speichern**.

Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>Anzeigen von Einwahlnummern für Audiokonferenzen im Microsoft Teams Admin Center

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **"Bearbeiten"**. Hier können Sie:

   - Zeigen Sie die Telefonnummern an, die für Audiokonferenzen verwendet werden sollen.

   - Zeigen Sie den Speicherort und die primäre Sprache an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet wird.

Siehe [Eine Liste der Audiokonferenznummern](see-a-list-of-audio-conferencing-numbers-in-teams.md) anzeigen.

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
