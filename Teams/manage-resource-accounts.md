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
description: Informationen zum Verwalten von Ressourcenkonten in Microsoft Teams
ms.openlocfilehash: 6666482c45cb8d97567ffb9a5c8b8a3f3bcc5636
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836277"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="46b15-103">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46b15-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="46b15-104">Ein Ressourcenkonto wird in Azure AD auch als *deaktiviertes Benutzerobjekt* bezeichnet und kann verwendet werden, um Ressourcen allgemein darzustellen.</span><span class="sxs-lookup"><span data-stu-id="46b15-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="46b15-105">In Exchange kann es z. B. verwendet werden, um Konferenzräume darzustellen und ermöglicht, dass diese eine Telefonnummer haben.</span><span class="sxs-lookup"><span data-stu-id="46b15-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="46b15-106">Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="46b15-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="46b15-107">In Microsoft Teams oder Skype for Business Online ist für jede Telefonsystem-Anrufwarteschleife oder automatische Telefonzentrale mindestens ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46b15-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="46b15-108">Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der vorgesehenen Verwendung der zugehörigen Anrufwarteschleife oder der automatischen Telefonzentrale ab, wie im folgenden Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="46b15-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="46b15-109">Sie können auch die Artikel zu Anrufwarteschleifen und automatischen Telefonzentralen, die am Ende dieses Artikels verknüpft sind, zu Rate ziehen, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46b15-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![Beispiel für Ressourcenkonten und Benutzerlizenzen](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="46b15-111">Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="46b15-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="46b15-112">Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="46b15-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="46b15-113">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46b15-113">Overview</span></span>

