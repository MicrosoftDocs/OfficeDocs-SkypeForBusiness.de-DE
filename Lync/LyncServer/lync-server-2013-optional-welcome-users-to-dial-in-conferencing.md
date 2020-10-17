---
title: 'Lync Server 2013: (optional) willkommene Benutzer für Einwahlkonferenzen'
description: 'Lync Server 2013: (optional) Begrüßung von Benutzern zu Einwahlkonferenzen.'
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
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546901"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>Optional Begrüßen von Benutzern für Einwahlkonferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Nachdem Sie Einwahlkonferenzen und Tests konfiguriert haben, um sicherzustellen, dass die Funktion ordnungsgemäß funktioniert, sollten Sie anfängliche persönliche Identifikationsnummern (Pins) für Benutzer festlegen und die Benutzer über die Verfügbarkeit des Features informieren, einschließlich einführende Anweisungen wie die anfängliche PIN und den Link zur Webseite für Einwahlkonferenzeinstellungen. Dieser Schritt ist optional. Normalerweise verwenden Sie das Cmdlet " **CsClientPin** ", um Pins zurückzusetzen, aber Sie können das Verfahren in diesem Thema zum ersten Mal verwenden, wenn Sie eine Willkommens-e-Mail mit den Informationen senden möchten. Wenn Sie die e-Mail nicht senden möchten, können Sie stattdessen die **Einstellung "CsClientPin** " verwenden.

Sie können das Skript " **CsPinSendCAWelcomeMail** " verwenden, um die PIN festzulegen und eine Willkommens-e-Mail an einen einzelnen Benutzer zu senden. Standardmäßig setzt das Skript keine PIN zurück, wenn es bereits festgelegt ist, aber Sie können den Parameter **Force** verwenden, um das Zurücksetzen einer PIN zu erzwingen. Die e-Mail-Nachricht wird mit Simple Mail Transfer Protocol (SMTP) gesendet.

Sie können ein Skript erstellen, mit dem das **CsPinSendCAWelcomeMail-** Skript iterativ ausgeführt wird, um Pins festzulegen und e-Mails an eine Gruppe von Benutzern zu senden. Sie können die e-Mail-Vorlage (d. h. die **CAWelcomeEmailTemplate.html** -Datei) ändern, um weitere Links zu Intranetseiten hinzuzufügen oder den e-Mail-Text zu ändern.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>So legen Sie eine anfängliche PIN fest und senden eine Willkommens-e-Mail

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

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
    
    **SmtpServer**     Das Skript verwendet standardmäßig den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter. Wenn die **$PSEmailServer** -Variable nicht festgelegt ist, müssen Sie diesen Parameter angeben.
    
    **Anmeldeinformationen**     Standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers. Wenn der aktuelle Benutzer nicht über die Berechtigung zum Senden von e-Mails im Namen der angegebenen von-Adresse verfügt, müssen Sie diesen Parameter angeben. Als allgemeine Regel müssen Sie diesen Parameter angeben, wenn Sie Ihre e-Mail-Adresse nicht als Absenderadresse angeben.
    
    Zum Beispiel:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    In diesem Beispiel wird eine neue PIN erstellt und dann eine Willkommens-e-Mail von Marco an Bob gesendet. Es wird der e-Mail-Text aus der Standardvorlage verwendet und die e-Mail-Nachricht im HTML-Format erstellt. Der Standardbetreff ist "Willkommen bei Dial in Conferencing".
    
    Ein weiteres Beispiel:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    In diesem Beispiel wird eine neue PIN mit dem Wert "383042650" für Bob erzwungen, obwohl Bob bereits über eine PIN verfügt und dann eine Willkommens-e-Mail von Marco an Bob sendet. Da der Parameter Credential angegeben wird, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert. Die e-Mail wird mithilfe der Secure Sockets Layer (SSL) gesendet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

