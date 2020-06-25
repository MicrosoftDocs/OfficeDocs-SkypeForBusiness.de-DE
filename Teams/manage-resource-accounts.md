---
title: Verwalten von Ressourcenkonten in Teams
ms.author: dstrome
author: dstrome
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
ms.openlocfilehash: b47e00323129211f657ec1dafc4e62a7cd6e4321
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868612"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="14dd1-103">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14dd1-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="14dd1-104">Ein Ressourcenkonto wird in Azure AD auch als *deaktiviertes Benutzerobjekt* bezeichnet und kann verwendet werden, um Ressourcen allgemein darzustellen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="14dd1-105">In Exchange kann es z. B. verwendet werden, um Konferenzräume darzustellen und ermöglicht, dass diese eine Telefonnummer haben.</span><span class="sxs-lookup"><span data-stu-id="14dd1-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="14dd1-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="14dd1-107">In Microsoft Teams oder Skype for Business Online ist für jede Telefonsystem-Anrufwarteschleife oder automatische Telefonzentrale mindestens ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14dd1-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="14dd1-108">Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der vorgesehenen Verwendung der zugehörigen Anrufwarteschleife oder der automatischen Telefonzentrale ab, wie im folgenden Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="14dd1-109">Sie können auch die Artikel zu Anrufwarteschleifen und automatischen Telefonzentralen, die am Ende dieses Artikels verknüpft sind, zu Rate ziehen, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![Beispiel für Ressourcenkonten und Benutzerlizenzen](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="14dd1-111">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="14dd1-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="14dd1-112">Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="14dd1-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="14dd1-113">Zuweisen einer Telefonnummer zu einer Telefon System-Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="14dd1-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="14dd1-114">Wenn Ihre Organisation bereits mindestens eine Telefonsystemlizenz verwendet, können Sie einer Telefonsystem-Anrufwarteschleife wie folgt eine Telefonnummer zuweisen:</span><span class="sxs-lookup"><span data-stu-id="14dd1-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="14dd1-115">Rufen sie eine Dienstnummer ab.</span><span class="sxs-lookup"><span data-stu-id="14dd1-115">Obtain a service number.</span></span>
2. <span data-ttu-id="14dd1-116">Rufen Sie eine kostenlose Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine kostenpflichtige Telefonsystemlizenz ab, die mit dem Ressourcenkonto oder einer Telefonsystemlizenz verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="14dd1-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="14dd1-117">Erstellen Sie das Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="14dd1-117">Create the resource account.</span></span> <span data-ttu-id="14dd1-118">Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="14dd1-119">Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu.</span><span class="sxs-lookup"><span data-stu-id="14dd1-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="14dd1-120">Weisen Sie dem Ressourcenkonto, dem Sie gerade Lizenzen zugewiesen haben, eine Dienstelefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="14dd1-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="14dd1-121">Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="14dd1-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="14dd1-122">Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="14dd1-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="14dd1-123">Wenn die automatische Telefonzentrale oder die Anrufwarteschlange unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="14dd1-123">If the auto attendant or call queue is nested under a top-level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="14dd1-124">Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Microsoft 365 oder Office 365-Anrufpläne verfügen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="14dd1-125">Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="14dd1-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="14dd1-126">Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="14dd1-127">Führen Sie beispielsweise den folgenden Befehl aus: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="14dd1-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="14dd1-128">Um Probleme mit dem Ressourcenkonto zu vermeiden, führen Sie die folgenden Schritte in dieser Reihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="14dd1-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="14dd1-129">Wenn die von Ihnen erstellte Telefonsystem-Anrufwarteschleife oder Telefonzentrale geschachtelt wird und keine Telefonnummer benötigt, ist die Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="14dd1-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="14dd1-130">Erstellen des Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="14dd1-130">Create the resource account</span></span>
2. <span data-ttu-id="14dd1-131">Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="14dd1-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="14dd1-132">Verknüpfen des Ressourcenkontos mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="14dd1-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="14dd1-133">Erstellen eines Ressourcenkontos mit einer Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="14dd1-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="14dd1-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="14dd1-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14dd1-135">Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="14dd1-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="14dd1-136">Eine automatische Telefonzentrale oder Anrufwarteschleife der obersten Ebene erfordert, dass eine Telefonnummer mit ihrer automatischen Telefonzentrale verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="14dd1-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="14dd1-137">Wenn Sie ein Ressourcenkonto erstellen möchten, das eine Telefonnummer verwendet, ist die Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="14dd1-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="14dd1-138">Portieren Sie eine gebührenpflichtige oder gebührenfreie Dienstnummer oder rufen Sie diese ab.</span><span class="sxs-lookup"><span data-stu-id="14dd1-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="14dd1-139">Die Nummer kann keiner anderen Voice Services oder Ressourcenkonten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="14dd1-140">Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre bestehenden gebührenpflichtigen oder gebührenfreien Dienstnummern abrufen oder portieren.</span><span class="sxs-lookup"><span data-stu-id="14dd1-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="14dd1-141">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Diensttelefonnummern erhalten haben, werden diese unter **Microsoft Teams Admin Center** > **Voice** > **Telefonnummern** angezeigt, und der **Nummerntyp** wird als **Dienst – gebührenfrei** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="14dd1-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="14dd1-142">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Service-Telefonnummern](getting-service-phone-numbers.md) oder wenn Sie eine vorhandene Service-Nummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="14dd1-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="14dd1-143">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose virtuelle Benutzerlizenz des Telefonsystems verwenden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="14dd1-144">Auf diese Weise können Telefonsystem-Funktionen für Telefonnummern auf Organisationsebene bereitgestellt werden, und Sie können die Funktionen der automatischen Telefonzentrale und der Anrufwarteschleife erstellen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="14dd1-145">Rufen Sie eine virtuelle Benutzerlizenz für das Telefonsystem oder eine herkömmliche Telefonsystemlizenz ab.</span><span class="sxs-lookup"><span data-stu-id="14dd1-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="14dd1-146">Wenn Sie die Lizenz für virtuelle Benutzer erhalten möchten, wechseln Sie im Microsoft 365 Admin Center zu den Abonnements für **Billing**  >  **Purchase Services**-  >  **Add-on** , und Scrollen Sie bis zum Ende – Sie sehen die Lizenz "Telefon System-virtueller Benutzer".</span><span class="sxs-lookup"><span data-stu-id="14dd1-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="14dd1-147">Wählen Sie **Jetzt kaufen** aus.</span><span class="sxs-lookup"><span data-stu-id="14dd1-147">Select **Buy now**.</span></span> <span data-ttu-id="14dd1-148">Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="14dd1-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="14dd1-149">Erstellen Sie ein neues Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="14dd1-149">Create a new resource account.</span></span> <span data-ttu-id="14dd1-150">Informationen finden Sie unter [Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center](#create-a-resource-account-in-the-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="14dd1-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="14dd1-151">Weisen Sie dem Ressourcenkonto eine Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine Telefonsystemlizenz zu.</span><span class="sxs-lookup"><span data-stu-id="14dd1-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="14dd1-152">Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md) und [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="14dd1-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="14dd1-153">Weisen Sie dem Ressourcenkonto die Dienstnummer zu.</span><span class="sxs-lookup"><span data-stu-id="14dd1-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="14dd1-154">Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="14dd1-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="14dd1-155">Richten Sie eines der Folgenden ein:</span><span class="sxs-lookup"><span data-stu-id="14dd1-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="14dd1-156">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="14dd1-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="14dd1-157">Cloud-Anrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="14dd1-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="14dd1-158">Verknüpfen Sie das Ressourcenkonto mit der automatischen Telefonzentrale oder der Anrufwarteschleife.</span><span class="sxs-lookup"><span data-stu-id="14dd1-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="14dd1-159">Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="14dd1-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="14dd1-160">Wenn Sie beim Erstellen einer automatischen Telefonzentrale ein Ressourcenkonto erstellen, werden die Lizenzen automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="14dd1-161">Erstellen eines Ressourcenkontos ohne Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="14dd1-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="14dd1-162">Eine geschachtelte automatische Telefonzentrale oder Anrufwarteschleife erfordert ein Ressourcenkonto, aber in vielen Fällen benötigt das entsprechende Ressourcenkonto keine Telefonnummer und die erforderliche Lizenzierung, um eine Telefonnummer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="14dd1-163">Wenn Sie ein Ressourcenkonto erstellen, für das keine Rufnummer erforderlich ist, müssen Sie die folgenden Aufgaben in der folgenden Reihenfolge ausführen:</span><span class="sxs-lookup"><span data-stu-id="14dd1-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="14dd1-164">Erstellen Sie ein neues Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="14dd1-164">Create a new resource account.</span></span> <span data-ttu-id="14dd1-165">Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-the-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="14dd1-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>

2. <span data-ttu-id="14dd1-166">Richten Sie eines der Folgenden ein:</span><span class="sxs-lookup"><span data-stu-id="14dd1-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="14dd1-167">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="14dd1-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="14dd1-168">Cloud-Anrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="14dd1-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
   
3. <span data-ttu-id="14dd1-169">Weisen Sie das Ressourcenkonto der Anrufwarteschleife oder der automatischen Telefonzentrale zu.</span><span class="sxs-lookup"><span data-stu-id="14dd1-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="14dd1-170">Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="14dd1-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="14dd1-171">Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="14dd1-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="14dd1-172">Nachdem Sie eine Telefon System Lizenz gekauft haben, wechseln Sie in der linken Navigationsleiste des Microsoft Teams admin Centers zu **organisationsweiten Einstellungen-**  >  **Ressourcenkonten**.</span><span class="sxs-lookup"><span data-stu-id="14dd1-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![Screenshot der Seite „Ressourcenkonten“](media/r-a-master.png)

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/teamscallout1.png)

