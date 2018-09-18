---
title: Verwalten der Audiokonferenzeinstellungen für meine Organisation in Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie Informationen zu den Schritten, mit denen Sie in Microsoft Teams einem Benutzer eine Lizenz für Dial-in-Konferenzen und eine Konferenzkennung zuweisen, sowie zu vielen anderen Einstellungen für Dial-in-Konferenzen. '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884705"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenzeinstellungen für meine Organisation in Microsoft Teams

Möglicherweise ist es einfacher für Sie, alle Audiokonferenzeinstellungen für Microsoft Teams an derselben Stelle zu sehen. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audiokonferenzen

> [!NOTE]
> Sie können mit Microsoft Teams keine Lizenzen zuweisen. Dazu müssen Sie das Office 365 Admin Center verwenden. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 **So weisen Sie eine Lizenz für einen Benutzer zu**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.
    
    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Submit** (Übermitteln).  
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**. 
    
4. Aktivieren Sie auf der Seite **Produktlizenzen** die Option **Audio Conferencing** (Audiokonferenz), und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.

4. Klicken Sie auf **Speichern**.

    
**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer

Sie können Änderungen an der E-Mail vornehmen, die automatisch an Benutzer gesendet wird. Dazu gehören die tatsächliche E-Mail-Adresse und der Anzeigename in den Kontaktinformationen des Absenders. Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern. Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="reset-the-meeting-conference-id"></a>Zurücksetzen der Konferenzkennung der Besprechung

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.  

4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Zurücksetzen**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. Diese Option ist standardmäßig aktiviert.

Siehe [Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Zurücksetzen der PIN eines Konferenzorganisators

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Obwohl Konferenzkennungen automatisch generiert und Benutzern zugewiesen werden, kann es vorkommen, dass Benutzer diese Nummer nicht verwenden möchten und Sie daher eine bestimmte Nummer festlegen müssen. Es ist auch möglich, dass Benutzer ihre Konferenzkennung vergessen oder verloren haben. 

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **PIN zurücksetzen**, und klicken Sie dann auf **Zurücksetzen**. 
  
    
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt. 
  
Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **Send conference info in email** (Konferenzinformationen per E-Mail senden). 

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet. 

  
Siehe [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.
 
3. Im Bereich **Audiokonferenz** können Sie die **Gebührenpflichtige Nummer** und, wenn dies zulässig ist, die **Gebührenfreie Nummer** festlegen.

4. Klicken Sie auf **Speichern**.
    
Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Auswählen von Einstellungen für die Audiokonferenzbrücke

**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**


1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).

    Diese Option ist standardmäßig aktiviert. Wenn Sie sie deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, standardmäßig nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.

4. Wählen Sie unter **Entry/exit announcement type** (Typ der Ankündigung für Zu- und Abgänge) die Option **Tones** (Töne) oder **Namen oder Telefonnummern** aus. 

    Wenn Sie **Namen oder Telefonnummern** ausgewählt haben, können Sie auch die Option **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen** aktivieren oder deaktivieren. 

5. Klicken Sie auf **Speichern**.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Geben Sie auf der Seite **Bridge settings** (Brückeneinstellungen) in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus vier bis zwölf Ziffern bestehen. Standardmäßig werden fünf Ziffern verwendet.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren der an Audiobenutzer gesendeten E-Mails**


1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Automatically send emails to users if their audio conferencing settings change** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**. 
 
    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).
    
    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Anzeigen und Festlegen der primären Sprache (Standardsprache) und der sekundären Sprachen (alternativen Sprachen) für eine Audiokonferenzbrücke

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie in der Liste eine Telefonnummer aus, und klicken Sie auf **Bearbeiten**.

3. Wählen Sie unter **Default language** (Standardsprache) und **Alternate languages (optional)** (Alternative Sprachen (optional)) die gewünschten Sprachen aus.


Siehe [Festlegen der Sprachen für die automatische Telefonzentrale für Audiokonferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Dial-in-Nummern für Audiokonferenzen


1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie in der Liste eine Telefonnummer aus, und klicken Sie auf **Bearbeiten**. Hier haben Sie folgende Möglichkeiten:
    
  - Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden. 
    
  - Zeigen Sie den Standort sowie die primäre Sprache an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.

  
Siehe [Anzeigen einer Liste mit Audiokonferenz-Telefonnummern](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


