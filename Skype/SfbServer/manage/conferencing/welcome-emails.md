---
title: Senden einer Willkommens-E-Mail an Einwahlbenutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzer bei Einwahlkonferenzen in Skype for Business Server willkommen heißen.'
ms.openlocfilehash: 1b585d4e0ff05bdb1faca0aa9c8b0863dd26f10f7d06bb1140211a2f1663e6b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313193"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Senden einer Willkommens-E-Mail an Einwahlbenutzer in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Benutzer bei Einwahlkonferenzen in Skype for Business Server willkommen heißen.
  
Nachdem Sie Einwahlkonferenzen konfiguriert und getestet haben, ob sie ordnungsgemäß funktionieren, sollten Sie die anfänglichen persönlichen Identifikationsnummern (PINs) für Benutzer festlegen und die Benutzer über die Verfügbarkeit des Features informieren. Sie können einführende Anweisungen wie die anfängliche PIN und den Link zur Webseite für Einwahlkonferenzen Einstellungen hinzufügen. 
  
In der Regel verwenden Sie das Cmdlet **"Set-CsClientPin",** um PINs zurückzusetzen, aber Sie können das Verfahren in diesem Thema verwenden, wenn Sie eine Einführungs-Willkommens-E-Mail mit den PIN-Informationen senden möchten. Wenn Sie die E-Mail nicht senden möchten, können Sie stattdessen **Set-CsClientPin** verwenden.
  
Sie können das **Set-CsPinSendCAWelcomeMail-Skript** verwenden, um die PIN festzulegen und eine Willkommens-E-Mail an einen einzelnen Benutzer zu senden. Standardmäßig setzt das Skript eine PIN nicht zurück, wenn sie bereits festgelegt ist. Sie können jedoch den Parameter "Force" verwenden, um das Zurücksetzen einer PIN zu erzwingen. Die E-Mail-Nachricht wird mithilfe von SMTP (Simple Mail Transfer Protocol) gesendet.
  
Sie können ein Skript erstellen, das das **Set-CsPinSendCAWelcomeMail-Skript** iterativ ausführt, um PINs festzulegen und E-Mails an eine Gruppe von Benutzern zu senden. Sie können die E-Mail-Vorlage (d. h. die Datei CAWelcomeEmailTemplate.html) ändern, um weitere Links zu Intranetseiten hinzuzufügen oder den E-Mail-Text zu ändern.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Festlegen einer anfänglichen PIN und Senden einer Willkommens-E-Mail

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** Standardmäßig verwendet das Skript den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter. Wenn die **variable $PSEmailServer** nicht festgelegt ist, müssen Sie diesen Parameter angeben.
    
**Anmeldeinformationen** Standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers. Wenn der aktuelle Benutzer nicht über die Berechtigung zum Senden von E-Mails im Namen der angegebenen Absenderadresse verfügt, müssen Sie diesen Parameter angeben. Geben Sie diesen Parameter als allgemeine Regel an, wenn Sie Ihre E-Mail-Adresse nicht als Absenderadresse angeben.
    
Im folgenden Beispiel wird eine neue PIN erstellt und dann eine Willkommens-E-Mail von Sven an Bob gesendet. Er verwendet den E-Mail-Text aus der Standardvorlage und erstellt die E-Mail-Nachricht im HTML-Format. Der Standardantrag lautet "Willkommen bei Einwahlkonferenzen":
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

Das nächste Beispiel erzwingt eine neue PIN mit dem Wert "383042650" für Bob, obwohl Bob über eine vorhandene PIN verfügte, und sendet dann eine Begrüßungs-E-Mail von Sven an Bob. Da der Parameter "Credential" angegeben ist, wird die Person, die den Befehl ausführt, aufgefordert, ein Kennwort einzugeben. Die E-Mail wird mithilfe der Secure Sockets Layer (SSL) gesendet:
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
