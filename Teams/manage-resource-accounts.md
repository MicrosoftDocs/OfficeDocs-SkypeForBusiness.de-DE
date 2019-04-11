---
title: Verwalten von Ressourcenkonten in Microsoft Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Erfahren Sie mehr über das Verwalten von Ressourcenkonten in Microsoft-Teams
ms.openlocfilehash: 3e3dbfb43498041296cb9cfb79341a3f40f2eda0
ms.sourcegitcommit: 7fe8daf07013d7c532f128a3ae3bbf51d1b2aac9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "31808054"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="1846b-103">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1846b-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="1846b-104">Ein Ressourcenkonto wird auch als ein deaktiviertes Benutzerobjekt in Azure Active Directory und kann verwendet werden, um Ressourcen im Allgemeinen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1846b-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="1846b-105">In Exchange kann verwendet werden, Konferenzräumen, beispielsweise darstellen und ermöglicht es ihnen, Sie haben eine Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="1846b-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="1846b-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal mit Skype für Business Server verwaltet werden, und diese Konten werden mithilfe von Powershell-Befehlen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1846b-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="1846b-107">In Microsoft-Teams oder Skype für Business Online, jeden Anruf Warteschlange oder automatische wird Attendant erforderlich, um ein Ressourcenkonto zugeordneten verfügen.</span><span class="sxs-lookup"><span data-stu-id="1846b-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="1846b-108">Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt wird abhängig von der beabsichtigten Verwendung von der zugehörigen Aufruf Warteschlange oder automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="1846b-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="1846b-109">Finden Sie in den Artikeln für Anruf Warteschlangen und automatische um-Telefonzentralen verknüpft unten in diesem Artikel, bevor Sie eine Telefonnummer ein Ressourcenkonto zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1846b-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="1846b-110">Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="1846b-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="1846b-111">Erforderliche Komponenten ein Ressourcenkonto eine Telefonnummer zuweisen</span><span class="sxs-lookup"><span data-stu-id="1846b-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="1846b-112">Erste Schritte beim es ist wichtig, sollten Sie einige Dinge bedenken:</span><span class="sxs-lookup"><span data-stu-id="1846b-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="1846b-113">Eine automatische Telefonzentrale oder ein Anruf Warteschlange ist erforderlich, um ein Ressourcenkonto zugeordneten verfügen.</span><span class="sxs-lookup"><span data-stu-id="1846b-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="1846b-114">Details auf Ressourcenkonten finden Sie unter [Manage Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="1846b-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="1846b-115">Wenn Sie eine direkte Routing Number zuweisen möchten, müssen Sie erwerben und weisen Sie die folgenden Lizenzen der Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on\).</span><span class="sxs-lookup"><span data-stu-id="1846b-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="1846b-116">Wenn Sie stattdessen eine Microsoft-Dienst Zahl zuordnen möchten, müssen Sie erwerben und weisen Sie Ihr Ressourcenkonto folgenden Lizenzen \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on und Aufrufen planen\).</span><span class="sxs-lookup"><span data-stu-id="1846b-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="1846b-117">Sie müssen nur die Ressourcenkonten mit einer Telefonnummer, die ihnen zugewiesenen lizenzieren.</span><span class="sxs-lookup"><span data-stu-id="1846b-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="1846b-118">In einer geschachtelten automatische Telefonzentrale oder ein Anruf Warteschlange müssen nicht Sie den Rest der automatischen Telefonzentralen lizenzieren, oder rufen Sie Warteschlangen aus, wenn keine ihnen zugeordnete Telefonnummern vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="1846b-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="1846b-119">Direkte Routing Service Zahlen für die automatische Telefonzentrale und Warteschlangen Anruf wird gegenwärtig nur für Microsoft-Teams, Benutzer und Agents unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1846b-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only at the moment.</span></span>

> [!NOTE] 
> <span data-ttu-id="1846b-120">Microsoft arbeitet eine entsprechende Lizenzierungsmodell für Anwendungen wie Cloud automatische Telefonzentrale und den Anruf-Warteschlangen für an jetzt Sie das Benutzerlizenzierung Objektmodell verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="1846b-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1846b-121">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans.</span><span class="sxs-lookup"><span data-stu-id="1846b-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="1846b-122">Finden Sie unter [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="1846b-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="1846b-123">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="1846b-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="1846b-124">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="1846b-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="1846b-125">Sie können eine direkte Routing Hybrid Anzahl Ihrer Ressourcenkonto zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1846b-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="1846b-126">Einzelheiten finden Sie unter [Planen der direkten Routing](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="1846b-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="1846b-127">Für Microsoft aufrufende plant können Sie nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder Port aus einer anderen Dienstanbieter ein Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="1846b-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="1846b-128">Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.</span><span class="sxs-lookup"><span data-stu-id="1846b-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="1846b-129">Ein Ressourcenkonto können nicht Benutzer (Abonnent) Rufnummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1846b-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="1846b-130">Nur Service gebührenpflichtige oder gebührenfreie Telefonnummern können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1846b-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="1846b-131">Eine Telefonnummer ein, um ein Ressourcenkonto zuzuweisen, müssen Sie abzurufen oder port Ihrer vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen.</span><span class="sxs-lookup"><span data-stu-id="1846b-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="1846b-132">Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1846b-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="1846b-133">Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) oder wenn Sie eine vorhandene Servicenummer durchstellen möchten, finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1846b-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1846b-134">Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1846b-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="1846b-135">Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="1846b-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="1846b-136">Erstellen Sie ein Ressourcenkonto im Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="1846b-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="1846b-137">Navigieren Sie zum Erstellen einer Ressourcenkontos im Microsoft-Teams, Administrationscenter zu **Org geltende Settings** > **Ressourcenkonten**, klicken Sie dann auf **+ Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1846b-137">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="1846b-138">Im Popup füllen Sie den Anzeigenamen und Benutzernamen für das Ressourcenkonto (der Domänenname sollte automatisch aufgefüllt) klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1846b-138">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Ressource-Konto](media/res-acct.png)

