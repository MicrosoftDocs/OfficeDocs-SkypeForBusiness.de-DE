---
title: 'Lync Server 2013: (optional) willkommene Benutzer für Einwahlkonferenzen'
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
ms.openlocfilehash: d3a949d1de2c3237e1cd432297a1ce1e1a7f3543
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="6bd6b-102">Optional Begrüßen von Benutzern für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bd6b-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bd6b-103">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6bd6b-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6bd6b-104">Nachdem Sie Einwahlkonferenzen und Tests konfiguriert haben, um sicherzustellen, dass die Funktion ordnungsgemäß funktioniert, sollten Sie die anfänglichen persönlichen Identifikationsnummern (Pins) für Benutzer festlegen und die Benutzer über die Verfügbarkeit des Features informieren, einschließlich einführende Anweisungen wie als anfänglicher PIN und Link zur Webseite für Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="6bd6b-105">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-105">This step is optional.</span></span> <span data-ttu-id="6bd6b-106">Normalerweise verwenden Sie das Cmdlet " **CsClientPin** ", um Pins zurückzusetzen, aber Sie können das Verfahren in diesem Thema zum ersten Mal verwenden, wenn Sie eine Willkommens-e-Mail mit den Informationen senden möchten.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="6bd6b-107">Wenn Sie die e-Mail nicht senden möchten, können Sie stattdessen die **Einstellung "CsClientPin** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="6bd6b-108">Sie können das Skript " **CsPinSendCAWelcomeMail** " verwenden, um die PIN festzulegen und eine Willkommens-e-Mail an einen einzelnen Benutzer zu senden.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="6bd6b-109">Standardmäßig setzt das Skript keine PIN zurück, wenn es bereits festgelegt ist, aber Sie können den Parameter **Force** verwenden, um das Zurücksetzen einer PIN zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="6bd6b-110">Die e-Mail-Nachricht wird mit Simple Mail Transfer Protocol (SMTP) gesendet.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="6bd6b-111">Sie können ein Skript erstellen, mit dem das **CsPinSendCAWelcomeMail-** Skript iterativ ausgeführt wird, um Pins festzulegen und e-Mails an eine Gruppe von Benutzern zu senden.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="6bd6b-112">Sie können die e-Mail-Vorlage (d **. CAWelcomeEmailTemplate. html** -Datei) so ändern, dass weitere Links zu Intranetseiten hinzugefügt oder der e-Mail-Text geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="6bd6b-113">So legen Sie eine anfängliche PIN fest und senden eine Willkommens-e-Mail</span><span class="sxs-lookup"><span data-stu-id="6bd6b-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="6bd6b-114">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6bd6b-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6bd6b-116">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="6bd6b-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="6bd6b-117">**SmtpServer**   standardmäßig verwendet das Skript den Wert der reservierten Umgebungsvariablen **$PSEmailServer** für diesen Parameter.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="6bd6b-118">Wenn die **$PSEmailServer** -Variable nicht festgelegt ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="6bd6b-119">**Anmeldeinformationen**   standardmäßig verwendet das Skript die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="6bd6b-120">Wenn der aktuelle Benutzer nicht über die Berechtigung zum Senden von e-Mails im Namen der angegebenen von-Adresse verfügt, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="6bd6b-121">Als allgemeine Regel müssen Sie diesen Parameter angeben, wenn Sie Ihre e-Mail-Adresse nicht als Absenderadresse angeben.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="6bd6b-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6bd6b-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="6bd6b-123">In diesem Beispiel wird eine neue PIN erstellt und dann eine Willkommens-e-Mail von Marco an Bob gesendet.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="6bd6b-124">Es wird der e-Mail-Text aus der Standardvorlage verwendet und die e-Mail-Nachricht im HTML-Format erstellt.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="6bd6b-125">Der Standardbetreff ist "Willkommen bei Dial in Conferencing".</span><span class="sxs-lookup"><span data-stu-id="6bd6b-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="6bd6b-126">Ein weiteres Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6bd6b-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="6bd6b-127">In diesem Beispiel wird eine neue PIN mit dem Wert "383042650" für Bob erzwungen, obwohl Bob bereits über eine PIN verfügt und dann eine Willkommens-e-Mail von Marco an Bob sendet.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="6bd6b-128">Da der Parameter Credential angegeben wird, wird die Person, die den Befehl ausführt, zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="6bd6b-129">Die e-Mail wird mithilfe der Secure Sockets Layer (SSL) gesendet.</span><span class="sxs-lookup"><span data-stu-id="6bd6b-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