<span data-ttu-id="46b15-114">Wenn Ihre Organisation bereits mindestens eine Telefonsystemlizenz verwendet, können Sie einer Telefonsystem-Anrufwarteschleife wie folgt eine Telefonnummer zuweisen:</span><span class="sxs-lookup"><span data-stu-id="46b15-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="46b15-115">Rufen sie eine Dienstnummer ab.</span><span class="sxs-lookup"><span data-stu-id="46b15-115">Obtain a service number.</span></span>
2. <span data-ttu-id="46b15-116">Rufen Sie eine kostenlose Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine kostenpflichtige Telefonsystemlizenz ab, die mit dem Ressourcenkonto oder einer Telefonsystemlizenz verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="46b15-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="46b15-117">Erstellen Sie das Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="46b15-117">Create the resource account.</span></span> <span data-ttu-id="46b15-118">Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen.</span><span class="sxs-lookup"><span data-stu-id="46b15-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="46b15-119">Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu.</span><span class="sxs-lookup"><span data-stu-id="46b15-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="46b15-120">Weisen Sie dem Ressourcenkonto, dem Sie gerade Lizenzen zugewiesen haben, eine Dienstelefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="46b15-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="46b15-121">Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="46b15-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="46b15-122">Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="46b15-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="46b15-123">Wenn die automatische Telefonzentrale oder Anrufwarteschleife unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschleifen benötigen.</span><span class="sxs-lookup"><span data-stu-id="46b15-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="46b15-124">Um Anrufe an Personen in Ihrer Organisation umzuleiten, die online sind, müssen diese über eine **Telefonsystemlizenz** verfügen und für Enterprise-VoIP aktiviert sein oder über einen Office 365-Anrufplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="46b15-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="46b15-125">Nähers hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="46b15-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="46b15-126">Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b15-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="46b15-127">Führen Sie beispielsweise den folgenden Befehl aus: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="46b15-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="46b15-128">Um Probleme mit dem Ressourcenkonto zu vermeiden, führen Sie die folgenden Schritte in dieser Reihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="46b15-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="46b15-129">Wenn die von Ihnen erstellte Telefonsystem-Anrufwarteschleife oder Telefonzentrale geschachtelt wird und keine Telefonnummer benötigt, ist die Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="46b15-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="46b15-130">Erstellen des Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="46b15-130">Create the resource account</span></span>
2. <span data-ttu-id="46b15-131">Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="46b15-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="46b15-132">Verknüpfen des Ressourcenkontos mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="46b15-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="46b15-133">Erstellen eines Ressourcenkontos mit einer Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="46b15-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="46b15-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="46b15-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="46b15-135">Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="46b15-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="46b15-136">Eine automatische Telefonzentrale oder Anrufwarteschleife der obersten Ebene erfordert, dass eine Telefonnummer mit ihrer automatischen Telefonzentrale verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="46b15-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="46b15-137">Wenn Sie ein Ressourcenkonto erstellen möchten, das eine Telefonnummer verwendet, ist die Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="46b15-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="46b15-138">Portieren Sie eine gebührenpflichtige oder gebührenfreie Dienstnummer oder rufen Sie diese ab.</span><span class="sxs-lookup"><span data-stu-id="46b15-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="46b15-139">Die Nummer kann keiner anderen Voice Services oder Ressourcenkonten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="46b15-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="46b15-140">Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre bestehenden gebührenpflichtigen oder gebührenfreien Dienstnummern abrufen oder portieren.</span><span class="sxs-lookup"><span data-stu-id="46b15-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="46b15-141">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Diensttelefonnummern erhalten haben, werden diese unter **Microsoft Teams Admin Center** > **Voice** > **Telefonnummern** angezeigt, und der **Nummerntyp** wird als **Dienst – gebührenfrei** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="46b15-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="46b15-142">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Service-Telefonnummern](getting-service-phone-numbers.md) oder wenn Sie eine vorhandene Service-Nummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="46b15-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="46b15-143">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose virtuelle Benutzerlizenz des Telefonsystems verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b15-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="46b15-144">Auf diese Weise können Telefonsystem-Funktionen für Telefonnummern auf Organisationsebene bereitgestellt werden, und Sie können die Funktionen der automatischen Telefonzentrale und der Anrufwarteschleife erstellen.</span><span class="sxs-lookup"><span data-stu-id="46b15-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="46b15-145">Rufen Sie eine virtuelle Benutzerlizenz für das Telefonsystem oder eine herkömmliche Telefonsystemlizenz ab.</span><span class="sxs-lookup"><span data-stu-id="46b15-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="46b15-146">Um die virtuelle Benutzerlizenz zu erhalten, wechseln Sie im Microsoft 365 Admin Center zur Seite **Rechnungsstellung** > **Dienste kaufen** > **Add-On-Abonnements** und scrollen Sie bis zum Ende. Dort sehen Sie die Lizenz „Telefonsystem – virtueller Benutzer“.</span><span class="sxs-lookup"><span data-stu-id="46b15-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="46b15-147">Wählen Sie **Jetzt kaufen** aus.</span><span class="sxs-lookup"><span data-stu-id="46b15-147">Select **Buy now**.</span></span> <span data-ttu-id="46b15-148">Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="46b15-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="46b15-149">Erstellen Sie ein neues Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="46b15-149">Create a new resource account.</span></span> <span data-ttu-id="46b15-150">Informationen hierzu finden Sie unter [Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="46b15-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="46b15-151">Weisen Sie dem Ressourcenkonto eine Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine Telefonsystemlizenz zu.</span><span class="sxs-lookup"><span data-stu-id="46b15-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="46b15-152">Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md) und [Zuweisen von Lizenzen zu einem Benutzer](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="46b15-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="46b15-153">Weisen Sie dem Ressourcenkonto die Dienstnummer zu.</span><span class="sxs-lookup"><span data-stu-id="46b15-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="46b15-154">Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="46b15-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="46b15-155">Richten Sie eines der Folgenden ein:</span><span class="sxs-lookup"><span data-stu-id="46b15-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="46b15-156">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="46b15-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="46b15-157">Cloud-Anrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="46b15-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="46b15-158">Verknüpfen Sie das Ressourcenkonto mit der automatischen Telefonzentrale oder der Anrufwarteschleife.</span><span class="sxs-lookup"><span data-stu-id="46b15-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="46b15-159">Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="46b15-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="46b15-160">Wenn Sie beim Erstellen einer automatischen Telefonzentrale ein Ressourcenkonto erstellen, werden die Lizenzen automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="46b15-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="46b15-161">Erstellen eines Ressourcenkontos ohne Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="46b15-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="46b15-162">Eine geschachtelte automatische Telefonzentrale oder Anrufwarteschleife erfordert ein Ressourcenkonto, aber in vielen Fällen benötigt das entsprechende Ressourcenkonto keine Telefonnummer und die erforderliche Lizenzierung, um eine Telefonnummer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="46b15-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="46b15-163">Wenn Sie ein Ressourcenkonto erstellen, für das keine Rufnummer erforderlich ist, müssen Sie die folgenden Aufgaben in der folgenden Reihenfolge ausführen:</span><span class="sxs-lookup"><span data-stu-id="46b15-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="46b15-164">Erstellen Sie ein neues Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="46b15-164">Create a new resource account.</span></span> <span data-ttu-id="46b15-165">Informationen hierzu finden Sie unter [Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="46b15-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="46b15-166">Richten Sie eines der Folgenden ein:</span><span class="sxs-lookup"><span data-stu-id="46b15-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="46b15-167">Automatische Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="46b15-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="46b15-168">Cloud-Anrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="46b15-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="46b15-169">Weisen Sie das Ressourcenkonto der Anrufwarteschleife oder der automatischen Telefonzentrale zu.</span><span class="sxs-lookup"><span data-stu-id="46b15-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="46b15-170">Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="46b15-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="46b15-171">Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="46b15-171">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="46b15-172">Nachdem Sie eine Telefon System Lizenz erworben haben, navigieren Sie mithilfe des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Ressourcenkonten**.</span><span class="sxs-lookup"><span data-stu-id="46b15-172">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Screenshot der Seite „Ressourcenkonten“](media/r-a-master.png)

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/teamscallout1.png)

