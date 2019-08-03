---
title: Konfigurieren eines Ressourcenkontos in Skype for Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Einrichten eines Ressourcenkontos für Skype for Business Server 2019.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160600"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="799dc-103">Konfigurieren von Ressourcenkonten</span><span class="sxs-lookup"><span data-stu-id="799dc-103">Configure resource accounts</span></span>

<span data-ttu-id="799dc-104">In Skype for Business Server 2019-Hybrid Implementierungen werden nur Cloud-Dienste verwendet, die vom Telefon System für Unified Messaging bereitgestellt werden und nicht in Exchange Online integriert werden können.</span><span class="sxs-lookup"><span data-stu-id="799dc-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="799dc-105">In Skype for Business Server 2019 können Sie nun die Cloud-Anrufwarteschlangen und die hier beschriebenen automatischen Telefonzentralen verwenden, [was Sie mit dem Telefon System in Office 365 erhalten](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span><span class="sxs-lookup"><span data-stu-id="799dc-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="799dc-106">Um diese Telefon System Dienste mit Skype for Business Server 2019 zu verwenden, müssen Sie Ressourcenkonten erstellen, die als Anwendungsendpunkte fungieren und Telefonnummern zugewiesen werden können, und dann mithilfe des Online Teams Admin Center die Anrufwarteschlange oder die automatische Telefonzentrale konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="799dc-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="799dc-107">Dieses Ressourcenkonto kann online verwaltet werden (Weitere Informationen finden Sie unter [Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) zum Erstellen von Online verwalteten Ressourcenkonten) oder vor Ort, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="799dc-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="799dc-108">Normalerweise verfügen Sie über mehrere Telefon System-Dienstknoten, die jeweils einem Ressourcenkonto zugeordnet sind, das Online oder in Skype for Business Server 2019 verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="799dc-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="799dc-109">Wenn Sie über eine Exchange um automatische Telefonzentrale und ein Anruf Warteschlangensystem verfügen, müssen Sie vor dem Wechsel zu Exchange Server 2019 oder Exchange Online die Details wie unten beschrieben manuell aufzeichnen und dann mithilfe des Teams Admin Center ein vollständig neues System implementieren. .</span><span class="sxs-lookup"><span data-stu-id="799dc-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="799dc-110">Übersicht</span><span class="sxs-lookup"><span data-stu-id="799dc-110">Overview</span></span>

