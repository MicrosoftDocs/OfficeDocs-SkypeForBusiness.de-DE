---
title: Konfigurieren der Integration zwischen einer lokalen Skype for Business Server-Bereitstellung und Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Zusammenfassung: Integrieren von Skype für Business Server und Outlook Web App.'
ms.openlocfilehash: 426dcb741e7e991e8ab06470f4b2e088aa0d866e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894225"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="3f81b-103">Konfigurieren der Integration zwischen einer lokalen Skype for Business Server-Bereitstellung und Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="3f81b-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="3f81b-104">**Zusammenfassung:** Integrieren von Skype für Business Server und Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3f81b-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="3f81b-105">Benutzer von lokalen Skype für Business Server-Bereitstellungen können Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online in einer hybriden Bereitstellung-Modus konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3f81b-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="3f81b-106">Zu den Interoperabilitätsfunktionen gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3f81b-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="3f81b-107">Um diese Integration aktivieren, müssen Sie den Edge-Server in Ihrer lokalen Skype für Business Server-Bereitstellung konfigurieren, durch die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="3f81b-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="3f81b-108">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="3f81b-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="3f81b-109">Konfigurieren eines Hostinganbieters auf dem Edge-Server</span><span class="sxs-lookup"><span data-stu-id="3f81b-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="3f81b-110">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="3f81b-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="3f81b-111">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="3f81b-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="3f81b-112">Um lokale Skype für Business Server mit Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3f81b-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="3f81b-113">Demselben Adressraum für SIP-Domäne wird von Skype für Business Server und Exchange Online-Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3f81b-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="3f81b-114">Verwenden die Skype als Business Server-Verwaltungsshell, Konfigurieren der Edge-Server für den Verbund durch das **Set-CSAccessEdgeConfiguration** -Cmdlet mit den im folgenden Beispiel angezeigten Parametern ausführen:</span><span class="sxs-lookup"><span data-stu-id="3f81b-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="3f81b-115">Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="3f81b-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="3f81b-116">Diese Eigenschaft bestimmt zudem, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adresse Speicherplatz Szenario mit Skype für Business Server und Exchange Online kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="3f81b-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="3f81b-117">Weitere Informationen zur Verwendung der Skype für Business Server-Verwaltungsshell finden Sie unter [Skype für Business Server-Verwaltungsshell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="3f81b-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="3f81b-118">Konfigurieren eines Hostinganbieters auf dem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="3f81b-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="3f81b-119">Konfigurieren Sie mit der Skype für Business Server-Verwaltungsshell, einen Hostinganbieter auf dem Edgeserver durch das **New-CsHostingProvider** -Cmdlet mit den Parametern im folgenden Beispiel ausführen:</span><span class="sxs-lookup"><span data-stu-id="3f81b-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="3f81b-120">Wenn Sie Office 365 über 21Vianet in China nutzen, ersetzen Sie den Wert für den Parameter ProxyFqdn in diesem Beispiel („exap.um.outlook.com“) mit dem FQDN für den Dienst, der in China von 21Vianet bereitgestellt wird: „exap.um.partner.outlook.cn“.</span><span class="sxs-lookup"><span data-stu-id="3f81b-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="3f81b-121">Wenn Sie Office 365 GCC hohe verwenden, ersetzen Sie den Wert für den Parameter ProxyFqdn in diesem Beispiel wird ("exap.um.outlook.com") durch den FQDN für hohe GCC: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="3f81b-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="3f81b-122">**Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise „Exchange Online“).</span><span class="sxs-lookup"><span data-stu-id="3f81b-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="3f81b-123">Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="3f81b-124">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3f81b-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="3f81b-125">Dieser Parameter muss auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-125">This must be set to True.</span></span>

- <span data-ttu-id="3f81b-126">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f81b-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="3f81b-127">Dieser Parameter muss auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-127">This must be set to True.</span></span>

- <span data-ttu-id="3f81b-128">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype für Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f81b-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="3f81b-129">Dieser Parameter muss auf FALSE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-129">This must be set to False.</span></span>

- <span data-ttu-id="3f81b-130">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an.</span><span class="sxs-lookup"><span data-stu-id="3f81b-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="3f81b-131">Für Exchange Online ist der FQDN „exap.um.outlook.com“.</span><span class="sxs-lookup"><span data-stu-id="3f81b-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="3f81b-132">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype für Business Server-Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3f81b-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="3f81b-133">Dieser Parameter muss auf FALSE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-133">This must be set to False.</span></span>

- <span data-ttu-id="3f81b-134">**"Verificationlevel"** Gibt die Überprüfung zulässig für Nachrichten, die an und von der gehosteten Anbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="3f81b-135">Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="3f81b-136">Wenn dieser Ebene nicht angegeben ist, wird die Meldung als nicht überprüfbar abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="3f81b-137">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="3f81b-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="3f81b-138">Die mithilfe der Cmdlets in den vorherigen Abschnitten vorgenommenen Änderungen werden automatisch auf dem Edge-Server angewendet, und im Allgemeinen zum Replizieren von weniger als eine Minute dauern.</span><span class="sxs-lookup"><span data-stu-id="3f81b-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="3f81b-139">Sie können überprüfen Sie den Replikationsstatus, und stellen dann sicher, dass die Änderungen an den Edge-Server mithilfe der folgenden Cmdlets angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="3f81b-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="3f81b-140">Führen Sie zum Überprüfen der Replikation-Updates auf einem Server in Ihrer Skype für Business Server-Bereitstellung das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="3f81b-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="3f81b-141">Überprüfen Sie, ob das aktuellste Wert TRUE für alle Replikate angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3f81b-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="3f81b-142">Führen Sie das folgende Cmdlet aus, um zu bestätigen, dass die Änderungen auf dem Edgeserver angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="3f81b-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="3f81b-143">Double-Wert prüfen Sie, ob die angezeigten Informationen die Änderungen ein Commit in den vorherigen Schritten entspricht.</span><span class="sxs-lookup"><span data-stu-id="3f81b-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f81b-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f81b-144">See also</span></span>

[<span data-ttu-id="3f81b-145">Bereitstellen von Skype für Business Server Voicemail Benutzer-auf gehostete Exchange um-Dienste</span><span class="sxs-lookup"><span data-stu-id="3f81b-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="3f81b-146">Gehostete Exchange Unified Messaging Integration in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="3f81b-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
