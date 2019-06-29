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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Informationen zum Verwalten von Ressourcenkonten in Microsoft Teams
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394500"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="a1338-103">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a1338-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="a1338-104">Ein Ressourcenkonto wird auch als deaktiviertes Benutzerobjekt in Azure Active Directory bezeichnet und kann verwendet werden, um Ressourcen im allgemeinen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="a1338-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="a1338-105">In Exchange kann Sie beispielsweise dazu verwendet werden, Konferenzräume darzustellen und Ihnen die Möglichkeit zu geben, eine Telefonnummer zu haben.</span><span class="sxs-lookup"><span data-stu-id="a1338-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="a1338-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a1338-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="a1338-107">In Microsoft Teams oder Skype for Business Online ist für jede Anrufwarteschlange oder automatische Telefonzentrale ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1338-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="a1338-108">Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der beabsichtigten Verwendung der zugehörigen Anrufwarteschlange oder der automatischen Telefonzentrale ab.</span><span class="sxs-lookup"><span data-stu-id="a1338-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="a1338-109">Weitere Informationen finden Sie in den Artikeln zu Anrufwarteschlangen und automatischen Telefonzentralen, die am Ende dieses Artikels verknüpft sind, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a1338-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="a1338-110">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="a1338-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="a1338-111">Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="a1338-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="a1338-112">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a1338-112">Overview</span></span>

