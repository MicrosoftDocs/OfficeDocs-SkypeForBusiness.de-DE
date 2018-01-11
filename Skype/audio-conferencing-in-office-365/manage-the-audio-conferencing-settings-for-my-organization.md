---
title: "Die Audiokonferenz Einstellungen für meine Organisation verwalten"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Finden Sie unter Schritte aus, um einem Benutzer, richten Sie ein Drittanbieter-Konferenzanbieter und viele andere Einstellungen für einwahlkonferenzen eine einwahlkonferenzen Lizenz und Konferenz-ID zuweisen. "
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Die Audiokonferenz Einstellungen für meine Organisation verwalten

Alle für die Audiokonferenz für Skype für Unternehmen und die Microsoft-Teams, an einem Ort finden Sie unter erleichtert möglicherweise. 
  
## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Audiokonferenz-Lizenzvertrags

> [!NOTE]
> Sie können nicht mithilfe der **Skype für Business Administrationscenter**Lizenzen zuweisen. Sie müssen das Office 365 Administrationscenter verwenden. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **So weisen eine Lizenz für einen Benutzer**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie im linken Navigationsbereich des **Office 365 Administrationscenter**, **Benutzern** > **aktive Benutzer**, und wählen Sie dann den oder die Benutzer aus der Liste der verfügbaren Benutzer aus.
    
    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie die Dropdownliste **Wählen Sie eine Ansicht** verwenden und klicken Sie dann wählen Sie eine der Optionen oder Ihre eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten**, **Weiter** zweimal und klicken Sie dann wählen Sie die Lizenz aus, und klicken Sie auf **Absenden**. Sie können mehrere Benutzer auch mithilfe von Windows Powershell Lizenzen zuweisen. Anweisungen und PowerShell-Skriptbeispiele finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**. 
    
4. Klicken Sie auf der Seite **Lizenzen** aktivieren Sie **Audiokonferenzen** , und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Nachdem Sie die Lizenz zugewiesen haben, kann Microsoft nicht zunächst in der Liste als Audiokonferenzanbieter angezeigt. In diesem Fall melden Sie sich im Office 365 Administrationscenter, oder drücken Sie STRG + F5, um das Browserfenster zu aktualisieren. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Weisen Sie eine Konferenz-ID für einen Benutzer

Eine Konferenz-ID wird automatisch zu einem Benutzer zugewiesen, wenn sie für Audiokonferenzen mit Microsoft als Anbieter von Audiokonferenzen festgelegt sind. Die Konferenz-ID zugewiesen werden kann, statische oder dynamische und wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist. 
  
Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder wählen Sie eine, die leicht zu merken ist. Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen So weisen Sie dynamische statt statische Konferenz-IDs, finden Sie unter [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Die Skype für Business-Verwaltungskonsole kann nicht verwendet werden, um eine Konferenz-ID, die einem Benutzer zuweisen, aber Sie können dazu das Windows PowerShell-Cmdlet verwenden.
  
Wenn die Konferenz-ID für einen Benutzer festlegen möchten, führen Sie Folgendes aus:
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Eine Konferenz-ID muss 7 Ziffern enthalten, und Sie ihn in die Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell nicht ändern können. 
  
Finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) erfahren Sie mehr über das Cmdlet.
  
