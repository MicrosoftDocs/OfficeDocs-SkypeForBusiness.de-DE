---
title: Integration zwischen Skype für Business Online und Exchange server
ms.reviewer: cbland
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Konfigurieren von OAuth aktiviert-Authentifizierung zwischen Exchange lokal und Skype für Business Online die Skype für Geschäfts- und Exchange-Integration in featureunterstützung beschriebenen Features.
ms.openlocfilehash: 976aae8287c1d9f209975d53ebc64ac80033c591
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216662"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="aba2d-103">Konfigurieren der Integration zwischen Skype für Unternehmen Online oder Microsoft-Teams und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="aba2d-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="aba2d-104">Konfigurieren der Integration zwischen Exchange Server und Skype für Business Online ermöglicht die Skype für Geschäfts- und Integration von Exchange-Features beschrieben in [Feature zu unterstützen](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="aba2d-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="aba2d-105">Dieses Thema bezieht sich auf Integration mit Exchange Server 2013 über 2019.</span><span class="sxs-lookup"><span data-stu-id="aba2d-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aba2d-106">Was Sie wissen müssen, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="aba2d-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aba2d-107">Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="aba2d-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="aba2d-108">Sie müssen Berechtigungen zugewiesen werden, bevor Sie dieses Verfahren oder Verfahren ausführen können.</span><span class="sxs-lookup"><span data-stu-id="aba2d-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="aba2d-109">Welche Berechtigungen Sie müssen finden Sie im Thema [Exchange and Shell Infrastructure Permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="aba2d-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="aba2d-110">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen in der Exchange-Verwaltungskonsole]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="aba2d-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="aba2d-111">Konfigurieren der Integration zwischen Exchange Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="aba2d-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="aba2d-112">Schritt 1: Konfigurieren von OAuth-Authentifizierung zwischen Exchange Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="aba2d-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="aba2d-113">Führen Sie die Schritte im folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="aba2d-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="aba2d-114">Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="aba2d-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="aba2d-115">Schritt 2: Erstellen Sie ein neues E-Mail-Konto für die Skype für Business Online oder Teams Partneranwendung</span><span class="sxs-lookup"><span data-stu-id="aba2d-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="aba2d-116">Dieser Schritt ist auf dem Exchange Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aba2d-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="aba2d-117">Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aba2d-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="aba2d-118">Dieses Konto wird anschließend im nächsten Schritt gebraucht.</span><span class="sxs-lookup"><span data-stu-id="aba2d-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="aba2d-119">Geben Sie eine überprüfte Domäne für Ihre Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="aba2d-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="aba2d-120">Diese Domäne sollte der gleichen Domäne wie die primäre SMTP-Domäne für den lokalen Exchange-Konten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aba2d-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="aba2d-121">Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="aba2d-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="aba2d-122">Darüber hinaus die \<DomainControllerFQDN\> sollte der FQDN eines Domänencontrollers sein.</span><span class="sxs-lookup"><span data-stu-id="aba2d-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="aba2d-123">Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.</span><span class="sxs-lookup"><span data-stu-id="aba2d-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="aba2d-124">Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.</span><span class="sxs-lookup"><span data-stu-id="aba2d-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="aba2d-125">Schritt 3: Erstellen Sie und aktivieren Sie eine Partneranwendung für Skype für Business Online oder Teams</span><span class="sxs-lookup"><span data-stu-id="aba2d-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="aba2d-126">Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="aba2d-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="aba2d-127">Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="aba2d-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="aba2d-128">Überprüfen Ihres Erfolgs</span><span class="sxs-lookup"><span data-stu-id="aba2d-128">Verify your success</span></span>

<span data-ttu-id="aba2d-129">Stellen Sie sicher, dass die Konfiguration korrekt ist, indem Sie überprüfen, dass einige der Features erfolgreich arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aba2d-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="aba2d-130">Vergewissern Sie sich, dass Outlook-Kalender-Delegierung zwischen zwei Benutzern mit Teams mit Exchange Server 2016 oder 2019 Postfächer funktioniert.</span><span class="sxs-lookup"><span data-stu-id="aba2d-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="aba2d-131">Vergewissern Sie sich, dass im Gesprächsverlauf von Outlook-Ordner Unterhaltungsverlauf für mobile Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aba2d-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="aba2d-132">Betrachten Sie alternativ den Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="aba2d-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="aba2d-133">Des Datenverkehrs in einem OAuth-Handshake ist wirklich charakteristischen (und nicht sehen, wie die Standardauthentifizierung), insbesondere zur Umgehung von Bereichen, wobei Sie Aussteller-Datenverkehr angezeigt, die folgendermaßen aussieht beginnen: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit einem / vor das @-Zeichen), in der Token, die übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="aba2d-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="aba2d-134">Benutzernamen und Kennwort an, das die Punkt OAuth wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aba2d-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="aba2d-135">Aber sehen Sie den Aussteller 'Office' – in diesem Fall ist "4" Skype für Unternehmen – und dem Bereich Ihres Abonnements.</span><span class="sxs-lookup"><span data-stu-id="aba2d-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="aba2d-136">Wenn Sie sicherstellen möchten, dass Sie erfolgreich OAuth verwenden, stellen Sie sicher, dass Sie wissen, was zu erwarten und wissen, wie der Datenverkehr aussehen sollte.</span><span class="sxs-lookup"><span data-stu-id="aba2d-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="aba2d-137">[Hier ist zu erwarten, dass](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)dies der Fall ist, hier ist ein ziemlich standard [Beispiel OAuth-Verkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (sehr nützlich zu lesen, obwohl es nicht Aktualisierungstoken verwendet), und es sind Fiddler-Erweiterungen, die Sie in Ihre OAuth JWT (JSON suchen können Web Token).</span><span class="sxs-lookup"><span data-stu-id="aba2d-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="aba2d-138">Es folgt ein [Beispiel für eine einrichten](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), jedoch können Sie diesen Prozess verpflichten sich gerne Netzwerk Tracing-Tools.</span><span class="sxs-lookup"><span data-stu-id="aba2d-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aba2d-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="aba2d-139">Related topics</span></span>

[<span data-ttu-id="aba2d-140">Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="aba2d-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