<span data-ttu-id="a1338-113">Wenn Ihr Telefon System Dienst eine Dienstnummer benötigt, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="a1338-113">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="a1338-114">Abrufen einer Dienstnummer</span><span class="sxs-lookup"><span data-stu-id="a1338-114">Obtain a service number</span></span>
2. <span data-ttu-id="a1338-115">Kaufen Sie eine Telefonsystem Lizenz (Office 365 Enterprise E1 oder E3 mit Telefonsystem hinzugefügt oder Office 365 Enterprise E5, das Telefonsystem umfasst)</span><span class="sxs-lookup"><span data-stu-id="a1338-115">Buy a Phone System license (Office 365 Enterprise E1 or E3 with Phone System added, or Office 365 Enterprise E5 which includes Phone System)</span></span>
3. <span data-ttu-id="a1338-116">Erstellen Sie das Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="a1338-116">Create the resource account.</span></span> <span data-ttu-id="a1338-117">Eine automatische Telefonzentrale oder eine Anrufwarteschlange ist für ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1338-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="a1338-118">Weisen Sie dem Ressourcenkonto die Lizenz für das Telefon System zu.</span><span class="sxs-lookup"><span data-stu-id="a1338-118">Assign the Phone System license to the resource account.</span></span>
5. <span data-ttu-id="a1338-119">Weisen Sie dem Ressourcenkonto eine Telefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="a1338-119">Assign a phone number to the resource account.</span></span>
6. <span data-ttu-id="a1338-120">Erstellen eines Telefon System Diensts (eine Anrufwarteschlange oder eine automatische Telefonzentrale)</span><span class="sxs-lookup"><span data-stu-id="a1338-120">Create a Phone System service (a call queue or auto attendant)</span></span>
7. <span data-ttu-id="a1338-121">Zuordnen des Ressourcenkontos zu einem Dienst: (neu-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="a1338-121">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="a1338-122">Wenn die automatische Telefonzentrale oder Anrufwarteschlange unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="a1338-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="a1338-123">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen.</span><span class="sxs-lookup"><span data-stu-id="a1338-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="a1338-124">Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a1338-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="a1338-125">Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1338-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="a1338-126">Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="a1338-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="a1338-127">Wenn der Telefonsystem Dienst, den Sie erstellen, geschachtelt wird und keine Telefonnummer benötigt, lautet der Vorgang wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1338-127">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="a1338-128">Erstellen des Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="a1338-128">Create the resource account</span></span>  
2. <span data-ttu-id="a1338-129">Erstellen eines Telefon System Diensts</span><span class="sxs-lookup"><span data-stu-id="a1338-129">Create a Phone System service</span></span>
3. <span data-ttu-id="a1338-130">Zuordnen des Ressourcenkontos zu einem Telefon System Dienst</span><span class="sxs-lookup"><span data-stu-id="a1338-130">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="a1338-131">Erstellen eines Ressourcenkontos mit einer Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="a1338-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="a1338-132">Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a1338-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="a1338-133">Portieren oder eine gebührenpflichtige oder gebührenfreie Servicenummer erhalten.</span><span class="sxs-lookup"><span data-stu-id="a1338-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="a1338-134">Die Nummer kann keinen anderen VoIP-Diensten oder Ressourcenkonten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a1338-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="a1338-135">Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren.</span><span class="sxs-lookup"><span data-stu-id="a1338-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="a1338-136">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **sprach** > **Telefonnummern**angezeigt, und der angegebene **Nummerntyp** wird als " **Dienst gebührenfrei**" aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1338-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="a1338-137">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](getting-service-phone-numbers.md) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a1338-137">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

2. <span data-ttu-id="a1338-138">Kaufen Sie eine Telefon System Lizenz.</span><span class="sxs-lookup"><span data-stu-id="a1338-138">Buy a Phone System license.</span></span> <span data-ttu-id="a1338-139">Sieh:</span><span class="sxs-lookup"><span data-stu-id="a1338-139">See:</span></span>  
   - [<span data-ttu-id="a1338-140">Office 365 Enterprise E1- und E3</span><span class="sxs-lookup"><span data-stu-id="a1338-140">Office 365 Enterprise E1 and E3</span></span>](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [<span data-ttu-id="a1338-141">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="a1338-141">Office 365 Enterprise E5</span></span>](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [<span data-ttu-id="a1338-142">Office 365 Enterprise E5-Software für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a1338-142">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="a1338-143">Erstellen Sie ein neues Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="a1338-143">Create a new resource account.</span></span> <span data-ttu-id="a1338-144">Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="a1338-144">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="a1338-145">Weisen Sie dem Ressourcenkonto die Lizenz für das Telefon System zu.</span><span class="sxs-lookup"><span data-stu-id="a1338-145">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="a1338-146">Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md) und [Zuweisen von Lizenzen zu einem Benutzer](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="a1338-146">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="a1338-147">Weisen Sie dem Ressourcenkonto die Dienstnummer zu.</span><span class="sxs-lookup"><span data-stu-id="a1338-147">Assign the service number to the resource account.</span></span> <span data-ttu-id="a1338-148">Weitere Informationen finden Sie unter Zuweisen/Aufheben der [Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="a1338-148">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="a1338-149">Richten Sie eine der folgenden Optionen ein:</span><span class="sxs-lookup"><span data-stu-id="a1338-149">Set up one of the following:</span></span>
   - [<span data-ttu-id="a1338-150">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="a1338-150">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="a1338-151">Cloud-Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="a1338-151">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="a1338-152">Weisen Sie dem Dienst das Ressourcenkonto zu.</span><span class="sxs-lookup"><span data-stu-id="a1338-152">Assign the resource account to the service.</span></span> <span data-ttu-id="a1338-153">Siehe [zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="a1338-153">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="a1338-154">Erstellen eines Ressourcenkontos ohne Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="a1338-154">Create a resource account without a phone number</span></span>

<span data-ttu-id="a1338-155">Zum Erstellen eines Ressourcenkontos, das keine Telefonnummer benötigt, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a1338-155">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="a1338-156">Erstellen Sie ein neues Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="a1338-156">Create a new resource account.</span></span> <span data-ttu-id="a1338-157">Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="a1338-157">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="a1338-158">Richten Sie eine der folgenden Optionen ein:</span><span class="sxs-lookup"><span data-stu-id="a1338-158">Set up one of the following:</span></span>
   - [<span data-ttu-id="a1338-159">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="a1338-159">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="a1338-160">Cloud-Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="a1338-160">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="a1338-161">Weisen Sie dem Dienst das Ressourcenkonto zu.</span><span class="sxs-lookup"><span data-stu-id="a1338-161">Assign the resource account to the service.</span></span> <span data-ttu-id="a1338-162">Siehe [zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="a1338-162">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="a1338-163">Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="a1338-163">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="a1338-164">Nachdem Sie eine Telefon System Lizenz und einen Anrufplan mit dem Microsoft Teams Admin Center gekauft haben, navigieren Sie zu den **organisationsweiten Einstellungen** > für**Ressourcenkonten**.</span><span class="sxs-lookup"><span data-stu-id="a1338-164">After you've bought a Phone System license and a Calling Plan, using Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Screenshot der Seite "Ressourcenkonten"](media/r-a-master.png)

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<span data-ttu-id="a1338-167">Klicken Sie zum Erstellen eines neuen Ressourcenkontos auf **+ Neues Konto**.</span><span class="sxs-lookup"><span data-stu-id="a1338-167">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="a1338-168">Füllen Sie im Popup den Anzeigenamen und den Benutzernamen für das Ressourcenkonto aus (der Domänenname sollte automatisch aufgefüllt werden), und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a1338-168">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Screenshot der Optionen für das neue Ressourcenkonto](media/res-acct.png)

<span data-ttu-id="a1338-170">Wenden Sie als nächstes eine Lizenz auf das Ressourcenkonto im Office 365 Admin Center an, wie unter [Zuweisen von Lizenzen für Benutzer in Office 365 for Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a1338-170">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="a1338-171">Ressourcenkontoname bearbeiten</span><span class="sxs-lookup"><span data-stu-id="a1338-171">Edit resource account name</span></span>

<span data-ttu-id="a1338-172">![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png) verweist Sie können den Anzeigenamen des Ressourcenkontos mit der Option " **Bearbeiten** " bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a1338-172">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="a1338-173">Klicken Sie auf **Speichern** , wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="a1338-173">Click **Save** when you are done.</span></span>
<span data-ttu-id="a1338-174">![Screenshot der Option "Ressourcenkonto bearbeiten"](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="a1338-174">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="a1338-175">Zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten</span><span class="sxs-lookup"><span data-stu-id="a1338-175">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="a1338-176">![Symbol der Zahl 3, auf eine Beschriftung im vorherigen Screenshot](media/sfbcallout3.png) verweisen nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen/Aufheben der **Zuweisung** klicken, um dem Ressourcenkonto eine Dienstnummer zuzuweisen oder die Ressource zuzuweisen. Konto an eine automatische Telefonzentrale oder eine Anrufwarteschlange, die bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a1338-176">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="a1338-177">Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a1338-177">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="a1338-178">Wenn Ihre Anrufwarteschlange oder automatische Telefonzentrale noch erstellt werden muss, können Sie das Ressourcenkonto während der Erstellung verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="a1338-178">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="a1338-179">Klicken Sie auf **Speichern** , wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="a1338-179">Click **Save** when you are done.</span></span>

<span data-ttu-id="a1338-180">Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuweisen möchten, müssen Sie PowerShell verwenden, und lesen Sie den folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a1338-180">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1338-181">Wenn Ihr Mandant keine Telefon System Lizenz hat, führt eine interne Überprüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a1338-181">If your tenant doesn't have a Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="a1338-182">Sie können die Nummer nicht zuweisen oder das Ressourcenkonto einem Dienst zuordnen.</span><span class="sxs-lookup"><span data-stu-id="a1338-182">You won't be able to assign the number or associate the resource account with a service.</span></span>

![Screenshot der Optionen zum Zuweisen/Aufheben der Zuweisung](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="a1338-184">Erstellen eines Ressourcenkontos in PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1338-184">Create a resource account in Powershell</span></span>

<span data-ttu-id="a1338-185">Je nachdem, ob sich Ihr Ressourcenkonto Online oder lokal befindet, müssen Sie mit der entsprechenden PowerShell-Aufforderung mit Administratorrechten eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="a1338-185">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="a1338-186">In den folgenden PowerShell-Cmdlet-Beispielen wird davon ausgegangen, dass das Ressourcenkonto mithilfe von [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) online verwaltet wird, um ein Online verwaltetes Ressourcenkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1338-186">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="a1338-187">Informationen zu Ressourcenkonten, die lokal in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, verwaltet werden, finden Sie unter [Konfigurieren von Cloud-Anrufwarteschlangen](/skypeforbusiness/hybrid/configure-call-queue.md) oder [Konfigurieren von automatischen Cloud-Telefonzentralen](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="a1338-187">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="a1338-188">Bei Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) wird [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1338-188">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="a1338-189">Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen verwenden müssen, sind:</span><span class="sxs-lookup"><span data-stu-id="a1338-189">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="a1338-190">**Automatische Telefonzentrale:** ce933385-9390-45D1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="a1338-190">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="a1338-191">**Anrufwarteschlange:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="a1338-191">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="a1338-192">Wenn Sie möchten, dass die Anrufwarteschlange oder die automatische Telefonzentrale von lokalen Benutzern durchsucht werden kann, sollten Sie Ihre Ressourcenkonten lokal erstellen, da Online Ressourcenkonten nicht mit Active Directory synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1338-192">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="a1338-193">Verwenden Sie den folgenden Befehl, um ein Ressourcenkonto für die Verwendung mit einer automatischen Telefonzentrale online zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1338-193">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="a1338-194">Sie können das Ressourcenkonto erst dann verwenden, wenn Sie ihm eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a1338-194">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="a1338-195">Informationen zum Anwenden einer Lizenz auf ein Konto im Office 365 Admin Center finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 für Unternehmen](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) und [Zuweisen von Lizenzen für Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="a1338-195">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="a1338-196">Optional Nachdem die richtige Lizenz auf das Ressourcenkonto angewendet wurde, können Sie eine Telefonnummer für das Ressourcenkonto einrichten, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a1338-196">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="a1338-197">Nicht für alle Ressourcenkonten ist eine Telefonnummer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1338-197">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="a1338-198">Wenn Sie keine Lizenz auf das Ressourcenkonto angewendet haben, schlägt die Zuweisung der Telefonnummer fehl.</span><span class="sxs-lookup"><span data-stu-id="a1338-198">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="a1338-199">Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="a1338-199">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="a1338-200">Am einfachsten ist es, die Online-Telefonnummer mit dem Microsoft Teams Admin Center festzulegen, wie es zuvor beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="a1338-200">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="a1338-201">Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="a1338-201">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="a1338-202">Verwalten von Ressourcenkonto Einstellungen im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="a1338-202">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="a1338-203">Navigieren Sie zum Verwalten von Ressourcenkonto Einstellungen im Microsoft Teams Admin Center zu **organisationsweiten Einstellungen**  > -**Ressourcenkonten**, wählen Sie das Ressourcenkonto aus, für das Sie die Einstellungen ändern möchten, und klicken Sie dann auf die Schaltfläche **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="a1338-203">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="a1338-204">auf dem Bildschirm " **Ressourcenkonto bearbeiten** " können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="a1338-204">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="a1338-205">**Anzeigenamen** für das Konto</span><span class="sxs-lookup"><span data-stu-id="a1338-205">**Display name** for the account</span></span>
- <span data-ttu-id="a1338-206">Anrufwarteschlange oder automatische Telefonzentrale, die das Konto verwendet</span><span class="sxs-lookup"><span data-stu-id="a1338-206">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="a1338-207">Telefonnummer, die dem Konto zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="a1338-207">Phone number assigned to the account</span></span>

<span data-ttu-id="a1338-208">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a1338-208">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="a1338-209">Löschen eines Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="a1338-209">Delete a resource account</span></span>

<span data-ttu-id="a1338-210">Stellen Sie sicher, dass Sie die Telefonnummer aus dem Ressourcenkonto distanzieren, bevor Sie Sie löschen, um zu verhindern, dass Ihre Servicenummer im ausstehenden Modus hängen bleibt.</span><span class="sxs-lookup"><span data-stu-id="a1338-210">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="a1338-211">Dazu können Sie die folgenden Unifiedgroup verwenden:</span><span class="sxs-lookup"><span data-stu-id="a1338-211">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="a1338-212">Anschließend können Sie das Ressourcenkonto über das Office 365-Verwaltungsportal auf der Registerkarte Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="a1338-212">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a1338-213">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a1338-213">Troubleshooting</span></span>

<span data-ttu-id="a1338-214">Wenn die Telefonnummer, die dem Ressourcenkonto im Team Admin Center zugewiesen ist, nicht angezeigt wird und Sie die Nummer nicht von dort aus zuweisen können, überprüfen Sie bitte Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a1338-214">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="a1338-215">Wenn das Department-Attribut den Skype for Business-Anwendungsendpunkt anzeigt, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a1338-215">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> <span data-ttu-id="a1338-216">Aktualisieren Sie die Webseite des Teams admin Centers, nachdem Sie das cmldet ausgeführt haben, und Sie sollten in der Lage sein, die Nummer richtig zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a1338-216">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="a1338-217">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="a1338-217">Related Information</span></span>

<span data-ttu-id="a1338-218">Für Implementierungen, die mit Skype for Business Server Hybrid sind:</span><span class="sxs-lookup"><span data-stu-id="a1338-218">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="a1338-219">Planen automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="a1338-219">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="a1338-220">Konfigurieren automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="a1338-220">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="a1338-221">Für Implementierungen in Teams oder Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="a1338-221">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="a1338-222">Was sind automatische Cloudtelefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="a1338-222">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="a1338-223">Einrichten einer automatischen Cloudtelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="a1338-223">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="a1338-224">Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="a1338-224">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="a1338-225">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="a1338-225">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="a1338-226">Neu – CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="a1338-226">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="a1338-227">Neu – CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a1338-227">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
