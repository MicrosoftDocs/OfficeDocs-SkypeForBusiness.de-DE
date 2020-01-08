---
title: Verwalten der Einstellungen von Audio Conferencing für meine Organisation in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Weitere Informationen finden Sie unter Skype for Business Online-Schritte zum Zuweisen einer Lizenz für Einwahlkonferenzen und einer Konferenz-ID für einen Benutzer und viele andere Einstellungen für Einwahlkonferenzen. '
ms.openlocfilehash: f5597ae2b857569b7890d81577e4fd4252da5106
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962703"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Verwalten der Einstellungen von Audio Conferencing für meine Organisation in Skype for Business Online

> [!NOTE]
> Wenn Sie in Microsoft Teams diese Einstellungen verwalten möchten, sehen Sie[Verwalten der Einstellungen für Audio Conferencing für meine Organisation im Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Es ist möglicherweise einfacher für Sie, alle Audiokonferenz-Einstellungen für Skype for Business an einem zentralen Ort anzuzeigen.


## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Audiokonferenz-Lizenz

> [!NOTE]
> Sie können keine Lizenzen über das **Skype for Business Admin Center**zuweisen. Sie müssen das Microsoft 365 Admin Center verwenden. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **So weisen Sie eine Lizenz für einen Benutzer zu**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie in der linken Navigationsleiste des Admin Centers zu **Benutzer** > **aktive**Benutzer, und wählen Sie dann den Benutzer oder die Benutzer aus der Liste der verfügbaren Benutzer aus.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Nachdem Sie die Lizenz zugewiesen haben, wird Microsoft möglicherweise zunächst nicht als Audiokonferenz-Anbieter in der Liste angezeigt. Wenn dies der Fall ist, melden Sie sich entweder beim Admin Center ab, oder drücken Sie STRG + F5, um das Browserfenster zu aktualisieren.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren von e-Mails, die an Audiokonferenz-Benutzer gesendet wurden

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.

3. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**.

    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften für den Benutzer, und klicken Sie auf **Konferenzinformationen per E-Mail senden**. Die Konferenzkennung und die Standardtelefonnummer für die Audiokonferenz sind in der Besprechungseinladung enthalten, die PIN jedoch nicht.

    Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**

- Sie können auch Windows PowerShell verwenden und Folgendes ausführen:

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer

Sie können die E-Mail, die automatisch an Ihre Benutzer gesendet wird, ändern, unter anderem die E-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders. Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell und dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) ändern. Um Änderungen an der E-Mail-Adresse vorzunehmen, über die die E-Mail an die Benutzer gesendet wird, müssen Sie:

- Geben Sie die e-Mail-Adresse im _SendEmailFromAddress_ -Parameter ein.

- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.

- Legen Sie den Parameter _SendEmailOverride_ auf _True_fest.

Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.

Sie können das Cmdlet " [Satz-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) " verwenden, um andere Einstellungen für Ihre Organisation, einschließlich e-Mail, zu verwalten.

Sehen Sie sich [e-Mails an, die automatisch an Benutzer gesendet werden, wenn sich Ihre audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center**zu **Audio conferencing** (Audiokonferenz), und klicken Sie im Aktionsbereich unter **Konferenzkennung** auf **Zurücksetzen**.

4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenzkennung generiert und per E-Mail an den Benutzer gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. Standardmäßig ist dies aktiviert.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.

3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.

4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.

Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt.

Siehe [Zurücksetzen der Audiokonferenz-Pin](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer e-Mail mit Audio-Konferenz Informationen an einen Benutzer

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.

3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.

4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. Im Aktionsbereich können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.

5. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Einrichten der Telefonnummern, die in Einladungen enthalten sind](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Auswählen von Einstellungen für die Audiokonferenz-Bridge

**Einrichten der Besprechungs Erfahrung, wenn Anrufer an einer Besprechung teilnehmen**


1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. Wechseln Sie im **Skype for Business Admin Center**in der linken Navigationsleiste zu **Audiokonferenz** > -**Einstellungen für Microsoft Bridge**.

4. Wählen Sie unter **Besprechungsteilnahme** die folgenden Aktionen aus:

   - **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits standardmäßig an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.

     Dies kann für Besprechungen festgelegt werden, wenn ein Benutzer mit einer Skype for Business-APP an einer Besprechung teilnimmt und die Einstellung " **Wenn Personen eingeben oder belassen** " im Menü "Skype-Besprechungs **Optionen** " der Besprechung ändert.

   - **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.

5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. Wechseln Sie im **Skype for Business Admin Center**in der linken Navigationsleiste zu **Audiokonferenz** > -**Einstellungen für Microsoft Bridge**.

4. Geben Sie unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.
    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.

3. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**.

    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Konferenzinformationen per E-Mail senden**.

    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

    Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Anzeigen und Festlegen der primären (Standard-) und sekundären (Alternativen) Sprachen auf einer Audiokonferenz-Brücke


1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.

4. Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festlegen** und dann auf der Seite **Sprachen festlegen** auf die Liste **Primäre Sprache**. In dieser Liste werden alle unterstützten Sprachen angezeigt.

    Außerdem können Sie die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Audiokonferenzanbieter auswählen. Die Reihenfolge, in der Sie Ihre Auswahl in den Dropdownlisten treffen, entspricht der Reihenfolge, in der die Sprachen Anrufern genannt werden.

Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Zeigen Sie die Telefonnummern an, die von Office 365 für Audiokonferenzen verwendet werden.

   - Zeigen Sie den Standort sowie die primären und sekundären Sprachen an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.

   - Wählen Sie die Standardtelefonnummer aus, die Benutzer erhalten, wenn sie für Audiokonferenzen aktiviert werden. Wenn jedoch die Standardtelefonnummer für die Audiokonferenzbrücke geändert wird, ändert sich die Standardtelefonnummer für vorhandene Benutzer nicht.

Sie können zu **Audiokonferenz** > -**Benutzern** wechseln und die Eigenschaften des Benutzers auswählen, um die Standardnummer für einen Benutzer zu ändern, indem Sie eine neue Nummer aus der Liste der in Ihrer Organisation verfügbaren Zahlen auswählen.

Weitere Informationen finden Sie unter [Anzeigen einer Liste von Audiokonferenz-Nummern](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zum Admin Center #a0 **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz) und dann zu **Benutzer**.

Siehe [Anzeigen einer Liste der Benutzer, die für Einwahlkonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

Weitere Hilfe zu den einzelnen Cmdlets finden Sie unter [Skype for Business Online-Cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

Hier sind die Einstellungen auf Organisationsebene:

- **Einstellung Eintrag/Exit Benachrichtigungen** Der Standardwert ist _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Einstellung von Namen-Aufzeichnung** Der Standardwert ist _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Einstellung der PIN-Länge** Der Standardwert ist 5.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Einstellung von nur Einwahl-Meetings über ein Telefon** Standard ist _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Festlegen, ob E-Mails an Benutzer gesendet werden** Der Standardwert ist _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Festlegen, ob E-Mail von einem anderen Konto gesendet wird** Der Standardwert ist _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Festlegen der Absenderadresse auf E-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Festlegen des Anzeigenamens für die E-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn nur das Admin Center verwendet wird, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen. Weitere Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user.md)


