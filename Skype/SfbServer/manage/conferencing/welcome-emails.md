---
title: Senden von Willkommens-e-Mails an Einwahlbenutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzer für Einwahlkonferenzen in Skype for Business Server willkommen heißen.'
ms.openlocfilehash: 6228d0636e878ccf9a208edf9afeee3fe1e808f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818436"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="14b58-103">Senden von Willkommens-e-Mails an Einwahlbenutzer in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="14b58-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="14b58-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzer für Einwahlkonferenzen in Skype for Business Server willkommen heißen.</span><span class="sxs-lookup"><span data-stu-id="14b58-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="14b58-105">Nach dem Konfigurieren von Einwahlkonferenzen und dem Testen der ordnungsgemäßen Funktionsweise sollten Sie persönliche Identifikationsnummern (PINs) für Ihre Benutzer einrichten und die Benutzer über die Verfügbarkeit dieser Funktion informieren.</span><span class="sxs-lookup"><span data-stu-id="14b58-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="14b58-106">Sie sollten den Benutzern die anfängliche PIN und den Link zur Webseite mit den Einwahlkonferenzeinstellungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="14b58-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="14b58-107">In der Regel verwenden Sie das Cmdlet " **Satz-CsClientPin** ", um Pins zurückzusetzen, doch Sie können das Verfahren in diesem Thema verwenden, wenn Sie eine einführende Willkommens-e-Mail mit den PIN-Informationen senden möchten.</span><span class="sxs-lookup"><span data-stu-id="14b58-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="14b58-108">Wenn Sie keine E-Mail senden möchten, können Sie stattdessen das Cmdlet **Set-CsClientPin** verwenden.</span><span class="sxs-lookup"><span data-stu-id="14b58-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="14b58-p103">Sie können mithilfe des Skripts **Set-CsPinSendCAWelcomeMail** eine PIN für einen einzelnen Benutzer einrichten und diesem Benutzer eine Begrüßungs-E-Mail senden. Mit diesem Skript wird eine bereits eingerichtete PIN standardmäßig nicht zurückgesetzt, Sie können das Zurücksetzen der PIN jedoch mithilfe des Parameters Force erzwingen. Die E-Mail-Nachricht wird über SMTP (Simple Mail Transfer Protocol) gesendet.</span><span class="sxs-lookup"><span data-stu-id="14b58-p103">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user. By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN. The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="14b58-p104">Sie können ein Skript erstellen, mit dem das **Set-CsPinSendCAWelcomeMail**-Skript iterativ ausgeführt wird, um PINs für eine Benutzergruppe einzurichten und E-Mails an diese Gruppe zu senden. Sie können die E-Mail-Vorlage (d. h. die Datei CAWelcomeEmailTemplate.html) bearbeiten, um weitere Links zu Intranetseiten hinzuzufügen oder den E-Mail-Text zu ändern.</span><span class="sxs-lookup"><span data-stu-id="14b58-p104">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users. You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="14b58-114">Einrichten einer anfänglichen PIN und Senden einer Begrüßungs-E-Mail</span><span class="sxs-lookup"><span data-stu-id="14b58-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="14b58-115">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="14b58-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="14b58-116">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="14b58-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14b58-117">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="14b58-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="14b58-118">**SmtpServer** Standardmäßig verwendet das Skript den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter.</span><span class="sxs-lookup"><span data-stu-id="14b58-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="14b58-119">Wenn die Variable **$PSEmailServer** nicht gesetzt ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="14b58-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="14b58-120">**Anmeldeinformationen** Standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="14b58-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="14b58-121">Wenn der aktuelle Benutzer nicht zum Senden von E-Mails im Namen der angegebenen Absenderadresse berechtigt ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="14b58-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="14b58-122">Als allgemeine Regel gilt: Wenn Sie nicht Ihre E-Mail-Adresse als Absenderadresse verwenden, geben Sie diesen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="14b58-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="14b58-p107">Im folgenden Beispiel wird eine neue PIN erstellt und anschließend eine Begrüßungs-E-Mail von Marco an Bob gesendet. Hierbei wird der E-Mail-Text der Standardvorlage verwendet und die E-Mail-Nachricht wird im HTML-Format erstellt. Die standardmäßige Betreffzeile lautet „Willkommen bei der Funktion für Einwahlkonferenzen“.</span><span class="sxs-lookup"><span data-stu-id="14b58-p107">The following example creates a new PIN, and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="14b58-p108">Das nächste Beispiel wird eine neue PIN mit dem Wert „383042650“ für Bob erzwungen, obwohl Bob bereits über eine PIN verfügt, und anschließend wird eine Begrüßungs-E-Mail von Marco an Bob gesendet. Da der Parameter „Credential“ angegeben ist, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert. Die E-Mail wird über SSL (Secure Sockets Layer) gesendet.</span><span class="sxs-lookup"><span data-stu-id="14b58-p108">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
