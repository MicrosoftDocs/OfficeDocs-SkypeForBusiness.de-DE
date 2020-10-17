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
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="faa40-103">Optional Begrüßen von Benutzern für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faa40-103">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faa40-104">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="faa40-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="faa40-105">Nachdem Sie Einwahlkonferenzen und Tests konfiguriert haben, um sicherzustellen, dass die Funktion ordnungsgemäß funktioniert, sollten Sie anfängliche persönliche Identifikationsnummern (Pins) für Benutzer festlegen und die Benutzer über die Verfügbarkeit des Features informieren, einschließlich einführende Anweisungen wie die anfängliche PIN und den Link zur Webseite für Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="faa40-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="faa40-106">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="faa40-106">This step is optional.</span></span> <span data-ttu-id="faa40-107">Normalerweise verwenden Sie das Cmdlet " **CsClientPin** ", um Pins zurückzusetzen, aber Sie können das Verfahren in diesem Thema zum ersten Mal verwenden, wenn Sie eine Willkommens-e-Mail mit den Informationen senden möchten.</span><span class="sxs-lookup"><span data-stu-id="faa40-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="faa40-108">Wenn Sie die e-Mail nicht senden möchten, können Sie stattdessen die **Einstellung "CsClientPin** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="faa40-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="faa40-109">Sie können das Skript " **CsPinSendCAWelcomeMail** " verwenden, um die PIN festzulegen und eine Willkommens-e-Mail an einen einzelnen Benutzer zu senden.</span><span class="sxs-lookup"><span data-stu-id="faa40-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="faa40-110">Standardmäßig setzt das Skript keine PIN zurück, wenn es bereits festgelegt ist, aber Sie können den Parameter **Force** verwenden, um das Zurücksetzen einer PIN zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="faa40-110">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="faa40-111">Die e-Mail-Nachricht wird mit Simple Mail Transfer Protocol (SMTP) gesendet.</span><span class="sxs-lookup"><span data-stu-id="faa40-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="faa40-112">Sie können ein Skript erstellen, mit dem das **CsPinSendCAWelcomeMail-** Skript iterativ ausgeführt wird, um Pins festzulegen und e-Mails an eine Gruppe von Benutzern zu senden.</span><span class="sxs-lookup"><span data-stu-id="faa40-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="faa40-113">Sie können die e-Mail-Vorlage (d. h. die **CAWelcomeEmailTemplate.html** -Datei) ändern, um weitere Links zu Intranetseiten hinzuzufügen oder den e-Mail-Text zu ändern.</span><span class="sxs-lookup"><span data-stu-id="faa40-113">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="faa40-114">So legen Sie eine anfängliche PIN fest und senden eine Willkommens-e-Mail</span><span class="sxs-lookup"><span data-stu-id="faa40-114">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="faa40-115">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="faa40-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="faa40-116">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="faa40-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="faa40-117">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="faa40-117">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="faa40-118">**SmtpServer**     Das Skript verwendet standardmäßig den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter.</span><span class="sxs-lookup"><span data-stu-id="faa40-118">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="faa40-119">Wenn die **$PSEmailServer** -Variable nicht festgelegt ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="faa40-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="faa40-120">**Anmeldeinformationen**     Standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="faa40-120">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="faa40-121">Wenn der aktuelle Benutzer nicht über die Berechtigung zum Senden von e-Mails im Namen der angegebenen von-Adresse verfügt, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="faa40-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="faa40-122">Als allgemeine Regel müssen Sie diesen Parameter angeben, wenn Sie Ihre e-Mail-Adresse nicht als Absenderadresse angeben.</span><span class="sxs-lookup"><span data-stu-id="faa40-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="faa40-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="faa40-123">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="faa40-124">In diesem Beispiel wird eine neue PIN erstellt und dann eine Willkommens-e-Mail von Marco an Bob gesendet.</span><span class="sxs-lookup"><span data-stu-id="faa40-124">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="faa40-125">Es wird der e-Mail-Text aus der Standardvorlage verwendet und die e-Mail-Nachricht im HTML-Format erstellt.</span><span class="sxs-lookup"><span data-stu-id="faa40-125">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="faa40-126">Der Standardbetreff ist "Willkommen bei Dial in Conferencing".</span><span class="sxs-lookup"><span data-stu-id="faa40-126">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="faa40-127">Ein weiteres Beispiel:</span><span class="sxs-lookup"><span data-stu-id="faa40-127">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="faa40-128">In diesem Beispiel wird eine neue PIN mit dem Wert "383042650" für Bob erzwungen, obwohl Bob bereits über eine PIN verfügt und dann eine Willkommens-e-Mail von Marco an Bob sendet.</span><span class="sxs-lookup"><span data-stu-id="faa40-128">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="faa40-129">Da der Parameter Credential angegeben wird, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="faa40-129">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="faa40-130">Die e-Mail wird mithilfe der Secure Sockets Layer (SSL) gesendet.</span><span class="sxs-lookup"><span data-stu-id="faa40-130">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

