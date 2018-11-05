---
title: 'Lync Server 2013: (Optional) Einladen von Benutzern zu Einwahlkonferenzen'
TOCTitle: (Optional) Einladen von Benutzern zu Einwahlkonferenzen
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398846(v=OCS.15)
ms:contentKeyID: 49295407
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Einladen von Benutzern zu Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Nach dem Konfigurieren von Einwahlkonferenzen und dem Testen der ordnungsgemäßen Funktionsweise sollten Sie persönliche Identifikationsnummern (PINs) für Ihre Benutzer einrichten und die Benutzer über die Verfügbarkeit dieser Funktion informieren. Sie sollten den Benutzern die anfängliche PIN und den Link zur Webseite mit den Einwahlkonferenzeinstellungen bereitstellen. Dieser Schritt ist optional. Üblicherweise verwenden Sie zum Einrichten von PINs das Cmdlet **Set-CsClientPin**, Sie können jedoch die anfänglichen PINs auch anhand des in diesem Thema beschriebenen Verfahrens einrichten, wenn Sie den Benutzern eine Begrüßungs-E-Mail mit den Informationen senden möchten. Wenn Sie keine E-Mail senden möchten, können Sie stattdessen das Cmdlet **Set-CsClientPin** verwenden.

Sie können mithilfe des Skripts **Set-CsPinSendCAWelcomeMail** eine PIN für einen einzelnen Benutzer einrichten und diesem Benutzer eine Begrüßungs-E-Mail senden. Mit diesem Skript wird eine bereits eingerichtete PIN standardmäßig nicht zurückgesetzt, Sie können das Zurücksetzen der PIN jedoch mithilfe des Parameters **Force** erzwingen. Die E-Mail-Nachricht wird über SMTP (Simple Mail Transfer Protocol) gesendet.

Sie können ein Skript erstellen, mit dem das **Set-CsPinSendCAWelcomeMail**-Skript iterativ ausgeführt wird, um PINs für eine Benutzergruppe einzurichten und E-Mails an diese Gruppe zu senden. Sie können die E-Mail-Vorlage (d. h. die Datei **CAWelcomeEmailTemplate.html**) bearbeiten, um weitere Links zu Intranetseiten hinzuzufügen oder den E-Mail-Text zu ändern.

## So richten Sie eine anfängliche PIN ein und senden eine Begrüßungs-E-Mail

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
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
    
    **SmtpServer**   Das Skript verwendet standardmäßig den Wert der reservierten Umgebungsvariable **$PSEmailServer** für diesen Parameter. Wenn die Variable **$PSEmailServer** nicht gesetzt ist, müssen Sie diesen Parameter angeben.
    
    **Credential**   Das Skript verwendet standardmäßig die Anmeldeinformationen des aktuellen Benutzers. Wenn der aktuelle Benutzer nicht zum Senden von E-Mails im Namen der angegebenen Absenderadresse berechtigt ist, müssen Sie diesen Parameter angeben. Als allgemeine Regel gilt: wenn Sie nicht Ihre E-Mail-Adresse als Absenderadresse verwenden, geben Sie diesen Parameter an.
    
    Beispiel:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    In diesem Beispiel wird eine neue PIN erstellt und anschließend eine Begrüßungs-E-Mail von Marco an Bob gesendet. Hierbei wird der E-Mail-Text der Standardvorlage verwendet, und die E-Mail-Nachricht wird im HTML-Format erstellt. Die standardmäßige Betreffzeile lautet "Willkommen bei der Funktion für Einwahlkonferenzen".
    
    Ein weiteres Beispiel:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    In diesem Beispiel wird eine neue PIN mit dem Wert "383042650" für Bob erzwungen, obwohl Bob bereits über eine PIN verfügt, und anschließend wird eine Begrüßungs-E-Mail von Marco an Bob gesendet. Da der Parameter "Credential" angegeben ist, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert. Die E-Mail wird über SSL (Secure Sockets Layer) gesendet.

