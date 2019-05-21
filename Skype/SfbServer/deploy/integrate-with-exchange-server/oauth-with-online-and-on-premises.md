---
title: Integration von Skype for Business Online und Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Wenn Sie die OAuth-Authentifizierung zwischen Exchange lokal und Skype for Business Online konfigurieren, werden die unter Funktionsunterstützung beschriebenen Funktionen für Skype for Business und die Exchange-Integration aktiviert.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278126"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="bf76a-103">Konfigurieren der Integration zwischen Skype for Business Online oder Microsoft Teams und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bf76a-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="bf76a-104">Durch die Konfiguration der Integration zwischen Exchange Server und Skype for Business Online werden die unter [Funktionsunterstützung](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)beschriebenen Funktionen für Skype for Business und Exchange integriert.</span><span class="sxs-lookup"><span data-stu-id="bf76a-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="bf76a-105">Dieses Thema bezieht sich auf die Integration in Exchange Server 2013 bis 2019.</span><span class="sxs-lookup"><span data-stu-id="bf76a-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bf76a-106">Was Sie wissen müssen, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="bf76a-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bf76a-107">Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="bf76a-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="bf76a-108">Sie müssen Berechtigungen zugewiesen sein, bevor Sie diese Schritte ausführen können.</span><span class="sxs-lookup"><span data-stu-id="bf76a-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="bf76a-109">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie im Thema zu den [Berechtigungen für Exchange-und Shell-Infrastruktur](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="bf76a-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="bf76a-110">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten können, finden Sie unter [Tastenkombinationen im Exchange Admin Center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="bf76a-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="bf76a-111">Konfigurieren der Integration zwischen Exchange Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="bf76a-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="bf76a-112">Schritt 1: Konfigurieren der OAuth-Authentifizierung zwischen Exchange Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="bf76a-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="bf76a-113">Führen Sie die im folgenden Artikel aufgeführten Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bf76a-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="bf76a-114">Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="bf76a-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="bf76a-115">Schritt 2: Erstellen eines neuen e-Mail-Benutzerkontos für die Skype for Business Online-oder Team Partner-Anwendung</span><span class="sxs-lookup"><span data-stu-id="bf76a-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="bf76a-116">Dieser Schritt erfolgt auf dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="bf76a-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="bf76a-117">Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bf76a-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="bf76a-118">Dieses Konto wird anschließend im nächsten Schritt gebraucht.</span><span class="sxs-lookup"><span data-stu-id="bf76a-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="bf76a-119">Geben Sie eine verifizierte Domäne für Ihre Exchange-Organisation an.</span><span class="sxs-lookup"><span data-stu-id="bf76a-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="bf76a-120">Diese Domäne sollte dieselbe Domäne sein wie die primäre SMTP-Domäne, die für die lokalen Exchange-Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf76a-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="bf76a-121">Diese Domäne wird im folgenden \<Verfahren als Ihre\> überprüfte Domäne bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bf76a-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="bf76a-122">Außerdem sollte der \<DomainControllerFQDN\> der FQDN eines Domänencontrollers sein.</span><span class="sxs-lookup"><span data-stu-id="bf76a-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="bf76a-123">Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.</span><span class="sxs-lookup"><span data-stu-id="bf76a-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="bf76a-124">Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.</span><span class="sxs-lookup"><span data-stu-id="bf76a-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="bf76a-125">Schritt 3: Erstellen und Aktivieren einer Partner Anwendung für Skype for Business Online oder Teams</span><span class="sxs-lookup"><span data-stu-id="bf76a-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="bf76a-126">Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bf76a-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="bf76a-127">Führen Sie den folgenden Befehl in der Exchange-PowerShell in Ihrer lokalen Exchange-Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="bf76a-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="bf76a-128">Überprüfen Ihres Erfolgs</span><span class="sxs-lookup"><span data-stu-id="bf76a-128">Verify your success</span></span>

<span data-ttu-id="bf76a-129">Überprüfen Sie, ob die Konfiguration korrekt ist, indem Sie sicherstellen, dass einige Features erfolgreich funktionieren.</span><span class="sxs-lookup"><span data-stu-id="bf76a-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="bf76a-130">Bestätigen Sie, dass die Outlook-Kalender Delegierung betweeen zwei Teams-Benutzer mit Exchange Server 2016-oder 2019-Postfächern funktioniert.</span><span class="sxs-lookup"><span data-stu-id="bf76a-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="bf76a-131">Der Konversations Verlauf für mobile Clients bestätigen ist im Outlook-Ordner "Konversations Verlauf" sichtbar.</span><span class="sxs-lookup"><span data-stu-id="bf76a-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="bf76a-132">Schauen Sie sich alternativ Ihren Traffic an.</span><span class="sxs-lookup"><span data-stu-id="bf76a-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="bf76a-133">Der Datenverkehr in einem OAuth-Handshake ist wirklich charakteristisch (und sieht nicht wie die Standardauthentifizierung aus), insbesondere im Bereich der Realms, wo Sie beginnen, den Emittenten-Traffic zu sehen, der wie folgt aussieht: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit a/before das @-Zeichen) in den Token, die übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="bf76a-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="bf76a-134">Sie sehen keinen Benutzernamen oder kein Kennwort, was der OAuth-Punkt ist.</span><span class="sxs-lookup"><span data-stu-id="bf76a-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="bf76a-135">Sie sehen aber den Aussteller "Office" – in diesem Fall "4" ist Skype for Business – und das Reich Ihres Abonnements.</span><span class="sxs-lookup"><span data-stu-id="bf76a-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="bf76a-136">Wenn Sie sicher sein möchten, dass Sie OAuth erfolgreich verwenden, stellen Sie sicher, dass Sie wissen, was Sie erwarten und wissen, wie der Datenverkehr aussehen soll.</span><span class="sxs-lookup"><span data-stu-id="bf76a-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="bf76a-137">Hier [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)sehen Sie also ein ziemlich Standard [Beispiel für OAuth-Datenverkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (wirklich hilfreich zum Lesen, obwohl es keine Aktualisierungs Tokens verwendet), und es gibt Fiddler-Erweiterungen, mit denen Sie Ihre OAuth-JWT (JSON Web-Token).</span><span class="sxs-lookup"><span data-stu-id="bf76a-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="bf76a-138">Hier ist ein [Beispiel für die Einrichtung](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), aber Sie können jedes Netzwerk-Tracing-Tool verwenden, mit dem Sie diesen Prozess durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf76a-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf76a-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bf76a-139">Related topics</span></span>

[<span data-ttu-id="bf76a-140">Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="bf76a-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
