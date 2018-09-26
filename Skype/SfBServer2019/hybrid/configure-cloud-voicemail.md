---
title: Konfigurieren von Voicemail von Cloud-Dienst
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Implementieren der Cloud-basierten Voicemail für Benutzer, der in Skype für Business Server verwaltet.
ms.openlocfilehash: 9cc990cbaecfea74b269809d9e31588d61eee93c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027816"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="29efa-103">Konfigurieren von Voicemail von Cloud-Dienst</span><span class="sxs-lookup"><span data-stu-id="29efa-103">Configure Cloud Voicemail service</span></span>


[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="29efa-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="29efa-104">Overview</span></span> 
<span data-ttu-id="29efa-105">In diesem Artikel wird beschrieben, wie Microsoft Cloud Voicemail-Dienst für Ihre Skype für lokale Geschäftsbenutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="29efa-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="29efa-106">In diesem Artikel wird davon ausgegangen, dass Sie bereits Skype für Business Server in einer unterstützten Topologie bereitgestellt haben und dass Sie die erforderlichen Komponenten für das Einrichten von hybridkonnektivität erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="29efa-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="29efa-107">Weitere Informationen zu den Vorteilen Planungsaspekte, und Anforderungen für die Implementierung von Cloud-Voicemail finden Sie unter [Planen der Cloud Voicemail Service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="29efa-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="29efa-108">Konfigurieren von Cloud-Voicemail umfasst die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="29efa-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="29efa-109">Stellen Sie sicher, dass Sie die erforderlichen Komponenten erfüllt sind, wie in der [Cloud Voicemail planen Service](plan-cloud-voicemail.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29efa-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="29efa-110">Stellen Sie sicher, dass Sie hybridkonnektivität wie beschrieben unter [hybridkonnektivität Plan](plan-hybrid-connectivity.md) and [Configure hybridkonnektivität](configure-hybrid-connectivity.md)eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="29efa-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="29efa-111">[Konfigurieren von Cloud Voicemail als Hostinganbieter auf dem Edge-Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29efa-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="29efa-112">[Konfigurieren einer voicemailrichtlinie für gehostete](#configure-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29efa-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="29efa-113">[Zuweisen einer voicemailrichtlinie für gehostete](#assign-a-hosted-voicemail-policy) , wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29efa-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="29efa-114">[Aktivieren eines Benutzers für Cloud Voicemail](#enable-a-user-for-cloud-voicemail) , wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29efa-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="29efa-115">Konfigurieren von Cloud-Voicemail als Hostinganbieter auf dem Edge-Server</span><span class="sxs-lookup"><span data-stu-id="29efa-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="29efa-116">Sie können Cloud Voicemail als Hostinganbieter auf dem Edge-Server konfigurieren, mit dem New-CsHostingProvider-Cmdlet mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="29efa-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="29efa-117">**Identität** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter, den Sie erstellen. beispielsweise Cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="29efa-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="29efa-118">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29efa-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="29efa-119">Dieser Parameter muss auf True festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="29efa-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="29efa-120">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem freigegebenen SIP-Adresse Speicherplatz Szenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29efa-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="29efa-121">Dieser Parameter muss auf True festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="29efa-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="29efa-122">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype für Business Server-Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29efa-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="29efa-123">Dieser Parameter muss auf False festgelegt.</span><span class="sxs-lookup"><span data-stu-id="29efa-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="29efa-124">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) für die vom Hostinganbieter verwendete Proxyserver an. beispielsweise proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="29efa-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="29efa-125">Diese Informationen erhalten Sie bei Ihrem Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="29efa-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="29efa-126">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="29efa-126">This value cannot be modified.</span></span> <span data-ttu-id="29efa-127">Wenn der Hostinganbieter seine Proxyserver ändert, müssen Sie löschen und Neuerstellen klicken Sie dann den Eintrag für den Anbieter.</span><span class="sxs-lookup"><span data-stu-id="29efa-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="29efa-128">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype für Business Server-Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="29efa-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="29efa-129">Dieser Parameter muss auf False festgelegt.</span><span class="sxs-lookup"><span data-stu-id="29efa-129">This parameter must be set to False.</span></span>

<span data-ttu-id="29efa-130">Beispielsweise konfiguriert das folgende Cmdlet in der Skype für Business-Verwaltungsshell, Cloud Voicemail als Hostinganbieter:</span><span class="sxs-lookup"><span data-stu-id="29efa-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="29efa-131">Konfigurieren einer voicemailrichtlinie für gehostete</span><span class="sxs-lookup"><span data-stu-id="29efa-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="29efa-132">Um sicherzustellen, dass Voicemail für Ihre Organisation an die Voicemail Cloud-Dienst weitergeleitet werden, müssen Sie eine gehostete voicemailrichtlinie für Ihre Organisation konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="29efa-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="29efa-133">In vielen Fällen nur eine gehostete voicemailrichtlinie ist erforderlich, und Sie können die globale Richtlinie alle Ihre Bedürfnisse ändern.</span><span class="sxs-lookup"><span data-stu-id="29efa-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="29efa-134">Wenn Ihre Organisation mehrere Richtlinien für gehostete Voicemail erfordert, können Sie Richtlinien hinzufügen, mit dem Cmdlet new-Cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="29efa-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="29efa-135">Um die globale Richtlinie zu ändern, führen Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell nach dem Aktualisieren Ihrer Organisation und die TenantID:</span><span class="sxs-lookup"><span data-stu-id="29efa-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="29efa-136">**Ziel** gibt den vollqualifizierten Domänennamen (FQDN) des gehosteten Cloud Voicemail-Diensts an.</span><span class="sxs-lookup"><span data-stu-id="29efa-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="29efa-137">Dieser Wert sollte auf **exap.um.outlook.com**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="29efa-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="29efa-138">**Organisation** ist die Standarddomäne, die Ihre Mandanten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="29efa-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="29efa-139">Sie können diese Informationen abrufen, indem Sie den Administrator des Mandanten melden Sie sich bei office.com, klicken Sie auf der app-Verwaltungskonsole, navigieren Sie auf der linken Seite **des Setups** und klicken Sie auf **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="29efa-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="29efa-140">Beispiel: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="29efa-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="29efa-141">Der Name der Organisation ist auch den Standard-Domänennamen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="29efa-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="29efa-142">**TenantID** wird verwendet, um Ihren Office 365-Mandanten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="29efa-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="29efa-143">Weitere Informationen finden Sie unter [Suchen Sie nach Ihrer Office 365-Mandanten-ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="29efa-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="29efa-144">Um sicherzustellen, dass eine voicemailrichtlinie für gehostete erfolgreich erstellt wurde, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="29efa-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="29efa-145">Zuweisen einer voicemailrichtlinie für gehostete</span><span class="sxs-lookup"><span data-stu-id="29efa-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="29efa-146">Standardmäßig Global gehostete voicemailrichtlinie für alle Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="29efa-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="29efa-147">Wenn Sie eine andere Richtlinie, bevor Sie Benutzer für gehostete Voicemail aktivieren verwenden, müssen Sie zunächst Benutzer der gewünschten gehostete voicemailrichtlinie erteilen mithilfe des Cmdlets [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="29efa-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="29efa-148">Beispielsweise weist der folgende Befehl ein nicht-globalen gehosteten voicemailrichtlinie, die einem Benutzer:</span><span class="sxs-lookup"><span data-stu-id="29efa-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="29efa-149">Aktivieren eines Benutzers für die Cloud-Voicemail</span><span class="sxs-lookup"><span data-stu-id="29efa-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="29efa-150">Zum Aktivieren eines Benutzers Voicemail Anrufen an die Cloud Voicemail weitergeleitet werden sollen, verwenden Sie das [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) -Cmdlet mit dem Parameter HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="29efa-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="29efa-151">Beispielsweise kann der folgende Befehl ein Benutzerkonto für Cloud Voicemail:</span><span class="sxs-lookup"><span data-stu-id="29efa-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="29efa-152">Das Cmdlet prüft, ob eine Cloud Voicemail-Richtlinie – auf global, Standort oder auf Benutzerebene – gilt für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="29efa-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="29efa-153">Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="29efa-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="29efa-154">Im nächste Beispiel wird ein Benutzerkonto für Cloud Voicemail deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="29efa-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="29efa-155">Das Cmdlet prüft, ob keine gehosteten voicemailrichtlinie--auf globaler, Website oder auf Benutzerebene – gilt für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="29efa-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="29efa-156">Wenn eine Richtlinie gilt, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="29efa-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="29efa-157">Benutzer müssen Enterprise-VoIP aktiviert sind, um Voicemail Microsoft Cloud-Dienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="29efa-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>