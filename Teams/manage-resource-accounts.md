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
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Verwalten von Resource-Konten in Microsoft-Teams
ms.openlocfilehash: 60fcfe34c665805eac90b5e5be862786e9e68de5
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210780"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="a10e4-103">Verwalten von Resource-Konten in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="a10e4-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="a10e4-104">Ein Ressourcenkonto wird auch als ein deaktiviertes Benutzerobjekt in Azure Active Directory und kann verwendet werden, um Ressourcen im Allgemeinen darstellen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="a10e4-105">In Exchange kann verwendet werden, Konferenzräumen, beispielsweise darstellen und ermöglicht es ihnen, Sie haben eine Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="a10e4-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="a10e4-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal mit Skype für Business Server verwaltet werden, und diese Konten werden mithilfe von Powershell-Befehlen erstellt.</span><span class="sxs-lookup"><span data-stu-id="a10e4-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="a10e4-107">In Microsoft-Teams oder Skype für Business Online, jeden Anruf Warteschlange oder automatische wird Attendant erforderlich, um ein Ressourcenkonto zugeordneten verfügen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="a10e4-108">Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt wird abhängig von der beabsichtigten Verwendung von der zugehörigen Aufruf Warteschlange oder automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="a10e4-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="a10e4-109">Finden Sie in den Artikeln für Anruf Warteschlangen und automatische um-Telefonzentralen verknüpft unten in diesem Artikel, bevor Sie eine Telefonnummer ein Ressourcenkonto zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="a10e4-110">Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="a10e4-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="a10e4-111">Erforderliche Komponenten ein Ressourcenkonto eine Telefonnummer zuweisen</span><span class="sxs-lookup"><span data-stu-id="a10e4-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="a10e4-112">Erste Schritte beim es ist wichtig, sollten Sie einige Dinge bedenken:</span><span class="sxs-lookup"><span data-stu-id="a10e4-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="a10e4-113">Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-113">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="a10e4-114">Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für die Ressourcenkonten zugewiesenen Warteschlangen oder automatische Telefonzentralen Aufrufen bei verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a10e4-114">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for resource accounts assigned to call queues or auto attendants.</span></span> <span data-ttu-id="a10e4-115">Die Anzahl der Ressourcenkonten ab können ist abhängig von der Anzahl der **Telefonsystem** und **Audiokonferenzen** Lizenzen, die in Ihrer Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a10e4-115">The number of resource accounts you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="a10e4-116">Weitere Informationen zu Lizenzierung finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a10e4-116">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a10e4-117">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans.</span><span class="sxs-lookup"><span data-stu-id="a10e4-117">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="a10e4-118">Finden Sie unter [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a10e4-118">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="a10e4-119">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a10e4-119">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="a10e4-120">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="a10e4-120">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="a10e4-121">Weitere Informationen zu Office 365 aufrufen plant, finden Sie unter [Aufrufen für Office 365 Plans](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a10e4-121">To learn more about Office 365 Calling Plans, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>
- <span data-ttu-id="a10e4-122">Sie können nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder in einem Ressourcenkonto aus einer anderen Dienstanbieter übertragen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-122">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="a10e4-123">Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.</span><span class="sxs-lookup"><span data-stu-id="a10e4-123">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="a10e4-124">Ein Ressourcenkonto können nicht Benutzer (Abonnent) Rufnummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a10e4-124">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="a10e4-125">Nur Service gebührenpflichtige oder gebührenfreie Telefonnummern können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a10e4-125">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="a10e4-126">Eine Telefonnummer ein, um ein Ressourcenkonto zuzuweisen, müssen Sie erhalten möchten, oder übertragen Ihre vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-126">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="a10e4-127">Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a10e4-127">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="a10e4-128">Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) oder Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a10e4-128">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a10e4-129">Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a10e4-129">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="a10e4-130">Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a10e4-130">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="a10e4-131">Erstellen Sie ein Ressourcenkonto in Powershell</span><span class="sxs-lookup"><span data-stu-id="a10e4-131">Create a resource account in Powershell</span></span>

 <span data-ttu-id="a10e4-132">Sie würden ein Ressourcenkonto durch Ausführen des entsprechenden Powershell-Cmdlets (für eine oder mehrere Ressourcenkonten) nach Bedarf erstellen, und geben Sie jeweils einen Namen und so weiter.</span><span class="sxs-lookup"><span data-stu-id="a10e4-132">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="a10e4-133">Derzeit keine Option zum Erstellen einer Ressource-Konto in der Verwaltungskonsole von Microsoft-Teams vorliegt, aber Sie können Telefonnummern bearbeiten und ändern Sie die Anruf Warteschlange oder Auto attendant Zuordnungen für ein Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="a10e4-133">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="a10e4-134">Je nachdem, ob Ihre Telefonnummer online oder lokal befindet müssen Sie in der entsprechenden Aufforderung Powershell mit Administratorberechtigungen eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="a10e4-134">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="a10e4-135">Hybrid Implementierungen (Zahlen Zahlen verwaltet auf direktes Routing, OPCH und CCE) werden [Neu CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) verwenden, um ein Ressourcenkonto erstellen, die lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="a10e4-135">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="a10e4-136">Nur Online Implementierungen [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) verwendet, die ein Resource-Konto verfügen, die online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="a10e4-136">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="a10e4-137">Es folgt ein Beispiel für online-Umgebung ein Ressourcenkonto erstellen:</span><span class="sxs-lookup"><span data-stu-id="a10e4-137">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

<span data-ttu-id="a10e4-138">Weitere Informationen zu diesem Befehl finden Sie unter [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="a10e4-138">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="a10e4-139">Es ist am einfachsten kann die Telefonnummer ein, mit dem Microsoft-Teams, Administrationscenter festlegen, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a10e4-139">It's easiest to set the phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="a10e4-140">Sie können auch die `Set-CsOnlineApplicationInstance` Befehl für eine Zuweisung eine Rufnummer, das Ressourcenkonto nach der anfänglichen Erstellung wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a10e4-140">You can also use the `Set-CsOnlineApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

<span data-ttu-id="a10e4-141">Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="a10e4-141">See [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="a10e4-142">Verwalten von Einstellungen für Ressource-Konto im Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="a10e4-142">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="a10e4-143">Navigieren Sie zum Verwalten von Einstellungen der Ressource-Konto im Microsoft-Teams, Administrationscenter zu **Org geltende Settings**  > **Ressource Firmen**, auswählen das Ressourcenkonto Sie Einstellungen für ändern müssen und dann auf die Schaltfläche **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="a10e4-143">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="a10e4-144">Klicken Sie im Bildschirm **Bearbeiten Ressourcenkonto** werden Sie ändern die:</span><span class="sxs-lookup"><span data-stu-id="a10e4-144">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="a10e4-145">**Anzeigename** für das Konto</span><span class="sxs-lookup"><span data-stu-id="a10e4-145">**Display name** for the account</span></span>
- <span data-ttu-id="a10e4-146">Rufen Sie die Warteschlange oder automatische um-Telefonzentrale, die das Konto verwendet</span><span class="sxs-lookup"><span data-stu-id="a10e4-146">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="a10e4-147">Das Konto zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="a10e4-147">Phone number assigned to the account</span></span>

<span data-ttu-id="a10e4-148">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a10e4-148">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="a10e4-149">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="a10e4-149">Related Information</span></span>

<span data-ttu-id="a10e4-150">Für Implementierungen sind, Hybrid mit Skype für Business Server:</span><span class="sxs-lookup"><span data-stu-id="a10e4-150">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="a10e4-151">Planen von Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="a10e4-151">Plan Cloud auto attendant</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="a10e4-152">Konfigurieren von Cloud-Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="a10e4-152">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="a10e4-153">Für Implementierungen in Teams oder Skype für Business Online:</span><span class="sxs-lookup"><span data-stu-id="a10e4-153">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="a10e4-154">Was sind automatische Telefonzentralen des Telefonsystems?</span><span class="sxs-lookup"><span data-stu-id="a10e4-154">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="a10e4-155">Einrichten einer automatischen Telefonzentrale für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="a10e4-155">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="a10e4-156">Beispiel für Small Business - richten Sie eine automatische Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="a10e4-156">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="a10e4-157">Erstellen einer Telefonsystem-Anrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="a10e4-157">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="a10e4-158">Neue CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="a10e4-158">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="a10e4-159">Neue CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a10e4-159">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
