---
title: 'Lync Server 2013: (Optional) Einladen von Benutzern zu Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27abf5da520f1c5befd3a477783bc3f9ae67e1b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(Optional) Einladen von Benutzern zu Einwahlkonferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Nachdem Sie Einwahlkonferenzen konfiguriert und getestet haben, um sicherzustellen, dass Sie ordnungsgemäß funktioniert, sollten Sie anfängliche persönliche Identifikationsnummern (Pins) für Benutzer festlegen und die Benutzer über die Verfügbarkeit der Funktion informieren, einschließlich einleitender Anweisungen wie als Initiale PIN und Link zur Webseite für Einwahlkonferenzeinstellungen. Dieser Schritt ist optional. In der Regel verwenden Sie das Cmdlet " **Satz-CsClientPin** ", um Pins zurückzusetzen, doch Sie können das Verfahren in diesem Thema zum ersten Mal verwenden, wenn Sie eine Willkommens-e-Mail mit den Informationen senden möchten. Wenn Sie keine E-Mail senden möchten, können Sie stattdessen das Cmdlet **Set-CsClientPin** verwenden.

Sie können mithilfe des Skripts **Set-CsPinSendCAWelcomeMail** eine PIN für einen einzelnen Benutzer einrichten und diesem Benutzer eine Begrüßungs-E-Mail senden. Standardmäßig setzt das Skript eine PIN nicht zurück, wenn Sie bereits festgesetzt ist, aber Sie können den Parameter **Force** verwenden, um das Zurücksetzen einer PIN zu erzwingen. Die E-Mail-Nachricht wird über SMTP (Simple Mail Transfer Protocol) gesendet.

Sie können ein Skript erstellen, mit dem das **Set-CsPinSendCAWelcomeMail**-Skript iterativ ausgeführt wird, um PINs für eine Benutzergruppe einzurichten und E-Mails an diese Gruppe zu senden. Sie können die e-Mail-Vorlage (d **. CAWelcomeEmailTemplate. html** -Datei) ändern, um weitere Links zu Intranetseiten hinzuzufügen oder den e-Mail-Text zu ändern.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>So setzen Sie eine Initiale PIN und senden eine Willkommens-e-Mail

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

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
    
    **SmtpServer**   standardmäßig verwendet das Skript den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter. Wenn die Variable **$PSEmailServer** nicht gesetzt ist, müssen Sie diesen Parameter angeben.
    
    **Anmeldeinformationen**   standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers. Wenn der aktuelle Benutzer nicht zum Senden von E-Mails im Namen der angegebenen Absenderadresse berechtigt ist, müssen Sie diesen Parameter angeben. Als allgemeine Regel gilt: Wenn Sie nicht Ihre E-Mail-Adresse als Absenderadresse verwenden, geben Sie diesen Parameter an.
    
    Beispiel:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    In diesem Beispiel wird eine neue PIN erstellt und dann eine Willkommens-e-Mail von Marco an Bob gesendet. Hierbei wird der E-Mail-Text der Standardvorlage verwendet und die E-Mail-Nachricht wird im HTML-Format erstellt. Das Standardthema lautet "Willkommen bei Dial in Conferencing".
    
    Ein weiteres Beispiel:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    In diesem Beispiel wird eine neue PIN mit dem Wert "383042650" für Bob erzwungen, obwohl Bob über eine vorhandene Pin verfügte und dann eine Willkommens-e-Mail von Marco an Bob sendet. Da der Parameter „Credential“ angegeben ist, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert. Die e-Mail wird mithilfe des Secure Sockets Layer (SSL) gesendet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

