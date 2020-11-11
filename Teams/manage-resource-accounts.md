---
title: Verwalten von Ressourcenkonten in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Ressourcenkonten in Microsoft Teams erstellen, bearbeiten und verwalten können.
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993517"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="cea51-103">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cea51-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="cea51-104">Ein Ressourcenkonto ist ein deaktiviertes Benutzerobjekt in Azure AD und kann verwendet werden, um Ressourcen im allgemeinen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="cea51-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="cea51-105">So kann beispielsweise ein Ressourcenkonto in Exchange verwendet werden, um Konferenzräume darzustellen und Ihnen eine Telefonnummer und einen Kalender zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cea51-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="cea51-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cea51-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="cea51-107">In Microsoft Teams ist für jede automatische Telefonzentrale oder Anrufwarteschlange ein Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cea51-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="cea51-108">Ressourcenkonten können auch Service-Telefonnummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cea51-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="cea51-109">So weisen Sie den automatischen Telefonzentralen und Anrufwarteschlangen Telefonnummern zu, die es den Anrufern von außerhalb der Teams ermöglichen, die automatische Telefonzentrale oder die Anrufwarteschlange zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="cea51-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="cea51-110">In diesem Artikel wird erläutert, wie Ressourcenkonten erstellt und für die Verwendung mit automatischen Telefonzentralen und Anrufwarteschlangen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cea51-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="cea51-111">Bevor Sie mit den Verfahren in diesem Artikel beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="cea51-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="cea51-112">Abrufen von Lizenzen für virtuelle Benutzer</span><span class="sxs-lookup"><span data-stu-id="cea51-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="cea51-113">Abrufen von Servicenummern</span><span class="sxs-lookup"><span data-stu-id="cea51-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="cea51-114">Abrufen von Lizenzen für virtuelle Benutzer</span><span class="sxs-lookup"><span data-stu-id="cea51-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="cea51-115">Für jedes Ressourcenkonto ist eine Lizenz erforderlich, damit Sie mit automatischen Telefonzentralen und Anrufwarteschlangen arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="cea51-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="cea51-116">Sie können eine ﻿kostenlose *Microsoft 365-Telefon System-virtuelle Benutzer* Lizenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="cea51-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="cea51-117">Informationen zum Abrufen dieser Lizenzen finden Sie unter [Lizenz für virtuelle Benutzer](teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="cea51-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="cea51-118">Es wird erläutert, wie Sie die Lizenz einem Ressourcenkonto später in diesem Artikel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cea51-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="cea51-119">Wenn Sie die Lizenz für virtuelle Benutzer erhalten möchten, wechseln Sie im Microsoft 365 Admin Center zu den Abonnements für **Billing**  >  **Purchase Services** -  >  **Add-on** , und Scrollen Sie bis zum Ende – Sie sehen die Lizenz für das *Telefon System-Virtual User* .</span><span class="sxs-lookup"><span data-stu-id="cea51-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="cea51-120">Wählen Sie **Jetzt kaufen** aus.</span><span class="sxs-lookup"><span data-stu-id="cea51-120">Select **Buy now**.</span></span> <span data-ttu-id="cea51-121">Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="cea51-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="cea51-122">Abrufen von Servicenummern</span><span class="sxs-lookup"><span data-stu-id="cea51-122">Obtain service numbers</span></span>

<span data-ttu-id="cea51-123">Dienstnummern sind für automatische Telefonzentralen und Anrufwarteschlangen optional, Sie benötigen jedoch mindestens eine Dienstnummer, damit Anrufer Ihre automatische Telefonzentrale und die Konfiguration der Anrufwarteschlange erreichen können.</span><span class="sxs-lookup"><span data-stu-id="cea51-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="cea51-124">Für jede automatische Telefonzentrale oder Anrufwarteschlange, deren direkte Erreichbarkeit durch eine Dienstnummer erfolgen soll, müssen Sie über ein Ressourcenkonto mit einer zugehörigen Servicenummer verfügen.</span><span class="sxs-lookup"><span data-stu-id="cea51-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="cea51-125">Ressourcenkonten können entweder gebührenpflichtige oder gebührenfreie Servicenummern verwenden.</span><span class="sxs-lookup"><span data-stu-id="cea51-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="cea51-126">Sie können neue Nummern anfordern oder vorhandene Nummern von einem anderen Netzbetreiber portieren.</span><span class="sxs-lookup"><span data-stu-id="cea51-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="cea51-127">Informationen zum Abrufen neuer Servicenummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="cea51-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="cea51-128">Informationen zum Portieren einer Nummer von einem anderen Netzbetreiber finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cea51-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="cea51-129">Erstellen eines Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="cea51-129">Create a resource account</span></span>

<span data-ttu-id="cea51-130">Sie können ein Ressourcenkonto im Team Admin Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="cea51-130">You can create a resource account in the Teams admin center.</span></span>

![Screenshot der Benutzeroberfläche "Ressourcenkonto hinzufügen"](media/resource-account-add.png)

1. <span data-ttu-id="cea51-132">Erweitern Sie im Team Admin Center **organisationsweite Einstellungen** , und klicken Sie dann auf **Ressourcenkonten**.</span><span class="sxs-lookup"><span data-stu-id="cea51-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="cea51-133">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cea51-133">Click **Add**.</span></span>

3. <span data-ttu-id="cea51-134">Füllen Sie im Bereich **Ressourcenkonto hinzufügen** die **Anzeigename** , den **Benutzernamen** und den **Typ des Ressourcenkontos** aus.</span><span class="sxs-lookup"><span data-stu-id="cea51-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="cea51-135">Der Typ des Ressourcenkontos kann eine **automatische Telefonzentrale** oder eine **Anrufwarteschlange** sein, je nachdem, wie Sie dieses Ressourcenkonto verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cea51-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="cea51-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cea51-136">Click **Save**.</span></span>

![Screenshot einer Liste von Ressourcenkonten](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="cea51-138">Zuweisen einer Lizenz</span><span class="sxs-lookup"><span data-stu-id="cea51-138">Assign a license</span></span>

<span data-ttu-id="cea51-139">Für jedes Ressourcenkonto müssen Sie eine *Microsoft 365-Telefonsystem-virtuelle Benutzer* Lizenz oder eine *Telefonsystem* Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cea51-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Screenshot der Benutzeroberfläche "Lizenzen zuweisen" im Microsoft 365 Admin Center](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="cea51-141">Klicken Sie im Microsoft 365 Admin Center auf das Ressourcenkonto, dem Sie eine Lizenz zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="cea51-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="cea51-142">Wählen Sie auf der Registerkarte **Lizenzen und apps** unter **Lizenzen** den Eintrag **Microsoft 365 Phone System – Virtual User** aus.</span><span class="sxs-lookup"><span data-stu-id="cea51-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="cea51-143">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="cea51-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="cea51-144">Zuweisen einer Servicenummer</span><span class="sxs-lookup"><span data-stu-id="cea51-144">Assign a service number</span></span>

<span data-ttu-id="cea51-145">Wenn Sie beabsichtigen, das Ressourcenkonto mit einer automatischen Telefonzentrale oder einer Anrufwarteschlange zu verwenden, für die eine Dienstnummer erforderlich ist, weisen Sie dem Ressourcenkonto eine Nummer zu.</span><span class="sxs-lookup"><span data-stu-id="cea51-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Screenshot der Benutzeroberfläche "Dienstnummer zuweisen"](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="cea51-147">Wählen Sie im Team Admin Center auf der Seite **Ressourcenkonten** das Ressourcenkonto aus, dem Sie eine Dienstnummer zuweisen möchten, und klicken Sie dann auf **zuweisen/** Aufheben der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="cea51-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="cea51-148">Wählen Sie in der Dropdownliste **Telefonnummerntyp** den Typ der Nummer aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cea51-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="cea51-149">Suchen Sie im Feld **zugewiesene Rufnummer** nach der Nummer, die Sie verwenden möchten, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cea51-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="cea51-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cea51-150">Click **Save**.</span></span>


<span data-ttu-id="cea51-151">Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuweisen möchten, müssen Sie PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="cea51-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="cea51-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cea51-152">Next steps</span></span>

<span data-ttu-id="cea51-153">Nachdem Sie die Einrichtung des Ressourcenkontos abgeschlossen und bei Bedarf eine Dienstnummer zugewiesen haben, können Sie das Ressourcenkonto mit einer automatischen Telefonzentrale oder einer Anrufwarteschlange verwenden.</span><span class="sxs-lookup"><span data-stu-id="cea51-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="cea51-154">Sehen Sie sich die folgenden Verweise an:</span><span class="sxs-lookup"><span data-stu-id="cea51-154">See the following references:</span></span>

 - [<span data-ttu-id="cea51-155">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="cea51-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="cea51-156">Cloud-Anrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="cea51-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="cea51-157">Mit der Option **Bearbeiten** können Sie den **Anzeigenamen** und den **Ressourcen** Kontotyp des Ressourcenkontos bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cea51-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="cea51-158">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cea51-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="cea51-159">Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden</span><span class="sxs-lookup"><span data-stu-id="cea51-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="cea51-160">Wenn Sie sich entscheiden, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer **Telefon System** Lizenz zu einer virtuellen Benutzerlizenz zu wechseln, müssen Sie die ﻿kostenlose virtuelle Benutzerlizenz erwerben und dann die Schritte im Microsoft 365 Admin Center ausführen, um [Benutzer in ein anderes Abonnement zu verschieben](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="cea51-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="cea51-161">Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu.</span><span class="sxs-lookup"><span data-stu-id="cea51-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="cea51-162">Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="cea51-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="cea51-163">In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="cea51-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="cea51-164">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cea51-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="cea51-165">Informationen zu Ressourcenkonten in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Planen von Cloud-Anrufwarteschlangen](/SkypeforBusiness/hybrid/plan-call-queue) oder [Planen automatischer Cloud-Telefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="cea51-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="cea51-166">Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) werden mithilfe des Cmdlets [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cea51-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="cea51-167">Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen verwenden müssen, sind:</span><span class="sxs-lookup"><span data-stu-id="cea51-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="cea51-168">**Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="cea51-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="cea51-169">**Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="cea51-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="cea51-170">Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cea51-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="cea51-171">Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, **müssen** in Skype for Business Server 2019 mithilfe der SFB-Verwaltungsshell Ressourcenkonten erstellt und mit Azure AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cea51-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="cea51-172">Bei hybride Implementierungen mit Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="cea51-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="cea51-173">Planen automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="cea51-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="cea51-174">Planen von Cloud-Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="cea51-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="cea51-175">Konfigurieren lokalen von Ressourcenkonten</span><span class="sxs-lookup"><span data-stu-id="cea51-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="cea51-176">Löschen eines Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="cea51-176">Delete a resource account</span></span>

<span data-ttu-id="cea51-177">Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt.</span><span class="sxs-lookup"><span data-stu-id="cea51-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="cea51-178">Anschließend können Sie das Ressourcenkonto im Microsoft 365 Admin Center auf der Registerkarte Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="cea51-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="cea51-179">Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:</span><span class="sxs-lookup"><span data-stu-id="cea51-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