<span data-ttu-id="1846b-140">Sie müssen auch das Ressourcenkonto eine Lizenz gilt gemäß [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="1846b-140">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="1846b-141">Sobald Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, klicken Sie auf **Zuweisen/Zuweisung entfernen** das Ressourcenkonto eine Telefonnummer zuweisen oder eine automatische Telefonzentrale oder ein Anruf-Warteschlange das Ressourcenkonto zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1846b-141">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="1846b-142">Erstellen Sie ein Ressourcenkonto in Powershell</span><span class="sxs-lookup"><span data-stu-id="1846b-142">Create a resource account in Powershell</span></span>

<span data-ttu-id="1846b-143">Für Microsoft aufrufende plant können Sie nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder Port aus einer anderen Dienstanbieter ein Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="1846b-143">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="1846b-144">Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.</span><span class="sxs-lookup"><span data-stu-id="1846b-144">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="1846b-145">Je nachdem, ob Ihre Telefonnummer online oder lokal befindet müssen Sie in der entsprechenden Aufforderung Powershell mit Administratorberechtigungen eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="1846b-145">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>


- <span data-ttu-id="1846b-146">Hybrid Implementierungen (Zahlen verwaltet auf direktes Routing) werden [Neu CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) verwenden, um ein Ressourcenkonto erstellen, die lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="1846b-146">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="1846b-147">Nur Online Implementierungen [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) verwendet, die ein Resource-Konto verfügen, die online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="1846b-147">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="1846b-148">Es folgt ein Beispiel für online-Umgebung mit einer automatischen Telefonzentrale ApplicationID Ressourcenkonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="1846b-148">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="1846b-149">Für eine Warteschlange Anruf können Sie die folgenden ApplicationID 11cd3e2e-Fccb-42ad-ad00-878b93575e07 verwenden:</span><span class="sxs-lookup"><span data-stu-id="1846b-149">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="1846b-150">Weitere Informationen zu diesem Befehl finden Sie unter [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1846b-150">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="1846b-151">Es ist am einfachsten, die mit dem Microsoft-Teams, Administrationscenter online Telefonnummer festgelegt, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1846b-151">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="1846b-152">Sie können auch die `Set-CsOnlineVoiceApplicationInstance` Befehl für eine Zuweisung eine Rufnummer, das Ressourcenkonto nach der anfänglichen Erstellung wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1846b-152">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="1846b-153">Die Telefon Zuweisung schlägt fehl, wenn Sie keine Lizenz beim Erstellen des Ressourcenkontos anwenden.</span><span class="sxs-lookup"><span data-stu-id="1846b-153">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="1846b-154">Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1846b-154">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="1846b-155">Verwalten von Einstellungen für Ressource-Konto im Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="1846b-155">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="1846b-156">Navigieren Sie zum Verwalten von Einstellungen der Ressource-Konto im Microsoft-Teams, Administrationscenter zu **Org geltende Settings**  > **Ressource Firmen**, auswählen das Ressourcenkonto Sie Einstellungen für ändern müssen und dann auf die Schaltfläche **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="1846b-156">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="1846b-157">Klicken Sie im Bildschirm **Bearbeiten Ressourcenkonto** werden Sie ändern die:</span><span class="sxs-lookup"><span data-stu-id="1846b-157">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="1846b-158">**Anzeigename** für das Konto</span><span class="sxs-lookup"><span data-stu-id="1846b-158">**Display name** for the account</span></span>
- <span data-ttu-id="1846b-159">Rufen Sie die Warteschlange oder automatische um-Telefonzentrale, die das Konto verwendet</span><span class="sxs-lookup"><span data-stu-id="1846b-159">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="1846b-160">Das Konto zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="1846b-160">Phone number assigned to the account</span></span>

<span data-ttu-id="1846b-161">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1846b-161">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="1846b-162">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="1846b-162">Related Information</span></span>

<span data-ttu-id="1846b-163">Für Implementierungen sind, Hybrid mit Skype für Business Server:</span><span class="sxs-lookup"><span data-stu-id="1846b-163">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="1846b-164">Planen automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="1846b-164">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="1846b-165">Konfigurieren automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="1846b-165">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="1846b-166">Für Implementierungen in Teams oder Skype für Business Online:</span><span class="sxs-lookup"><span data-stu-id="1846b-166">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="1846b-167">Was sind automatische Telefonzentralen des Telefonsystems?</span><span class="sxs-lookup"><span data-stu-id="1846b-167">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="1846b-168">Einrichten einer automatischen Telefonzentrale des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="1846b-168">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="1846b-169">Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="1846b-169">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="1846b-170">Erstellen einer Warteschlange für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="1846b-170">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="1846b-171">Neue CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="1846b-171">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="1846b-172">Neue CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="1846b-172">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
