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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Lesen Skype for Business Onlineschritte zum Zuweisen einer Lizenz für Einwahlkonferenzen und einer Konferenz-ID zu einem Benutzer und vielen anderen Einstellungen für Einwahlkonferenzen. '
ms.openlocfilehash: 0bed95f9f5b8429dce52333046cd8c732c4bc0e9d94539d92c1e96f2d3284172
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306238"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Verwalten der Einstellungen von Audio Conferencing für meine Organisation in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Wenn Sie in Microsoft Teams diese Einstellungen verwalten möchten, sehen Sie[Verwalten der Einstellungen für Audio Conferencing für meine Organisation im Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Möglicherweise ist es für Sie einfacher, alle Audiokonferenzeinstellungen für die Skype for Business an einem Ort zu sehen.


## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audiokonferenzen

> [!NOTE]
> Sie können lizenzen nicht über das Admin Center **Skype for Business zuweisen.** Sie müssen die Microsoft 365 Admin Center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **So weisen Sie einem Benutzer eine Lizenz zu**

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Navigieren Sie in der linken Navigationsleiste des Admin Centers zu Benutzer aktive Benutzer , und wählen Sie dann den oder die Benutzer aus der Liste der verfügbaren Benutzer  >  aus.

    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**. Mit Windows PowerShell können Sie auch mehreren Benutzern Lizenzen zuweisen. Anweisungen und PowerShell-Beispielskripts finden Sie unter [Zuweisen Skype for Business Lizenzen.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.

4. Aktivieren Sie **auf der Seite** Produktlizenzen die Schaltfläche Audio **conferencing (Audiokonferenz),** und klicken Sie dann auf **Speichern.** Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Nachdem Sie die Lizenz zugewiesen haben, wird Microsoft möglicherweise nicht zuerst in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall beim Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren von E-Mails, die an Audiokonferenzbenutzer gesendet wurden

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center > **Skype for Business** und klicken Sie in der linken Navigationsleiste auf **Audio conferencing (Audiokonferenz).**

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

    Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer

Sie können Änderungen an der E-Mail vornehmen, die automatisch an Ihre Benutzer gesendet wird, einschließlich der tatsächlichen E-Mail-Adresse und des Anzeigenamens der Kontaktinformationen des Absenders. Standardmäßig ist der Absender der E-Mails Microsoft 365 oder Office 365, aber Sie können die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und dem [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) ändern. So ändern Sie die E-Mail-Adresse, die als Absender von E-Mail-Nachrichten an Benutzer verwendet wird:

- Geben Sie die E-Mail-Adresse in den Parameter _SendEmailFromAddress_ ein.

- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.

- Legen Sie den Parameter _SendEmailOverride_ auf _True_ fest.

Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.

Sie können das [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) verwenden, um andere Einstellungen für Ihre Organisation zu verwalten, einschließlich E-Mail.

Weitere [Informationen finden Sie unter E-Mails,](emails-sent-to-users-when-their-settings-change.md)die automatisch an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern.

## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie im Aktionsbereich unter **Konferenzkennung** auf **Zurücksetzen**.

4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenzkennung generiert und per E-Mail an den Benutzer gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. Standardmäßig ist dies aktiviert.

    > [!IMPORTANT]
    >  Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Benutzer können das Skype for Business Meeting Migration Tool verwenden, um ihre vorhandenen Besprechungen zu aktualisieren. Informationen zum Herunterladen, Installieren und Ausführen des Skype for Business Meeting Update Tools finden Sie unter: Meeting Update Tool für Skype for Business und [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4) [Skype for Business Online, Meeting Migration Tool (64-Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)und [Skype for Business Online, Meeting Migration Tool (32-Bit).](https://www.microsoft.com/download/details.aspx?id=54079)

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Konferenzkennungen werden zwar automatisch erstellt und Benutzern zugewiesen, es kann aber sein, dass Benutzer diese Nummer nicht verwenden möchten und Sie sie auf eine bestimmte Nummer festlegen möchten oder die Benutzer ihre Konferenz-ID vergessen oder verloren haben. Sie können das Skype for Business Administrationscenter und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.


1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center > **Skype for Business** und klicken Sie in der linken Navigationsleiste auf **Audio conferencing (Audiokonferenz).**

3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.

4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.

Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt.

Weitere [Informationen finden Sie unter Zurücksetzen der Audiokonferenz-PIN.](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center > **Skype for Business** und klicken Sie in der linken Navigationsleiste auf **Audio conferencing (Audiokonferenz).**

3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.

4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. |||UNTRANSLATED_CONTENT_START|||In the left navigation, go to **Audio conferencing** > **Users**.|||UNTRANSLATED_CONTENT_END||| Wählen Sie den Benutzer aus, den Sie für Audiokonferenzen aktivieren möchten.

4. Im Aktionsbereich können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.

5. Klicken Sie auf **Speichern**.

Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Auswählen der Einstellungen für die Audiokonferenzbrücke

**Festlegen der Besprechungserfahrung, wenn Anrufer an einer Besprechung teilnehmen**


1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Wechseln Sie **Skype for Business linken** Navigationsbereich im Admin Center zu **Audio conferencing**  >  **Microsoft Bridge-Einstellungen**.

4. Wählen Sie unter **Besprechungsteilnahme** die folgenden Aktionen aus:

   - **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits standardmäßig an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.

     Dies kann für eine Besprechung festgelegt werden, wenn ein Benutzer einer Besprechung mit einer  Skype for Business-App beitritt und die Einstellung Beim  Betreten oder Verlassen von Personen ankündigen im Menü Skype-Besprechung-Optionen der Besprechung geändert wird.

   - **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.

5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Wechseln Sie **Skype for Business linken** Navigationsbereich im Admin Center zu **Audio conferencing**  >  **Microsoft Bridge-Einstellungen**.

4. Geben Sie unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.
    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center > **Skype for Business** und klicken Sie in der linken Navigationsleiste auf **Audio conferencing (Audiokonferenz).**

3. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**.

    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Konferenzinformationen per E-Mail senden**.

    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

    Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Lesen und Festlegen der primären (Standard) und sekundären (alternativen) Sprachen für eine Audiokonferenzbrücke


1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.

4. Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festlegen** und dann auf der Seite **Sprachen festlegen** auf die Liste **Primäre Sprache**. In dieser Liste werden alle unterstützten Sprachen angezeigt.

    Außerdem können Sie die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Audiokonferenzanbieter auswählen. Die Reihenfolge, in der Sie Ihre Auswahl in den Dropdownlisten treffen, entspricht der Reihenfolge, in der die Sprachen Anrufern genannt werden.

Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**
 
3. Navigieren Sie **Skype for Business linken** Navigationsbereich im Admin **Center zu Audio conferencing** Microsoft  >  **Bridge**. Hier können Sie:

   - Zeigen Sie die Telefonnummern an, die von der Microsoft 365 oder Office 365, die für Audiokonferenzen verwendet werden sollen.

   - Zeigen Sie den Standort sowie die primären und sekundären Sprachen an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.

   - Wählen Sie die Standardtelefonnummer aus, die Benutzer erhalten, wenn sie für Audiokonferenzen aktiviert werden. Wenn jedoch die Standardtelefonnummer für die Audiokonferenzbrücke geändert wird, ändert sich die Standardtelefonnummer für vorhandene Benutzer nicht.

Sie können zu **Benutzer von Audiokonferenzen** wechseln und die Eigenschaften des Benutzers auswählen, um die Standardnummer für einen Benutzer zu ändern, indem Sie eine neue Nummer aus der Liste der in Ihrer Organisation verfügbaren Nummern  >   auswählen.

Weitere Informationen finden Sie unter Sehen Sie sich [eine Liste der Audiokonferenznummern an.](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz) und dann zu **Benutzer**.

Siehe [Anzeigen einer Liste der Benutzer, die für Einwahlkonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Es gibt mehrere Einstellungen, die Sie auf Organisationsebene mithilfe von Einstellungen Windows PowerShell. Dies erleichtert das Anwenden von Einstellungen auf alle Benutzer.

Weitere Hilfe zu den einzelnen Cmdlets finden Sie unter Skype for Business [Online-Cmdlets.](/previous-versions//mt228132(v=technet.10))

Dies sind die Einstellungen auf Organisationsebene:

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

  ## <a name="want-to-know-more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Admin Centers viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Die Einstellungen für viele Benutzer gleichzeitig ändern. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user.md)
