---
title: Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Zusammenfassung: Integrieren von Skype for Business Server und Outlook Web App.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221185"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="2c772-103">Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="2c772-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="2c772-104">**Zusammenfassung:** Integrieren Sie Skype for Business Server und Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="2c772-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="2c772-105">Kunden, die lokale Skype for Business Server-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online im Hybrid Bereitstellungsmodus konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2c772-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="2c772-106">Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2c772-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="2c772-107">Um diese Integration zu ermöglichen, müssen Sie die Edgeserver in Ihrer lokalen Skype for Business Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="2c772-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="2c772-108">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="2c772-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="2c772-109">Konfigurieren eines Host Anbieters im Edgeserver</span><span class="sxs-lookup"><span data-stu-id="2c772-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="2c772-110">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="2c772-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="2c772-111">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="2c772-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="2c772-112">Um lokale Skype for Business Server mit Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2c772-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="2c772-113">Derselbe SIP-Domänen Adressraum wird sowohl von Skype for Business Server als auch vom Exchange Online Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c772-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="2c772-114">Konfigurieren Sie mithilfe der Skype for Business Server Verwaltungsshell den Edgeserver für den Verbund, indem Sie das Cmdlet " **csaccessedgeconfiguration nicht angeben** " mit den im folgenden Beispiel angezeigten Parametern ausführen:</span><span class="sxs-lookup"><span data-stu-id="2c772-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="2c772-115">Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="2c772-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="2c772-116">Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adressraum Szenario mit Skype for Business Server und Exchange Online kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="2c772-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="2c772-117">Ausführliche Informationen zur Verwendung der Skype for Business Server-Verwaltungsshell finden Sie unter [Skype for Business Server Management Shell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="2c772-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="2c772-118">Konfigurieren eines Hostinganbieters auf dem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="2c772-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="2c772-119">Konfigurieren Sie mithilfe der Skype for Business Server Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das Cmdlet **New-CsHostingProvider** mit den Parametern im folgenden Beispiel ausführen:</span><span class="sxs-lookup"><span data-stu-id="2c772-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="2c772-120">Wenn Sie Microsoft 365 oder Office 365 betrieben von 21Vianet in China verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für den Dienst, der von 21Vianet verwaltet wird: "exap.um.Partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="2c772-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="2c772-121">Wenn Sie Microsoft 365 oder Office 365 gcc High verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für gcc High: "exap.um.office365.US".</span><span class="sxs-lookup"><span data-stu-id="2c772-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="2c772-122">**Identity** gibt einen eindeutigen Bezeichner für den Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="2c772-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="2c772-123">Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="2c772-124">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2c772-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="2c772-125">Dieser Parameter muss auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-125">This must be set to True.</span></span>

- <span data-ttu-id="2c772-126">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c772-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="2c772-127">Dieser Parameter muss auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-127">This must be set to True.</span></span>

- <span data-ttu-id="2c772-128">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype for Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c772-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="2c772-129">Dieser Parameter muss auf FALSE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-129">This must be set to False.</span></span>

- <span data-ttu-id="2c772-130">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an.</span><span class="sxs-lookup"><span data-stu-id="2c772-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="2c772-131">Für Exchange Online ist der FQDN "exap.um.outlook.com".</span><span class="sxs-lookup"><span data-stu-id="2c772-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="2c772-132">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2c772-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="2c772-133">Dieser Parameter muss auf FALSE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-133">This must be set to False.</span></span>

- <span data-ttu-id="2c772-134">**"Verificationlevel"** Gibt die zulässige Überprüfungsebene für Nachrichten an, die vom gehosteten Anbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="2c772-135">Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="2c772-136">Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="2c772-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="2c772-137">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="2c772-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="2c772-138">Die Änderungen, die Sie mit den Cmdlets in den vorhergehenden Abschnitten vorgenommen haben, werden automatisch auf die Edgeserver angewendet und dauern in der Regel weniger als eine Minute, um repliziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="2c772-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="2c772-139">Sie können den Replikationsstatus überprüfen und anschließend überprüfen, ob die Änderungen auf Ihre Edgeserver mithilfe der folgenden Cmdlets angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="2c772-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="2c772-140">Führen Sie das folgende Cmdlet aus, um Replikationsupdates auf einem internen Server in Ihrer Skype for Business Server-Bereitstellung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="2c772-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="2c772-141">Überprüfen Sie, ob uptodate-Wert true für alle Replikate angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2c772-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="2c772-142">Um zu bestätigen, dass die Änderungen übernommen wurden, führen Sie im Edgeserver das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="2c772-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="2c772-143">Überprüfen Sie, ob die angezeigten Informationen mit den in den vorherigen Schritten zugesicherten Änderungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2c772-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c772-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c772-144">See also</span></span>

[<span data-ttu-id="2c772-145">Bereitstellen von Voicemail für Skype for Business Server-Benutzer in gehosteten Exchange um</span><span class="sxs-lookup"><span data-stu-id="2c772-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="2c772-146">Hosted Exchange Unified Messaging-Integration in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2c772-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
