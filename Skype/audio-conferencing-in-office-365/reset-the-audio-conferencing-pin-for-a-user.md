---
title: "Zurücksetzen der Einwahlkonferenz-PIN für einen Benutzer"
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
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# Zurücksetzen der Einwahlkonferenz-PIN für einen Benutzer

Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Benutzer erzeugt wird, der für Einwahlkonferenzen aktiviert ist. Der Organisator einer Besprechung verwendet eine PIN für Einwahlkonferenzen, um sich als Organisator der Besprechung auszuweisen und eine Besprechung per Telefon zu starten. Wenn der Organisator den Skype for Business-Client zum Starten der Besprechung verwendet, ist keine PIN erforderlich. Vergisst ein Benutzer seine PIN und kann sie nicht in der E-Mail finden, die er bei seiner Aktivierung für Einwahlkonferenzen erhalten hat, muss ein Administrator seine eigene PIN zurücksetzen. Ein Benutzer kann seine eigene PIN nicht zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein berechtigter Benutzer über einen Skype for Business-Client teilnimmt oder wenn der Organisator per Telefon mit seiner PIN teilnimmt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.
  
## 

### Zurücksetzen der PIN eines Organisators einer Konferenz

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business** und klicken Sie in der linken Navigationsleiste auf **Einwahlkonferenzen**.
    
3. Klicken Sie auf **Benutzer mit eingehenden Verbindungen** und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.
    
4. Klicken Sie im Bereich „Aktion" auf **PIN zurücksetzen**.
    
## Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird. Nach dem Zurücksetzen der PIN durch einen Administrator wird die PIN im Skype for Business Admin Center und bei Verwendung von **Get-CsCsOnlineDialInConfencingUser** in der Windows PowerShell in den Ergebnissen als *********** dargestellt.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Einwahlkonferenzen aktiviert werden oder ihre PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird dem Benutzer allerdings keine E-Mail zum Zurücksetzen einer PIN gesendet. In diesem Fall müssen Sie dem Benutzer die PIN-Informationen manuell senden.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Standardmäßig ist eingestellt, dass Besprechungen nicht von einem anonymen Anrufer gestartet werden können.
    
- Wenn Sie einen Benutzer für Einwahlkonferenzen aktivieren, erhält dieser standardmäßig eine E-Mail, die Konferenzinformationen und seine PIN enthält. Der Benutzer muss über ein Office 365-Postfach verfügen, da ihm beim Zurücksetzen seiner PIN eine neue PIN per E-Mail an seine primäre für ihn eingerichtete SMTP-Adresse (Alias) gesendet wird.
    
- Wenn Sie eine Einwahlkonferenz einrichten, legen Sie die Ziffern fest, die für die PINs in Ihrem Unternehmen erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die PIN-Längeneinstellung ändern, wird die Änderung nur auf neu erzeugte PINs angewendet und nicht auf PIN-Einstellungen vorhandener Benutzer, die bereits für Einwahlkonferenzen aktiviert sind. Weitere Informationen finden Sie unter [Konfigurieren der Länge der PIN für Einwahl-Besprechungen](set-the-length-of-the-pin-for-audio-conferencing-meetings.md)
    
- Die E-Mail wird standardmäßig an die primäre SMTP-Adresse für Office 365 gesendet. Sie können die E-Mail auch an Nicht-Office 365-Adressen wie Hotmail- oder MSN-E-Mail-Adressen senden. Bei Verwendung der Windows PowerShell können Sie die Standard-E-Mail-Adresse überschreiben. Dies ist hilfreich, wenn der Benutzer kein Exchange-Postfach in Office 365 hat.
    
- Der Mandantenadministrator kann die Standardbenutzeradresse, an die die E-Mail gesendet wird, über das folgende Cmdlet überschreiben:  `Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"`. Der Parameter  _SendEmail_ ist für das Überschreiben der E-Mail-Adresse des Benutzers erforderlich.
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
- Sie können die PIN für Amos Marble konfigurieren, indem Sie Folgendes ausführen:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
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
  