<span data-ttu-id="14dd1-175">Klicken Sie auf **Hinzufügen**, um ein neues Ressourcenkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="14dd1-176">Füllen Sie im Bereich **Ressourcenkonto hinzufügen** den **Anzeige Namen**, den **Benutzernamen** aus (der Domänenname sollte automatisch aufgefüllt werden), und geben Sie den **Ressourcen Kontotyp** für das Ressourcenkonto ein.</span><span class="sxs-lookup"><span data-stu-id="14dd1-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="14dd1-177">Der Typ des Ressourcenkontos kann eine **automatische Telefonzentrale** oder eine **Anrufwarteschlange**sein, abhängig von der APP, die Sie dem Ressourcenkonto zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="14dd1-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="14dd1-178">Wenn Sie fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14dd1-178">When you're ready, click **Save**.</span></span>

![Screenshot der Optionen für „Neues Ressourcenkonto“](media/res-acct.png)

<span data-ttu-id="14dd1-180">Wenden Sie als nächstes eine Lizenz auf das Ressourcenkonto im Microsoft 365 Admin Center an, wie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14dd1-180">Next, apply a license to the resource account in the Microsoft 365 Admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="14dd1-181">Ressourcenkonto bearbeiten</span><span class="sxs-lookup"><span data-stu-id="14dd1-181">Edit resource account</span></span> 