<span data-ttu-id="799dc-111">Wenn für den Telefon System Dienst eine Dienstnummer erforderlich ist, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt werden:</span><span class="sxs-lookup"><span data-stu-id="799dc-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="799dc-112">Abrufen einer Dienstnummer</span><span class="sxs-lookup"><span data-stu-id="799dc-112">Obtain a service number</span></span>
2. <span data-ttu-id="799dc-113">Kaufen einer Telefon System-Lizenz</span><span class="sxs-lookup"><span data-stu-id="799dc-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="799dc-114">Erstellen Sie das Ressourcenkonto.</span><span class="sxs-lookup"><span data-stu-id="799dc-114">Create the resource account.</span></span> <span data-ttu-id="799dc-115">Für eine automatische Telefonzentrale oder Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="799dc-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="799dc-116">Warten auf eine Active Directory-Synchronisierung zwischen Online und vor Ort</span><span class="sxs-lookup"><span data-stu-id="799dc-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="799dc-117">Weisen Sie dem Ressourcenkonto die Telefon System Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="799dc-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="799dc-118">Weisen Sie dem Ressourcenkonto eine Dienstnummer zu.</span><span class="sxs-lookup"><span data-stu-id="799dc-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="799dc-119">Erstellen eines Telefon System Diensts (Anrufwarteschlange oder automatische Telefonzentrale)</span><span class="sxs-lookup"><span data-stu-id="799dc-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="799dc-120">Zuordnen des Ressourcenkontos zu einem Dienst: (New-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="799dc-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="799dc-121">Wenn die automatische Telefonzentrale oder die Anrufwarteschlange unter einer automatischen Telefonzentrale auf oberster Ebene geschachtelt ist, benötigt das zugehörige Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="799dc-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="799dc-122">Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder Office 365 Anrufpläne haben.</span><span class="sxs-lookup"><span data-stu-id="799dc-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="799dc-123">Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](/MicrosoftTeams/assign-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="799dc-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="799dc-124">Um Sie für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="799dc-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="799dc-125">Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="799dc-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="799dc-126">Wenn der Telefonsystem Dienst, den Sie erstellen, geschachtelt wird und keine Telefonnummer benötigt, lautet der Vorgang wie folgt:</span><span class="sxs-lookup"><span data-stu-id="799dc-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="799dc-127">Erstellen des Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="799dc-127">Create the resource account</span></span>  
2. <span data-ttu-id="799dc-128">Warten auf eine Active Directory-Synchronisierung zwischen Online und vor Ort</span><span class="sxs-lookup"><span data-stu-id="799dc-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="799dc-129">Erstellen eines Telefon System Diensts</span><span class="sxs-lookup"><span data-stu-id="799dc-129">Create a Phone System service</span></span>
4. <span data-ttu-id="799dc-130">Zuordnen des Ressourcenkontos zu einem Telefon System Dienst</span><span class="sxs-lookup"><span data-stu-id="799dc-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="799dc-131">Erstellen eines Ressourcenkontos mit einer Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="799dc-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="799dc-132">Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="799dc-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="799dc-133">Port oder erhalten Sie eine gebührenpflichtige oder gebührenfreie Servicenummer.</span><span class="sxs-lookup"><span data-stu-id="799dc-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="799dc-134">Die Nummer kann keinem anderen VoIP-Dienst oder Ressourcenkonto zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="799dc-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="799dc-135">Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren.</span><span class="sxs-lookup"><span data-stu-id="799dc-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="799dc-136">Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in **Microsoft Teams Admin Center** > -**VoIP** > -**Telefonnummern**angezeigt, und der aufgeführte **Nummerntyp** wird als **Dienst gebührenfrei**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="799dc-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="799dc-137">Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst Rufnummern](/MicrosoftTeams/getting-service-phone-numbers) oder wenn Sie eine vorhandene Dienstnummer übertragen möchten, unter [übertragen von Telefonnummern zu Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="799dc-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="799dc-138">Wenn Sie sich außerhalb der USA befinden, können Sie das Microsoft Teams Admin Center nicht zum Abrufen von Dienstnummern verwenden.</span><span class="sxs-lookup"><span data-stu-id="799dc-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="799dc-139">Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) , anstatt zu sehen, wie es von außerhalb der Vereinigten Staaten zu tun.</span><span class="sxs-lookup"><span data-stu-id="799dc-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="799dc-140">Kaufen Sie eine Telefon System Lizenz.</span><span class="sxs-lookup"><span data-stu-id="799dc-140">Buy a Phone System license.</span></span> <span data-ttu-id="799dc-141">Siehe:</span><span class="sxs-lookup"><span data-stu-id="799dc-141">See:</span></span>  
   - [<span data-ttu-id="799dc-142">Office 365 Enterprise E1 und E3</span><span class="sxs-lookup"><span data-stu-id="799dc-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="799dc-143">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="799dc-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="799dc-144">Office 365 Enterprise E5-Business-Software</span><span class="sxs-lookup"><span data-stu-id="799dc-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="799dc-145">Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jeden Telefon System Dienst ausführen und jedem einen Namen, eine SIP-Adresse usw. geben.</span><span class="sxs-lookup"><span data-stu-id="799dc-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="799dc-146">Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="799dc-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="799dc-147">Optional Sobald Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD zwischen Online und vor Ort synchronisiert wird, oder eine Synchronisierung erzwingen und mit der Online Konfiguration von Telefon System Diensten fortfahren.</span><span class="sxs-lookup"><span data-stu-id="799dc-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="799dc-148">Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Connect ausgeführt wird (wenn Sie nicht bereits fertig `import-module adsync` sind, müssen Sie zum Ausführen des Befehls laden):</span><span class="sxs-lookup"><span data-stu-id="799dc-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="799dc-149">Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .</span><span class="sxs-lookup"><span data-stu-id="799dc-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="799dc-150">Weisen Sie dem Ressourcenkonto die Telefon System Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="799dc-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="799dc-151">Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](/MicrosoftTeams/assign-teams-licenses) und [Zuweisen von Lizenzen zu einem Benutzer](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="799dc-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="799dc-152">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die virtuelle Benutzerlizenz für das ﻿kostenlose Telefon System verwenden.</span><span class="sxs-lookup"><span data-stu-id="799dc-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="799dc-153">Dadurch werden Telefon System Funktionen für Telefonnummern auf Organisationsebene bereitgestellt, und Sie können eine automatische Telefonzentrale und Funktionen für die Anrufwarteschlange erstellen.</span><span class="sxs-lookup"><span data-stu-id="799dc-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="799dc-154">Weisen Sie die Dienstnummer dem Ressourcenkonto zu.</span><span class="sxs-lookup"><span data-stu-id="799dc-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="799dc-155">Verwenden Sie `Set-CsHybridApplicationEndpoint` den Befehl, um dem Ressourcenkonto eine Telefonnummer zuzuweisen (mit der Option-LineURI).</span><span class="sxs-lookup"><span data-stu-id="799dc-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="799dc-156">Weitere Informationen zu diesem Befehl finden Sie unter [Festlegen von CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="799dc-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="799dc-157">Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto eine direkte Weiterleitung oder eine Hybrid Nummer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="799dc-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="799dc-158">Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefonzentrale oder einer Anrufwarteschlange zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="799dc-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="799dc-159">Benutzer (Teilnehmer-) Telefonnummern können keinem Ressourcenkonto zugewiesen werden, es dürfen nur Dienst gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="799dc-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="799dc-160">Erstellen Sie den Telefonsystem Dienst.</span><span class="sxs-lookup"><span data-stu-id="799dc-160">Create the Phone system service.</span></span> <span data-ttu-id="799dc-161">Sehen Sie sich eines der folgenden Themen an:</span><span class="sxs-lookup"><span data-stu-id="799dc-161">See one of the following:</span></span>

   - [<span data-ttu-id="799dc-162">Einrichten einer automatischen Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="799dc-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="799dc-163">Erstellen einer Warteschlange für Cloud-Anrufe</span><span class="sxs-lookup"><span data-stu-id="799dc-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="799dc-164">Ordnen Sie das Ressourcenkonto dem Telefonsystem Dienst zu, den Sie zuvor ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="799dc-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="799dc-165">Ein Beispiel für eine Small Business-Implementierung ist im [Small Business-Beispiel verfügbar: Einrichten einer automatischen Telefonzentrale](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) und eines [Beispiels für kleine Unternehmen – Einrichten einer Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="799dc-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="799dc-166">Erstellen eines Ressourcenkontos ohne Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="799dc-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="799dc-167">In diesem Abschnitt wird das Erstellen eines Ressourcenkontos erläutert, das lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="799dc-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="799dc-168">Das Erstellen eines Online verwalteten Ressourcenkontos wird unter Verwalten von [Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)erläutert.</span><span class="sxs-lookup"><span data-stu-id="799dc-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="799dc-169">Diese Schritte sind erforderlich, unabhängig davon, ob Sie ein neues Telefonsystem-Dienst System erstellen oder die ursprünglich in Exchange um erstellte Struktur neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="799dc-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="799dc-170">Melden Sie sich am Skype for Business Front-End-Server an, und führen Sie die folgenden PowerShell-Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="799dc-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="799dc-171">Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jeden Telefon System Dienst ausführen und jedem einen Namen, eine SIP-Adresse usw. geben.</span><span class="sxs-lookup"><span data-stu-id="799dc-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="799dc-172">Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="799dc-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="799dc-173">Optional Sobald Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD zwischen Online und vor Ort synchronisiert wird, oder eine Synchronisierung erzwingen und mit der Online Konfiguration von Telefon System Diensten fortfahren.</span><span class="sxs-lookup"><span data-stu-id="799dc-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="799dc-174">Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Connect ausgeführt wird (wenn Sie nicht bereits fertig `import-module adsync` sind, müssen Sie zum Ausführen des Befehls laden):</span><span class="sxs-lookup"><span data-stu-id="799dc-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="799dc-175">Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .</span><span class="sxs-lookup"><span data-stu-id="799dc-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="799dc-176">Erstellen Sie den Telefonsystem Dienst.</span><span class="sxs-lookup"><span data-stu-id="799dc-176">Create the Phone system service.</span></span> <span data-ttu-id="799dc-177">Sehen Sie sich eines der folgenden Themen an:</span><span class="sxs-lookup"><span data-stu-id="799dc-177">See one of the following:</span></span>
   - [<span data-ttu-id="799dc-178">Einrichten einer automatischen Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="799dc-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="799dc-179">Erstellen einer Warteschlange für Cloud-Anrufe</span><span class="sxs-lookup"><span data-stu-id="799dc-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="799dc-180">Ordnen Sie das Ressourcenkonto und den zuvor ausgewählten Telefon System Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="799dc-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="799dc-181">Ein Beispiel für eine Small Business-Implementierung ist im [Small Business-Beispiel verfügbar: Einrichten einer automatischen Telefonzentrale](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) und eines [Beispiels für kleine Unternehmen – Einrichten einer Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="799dc-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="799dc-182">Testen der Implementierung</span><span class="sxs-lookup"><span data-stu-id="799dc-182">Test the implementation</span></span>

<span data-ttu-id="799dc-183">Die beste Möglichkeit zum Testen der Implementierung besteht darin, die für einen Telefon System Dienst konfigurierte Nummer aufzurufen und eine Verbindung mit einem der Agents oder Menüs herzustellen.</span><span class="sxs-lookup"><span data-stu-id="799dc-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="799dc-184">Sie können auch schnell einen Test Anruf tätigen, indem Sie die **Schaltfläche Test** im Aktionsbereich Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="799dc-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="799dc-185">Wenn Sie Änderungen an einem Telefon System Dienst vornehmen möchten, wählen Sie ihn aus, und klicken Sie dann im Aktionsbereich auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="799dc-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="799dc-186">Verschieben einer Exchange um automatischen Telefonzentrale oder Anrufwarteschlange in das Telefon System</span><span class="sxs-lookup"><span data-stu-id="799dc-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="799dc-187">Bei der Migration von Exchange um zu Telefon System müssen die Struktur der Anrufwarteschlange und der automatischen Telefonzentrale neu erstellt werden, und die direkte Migration von der einen zur anderen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="799dc-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="799dc-188">So implementieren Sie eine Reihe von Anrufwarteschlangen und automatischen Telefonzentralen erneut:</span><span class="sxs-lookup"><span data-stu-id="799dc-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="799dc-189">Rufen Sie eine Liste aller Exchange um automatischen Telefonzentralen und Anrufwarteschlangen ab, indem Sie den folgenden Befehl auf dem Exchange 2013-oder 2016-System ausführen, während Sie als Administrator angemeldet sind:</span><span class="sxs-lookup"><span data-stu-id="799dc-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="799dc-190">Notieren Sie für jede aufgeführte Exchange um Anrufwarteschlange oder automatische Telefonzentrale ihre Position in der Struktur, den Einstellungen und Abrufen von Kopien zugeordneter Sound-oder Text-zu-Sprache-Dateien (die GUID in der Ausgabe ist der Name eines Ordners, in dem die Dateien gespeichert sind).</span><span class="sxs-lookup"><span data-stu-id="799dc-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="799dc-191">Sie können diese Details abrufen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="799dc-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="799dc-192">Weitere Informationen zu diesem Befehl finden Sie unter [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="799dc-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="799dc-193">Eine vollständige Liste der Optionen, die Sie möglicherweise erfassen müssen, finden Sie unter [UMAutoAttendant-Mitglieder](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , aber die wichtigsten Optionen, die Sie beachten sollten, sind:</span><span class="sxs-lookup"><span data-stu-id="799dc-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="799dc-194">Geschäftszeiten</span><span class="sxs-lookup"><span data-stu-id="799dc-194">Business hours</span></span>
    - <span data-ttu-id="799dc-195">Außerhalb der Geschäftszeiten</span><span class="sxs-lookup"><span data-stu-id="799dc-195">Non-business hours</span></span>
    - <span data-ttu-id="799dc-196">Sprache</span><span class="sxs-lookup"><span data-stu-id="799dc-196">Language</span></span>
    - <span data-ttu-id="799dc-197">Feiertagszeitplan</span><span class="sxs-lookup"><span data-stu-id="799dc-197">Holiday schedule</span></span>

3. <span data-ttu-id="799dc-198">Erstellen Sie wie oben beschrieben neue lokale Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="799dc-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="799dc-199">Zuweisen der automatischen Telefonzentrale der obersten Ebene zu Testzwecken zu einer temporären Nummer</span><span class="sxs-lookup"><span data-stu-id="799dc-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="799dc-200">Konfigurieren Sie einen Telefonsystem Dienst, der die Endpunkte verwendet, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="799dc-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="799dc-201">Möglicherweise ist es hilfreich, die Übungen im Tutorial mit dem Titel [Small Business Beispiel-Einrichten einer automatischen Telefonzentrale](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) zum Erstellen einer logischen Zuordnung der Hierarchien in Ihrem alten Exchange um System zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="799dc-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="799dc-202">Testen Sie den Telefon System Dienst.</span><span class="sxs-lookup"><span data-stu-id="799dc-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="799dc-203">Weisen Sie die Telefonnummer, die der Exchange um Anrufwarteschlange oder automatischen Telefonzentrale zugeordnet ist, dem entsprechenden Telefonsystem Dienst neu zu.</span><span class="sxs-lookup"><span data-stu-id="799dc-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="799dc-204">Wenn Sie zu diesem Zeitpunkt bereits um-Voicemail migriert haben, sollten Sie in der Lage sein, zu Exchange Server 2019 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="799dc-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="799dc-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="799dc-205">See Also</span></span>

[<span data-ttu-id="799dc-206">Erstellen einer Warteschlange für Cloud-Anrufe</span><span class="sxs-lookup"><span data-stu-id="799dc-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="799dc-207">Was sind automatische Cloud-Telefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="799dc-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="799dc-208">Einrichten einer automatischen Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="799dc-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="799dc-209">Planen automatischer Cloud-Telefonzentralen</span><span class="sxs-lookup"><span data-stu-id="799dc-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="799dc-210">Planen von Cloud-Anrufwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="799dc-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="799dc-211">Planen des Cloud-Voicemail-Diensts für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="799dc-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="799dc-212">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="799dc-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="799dc-213">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="799dc-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="799dc-214">[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(zum Erstellen von Ressourcenkonten, die Online verwaltet werden\)</span><span class="sxs-lookup"><span data-stu-id="799dc-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
