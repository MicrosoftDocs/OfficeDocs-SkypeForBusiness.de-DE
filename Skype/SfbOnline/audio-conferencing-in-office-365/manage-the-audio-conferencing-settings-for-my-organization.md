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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Finden Sie unter Skype for Business Online Schritte, um einem Benutzer eine Einwahlkonferenz-Lizenz, eine Konferenz-ID und viele andere Einstellungen für Einwahlkonferenzen zuzuweisen. '
ms.openlocfilehash: d8fc38929e059d0c8fdaf0babec5f8b6fb72856a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255728"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Verwalten der Einstellungen von Audio Conferencing für meine Organisation in Skype for Business Online

> [!NOTE]
> Wenn Sie in Microsoft Teams diese Einstellungen verwalten möchten, sehen Sie[Verwalten der Einstellungen für Audio Conferencing für meine Organisation im Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Möglicherweise ist es einfacher für Sie, alle Einstellungen für Audio Conferencing für Skype for Business und Microsoft Teams an einer einzigen Stelle zu sehen.


## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audio Conferencing

> [!NOTE]
> Sie können mithilfe des **Skype for Business Administrationscenters**keine Lizenzen zuweisen. Sie müssen das Office 365 Administrationscenter verwenden. Sehen Sie[Zuweisen von Lizenzen für Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **So weisen Sie eine Lizenz für einen Benutzer zu**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.

    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**. Mit Windows PowerShell können Sie auch mehreren Benutzern Lizenzen zuweisen. Anleitungen und PowerShell-Beispielskripts finden Sie unter [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.

4. KLicken Sie auf der Seite **Produktlizenzen** auf **Audio Conferencing** und dann klicken Sie auf **Save**. Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren der an Benutzer von Audio Conferencing gesendeten E-Mails

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admincenters**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).

3. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**.

    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften für den Benutzer, und klicken Sie auf **Konferenzinformationen per E-Mail senden**. Die Konferenzkennung und die Standardtelefonnummer für die Audiokonferenz sind in der Besprechungseinladung enthalten, die PIN jedoch nicht.

    Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**

- Sie können auch Windows PowerShell verwenden und Folgendes ausführen:

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer

Sie können die E-Mail, die automatisch an Ihre Benutzer gesendet wird, ändern, unter anderem die E-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders. Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell und dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ändern. Um Änderungen an der E-Mail-Adresse vorzunehmen, über die die E-Mail an die Benutzer gesendet wird, müssen Sie:

- Die E-Mail-Adresse in den Parameter_SendEmailFromAddress_ eingeben.

- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.

- Legen Sie den Parameter _SendEmailOverride_ auf _True_fest.

Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.

Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

Weitere Informationen finden Sie unter [E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Einstellungen für Audio Conferencing ändern](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Setzen Sie die Meeting-Konferenz-ID zurück

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center**zu **Audio conferencing** (Audiokonferenz), und klicken Sie im Aktionsbereich unter **Konferenzkennung** auf **Zurücksetzen**.

4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenzkennung generiert und per E-Mail an den Benutzer gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. Standardmäßig ist dies aktiviert.

    > [!IMPORTANT]
    >  Nachdem eine neue Konferenz-ID erstellt wurde, kann die alte Konferenz-ID von Anrufern nicht mehr verwendet werden. Informieren Sie Benutzer von Plänen deren vorhandene Meeting-Einladungen neu zu planen, um sicher zu gehen, dass die neue Konferenz-ID der Einladungen hinzugefügt wird. Die Benutzer können das Skype for Business Meeting-Migrationstool für ihre vorhandenen Meetings aktualisieren. Informationen zum Herunterladen, installieren und ausführen des Skype for Business Meeting-Updatetools finden Sie unter: [Meeting-Updatetool für Skype for Business und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting-Migrationstool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), und  [Skype for Business Online, Meeting-Migrationstool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Zurücksetzen der PIN eines Konferenz-Organisators

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es jedoch geschehen, dass ein Benutzer diese nicht verwenden und sie durch eine bestimmte Zahl ersetzen möchte, oder Ihr Benutzer kann sich seine Konferenz-ID nicht merken oder hat sie verloren. Sie können das Skype for Business Administrationscenter und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.


1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).

3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.

4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.

Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt.

See [Zurücksetzen der PIN für Audio Conferencing](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit den Informationen zum Audio Conferencing an einen Benutzer

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).

3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.

4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.

Siehe[Senden einer E-Mail zu einem Benutzer mit seinen Informationen zum Audio Conferencing](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Wechseln Sie im linken Navigationsbereich zu **Audio Conferencing** > **Benutzer**. Wählen Sie den Benutzer, den Sie für Audio Conferencing aktivieren möchten.

4. Im Aktionsbereich können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.

5. Klicken Sie auf **Save**.

Sehen Sie [Einrichten der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Bridge-Einstellungen für Audio Conferencing auswählen

**Legen Sie die Meeting-Erfahrung fest, wenn Anrufer einem Meeting beitreten**


1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Gehen Sie in der linken Navigationsleiste zu **Skype for Business Admin Center**und dann zu **Audio Conferencing** > **Microsoft Bridge Einstellungen**.

4. Wählen Sie unter **Besprechungsteilnahme** die folgenden Aktionen aus:

  - **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits standardmäßig an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.

    Dies kann auf einer Meeting-zu-Meeting Basis festgelegt werden, wenn ein Benutzer, der eine Skype for Business-App benutzt einem Meeting beitritt und dann die Einstellung **Ankündigen wenn Personen Eintreten oder Verlassen** im Skype Meeting **Optionen** Menü des Meetings ändern.

  - **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.

5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).

 **Festlegen der Länge der PIN für Besprechungen**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Gehen Sie in der linken Navigationsleiste zu **Skype for Business Admin Center**und dann zu **Audio Conferencing** > **Microsoft Bridge Einstellungen**.

4. Geben Sie unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.

Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).

 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).

3. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**.

    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Konferenzinformationen per E-Mail senden**.

    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

    Siehe[Senden einer E-Mail zu einem Benutzer mit seinen Informationen zum Audio Conferencing](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Anzeigen und Festlegen der primären (Standard) und sekundären (alternativen) Sprachen auf einer Audio Conferencing Bridge


1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.

4. Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festlegen** und dann auf der Seite **Sprachen festlegen** auf die Liste **Primäre Sprache**. In dieser Liste werden alle unterstützten Sprachen angezeigt.

    Außerdem können Sie die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Audiokonferenzanbieter auswählen. Die Reihenfolge, in der Sie Ihre Auswahl in den Dropdownlisten treffen, entspricht der Reihenfolge, in der die Sprachen Anrufern genannt werden.

Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Gehen Sie in der linken Navigationsleiste zu **Skype for Business Admin Center** und dann zu **Audio Conferencing** > **Microsoft Bridge Einstellungen**. Hier können Sie:

  - Die Telefonnummern anzeigen, die von Office 365 zur Verwendung für Audio Conferencing festgelegt werden.

  - Zeigen Sie den Standort sowie die primären und sekundären Sprachen an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.

  - Wählen Sie die Standardtelefonnummer aus, die Benutzer erhalten, wenn sie für Audiokonferenzen aktiviert werden. Wenn jedoch die Standardtelefonnummer für die Audiokonferenzbrücke geändert wird, ändert sich die Standardtelefonnummer für vorhandene Benutzer nicht.

Sie können zu **Audio Conferencing** > **Benutzer** gehen und die Eigenschaften des Benutzers wählen, um die Standardnummer für einen Benutzer zu ändern, indem Sie eine neue Nummer aus der Liste von Nummern wählen, die in Ihrer Organisation zur Verfügung stehen.

Siehe [Anzeigen einer Liste mit Telefonnummern für Audio Conferencing](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Hier finden Sie eine Liste der Benutzer, die aktiviert sind

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz) und dann zu **Benutzer**.

Siehe [Anzeigen einer Liste der Benutzer, die für Einwahlkonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Es gibt mehrere Einstellungen, die auf Organisationsebene mithilfe von Windows PowerShell verwaltet werden können. Dies macht es einfach, Einstellungen für alle Benutzer zu übernehmen.

Weitere Hilfe für jedes Cmdlet, erhalten Sie unter [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

Hier sind die Einstellungen auf Organisationsebene:

- **Einstellung Eintrag/Exit Benachrichtigungen** Der Standardwert ist _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Einstellung von Namen-Aufzeichnung** Der Standardwert ist _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Einstellung der PIN-Länge** Der Standardwert ist 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Einstellung von nur Einwahl-Meetings über ein Telefon** Standard ist _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Festlegen, ob E-Mails an Benutzer gesendet werden** Der Standardwert ist _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Festlegen, ob E-Mail von einem anderen Konto gesendet wird** Der Standardwert ist _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Festlegen der Absenderadresse auf E-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Festlegen des Anzeigenamens für die E-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Einstellungen für Audio Conferencing für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user.md)


