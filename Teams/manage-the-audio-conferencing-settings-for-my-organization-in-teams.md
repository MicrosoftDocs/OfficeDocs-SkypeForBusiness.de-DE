---
title: Verwalten der Audiokonferenz Einstellungen für die Organisation im Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie Informationen zu den Schritten, mit denen Sie in Microsoft Teams einem Benutzer eine Lizenz für Dial-in-Konferenzen und eine Konferenzkennung zuweisen, sowie zu vielen anderen Einstellungen für Dial-in-Konferenzen. '
ms.openlocfilehash: bc2f51cabe73db326c5a070f75d55c30fb1af367
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531127"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenz Einstellungen für die Organisation im Microsoft-Teams

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
  
## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen**auf **Konferenz-ID zurückgesetzt**.  

3. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Zurücksetzen**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Zurücksetzen der PIN eines Organisators einer Konferenz

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten und es eine bestimmte Anzahl festgelegt werden soll, oder Ihre Benutzer können nicht merken oder verloren haben ihre Konferenz-ID. 

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen**klicken Sie auf **Zurücksetzen PIN**und klicken Sie dann auf **Zurücksetzen**. 
  
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt. 
  
Finden Sie unter [der Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit den Informationen zur Audiokonferenz an einen Benutzer

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen**auf **Konferenz Informationen in e-Mail-Nachricht senden**. 

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet. 

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.
 
3. Klicken Sie im Bereich **Audiokonferenzen** können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.

4. Klicken Sie auf **Speichern**.
    
Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Auswählen von Audiokonferenzen Brücke

**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).

    Dies ist standardmäßig aktiviert. Wenn Sie diese Option deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn jemand Beitritt oder die Besprechung verlässt.

4. Wählen Sie unter **Entry/Exit Ankündigung Typ** **Töne** oder **Namen, oder Rufnummern**. 

    Wenn Sie den **Namen oder die Telefonnummern**auswählen, können Sie auch auswählen, aktivieren oder Deaktivieren von **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen**. 

5. Klicken Sie auf **Speichern**.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Einstellungen Bridge** Geben Sie die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder deaktivieren **für Benutzer-e-Mails automatisch gesendet, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.

4. Klicken Sie auf **Speichern**. 
 
    Sie können auch den e-Mail an den Benutzer mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen in e-Mail-Nachricht senden**.
    
    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Finden Sie unter, und legen Sie die primären (Standard) und die sekundären Sprachen (alternative) auf eine audiokonferenzbrücke

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.

3. Wählen Sie die Sprachen, die Sie unter **Default Language** und **(optional) alternative Sprachen**werden soll.

4. Klicken Sie auf **Speichern**.


Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**. Hier können Sie:
    
   - Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden. 
    
   - Schauen Sie den Speicherort und die primäre Sprache, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.

  
Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