<span data-ttu-id="14dd1-182">![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist ](media/teamscallout2.png) Sie können den **Anzeigenamen** des Ressourcenkontos und den **Ressourcen Kontotyp** mithilfe der Option " **Bearbeiten** " bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="14dd1-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="14dd1-183">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14dd1-183">Click **Save** when you are done.</span></span>

![Screenshot der Option „Ressourcenkonto bearbeiten“](media/r-a-edit.png)

<span data-ttu-id="14dd1-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="14dd1-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="14dd1-186">Zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten</span><span class="sxs-lookup"><span data-stu-id="14dd1-186">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="14dd1-187">![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist ](media/teamscallout3.png) nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen **/** Aufheben der Zuweisung klicken, um dem Ressourcenkonto eine Dienstnummer zuzuweisen, den Typ der Telefonnummer festzulegen oder das Ressourcenkonto einer bestimmten automatischen Telefonzentrale oder Anrufwarteschlange zuzuweisen, die bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="14dd1-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="14dd1-188">Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="14dd1-189">Wenn Sie die Anrufwarteschlange oder die automatische Telefonzentrale, die Sie dem Ressourcenkonto zuordnen, noch nicht erstellt haben, lassen Sie das Feld leer.</span><span class="sxs-lookup"><span data-stu-id="14dd1-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account, leave that field blank.</span></span> <span data-ttu-id="14dd1-190">Sie können das Ressourcenkonto während der Erstellung verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="14dd1-191">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14dd1-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="14dd1-192">Die Optionen für den **Typ "Telefonnummer** " lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="14dd1-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="14dd1-193">Keine</span><span class="sxs-lookup"><span data-stu-id="14dd1-193">None</span></span>
- <span data-ttu-id="14dd1-194">Online</span><span class="sxs-lookup"><span data-stu-id="14dd1-194">Online</span></span>
- <span data-ttu-id="14dd1-195">Gebührenfrei</span><span class="sxs-lookup"><span data-stu-id="14dd1-195">Toll-free</span></span>
- <span data-ttu-id="14dd1-196">Lokal</span><span class="sxs-lookup"><span data-stu-id="14dd1-196">On-premises</span></span>

![Screenshot der Optionen „Zuweisen/Aufheben der Zuweisung“](media/r-a-assign.png)

<span data-ttu-id="14dd1-198">Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid-Nummer zuweisen möchten, müssen Sie PowerShell verwenden, siehe hierzu den folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14dd1-199">Wenn Ihr Ressourcenkonto nicht über eine gültige Lizenz verfügt, führt eine interne Prüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="14dd1-200">Sie sind dann nicht in der Lage, die Nummer zuzuweisen oder das Ressourcenkonto einer Anrufwarteschleife oder automatischen Telefonzentrale zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14dd1-201">Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="14dd1-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="14dd1-202">Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden</span><span class="sxs-lookup"><span data-stu-id="14dd1-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="14dd1-203">Wenn Sie sich entscheiden, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer Telefon System Lizenz zu einer virtuellen Benutzerlizenz zu wechseln, müssen Sie die ﻿kostenlose virtuelle Benutzerlizenz erwerben und dann die Schritte im Microsoft 365 Admin Center ausführen, um [Benutzer in ein anderes Abonnement zu verschieben](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="14dd1-203">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="14dd1-204">Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu.</span><span class="sxs-lookup"><span data-stu-id="14dd1-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="14dd1-205">Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="14dd1-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="14dd1-206">In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="14dd1-207">Erstellen eines Ressourcenkontos in PowerShell</span><span class="sxs-lookup"><span data-stu-id="14dd1-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="14dd1-208">Je nachdem, ob Ihr Ressourcenkonto online oder in Skype for Business 2019 vorliegt, müssen Sie eine Verbindung mit der entsprechenden PowerShell-Eingabeaufforderung mit Administratorrechten herstellen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="14dd1-209">In den folgenden Beispielen für PowerShell-Cmdlets wird gezeigt, wie Sie mit [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ein online verwaltetes Ressourcenkonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="14dd1-210">Informationen zu Ressourcenkonten in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Planen von Cloud-Anrufwarteschlangen](/SkypeforBusiness/hybrid/plan-call-queue) oder [Planen automatischer Cloud-Telefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="14dd1-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="14dd1-211">Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) werden mithilfe des Cmdlets [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="14dd1-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="14dd1-212">Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen benötigen, sind Folgende:</span><span class="sxs-lookup"><span data-stu-id="14dd1-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="14dd1-213">**Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="14dd1-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="14dd1-214">**Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="14dd1-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="14dd1-215">Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="14dd1-216">Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, dann **müssen** die Ressourcenkonten mithilfe der SfB-Management-Shell in Skype for Business Server 2019 erstellt und mit Azure AD online synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="14dd1-217">Verwenden Sie den folgenden Befehl, um ein Ressourcenkonto für die Verwendung mit einer automatischen Telefonzentrale online zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="14dd1-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="14dd1-218">Sie können das Ressourcenkonto erst dann verwenden, wenn Sie ihm eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="14dd1-219">Informationen dazu, wie Sie eine Lizenz auf ein Konto im Microsoft 365 Admin Center anwenden, finden Sie unter[Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) und [Zuweisen von Lizenzen für Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="14dd1-219">To learn how to apply a license to an account in the Microsoft 365 admin center, see[Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="14dd1-220">Optional Nachdem die richtige Lizenz auf das Ressourcenkonto angewendet wurde, können Sie dem Ressourcenkonto eine Telefonnummer zuweisen, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-220">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="14dd1-221">Nicht alle Ressourcenkonten benötigen eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="14dd1-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="14dd1-222">Wenn Sie keine Lizenz auf das Ressourcenkonto angewendet haben, schlägt die Zuweisung der Telefonnummer fehl.</span><span class="sxs-lookup"><span data-stu-id="14dd1-222">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="14dd1-223">Weitere Details hierzu finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14dd1-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="14dd1-224">Die Online-Telefonnummer lässt sich am einfachsten mithilfe des Microsoft Teams Admin Centers festlegen, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14dd1-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="14dd1-225">Wenn Sie einem (in Microsoft Teams oder Skype for Business Server 2019 verwalteten) Ressourcenkonto eine direkte Routingtelefonnummer zuweisen möchten, verwenden Sie das folgende Cmdlet für Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14dd1-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="14dd1-226">Verwalten von Ressourcenkonto Einstellungen im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="14dd1-226">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="14dd1-227">Wenn Sie die Ressourcenkonto Einstellungen im Microsoft Teams Admin Center verwalten möchten, wechseln Sie zu **organisationsweiten Einstellungen**  >  **Ressourcenkonten**, wählen Sie das Ressourcenkonto aus, für das Sie die Einstellungen ändern müssen, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="14dd1-227">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="14dd1-228">Im Bereich **Ressourcenkonto bearbeiten** können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="14dd1-228">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="14dd1-229">**Anzeigename** für das Konto</span><span class="sxs-lookup"><span data-stu-id="14dd1-229">**Display name** for the account</span></span>
- <span data-ttu-id="14dd1-230">Anrufwarteschleife oder automatische Telefonzentrale, die das Konto verwendet</span><span class="sxs-lookup"><span data-stu-id="14dd1-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="14dd1-231">Dem Konto zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="14dd1-231">Phone number assigned to the account</span></span>

<span data-ttu-id="14dd1-232">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14dd1-232">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="14dd1-233">Löschen eines Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="14dd1-233">Delete a resource account</span></span>

<span data-ttu-id="14dd1-234">Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="14dd1-235">Dazu können Sie das folgende Cmdlet verwenden:</span><span class="sxs-lookup"><span data-stu-id="14dd1-235">You can do that using the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="14dd1-236">Anschließend können Sie das Ressourcenkonto im Microsoft 365 Admin Center auf der Registerkarte Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-236">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="14dd1-237">Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:</span><span class="sxs-lookup"><span data-stu-id="14dd1-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="14dd1-238">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="14dd1-238">Troubleshooting</span></span>

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="14dd1-239">Im Microsoft Teams Admin Center wird die Telefonnummer, die dem Ressourcenkonto zugewiesen ist, nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-239">You don't see the phone number assigned to the resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="14dd1-240">Wenn die Telefonnummer, die dem Ressourcenkonto im Microsoft Teams Admin Center zugewiesen ist, nicht angezeigt wird und Sie die Nummer nicht von dort aus zuweisen können, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="14dd1-240">If you don't see the phone number assigned to the resource account in the Microsoft Teams admin center and you are unable to assign the number from there, check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="14dd1-241">Wenn das Department-Attribut den Skype for Business-Anwendungsendpunkt anzeigt, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="14dd1-241">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="14dd1-242">Aktualisieren Sie nach dem Ausführen des cmldet die Website des Teams Admin Centers. Sie sollten dann in der Lage sein, die Nummer ordnungsgemäß zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="14dd1-242">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a><span data-ttu-id="14dd1-243">Sie erhalten ein "Wir können dieses Ressourcenkonto nicht für Dienste verwenden".</span><span class="sxs-lookup"><span data-stu-id="14dd1-243">You get a "We can't use this resource account for services."</span></span> <span data-ttu-id="14dd1-244">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="14dd1-244">error message</span></span>

<span data-ttu-id="14dd1-245"><a name="blocksignin"> </a></span><span class="sxs-lookup"><span data-stu-id="14dd1-245"><a name="blocksignin"> </a></span></span>

<span data-ttu-id="14dd1-246">Wenn Sie versuchen, ein Ressourcenkonto zu verwenden, erhalten Sie die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="14dd1-246">You get the following error message when you try to use a resource account:</span></span>

<span data-ttu-id="14dd1-247">"Dieses Ressourcenkonto kann nicht für Dienste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-247">"We can't use this resource account for services.</span></span> <span data-ttu-id="14dd1-248">Das Ressourcenkonto muss deaktiviert und für die Anmeldung gesperrt sein.</span><span class="sxs-lookup"><span data-stu-id="14dd1-248">The resource account must be DISABLED and BLOCKED from signing in.</span></span> <span data-ttu-id="14dd1-249">Sie müssen die Anmeldung für dieses Ressourcenkonto auf der Seite "Benutzer" im Microsoft 365 Admin Center blockieren. "</span><span class="sxs-lookup"><span data-stu-id="14dd1-249">You must BLOCK sign-ins for this resource account on the Users page in the Microsoft 365 admin center."</span></span>

<span data-ttu-id="14dd1-250">Wenn Sie ein Ressourcenkonto erstellen, ist es standardmäßig deaktiviert, und die Anmeldung ist für das Konto gesperrt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-250">When you create a resource account, by default, it's disabled and sign in is blocked for the account.</span></span> <span data-ttu-id="14dd1-251">Diese Einstellungen sollten nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-251">These settings shouldn't be changed.</span></span> <span data-ttu-id="14dd1-252">Um diese Fehlermeldung zu beheben, blockieren Sie das Ressourcenkonto, bevor Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="14dd1-252">To resolve this error message, block the resource account from signing in.</span></span> <span data-ttu-id="14dd1-253">Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="14dd1-253">To do this:</span></span>

1. <span data-ttu-id="14dd1-254">Wechseln Sie im Microsoft 365 Admin Center zu **Benutzer**, suchen Sie nach, und wählen Sie dann das Ressourcenkonto aus.</span><span class="sxs-lookup"><span data-stu-id="14dd1-254">In the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span>
2. <span data-ttu-id="14dd1-255">Klicken Sie oben im Bereich unter dem Anzeigenamen auf **diesen Benutzer blockieren?**, aktivieren Sie das Kontrollkästchen **diesen Benutzer von der Anmeldung blockieren** , und wählen Sie dann **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="14dd1-255">At the top of the pane under the display name, click **Block this user?**, select the **Block this user from signing in** check box, and then select **Save changes**.</span></span>

   ![Screenshot der Option "diesen Nutzer blockieren"](media/res-acct-block.png)

    <span data-ttu-id="14dd1-257">Anschließend wird unter dem Anzeigenamen "Anmelden blockiert" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dd1-257">After you do this, you'll see "Sign in blocked" under the display name.</span></span>

      ![Screenshot der Meldung "Anmeldung blockiert"](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a><span data-ttu-id="14dd1-259">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="14dd1-259">Related Information</span></span>

<span data-ttu-id="14dd1-260">Bei hybride Implementierungen mit Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="14dd1-260">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="14dd1-261">Planen automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="14dd1-261">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="14dd1-262">Planen von Cloud-Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="14dd1-262">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="14dd1-263">Konfigurieren lokalen von Ressourcenkonten</span><span class="sxs-lookup"><span data-stu-id="14dd1-263">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="14dd1-264">Bei Implementierungen in Teams oder Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="14dd1-264">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="14dd1-265">Was sind automatische Cloudtelefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="14dd1-265">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="14dd1-266">Einrichten einer automatischen Cloudtelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="14dd1-266">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="14dd1-267">Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="14dd1-267">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="14dd1-268">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="14dd1-268">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="14dd1-269">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="14dd1-269">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="14dd1-270">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="14dd1-270">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="14dd1-271">Neu – CsOnlineApplicationInstanceAssociation</span><span class="sxs-lookup"><span data-stu-id="14dd1-271">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="14dd1-272">Telefonsystem – virtuelle Benutzerlizenz</span><span class="sxs-lookup"><span data-stu-id="14dd1-272">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
