---
title: Ändern der Einstellungen für eine Audiokonferenzbrücke
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/03/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Get the steps you need to change settings for a conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business or Microsoft Teams apps. "
ms.openlocfilehash: 727392bc81bce2fb3cfd84029e6a275e1eed3e24
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Ändern der Einstellungen für eine Audiokonferenzbrücke

Beim Einrichten von Audiokonferenzen in Office 365 erhalten Sie von einer sogenannten Audiokonferenzbrücke Telefonnummern für Ihre Benutzer. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist am Ende der Skype for Business- oder Microsoft Teams-Besprechungseinladung zu finden.
  
Die Konferenzbrücke nimmt den Anruf an und gibt Sprachanweisungen einer automatischen Telefonzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. Besprechungsorganisatoren erhalten PINs, damit sie eine Besprechung starten können, wenn sie keine Skype for Business- oder Microsoft Teams-App verwenden.

  > [!IMPORTANT]
  > Der Besprechungsorganisator benötigt nur dann eine PIN, wenn die Besprechung nicht bereits von einem Benutzer einer Skype for Business- oder Microsoft Teams-App gestartet wurde. Wenn sich alle Teilnehmer in die Besprechung einwählen, benötigt der Besprechungsorganisator die PIN zum Starten der Besprechung. 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a>Using the Microsoft Teams and Skype for Business Admin Center

1. In the left navigation, go to **Meetings** > **Conference bridges**. 

2. At the top of the **Conference bridges** page, click **Bridge settings**. 

3. In the **Bridge settings** pane, select: 
  - **Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.
    
    When you turn on **Meeting entry and exit notifications**, you can select these options:
    
  - **Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.
    
  - **Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.
      
  - **Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.

4. To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.

5. To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.
    See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.
 
6. Klicken Sie auf **Anwenden**. 

## <a name="using-skype-for-business-admin-center"></a>Using Skype for Business admin center

 **Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**
    
1. In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. Wählen Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Besprechungsteilnahme** Folgendes aus:
    
  - **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.
    
    Bei Auswahl von **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren** können Sie diese Optionen in der Liste **Entry/exit announcement type** (Typ der Benachrichtigung bei Zu- oder Abgang) auswählen:
    
  - **Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.
    
  - **Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.
  
  - **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.
    
3. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
**Festlegen der Länge der PIN für Besprechungen**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Geben Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.
    
    > [!IMPORTANT]
    > Die PIN muss aus 4 bis 12 Ziffern bestehen. 
  
**Auswählen, ob E-Mails an Ihre Benutzer gesendet werden sollen**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.
    
    See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>See Also

[Einrichten von Audiokonferenzen](set-up-audio-conferencing.md)
