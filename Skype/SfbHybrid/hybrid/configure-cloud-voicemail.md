---
title: Konfigurieren des Cloud Voicemail-Diensts für lokale Benutzer
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Implementieren von Cloud-basierter Voicemail für Benutzer, die in Skype for Business Server verwaltet werden.
ms.openlocfilehash: 4542207beb3ccd090c1215a8832f53b3ab08ed97
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288713"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="44165-103">Konfigurieren des Cloud Voicemail-Diensts für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="44165-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="44165-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="44165-104">Overview</span></span> 
<span data-ttu-id="44165-105">In diesem Artikel wird beschrieben, wie Sie den Microsoft Cloud Voicemail-Dienst für Ihre Skype for Business lokalen Benutzern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44165-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="44165-106">In diesem Artikel wird davon ausgegangen, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben und dass Sie die Voraussetzungen für die Einrichtung der Hybrid Konnektivität erfüllt haben.</span><span class="sxs-lookup"><span data-stu-id="44165-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="44165-107">Weitere Informationen zu den Vorteilen, Planungsüberlegungen und Anforderungen für die Implementierung von Cloud-Voicemail finden Sie unter [Plan Cloud Voicemail Service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="44165-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="44165-108">Das Konfigurieren der Cloud-Voicemail umfasst die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="44165-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="44165-109">Stellen Sie sicher, dass Sie die Voraussetzungen erfüllt haben, wie unter [Plan Cloud Voicemail Service](plan-cloud-voicemail.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44165-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="44165-110">Stellen Sie sicher, dass Sie die Hybrid Konnektivität wie unter [Plan Hybrid](plan-hybrid-connectivity.md) Connectivity und [configure Hybrid Connectivity](configure-hybrid-connectivity.md)beschrieben eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="44165-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="44165-111">[Konfigurieren Sie die Cloud-Voicemail als Hostanbieter auf dem Edgeserver](#configure-cloud-voicemail-as-the-hosting-provider) , wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44165-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="44165-112">[Konfigurieren Sie eine Richtlinie für gehostete Voicemail](#configure-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44165-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="44165-113">[Weisen Sie eine Richtlinie für gehostete Voicemail](#assign-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben zu.</span><span class="sxs-lookup"><span data-stu-id="44165-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="44165-114">[Aktivieren Sie einen Benutzer für Cloud-Voicemail](#enable-a-user-for-cloud-voicemail) , wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44165-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="44165-115">Konfigurieren der Cloud-Voicemail als Hostanbieter</span><span class="sxs-lookup"><span data-stu-id="44165-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="44165-116">Sie konfigurieren Cloud-Voicemail als Hostanbieter auf einem Front-End-Server mithilfe des New-CsHostingProvider-Cmdlets mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="44165-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="44165-117">**Identity** gibt einen eindeutigen Bezeichner für den Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. beispielsweise Cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="44165-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="44165-118">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="44165-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="44165-119">Dieser Parameter muss auf true festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="44165-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="44165-120">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44165-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="44165-121">Dieser Parameter muss auf true festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="44165-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="44165-122">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype for Business Server Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44165-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="44165-123">Dieser Parameter muss auf false festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="44165-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="44165-124">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vom Hostanbieter verwendeten Proxy Server an. Beispiel: Proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="44165-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="44165-125">Sie erhalten diese Information von Ihrem Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="44165-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="44165-126">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="44165-126">This value cannot be modified.</span></span> <span data-ttu-id="44165-127">Wenn der Hostanbieter seinen Proxy Server ändert, müssen Sie den Eintrag für diesen Anbieter löschen und dann neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="44165-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="44165-128">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="44165-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="44165-129">Dieser Parameter muss auf false festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="44165-129">This parameter must be set to False.</span></span>

<span data-ttu-id="44165-130">Beispielsweise konfiguriert das folgende Cmdlet in der Skype for Business Verwaltungsshell die Cloud-Voicemail als Hostanbieter:</span><span class="sxs-lookup"><span data-stu-id="44165-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="44165-131">Konfigurieren einer Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="44165-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="44165-132">Um sicherzustellen, dass Voicemail für Ihre Organisation an den Cloud-Voicemaildienst weitergeleitet wird, müssen Sie eine Richtlinie für gehostete Voicemails für Ihre Organisation konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44165-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="44165-133">In vielen Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich, und Sie können die globale Richtlinie ändern, um alle Ihre Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="44165-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="44165-134">Wenn in Ihrer Organisation mehrere Richtlinien für gehostete Voicemails erforderlich sind, können Sie mithilfe des Cmdlets New-cshostedvoicemailpolicy Richtlinien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="44165-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="44165-135">Um die globale Richtlinie zu ändern, führen Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus, nachdem Sie Ihre Organisation und die Mandanten-und Verwaltungskonsole aktualisiert haben:</span><span class="sxs-lookup"><span data-stu-id="44165-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="44165-136">**Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Cloud-Voicemail-Diensts an.</span><span class="sxs-lookup"><span data-stu-id="44165-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="44165-137">Dieser Wert sollte auf **exap.um.Outlook.com**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="44165-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="44165-138">**Organisation** ist die Standarddomäne, die Ihrem Mandanten zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="44165-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="44165-139">Sie können diese Informationen abrufen, indem Sie den mandantenadministrator bei Office.com anmelden, auf die Admin Center-App klicken, zu **Setup** auf der linken Seite navigieren und auf **Domänen**klicken.</span><span class="sxs-lookup"><span data-stu-id="44165-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="44165-140">Beispiel: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="44165-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="44165-141">Der Name der Organisation ist auch der Standarddomänenname in Office 365.</span><span class="sxs-lookup"><span data-stu-id="44165-141">The Organization name is also the Default Domain name in Office 365.</span></span>

<span data-ttu-id="44165-142">Um sicherzustellen, dass eine Richtlinie für gehostete Voicemail erfolgreich erstellt wurde, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="44165-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="44165-143">Zuweisen einer Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="44165-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="44165-144">Standardmäßig wird die globale Richtlinie für gehostete Voicemail allen Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="44165-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="44165-145">Wenn Sie eine andere Richtlinie verwenden, müssen Sie vor dem Aktivieren von Benutzern für gehostete Voicemails Benutzern zunächst die gewünschte Richtlinie für gehostete Voicemail erteilen, indem Sie das [Grant-CSHostedVoicemailPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="44165-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="44165-146">Mit dem folgenden Befehl wird beispielsweise einem Benutzer eine nicht global gehostete Voicemail-Richtlinie zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="44165-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="44165-147">Aktivieren eines Benutzers für Cloud-Voicemail</span><span class="sxs-lookup"><span data-stu-id="44165-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="44165-148">Um zu ermöglichen, dass Voicemail-Anrufe eines Benutzers an die Cloud-Voicemail weitergeleitet werden, verwenden Sie das Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) " mit dem Parameter "HostedVoiceMail".</span><span class="sxs-lookup"><span data-stu-id="44165-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="44165-149">Mit dem folgenden Befehl wird beispielsweise ein Benutzerkonto für die Cloud-Voicemail aktiviert:</span><span class="sxs-lookup"><span data-stu-id="44165-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="44165-150">Das Cmdlet überprüft, ob eine Cloud-Voicemail-Richtlinie auf globaler, Standort-oder Benutzerebene für diesen Benutzer gilt.</span><span class="sxs-lookup"><span data-stu-id="44165-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="44165-151">Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="44165-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="44165-152">Im nächsten Beispiel wird ein Benutzerkonto für die Cloud-Voicemail deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="44165-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="44165-153">Das Cmdlet überprüft, ob keine Richtlinie für gehostete Voicemails – auf globaler, Standort-oder Benutzerebene – auf diesen Benutzer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="44165-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="44165-154">Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="44165-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="44165-155">Benutzer müssen für die Verwendung des Microsoft Cloud Voicemail-Diensts Enterprise-Voice aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="44165-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
