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
ms.openlocfilehash: 055e419e5a82233676e5b66857589216b4dbca6d
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517232"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="78be1-103">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="78be1-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="78be1-104">Ein Ressourcenkonto wird auch als ein deaktiviertes Benutzerobjekt in Azure Active Directory und kann verwendet werden, um Ressourcen im Allgemeinen darstellen.</span><span class="sxs-lookup"><span data-stu-id="78be1-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="78be1-105">In Exchange kann verwendet werden, Konferenzräumen, beispielsweise darstellen und ermöglicht es ihnen, Sie haben eine Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="78be1-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="78be1-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal mit Skype für Business Server verwaltet werden, und diese Konten werden mithilfe von Powershell-Befehlen erstellt.</span><span class="sxs-lookup"><span data-stu-id="78be1-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="78be1-107">In Microsoft-Teams oder Skype für Business Online, jeden Anruf Warteschlange oder automatische wird Attendant erforderlich, um ein Ressourcenkonto zugeordneten verfügen.</span><span class="sxs-lookup"><span data-stu-id="78be1-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="78be1-108">Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt wird abhängig von der beabsichtigten Verwendung von der zugehörigen Aufruf Warteschlange oder automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="78be1-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="78be1-109">Finden Sie in den Artikeln für Anruf Warteschlangen und automatische um-Telefonzentralen verknüpft unten in diesem Artikel, bevor Sie eine Telefonnummer ein Ressourcenkonto zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78be1-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="78be1-110">Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="78be1-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="78be1-111">Erforderliche Komponenten ein Ressourcenkonto eine Telefonnummer zuweisen</span><span class="sxs-lookup"><span data-stu-id="78be1-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="78be1-112">Erste Schritte beim es ist wichtig, sollten Sie einige Dinge bedenken:</span><span class="sxs-lookup"><span data-stu-id="78be1-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="78be1-113">Eine automatische Telefonzentrale oder ein Anruf Warteschlange ist erforderlich, um ein Ressourcenkonto zugeordneten verfügen.</span><span class="sxs-lookup"><span data-stu-id="78be1-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="78be1-114">Details auf Ressourcenkonten finden Sie unter [Manage Ressourcenkonten in Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="78be1-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="78be1-115">Wenn Sie eine direkte Routing Number zuweisen möchten, müssen Sie erwerben und weisen Sie die folgenden Lizenzen der Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on\).</span><span class="sxs-lookup"><span data-stu-id="78be1-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="78be1-116">Wenn Sie stattdessen eine Microsoft-Dienst Zahl zuordnen möchten, müssen Sie erwerben und weisen Sie Ihr Ressourcenkonto folgenden Lizenzen \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on und Aufrufen planen\).</span><span class="sxs-lookup"><span data-stu-id="78be1-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="78be1-117">Microsoft arbeitet eine entsprechende Lizenzierungsmodell für Anwendungen wie Cloud automatische Telefonzentrale und den Anruf-Warteschlangen für an jetzt Sie das Benutzerlizenzierung Objektmodell verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="78be1-117">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78be1-118">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans.</span><span class="sxs-lookup"><span data-stu-id="78be1-118">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="78be1-119">Finden Sie unter [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="78be1-119">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="78be1-120">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="78be1-120">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="78be1-121">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="78be1-121">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="78be1-122">Sie können eine direkte Routing Hybrid Anzahl Ihrer Ressourcenkonto zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78be1-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="78be1-123">Einzelheiten finden Sie unter [Planen der direkten Routing](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="78be1-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="78be1-124">Für Microsoft aufrufende plant können Sie nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder in einem Ressourcenkonto aus einer anderen Dienstanbieter übertragen.</span><span class="sxs-lookup"><span data-stu-id="78be1-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="78be1-125">Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.</span><span class="sxs-lookup"><span data-stu-id="78be1-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="78be1-126">Ein Ressourcenkonto können nicht Benutzer (Abonnent) Rufnummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="78be1-126">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="78be1-127">Nur Service gebührenpflichtige oder gebührenfreie Telefonnummern können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="78be1-127">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="78be1-128">Eine Telefonnummer ein, um ein Ressourcenkonto zuzuweisen, müssen Sie erhalten möchten, oder übertragen Ihre vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen.</span><span class="sxs-lookup"><span data-stu-id="78be1-128">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="78be1-129">Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="78be1-129">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="78be1-130">Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) oder wenn Sie eine vorhandene Servicenummer durchstellen möchten, finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="78be1-130">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="78be1-131">Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="78be1-131">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="78be1-132">Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="78be1-132">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="78be1-133">Erstellen Sie ein Ressourcenkonto im Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="78be1-133">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="78be1-134">Navigieren Sie zum Erstellen einer Ressourcenkontos im Microsoft-Teams, Administrationscenter zu **Org geltende Settings** > **Ressourcenkonten**, klicken Sie dann auf **+ Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="78be1-134">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="78be1-135">Im Popup füllen Sie den Anzeigenamen und Benutzernamen für das Ressourcenkonto (der Domänenname sollte automatisch aufgefüllt) klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="78be1-135">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Ressource-Konto](media/res-acct.png)

<span data-ttu-id="78be1-137">Sie müssen auch das Ressourcenkonto eine Lizenz gilt gemäß [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="78be1-137">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="78be1-138">Sobald Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, klicken Sie auf **Zuweisen/Zuweisung entfernen** das Ressourcenkonto eine Telefonnummer zuweisen oder eine automatische Telefonzentrale oder ein Anruf-Warteschlange das Ressourcenkonto zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="78be1-138">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="78be1-139">Erstellen Sie ein Ressourcenkonto in Powershell</span><span class="sxs-lookup"><span data-stu-id="78be1-139">Create a resource account in Powershell</span></span>

 <span data-ttu-id="78be1-140">Sie würden ein Ressourcenkonto durch Ausführen des entsprechenden Powershell-Cmdlets (für eine oder mehrere Ressourcenkonten) nach Bedarf erstellen, und geben Sie jeweils einen Namen und so weiter.</span><span class="sxs-lookup"><span data-stu-id="78be1-140">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="78be1-141">Derzeit keine Option zum Erstellen einer Ressource-Konto in der Verwaltungskonsole von Microsoft-Teams vorliegt, aber Sie können Telefonnummern bearbeiten und ändern Sie die Anruf Warteschlange oder Auto attendant Zuordnungen für ein Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="78be1-141">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="78be1-142">Je nachdem, ob Ihre Telefonnummer online oder lokal befindet müssen Sie in der entsprechenden Aufforderung Powershell mit Administratorberechtigungen eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="78be1-142">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="78be1-143">Hybrid Implementierungen (Zahlen Zahlen verwaltet auf direktes Routing, OPCH und CCE) werden [Neu CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) verwenden, um ein Ressourcenkonto erstellen, die lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="78be1-143">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="78be1-144">Nur Online Implementierungen [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) verwendet, die ein Resource-Konto verfügen, die online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="78be1-144">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="78be1-145">Es folgt ein Beispiel für online-Umgebung mit einer automatischen Telefonzentrale ApplicationID Ressourcenkonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="78be1-145">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="78be1-146">Für eine Warteschlange Anruf können Sie die folgenden ApplicationID 11cd3e2e-Fccb-42ad-ad00-878b93575e07 verwenden:</span><span class="sxs-lookup"><span data-stu-id="78be1-146">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="78be1-147">Weitere Informationen zu diesem Befehl finden Sie unter [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="78be1-147">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="78be1-148">Es ist am einfachsten, die mit dem Microsoft-Teams, Administrationscenter online Telefonnummer festgelegt, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78be1-148">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="78be1-149">Sie können auch die `Set-CsOnlineVoiceApplicationInstance` Befehl für eine Zuweisung eine Rufnummer, das Ressourcenkonto nach der anfänglichen Erstellung wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="78be1-149">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="78be1-150">Die Telefon Zuweisung schlägt fehl, wenn Sie keine Lizenz beim Erstellen des Ressourcenkontos anwenden.</span><span class="sxs-lookup"><span data-stu-id="78be1-150">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="78be1-151">Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="78be1-151">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="78be1-152">Verwalten von Einstellungen für Ressource-Konto im Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="78be1-152">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="78be1-153">Navigieren Sie zum Verwalten von Einstellungen der Ressource-Konto im Microsoft-Teams, Administrationscenter zu **Org geltende Settings**  > **Ressource Firmen**, auswählen das Ressourcenkonto Sie Einstellungen für ändern müssen und dann auf die Schaltfläche **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="78be1-153">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="78be1-154">Klicken Sie im Bildschirm **Bearbeiten Ressourcenkonto** werden Sie ändern die:</span><span class="sxs-lookup"><span data-stu-id="78be1-154">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="78be1-155">**Anzeigename** für das Konto</span><span class="sxs-lookup"><span data-stu-id="78be1-155">**Display name** for the account</span></span>
- <span data-ttu-id="78be1-156">Rufen Sie die Warteschlange oder automatische um-Telefonzentrale, die das Konto verwendet</span><span class="sxs-lookup"><span data-stu-id="78be1-156">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="78be1-157">Das Konto zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="78be1-157">Phone number assigned to the account</span></span>

<span data-ttu-id="78be1-158">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="78be1-158">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="78be1-159">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="78be1-159">Related Information</span></span>

<span data-ttu-id="78be1-160">Für Implementierungen sind, Hybrid mit Skype für Business Server:</span><span class="sxs-lookup"><span data-stu-id="78be1-160">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="78be1-161">Planen automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="78be1-161">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="78be1-162">Konfigurieren automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="78be1-162">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="78be1-163">Für Implementierungen in Teams oder Skype für Business Online:</span><span class="sxs-lookup"><span data-stu-id="78be1-163">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="78be1-164">Was sind automatische Telefonzentralen des Telefonsystems?</span><span class="sxs-lookup"><span data-stu-id="78be1-164">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="78be1-165">Einrichten einer automatischen Telefonzentrale des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="78be1-165">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="78be1-166">Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="78be1-166">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="78be1-167">Erstellen einer Warteschlange für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="78be1-167">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="78be1-168">Neue CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="78be1-168">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="78be1-169">Neue CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="78be1-169">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
