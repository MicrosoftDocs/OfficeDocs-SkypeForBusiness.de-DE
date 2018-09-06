---
title: Verwalten der Audiokonferenz Einstellungen für meine Organisation im Microsoft-Teams
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Finden Sie unter Microsoft-Teams Schritte eines Benutzers und viele andere Einstellungen für einwahlkonferenzen eine einwahlkonferenzen Lizenz und Konferenz-ID zugewiesen. '
ms.openlocfilehash: 2e372c76cbbedeaa7558b4308366262e93cb5b91
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780372"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenz Einstellungen für meine Organisation im Microsoft-Teams

Alle für die Audiokonferenz für Microsoft-Teams an einem Ort finden Sie unter erleichtert möglicherweise. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audiokonferenzen

> [!NOTE]
> Sie können keine Lizenzen von Teams zuweisen. Sie müssen das Office 365 Administrationscenter verwenden. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 **So weisen Sie eine Lizenz für einen Benutzer zu**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.
    
    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**.  
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**. 
    
4. Aktivieren Sie auf der Seite **Produktlizenzen** die Option **Audio Conferencing** (Audiokonferenz), und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder Deaktivieren von **Benutzern Wenn Ändern ihrer Einstellungen für die Zugriffsnummer für Einwahl-e-Mails automatisch gesendet**.

4. Klicken Sie auf **Speichern**.

    
**Verwenden von Windows PowerShell**
  
Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer

Sie können die e-Mail-Nachricht ändern, die automatisch an Ihre Benutzer, einschließlich der tatsächliche e-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders gesendet wird. In der Standardeinstellung der Absender der e-Mail ist Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell. Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen**auf **Konferenz-ID zurückgesetzt**.  

4. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Zurücksetzen**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Zurücksetzen der PIN eines Organisators einer Konferenz

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten und es eine bestimmte Anzahl festgelegt werden soll, oder Ihre Benutzer können nicht merken oder verloren haben ihre Konferenz-ID. 

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen**klicken Sie auf **Zurücksetzen PIN**und klicken Sie dann auf **Zurücksetzen**. 
  
    
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt. 
  
Finden Sie unter [der Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit den Informationen zur Audiokonferenz an einen Benutzer

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen**auf **Konferenz Informationen in e-Mail-Nachricht senden**. 

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet. 

  
Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Festlegen des Telefons, die Zahlen enthalten auf invites

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.
 
3. Klicken Sie im Bereich **Audiokonferenzen** können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.

4. Klicken Sie auf **Speichern**.
    
Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Audiokonferenzen Bridge Einstellungen auswählen

**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**


1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Einstellungen Bridge** **und**aktivieren Sie oder deaktivieren Sie Besprechungseintrag Benachrichtigungen zu beenden.

    Dies ist standardmäßig aktiviert. Wenn Sie diese Option deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn jemand Beitritt oder die Besprechung verlässt.

4. Wählen Sie unter **Entry/Exit Ankündigung Typ** **Töne** oder **Namen, oder Rufnummern**. 

    Wenn Sie den **Namen oder die Telefonnummern**auswählen, können Sie auch auswählen, aktivieren oder Deaktivieren von **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen**. 

5. Klicken Sie auf **Speichern**.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Einstellungen Bridge** Geben Sie die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**


1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder deaktivieren **für Benutzer-e-Mails automatisch gesendet, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.

4. Klicken Sie auf **Speichern**. 
 
    Sie können auch den e-Mail an den Benutzer mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen in e-Mail-Nachricht senden**.
    
    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Finden Sie unter, und legen Sie die primären (Standard) und die sekundären Sprachen (alternative) auf eine audiokonferenzbrücke

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.

3. Wählen Sie die Sprachen, die Sie unter **Default Language** und **(optional) alternative Sprachen**werden soll.


Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen


1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**. Hier können Sie:
    
  - Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden. 
    
  - Schauen Sie den Speicherort und die primäre Sprache, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.

  
Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