<span data-ttu-id="46b15-175">Klicken Sie zum Erstellen eines neuen Ressourcenkontos auf **+ Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="46b15-175">To create a new resource account click **+ Add**.</span></span> <span data-ttu-id="46b15-176">Füllen Sie im Popup-Fenster den **Anzeigenamen**, den **Benutzernamen** (der Domänenname sollte automatisch aufgefüllt werden) und den Typ des Ressourcen **Kontos** für das Ressourcenkonto aus.</span><span class="sxs-lookup"><span data-stu-id="46b15-176">In the pop-up, fill out the **Display name**, **Username** (the domain name should populate automatically), and **Resource account type**  for the resource account.</span></span> <span data-ttu-id="46b15-177">Der Ressourcen Kontotyp kann abhängig von der APP, die Sie dem Ressourcenkonto zuordnen möchten, entweder eine **automatische Telefonzentrale** oder eine **Anrufwarteschlange** sein.</span><span class="sxs-lookup"><span data-stu-id="46b15-177">Resource account type can be either **Auto attendant** or **Call queue** depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="46b15-178">Wenn Sie fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46b15-178">When you are ready,  click **Save**.</span></span>

![Screenshot der Optionen für „Neues Ressourcenkonto“](media/res-acct.png)

<span data-ttu-id="46b15-180">Wenden Sie als nächstes im O365 Admin Center eine Lizenz auf das Ressourcenkonto an, wie unter Zuweisen von [Lizenzen zu Benutzern in Office 365 Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46b15-180">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="46b15-181">Ressourcenkonto bearbeiten</span><span class="sxs-lookup"><span data-stu-id="46b15-181">Edit resource account</span></span> 

<span data-ttu-id="46b15-182">![Symbol der](media/teamscallout2.png) Zahl 2, die auf eine Legende im vorherigen Screenshot verweist Sie können den **Anzeigenamen** des Ressourcenkontos und den **Ressourcen Kontotyp** mithilfe der Option " **Bearbeiten** " bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="46b15-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="46b15-183">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46b15-183">Click **Save** when you are done.</span></span>

![Screenshot der Option „Ressourcenkonto bearbeiten“](media/r-a-edit.png)

<span data-ttu-id="46b15-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="46b15-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="46b15-186">Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten</span><span class="sxs-lookup"><span data-stu-id="46b15-186">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="46b15-187">![Symbol der Zahl 3, auf eine Beschriftung im vorherigen Screenshot](media/teamscallout3.png) verweisen nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen/Aufheben der **Zuweisung** klicken, um dem Ressourcenkonto eine Dienstnummer zuzuweisen, den Typ der Telefonnummer festzulegen oder das Ressourcenkonto einer bestimmten automatischen Telefonzentrale oder Anrufwarteschlange zuzuweisen, die bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="46b15-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="46b15-188">Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen.</span><span class="sxs-lookup"><span data-stu-id="46b15-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="46b15-189">Wenn Sie die Anrufwarteschlange oder die automatische Telefonzentrale, die Sie dem Ressourcenkonto zuordnen, noch nicht erstellt haben, lassen Sie das Feld leer.</span><span class="sxs-lookup"><span data-stu-id="46b15-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account,leave that field blank.</span></span> <span data-ttu-id="46b15-190">Sie können das Ressourcenkonto während der Erstellung verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="46b15-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="46b15-191">Klicken Sie abschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46b15-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="46b15-192">Die Optionen für den **Typ "Telefonnummer** " lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="46b15-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="46b15-193">Keine</span><span class="sxs-lookup"><span data-stu-id="46b15-193">None</span></span>
- <span data-ttu-id="46b15-194">Online</span><span class="sxs-lookup"><span data-stu-id="46b15-194">Online</span></span>
- <span data-ttu-id="46b15-195">Gebührenfrei</span><span class="sxs-lookup"><span data-stu-id="46b15-195">Toll-free</span></span>
- <span data-ttu-id="46b15-196">Lokal</span><span class="sxs-lookup"><span data-stu-id="46b15-196">On-premises</span></span>

![Screenshot der Optionen „Zuweisen/Aufheben der Zuweisung“](media/r-a-assign.png)

<span data-ttu-id="46b15-198">Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid-Nummer zuweisen möchten, müssen Sie PowerShell verwenden, siehe hierzu den folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="46b15-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46b15-199">Wenn Ihr Ressourcenkonto nicht über eine gültige Lizenz verfügt, führt eine interne Prüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="46b15-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="46b15-200">Sie sind dann nicht in der Lage, die Nummer zuzuweisen oder das Ressourcenkonto einer Anrufwarteschleife oder automatischen Telefonzentrale zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="46b15-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46b15-201">Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="46b15-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="46b15-202">Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden</span><span class="sxs-lookup"><span data-stu-id="46b15-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="46b15-203">Wenn Sie sich entscheiden, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer Telefonsystemlizenz auf eine virtuelle Benutzerlizenz zu übertragen, müssen Sie die ﻿kostenlose virtuelle Benutzerlizenz erwerben. Führen Sie dann die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer zu einem anderen Abonnement zu verschieben](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="46b15-203">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="46b15-204">Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu.</span><span class="sxs-lookup"><span data-stu-id="46b15-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="46b15-205">Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="46b15-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="46b15-206">In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="46b15-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="46b15-207">Erstellen eines Ressourcenkontos in PowerShell</span><span class="sxs-lookup"><span data-stu-id="46b15-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="46b15-208">Je nachdem, ob Ihr Ressourcenkonto online oder in Skype for Business 2019 vorliegt, müssen Sie eine Verbindung mit der entsprechenden PowerShell-Eingabeaufforderung mit Administratorrechten herstellen.</span><span class="sxs-lookup"><span data-stu-id="46b15-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="46b15-209">In den folgenden Beispielen für PowerShell-Cmdlets wird gezeigt, wie Sie mit [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ein online verwaltetes Ressourcenkonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="46b15-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="46b15-210">Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden und mit Cloud-Anrufwarteschleifen und automatischen Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Konfigurieren von Cloud-Anrufwarteschlangen](/skypeforbusiness/hybrid/configure-call-queue.md) oder [Konfigurieren von automatischen Cloud-Telefonzentralen](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="46b15-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="46b15-211">Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) werden mithilfe des Cmdlets [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="46b15-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="46b15-212">Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen benötigen, sind Folgende:</span><span class="sxs-lookup"><span data-stu-id="46b15-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="46b15-213">**Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="46b15-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="46b15-214">**Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="46b15-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="46b15-215">Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="46b15-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="46b15-216">Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, dann **müssen** die Ressourcenkonten mithilfe der SfB-Management-Shell in Skype for Business Server 2019 erstellt und mit Azure AD online synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="46b15-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="46b15-217">Verwenden Sie den folgenden Befehl, um ein Ressourcenkonto für die Verwendung mit einer automatischen Telefonzentrale online zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="46b15-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="46b15-218">Sie können das Ressourcenkonto erst dann verwenden, wenn Sie ihm eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46b15-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="46b15-219">Informationen zum Zuweisen einer Lizenz zu einem Konto im O365 Admin Center finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) sowie unter [Zuweisen von Skype for Business-Lizenzen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="46b15-219">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="46b15-220">(Optional) Nachdem Sie die richtige Lizenz auf das Ressourcenkonto angewendet haben, können Sie eine Telefonnummer für das Ressourcenkonto zuweisen, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="46b15-220">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="46b15-221">Nicht alle Ressourcenkonten benötigen eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="46b15-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="46b15-222">Wenn Sie keine Lizenz auf das Ressourcenkonto angewendet haben, schlägt die Telefonnummernzuordnung fehl.</span><span class="sxs-lookup"><span data-stu-id="46b15-222">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="46b15-223">Weitere Details hierzu finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="46b15-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46b15-224">Die Online-Telefonnummer lässt sich am einfachsten mithilfe des Microsoft Teams Admin Centers festlegen, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46b15-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="46b15-225">Wenn Sie einem (in Microsoft Teams oder Skype for Business Server 2019 verwalteten) Ressourcenkonto eine direkte Routingtelefonnummer zuweisen möchten, verwenden Sie das folgende Cmdlet für Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="46b15-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="46b15-226">Verwalten der Einstellungen für das Ressourcenkonto in Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="46b15-226">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="46b15-227">Wenn Sie die Einstellungen für das Ressourcenkonto im Microsoft Teams Admin Center verwalten möchten, navigieren Sie zu **Organisationsweite Einstellungen** > **Ressourcenkonten** und wählen Sie das Ressourcenkonto aus, für das Sie die Einstellungen ändern möchten. Klicken Sie dann auf die Schaltfläche **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="46b15-227">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="46b15-228">Auf dem Bildschirm **Ressourcenkonto bearbeiten** können Sie diese Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="46b15-228">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="46b15-229">**Anzeigename** für das Konto</span><span class="sxs-lookup"><span data-stu-id="46b15-229">**Display name** for the account</span></span>
- <span data-ttu-id="46b15-230">Anrufwarteschleife oder automatische Telefonzentrale, die das Konto verwendet</span><span class="sxs-lookup"><span data-stu-id="46b15-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="46b15-231">Dem Konto zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="46b15-231">Phone number assigned to the account</span></span>

<span data-ttu-id="46b15-232">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46b15-232">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="46b15-233">Löschen eines Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="46b15-233">Delete a resource account</span></span>

<span data-ttu-id="46b15-234">Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt.</span><span class="sxs-lookup"><span data-stu-id="46b15-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="46b15-235">Zu diesem Zweck können Sie die folgenden Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="46b15-235">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="46b15-236">Sobald Sie dies getan haben, können Sie das Ressourcenkonto über das O365-Administratorportal unter der Registerkarte „Benutzer“ löschen.</span><span class="sxs-lookup"><span data-stu-id="46b15-236">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="46b15-237">Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:</span><span class="sxs-lookup"><span data-stu-id="46b15-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="46b15-238">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="46b15-238">Troubleshooting</span></span>

<span data-ttu-id="46b15-239">Wenn die Telefonnummer, die dem Ressourcenkonto im Admin Center des Teams zugeordnet ist, nicht angezeigt wird und Sie die Nummer dort nicht zuweisen können, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="46b15-239">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="46b15-240">Wenn das Department-Attribut den Skype for Business-Anwendungsendpunkt anzeigt, führen Sie den folgenden Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="46b15-240">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="46b15-241">Aktualisieren Sie nach dem Ausführen des cmldet die Website des Teams Admin Centers. Sie sollten dann in der Lage sein, die Nummer ordnungsgemäß zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="46b15-241">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="46b15-242">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="46b15-242">Related Information</span></span>

<span data-ttu-id="46b15-243">Bei hybride Implementierungen mit Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="46b15-243">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="46b15-244">Planen automatischer Cloudtelefonzentralen</span><span class="sxs-lookup"><span data-stu-id="46b15-244">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="46b15-245">Planen von Cloud-Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="46b15-245">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="46b15-246">Konfigurieren lokalen von Ressourcenkonten</span><span class="sxs-lookup"><span data-stu-id="46b15-246">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="46b15-247">Bei Implementierungen in Teams oder Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="46b15-247">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="46b15-248">Was sind automatische Cloudtelefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="46b15-248">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="46b15-249">Einrichten einer automatischen Cloudtelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="46b15-249">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="46b15-250">Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="46b15-250">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="46b15-251">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="46b15-251">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="46b15-252">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="46b15-252">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="46b15-253">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="46b15-253">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="46b15-254">Telefonsystem – virtuelle Benutzerlizenz</span><span class="sxs-lookup"><span data-stu-id="46b15-254">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
