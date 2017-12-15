---
title: "Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer

Es kann erforderlich sein, Benutzern ihre Einwahlkonferenzdaten zuzusenden. Dazu können Sie im Skype for Business Admin Center unter den Einwahleigenschaften für einen Benutzer auf **Konferenzinformationen per E-Mail senden** klicken. Wenn Sie diese E-Mail senden, enthält sie alle Einwahldaten, wie zum Beispiel:
  
- Die Konferenztelefon- oder Einwahltelefonnummer für den Benutzer.
    
- Die Konferenz-ID des Benutzers.
    
    > [!NOTE]
    > Feste Nummern werden verwendet, wenn sich die Mitarbeiter Ihres Unternehmens keine Zufallszahlenkombinationen merken möchten und es bevorzugen, eine bestimmte bzw. leicht zu merkende Nummer auszuwählen. Bei der Verwendung von dynamischen Konferenz-IDs wird für jede, vom Benutzer geplante Besprechung, eine eindeutige Konferenz-ID zugewiesen. Wenn Sie dynamische Konferenz-IDs zuweisen möchten, klicken Sie [Verwenden von Audiokonferenzanbieter dynamische IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)
  
So kann diese gesendete E-Mail aussehen:
  
![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Gehen Sie auf das **Office 365 Admin Center** > **Skype for Business** und klicken Sie in der linken Navigationsleiste auf **Einwahlkonferenzen**.
    
3. Klicken Sie auf **Benutzer mit eingehenden Verbindungen** und wählen Sie dann den Benutzer aus.
    
4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.
    
> [!TIP]
> Sie können dem Benutzer auch eine E-Mail über die Einwahlkonferenzeinstellungen senden. Navigieren Sie dazu zu den Benutzereigenschaften > **Einwahlkonferenzen** > **Konferenzinformationen per E-Mail senden**. 
  
## Was sollten Sie sonst über diese E-Mails wissen?

- Es gibt mehrere E-Mails, die Ihren Benutzern im Unternehmen nach ihrer Aktivierung für Einwahlkonferenzen gesendet werden:
    
  - Wenn ihnen eine Lizenz für **Skype for Business PSTN Conferencing** zugewiesen wird.
    
  - Wenn Sie die Einwahlkonferenz-PIN des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn ihnen die Lizenz für **Skype for Business PSTN Conferencing** entzogen wird.
    
  - Wenn sich der Anbieter von Einwahlkonferenzen eines Benutzers von Microsoft auf einen anderen Anbieter oder **Kein** ändert.
    
  - Wenn sich der Anbieter von Einwahlkonferenzen eines Benutzers von einem anderen auf Microsoft ändert.
    
- Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den angezeigten Namen mithilfe von Windows PowerShell und des Cmdlets [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=708983) ändern. Um Änderungen an der E-Mail-Adresse vorzunehmen, über die die E-Mail an die Benutzer gesendet wird, müssen Sie:
    
    > [!NOTE]
    > Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der festgelegten benutzerdefinierten Absenderadresse gesendet werden. 
  
  - Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
  - Den Parameter  _SendEmailOverride_ auf _True_ einstellen.
    
  - Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
    So senden Sie eine E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](http://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  