> [!IMPORTANT]
>  Nachdem eine neue Konferenz-ID erstellt wurde, kann nicht die alte Konferenz-ID BSSID verwendet werden. Informieren Sie Benutzer von Plänen ihrer vorhandenen meeting-Einladungen für sicher, dass die neue Konferenz ansetzen, die ID der Einladungen hinzugefügt wird. Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen. Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und Skype für Online Business [Besprechung Migrationstool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Finden Sie unter [finden Sie unter, ändern, und setzen Sie eine Konferenz-ID, die einem Benutzer zugewiesenen zurück](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Ändern des Audiokonferenz-Anbieters von Microsoft mit einem Drittanbieter-Anbieter

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und klicken Sie dann, und wählen Sie den Benutzer, die Sie den Audiokonferenz-Anbieter für ändern möchten.
    
4. Klicken Sie im Bereich „Aktion" auf **Bearbeiten**. 
    
5. Wählen Sie auf **der Eigenschaftenseite unter **Anbietername**** den Anbieter von Audiokonferenzen für den Benutzer.
    
    > [!NOTE]
    > Wenn Sie mehrere Benutzer ausgewählt haben, können Sie nur Microsoft als Anbieter von Audiokonferenzen oder **keine** auswählen.
  
6. Klicken Sie auf **Speichern**. 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren Sie oder deaktivieren Sie e-Mails senden audiokonferenzbenutzer

Sie können die Skype für Business Administrationscenter oder mit Windows PowerShell verwenden, aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet.
  
 **Verwenden die Skype für Business-Verwaltungskonsole**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Aktivieren Sie auf der Seite **Microsoft-Brücke Einstellungen** , oder deaktivieren Sie, die **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.
    
4. Klicken Sie auf **Speichern**.
    
    Sie können auch den-e-Mails für den Benutzer mit den Einstellungen Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen per e-Mail senden**. Die Konferenz-ID und Standardwerte in der Audiokonferenz Telefonnummer ist auf die Besprechung einladen, aber nicht die PIN enthalten.
    
    Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).
    
 **Mithilfe von Windows PowerShell**
  
- Sie können auch die Windows PowerShell verwenden und ausführen: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Das [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie um andere Einstellungen für Ihre Organisation, einschließlich e-Mail zu verwalten.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Ändern von Kontaktinformationen des Absenders in e-Mail-Nachrichten an Benutzer gesendet

Sie können die e-Mail-Nachricht ändern, die automatisch an Ihre Benutzer, einschließlich der tatsächliche e-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders gesendet wird. Standardmäßig ist des Absenders der e-Mail Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Um die e-Mail-Adresse ändern, die die e-Mail-Nachricht an die Benutzer senden, müssen Sie folgende Aktionen ausführen:
  
- Geben Sie die e-Mail-Adresse in der _SendEmailFromAddress_ -Parameter.
    
- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
- Den Parameter _SendEmailOverride_ auf _True_festgelegt.
    
Sie können die Änderungen an der e-Mail an Benutzer, wie die e-Mail-Adresse, der von die e-Mail gesendet wird oder den Anzeigenamen für die e-Mail-durch Ausführen von vornehmen:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Wenn Sie die Informationen der e-Mail-Adresse ändern möchten, müssen Sie sicherstellen, dass die eingehenden e-Mail-Adressrichtlinien Ihrer Organisation-e-Mails zulassen, die von der benutzerdefinierten e-Mail-Adresse stammen.
  
Das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " können Sie um andere Einstellungen für Ihre Organisation, einschließlich e-Mail zu verwalten.
  
Finden Sie unter [-e-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Zurücksetzen die Besprechung Konferenz-ID

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie an der **Audiokonferenz**, und klicken Sie im Aktionsbereich unter **Konferenz-ID**der **Skype für Business Administrationscenter**, im Navigationsbereich, klicken Sie auf **Zurücksetzen**.
    
4. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**. Eine Konferenz-ID wird automatisch erstellt und eine e-Mail an den Benutzer mit der neuen Konferenz-ID gesendet, wenn Senden von e-Mails an Ihre Benutzer aktiviert ist. Es ist standardmäßig aktiviert.
    
    > [!IMPORTANT]
    >  Nachdem eine neue Konferenz-ID erstellt wurde, kann nicht die alte Konferenz-ID BSSID verwendet werden. Informieren Sie Benutzer von Plänen ihrer vorhandenen meeting-Einladungen für sicher, dass die neue Konferenz ansetzen, die ID der Einladungen hinzugefügt wird. Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen. Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter: [Besprechung Update-Tool für Skype für Unternehmen und Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Meeting-Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047), und [Skype für Unternehmen Online, Besprechung Migrationstool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Zurücksetzen der PIN eines Organisators einer Konferenz

Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist. Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen Wenn Sie zuweisen dynamische statt statische-Konferenz-IDs, [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Zwar eine statische Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten und es eine bestimmte Anzahl festgelegt werden soll, oder Ihre Benutzer können nicht merken oder verloren haben ihre Konferenz-ID. Sie können die Skype für Business Administrationscenter und Windows PowerShell verwenden, anzeigen, ändern und Zurücksetzen ihrer Konferenz-ID.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer, dem Sie für die PIN zurücksetzen möchten.
    
4. Klicken Sie im Aktionsbereich unter **PIN**, auf **Zurücksetzen**.
    
Benutzer erhalten eine e-Mail mit ihrer PIN, wenn sie aktiviert sind, für Audiokonferenzen oder wenn die PIN zurückgesetzt wird. Aber wenn Sie automatisch deaktiviert haben Senden von e-Mails, eine PIN zurücksetzen-e-Mail wird nicht gesendet werden und Sie müssen die PIN für den Benutzer manuell veranlassen. Die PIN-Nummer wird nur einmal angezeigt, nachdem er zurückgesetzt wurde. Nachdem sie direkt nach der zurückzusetzende angezeigt wird, wird nicht die PIN nicht mehr auf die Benutzereigenschaften angezeigt; Stattdessen *** angezeigt werden soll. 
  
Finden Sie unter [Audio Conferencing PIN eines Benutzers zurücksetzen](reset-the-audio-conferencing-pin-for-a-user.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden Sie eine e-Mail mit Audiokonferenz Informationen zu einem Benutzer

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer, dem Sie für die PIN zurücksetzen möchten.
    
4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.
    
    > [!NOTE]
    > Wenn Sie dies tun, wird nicht die Audiokonferenz PIN an den Benutzer gesendet. 
  
Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>Festlegen von Audiokonferenzen Standardrufnummer für Besprechungsorganisatoren

 **Festlegen der Audiokonferenz Standardrufnummer für Besprechungsorganisatoren, wenn Sie einen Benutzer für Audiokonferenzen aktivieren**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie im linken Navigationsbereich zur **Audiokonferenz** > **Benutzer**. Wählen Sie den Benutzer, den Sie für Audiokonferenzen aktivieren möchten.
    
4. Klicken Sie im Aktionsbereich in den Eigenschaften des Benutzers auf **Bearbeiten**.
    
5. Verwenden Sie auf der Seite **Eigenschaften** unter **Anbietername**der Dropdown Liste den Anbieter von Audiokonferenzen auswählen.
    
  - Wenn Sie Microsoft als Anbieter von Audiokonferenzen auswählen, können Sie Audiokonferenzen Standardrufnummer aus der Liste auswählen.  
    
  - Wenn Sie ein Drittanbieter-ACP als der Audiokonferenz-Anbieter auswählen, müssen Sie die gebührenpflichtige manuell eingeben und gegebenenfalls die gebührenfreie Telefonnummer. Diese Rufnummern werden die Standardrufnummer.
    
    Audiokonferenzen Standardrufnummer eines Benutzers ist die Nummer, die auf der besprechungseinladung angezeigt wird, wenn sie eine Besprechung planen.
    
6. Klicken Sie auf **Speichern**. 
    
Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md).
  
 **Festlegen der Audiokonferenz Standardrufnummer für Besprechungsorganisatoren, nachdem Sie einen Benutzer für die Audiokonferenz aktiviert haben**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer werden soll, und klicken Sie auf der Seite Aktion auf **Bearbeiten**.
    
4. Verwenden Sie auf der Seite **Eigenschaften** unter **Anbietername**der Dropdown Liste den Anbieter von Audiokonferenzen auswählen.
    
  - Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, können Sie die Standardrufnummer Audiokonferenzen aus der Liste auswählen.  
    
  - Wenn der Benutzer ein Drittanbieter-ACP als Anbieter von Audiokonferenzen verwendet wird, müssen Sie die gebührenpflichtige manuell eingeben und gegebenenfalls die gebührenfreie Telefonnummer.
    
    Audiokonferenzen Standardrufnummer eines Benutzers ist die Nummer, die auf der besprechungseinladung angezeigt wird, wenn sie eine Besprechung planen.
    
5. Klicken Sie auf **Speichern**. 
    
Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md).
  
## <a name="setting-audio-conferencing-bridge-settings"></a>Audiokonferenzen Bridge Einstellungen festlegen

 **Die besprechungsumgebung festgelegt, wenn der Anrufer an einer Besprechung teilnehmen**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Wählen Sie unter **Erleben Sie die Teilnahme an einer Besprechung**die folgenden Aktionen aus:
    
  - **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden** Diese Option ist standardmäßig ausgewählt. Wenn Sie dieses Kontrollkästchen deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn ein Benutzer eingibt oder die Besprechung verlässt.
    
    Dies kann für einzelne Besprechung von Besprechungen festgelegt werden, wenn ein Benutzer eine Besprechung mit einer Skype für Business oder Microsoft-Teams app Beitritt und diese ändern Sie die Einstellung **Announce Wenn Personen eingeben oder diese verlassen** Skype-Besprechung oder Microsoft-Teams, **Optionen** im Menü des der Besprechung.
    
  - **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen** Diese Option ist standardmäßig ausgewählt. Wenn Sie dieses Kontrollkästchen deaktivieren, werden nicht Anrufer aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen.
    
5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
Finden Sie unter [ändern die Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Legen Sie die PIN-Mindestlänge für Besprechungen**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Klicken Sie unter **Sicherheit**Geben Sie die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.
    
    Die PIN muss zwischen 4 und 12 Ziffern. Der Standardwert ist 5.
    
Finden Sie unter [ändern die Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren von e-Mail an audio-Benutzer gesendet wird**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Aktivieren Sie auf der Seite **Microsoft-Brücke Einstellungen** , oder deaktivieren Sie, die **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.
    
4. Klicken Sie auf **Speichern**.
    
    Sie können auch den e-Mail an den Benutzer mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen per e-Mail senden**.
    
    Wenn Sie dies tun, wird eine e-Mail gesendet werden, die nur enthält Konferenz-ID und Konferenztelefonnummer, doch die PIN nicht enthalten.
    
    Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>Finden Sie unter, und legen Sie die primären und sekundären Sprachen für eine audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In der **Skype für Business Administrationscenter**, im linken Navigationsbereich wechseln Sie zur **Audiokonferenz**, und klicken Sie dann auf **Microsoft-Brücke**.
    
4. Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festgelegt** , und klicken Sie dann auf der Seite **festlegen Sprachen** auf der Verwendung der Liste der **primären Sprache** , um die vollständige Liste der unterstützten Sprachen anzuzeigen.
    
    Sie können auch die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Anbieter von Audiokonferenzen auswählen. Die Reihenfolge, die Sie in den Listen auswählen ist der gleichen Reihenfolge, in der Sprachen zu den Anrufern dargestellt werden.
    
Finden Sie unter [Festlegen von automatischen Telefonzentralen Sprachen für Audiokonferenzen](set-auto-attendant-languages-for-audio-conferencing.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Finden Sie unter Einwahlnummern Audiokonferenzen

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft-Brücke**. Hier können Sie:
    
  - Zeigen Sie die Telefonnummern, die vom Office 365 festgelegt werden, für die Audiokonferenz verwendet werden soll. 
    
  - Lesen Sie den Speicherort und der primären und sekundären Sprachen, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.
    
  - Wählen Sie die Standardrufnummer, die Benutzern gewährt wird, wenn sie für Audiokonferenzen aktiviert sind. Jedoch wird nicht die Standardrufnummer über die audiokonferenzbrücke geändert wird, die Standardrufnummer für vorhandene Benutzer ändern.
    
Sie können wechseln Sie zur **Audiokonferenz** > **Benutzer** und wählen Sie die Eigenschaften des Benutzers ändern des Standard für einen Benutzer Zahlenformatvorlage wählen Sie eine neue Nummer aus der Liste von Zahlen, die in Ihrer Organisation zur Verfügung stehen.
  
Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Anzeigen einer Liste der Benutzer, die aktiviert sind

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen**> und anschließend **Benutzer**.
    
Sehen Sie [eine Liste von Benutzern, die für Audiokonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Es gibt mehrere Einstellungen, die auf Organisationsebene mithilfe von Windows PowerShell verwaltet werden können. Dies vereinfacht die Einstellungen gelten für alle Benutzer. 
    
Wenn Sie weitere Hilfe auf jedes Cmdlet erhalten möchten, finden Sie unter [Skype für Business Online Cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

Hier sind die Einstellungen auf Organisationsebene: 
> 
- **Eintrag/Exit Benachrichtigungen festlegen** Der Standardwert ist _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **Festlegen von Namen Aufzeichnung** Der Standardwert ist _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Festlegen der PIN-Länge** Der Standardwert ist 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Festlegen von nur Einwahl Besprechungen über ein Telefon** Die standardmäßige _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Festlegen, ob e-Mail an Benutzer senden** Der Standardwert ist _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Festlegen, ob e-Mail von einem anderen Konto gesendet** Der Standardwert ist _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Festlegen der Absenderadresse auf e-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_an. 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Festlegen der Anzeigename für die e-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_an.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie wissen, Weitere Informationen zu Windows PowerShell   
- Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind. Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie Einstellungen Änderungen für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenz Einstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user.md)

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

