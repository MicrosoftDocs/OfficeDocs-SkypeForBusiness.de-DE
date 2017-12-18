---
title: "Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
description: "Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. "
---

# Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](26ea19d3-e420-4fc1-baa3-2692d17e5e1d.md#MT_Footer).  
  
Audiokonferenzanbieter standardmäßig senden e-Mail an die Benutzer an, wenn sie für Audiokonferenzanbieter aktiviert sind. Es kann vorkommen durch, wenn Sie zum Verringern der Anzahl der e-Mail-Nachrichten, die an Skype für Business und Microsoft Teams Benutzer gesendet werden sollen, und in diesem Fall Sie können diese Option deaktivieren.
  
Wenn Sie beim Senden von e-Mails deaktivieren, werden alle Audiokonferenzanbieter e-Mails an die Benutzer e-Mails für Wenn Benutzer aktiviert oder deaktiviert für Audiokonferenzanbieter, wenn seine PIN zurückgesetzt wird, wenn die Konferenz-ID und das standardmäßige Konferenzen Zahl Änderungen Telefon, einschließlich gesendet.
  
Hier ist ein Beispiel für die e-Mail, die an Benutzer gesendet wird, wenn sie für Audio Konferenzen aktiviert sind:
  
![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere e-Mail-Nachrichten, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzanbieter aus:
    
  - Wenn eine Lizenz **Audio Konferenzen** zu zugewiesen wird.
    
  - Wenn Sie manuell des Benutzers Audiokonferenzanbieter PIN zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn die Lizenz **Audio Konferenzen** daraus entfernt wird.
    
  - Wenn der Audiokonferenzanbieter eines Benutzers Nachschlagen von Microsoft zu einem anderen Anbieter oder **keine** geändert wird.
    
  - Wenn der Audiokonferenzanbieter eines Benutzers an Microsoft geändert wird.
    
## Aktivieren oder Deaktivieren von e-Mails an Benutzer gesendet wird

Sie können das Senden von E-Mails an Benutzer über das Skype for Business Admin Center oder die Windows PowerShell aktivieren oder deaktivieren.
  
 **Verwenden die Skype für Business Administrationscenter**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365-Verwaltungskonsole** > **Skype for Business**, und klicken Sie im linken Navigationsbereich auf **Audio Konferenzen**.
    
3. Klicken Sie auf der Einstellungsseite **Bridge Microsoft** aktivieren Sie oder deaktivieren Sie die **automatisch e-Mails an Benutzer senden, wenn keines der Audiokonferenzanbieter Konfiguration Änderungen**.
    
4. Klicken Sie auf **Speichern**.
    
    > [!TIP]
    > Sie können e-Mail auch für den Benutzer mit den Einstellungen Audiokonferenzanbieter senden, indem Sie auf die Eigenschaften des Benutzers > **Audio Konferenzen** > **Konferenz Informationen per e-Mail senden**. > Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN. > Finden Sie unter [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-audio-conferencing-information.md). 
  
 **Mithilfe von Windows PowerShell**
  
- Führen Sie Folgendes aus, um das Senden von E-Mails zu deaktivieren: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Damit Sie mit diesem Cmdlet können, finden Sie unter [Festlegen-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## Was sollten Sie noch wissen?

- Wenn automatische e-Mails deaktiviert sind, können Sie weiterhin manuell auslösen, senden eine e-Mail-Nachricht mit der Konferenz-ID und Telefonnummer den Skype für Business-Verwaltungskonsole verwenden. In diesem Fall wird nicht die PIN jedoch aufgenommen werden. Wenn Sie den Audiokonferenzanbieter PIN zurücksetzen möchten, und Senden von e-Mails deaktiviert ist, müssen Sie es in eine andere Methode an den Benutzer senden.
    
- Standardmäßig der Absender die e-Mail-Nachrichten werden von Office 365, aber ändern Sie die e-Mail-Adresse und Anzeigename bei der Verwendung von Windows PowerShell und auch das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) " verwenden.
    
    > [!NOTE]
    > Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihrer Umgebung für eingehende E-Mails zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden. 
  
  - Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
  - Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
  - Den Parameter  _SendEmailOverride_ auf _True_ einstellen.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Sie können diese Cmdlets auch verwenden, um Zeit zu sparen oder um dies zu automatisieren.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Entfernen-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Einwahlkonferenzen in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

