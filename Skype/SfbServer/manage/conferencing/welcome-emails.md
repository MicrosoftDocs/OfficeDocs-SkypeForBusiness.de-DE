---
title: Senden von Willkommens-e-Mails an Einwahlbenutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzer für Einwahlkonferenzen in Skype for Business Server willkommen heißen.'
ms.openlocfilehash: db2e8bd84fa6a03bad845a87f7fb3c1532ae7ec2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280306"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Senden von Willkommens-e-Mails an Einwahlbenutzer in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzer für Einwahlkonferenzen in Skype for Business Server willkommen heißen.
  
Nach dem Konfigurieren von Einwahlkonferenzen und dem Testen der ordnungsgemäßen Funktionsweise sollten Sie persönliche Identifikationsnummern (PINs) für Ihre Benutzer einrichten und die Benutzer über die Verfügbarkeit dieser Funktion informieren. Sie sollten den Benutzern die anfängliche PIN und den Link zur Webseite mit den Einwahlkonferenzeinstellungen bereitstellen. 
  
In der Regel verwenden Sie das Cmdlet " **Satz-CsClientPin** ", um Pins zurückzusetzen, doch Sie können das Verfahren in diesem Thema verwenden, wenn Sie eine einführende Willkommens-e-Mail mit den PIN-Informationen senden möchten. Wenn Sie keine E-Mail senden möchten, können Sie stattdessen das Cmdlet **Set-CsClientPin** verwenden.
  
Sie können mithilfe des Skripts **Set-CsPinSendCAWelcomeMail** eine PIN für einen einzelnen Benutzer einrichten und diesem Benutzer eine Begrüßungs-E-Mail senden. Mit diesem Skript wird eine bereits eingerichtete PIN standardmäßig nicht zurückgesetzt, Sie können das Zurücksetzen der PIN jedoch mithilfe des Parameters Force erzwingen. Die E-Mail-Nachricht wird über SMTP (Simple Mail Transfer Protocol) gesendet.
  
Sie können ein Skript erstellen, mit dem das **Set-CsPinSendCAWelcomeMail**-Skript iterativ ausgeführt wird, um PINs für eine Benutzergruppe einzurichten und E-Mails an diese Gruppe zu senden. Sie können die E-Mail-Vorlage (d. h. die Datei CAWelcomeEmailTemplate.html) bearbeiten, um weitere Links zu Intranetseiten hinzuzufügen oder den E-Mail-Text zu ändern.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Einrichten einer anfänglichen PIN und Senden einer Begrüßungs-E-Mail

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```
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

**SmtpServer** Standardmäßig verwendet das Skript den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter. Wenn die Variable **$PSEmailServer** nicht gesetzt ist, müssen Sie diesen Parameter angeben.
    
**Anmeldeinformationen** Standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers. Wenn der aktuelle Benutzer nicht zum Senden von E-Mails im Namen der angegebenen Absenderadresse berechtigt ist, müssen Sie diesen Parameter angeben. Als allgemeine Regel gilt: Wenn Sie nicht Ihre E-Mail-Adresse als Absenderadresse verwenden, geben Sie diesen Parameter an.
    
Im folgenden Beispiel wird eine neue PIN erstellt und anschließend eine Begrüßungs-E-Mail von Marco an Bob gesendet. Hierbei wird der E-Mail-Text der Standardvorlage verwendet und die E-Mail-Nachricht wird im HTML-Format erstellt. Die standardmäßige Betreffzeile lautet „Willkommen bei der Funktion für Einwahlkonferenzen“.
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

Das nächste Beispiel wird eine neue PIN mit dem Wert „383042650“ für Bob erzwungen, obwohl Bob bereits über eine PIN verfügt, und anschließend wird eine Begrüßungs-E-Mail von Marco an Bob gesendet. Da der Parameter „Credential“ angegeben ist, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert. Die E-Mail wird über SSL (Secure Sockets Layer) gesendet.
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
