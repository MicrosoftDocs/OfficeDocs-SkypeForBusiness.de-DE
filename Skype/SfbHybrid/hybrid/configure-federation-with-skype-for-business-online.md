---
title: Konfigurieren der Hybridbereitstellung von Skype for Business
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online konfigurieren.'
ms.openlocfilehash: bd8b3ee3e70cb3662a4eae68fdb5ae6149b55a84
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43750032"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="5847c-103">Konfigurieren der Hybridbereitstellung von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5847c-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="5847c-104">Für die Konfiguration der Skype for Business-Hybridbereitstellung müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="5847c-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="5847c-105">[Konfigurieren Sie den lokalen Edgedienst so, dass er mit Office 365 oder einer anderen Organisation verbündet wird](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span><span class="sxs-lookup"><span data-stu-id="5847c-105">[Configure your on-premises Edge service to federate with Office 365 or another organization](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span></span>
- <span data-ttu-id="5847c-106">[Konfigurieren Sie Ihre lokale Umgebung, um Office 365 zu Vertrauen und den freigegebenen SIP-Adressraum mit Office 365 zu aktivieren](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="5847c-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="5847c-107">[Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrem Office 365 Mandanten](#enable-shared-sip-address-space-in-your-office-365-tenant).</span><span class="sxs-lookup"><span data-stu-id="5847c-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="5847c-108">Beachten Sie, dass Sie bei einer lokalen Exchange-Organisation möglicherweise OAuth zwischen der lokalen Exchange-Umgebung und Skype for Business Online Umgebungen konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5847c-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="5847c-109">Weitere Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) und [Planen der Integration von Skype for Business und Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="5847c-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a><span data-ttu-id="5847c-110">Konfigurieren des lokalen Edge-Diensts für den Verbund mit Office 365 oder einer anderen Organisation</span><span class="sxs-lookup"><span data-stu-id="5847c-110">Configure your on-premises Edge service to federate with Office 365 or another organization</span></span>

<span data-ttu-id="5847c-111">Durch einen Partnerverbund können Benutzer in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrem Unternehmen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="5847c-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="5847c-112">Führen Sie das folgende Cmdlet in der Skype for Business Server Verwaltungsshell aus, um den Verbund zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5847c-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="5847c-113">Wenn der Wert "-EnablePartnerDiscovery" auf "$true" festgelegt ist, verwendet Skype for Business Server DNS-Einträge zum ausprobieren und ermitteln von Partnerdomänen, die nicht in der Liste "AllowedDomains" aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5847c-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="5847c-114">Wenn der Wert auf $false festgelegt ist, werden Skype for Business Server nur mit Domänen in der AllowedDomains-Liste Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="5847c-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="5847c-115">Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5847c-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="5847c-116">Weitere Informationen zum Aktivieren des Verbund zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern einer Skype for Business Online Organisation finden Sie unter [Konfigurieren der Verbundunterstützung für einen Skype for Business Online-Kunden in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="5847c-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="5847c-117">Konfigurieren der lokalen Umgebung zur Aktivierung des freigegebenen SIP-Adressraums mit Office 365</span><span class="sxs-lookup"><span data-stu-id="5847c-117">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="5847c-118">Sie müssen auch Ihre lokale Umgebung für eine Vertrauensstellung mit Office 365 und für die Aktivierung des freigegebenen SIP-Adressraums für Office 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5847c-118">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="5847c-119">Dies bedeutet, dass Office 365 potenziell Benutzerkonten für dieselbe Gruppe von SIP-Domänen wie Ihre lokale Umgebung hosten kann und dass Nachrichten zwischen Benutzern, die lokal gehostet werden, und Online weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="5847c-119">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="5847c-120">Konfigurieren Sie hierzu einen Hostinganbieter mit ProxyFqdn = sipfed. online. lync. com, wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5847c-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="5847c-121">Überprüfen Sie zunächst, ob Sie bereits über einen Hostinganbieter mit ProxyFqdn = sipfed. online. lync. com verfügen.</span><span class="sxs-lookup"><span data-stu-id="5847c-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="5847c-122">Wenn eine vorhanden ist, entfernen Sie Sie mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="5847c-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="5847c-123">Erstellen Sie dann einen neuen Hostinganbieter, verwenden Sie das New-CsHostingProvider-Cmdlet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5847c-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="5847c-124">Aktivieren des freigegebenen SIP-Adressraums in Ihrem Office 365 Mandanten</span><span class="sxs-lookup"><span data-stu-id="5847c-124">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="5847c-125">Zusätzlich zu der Änderung, die Sie in Ihrer lokalen Bereitstellung vorgenommen haben, müssen Sie die entsprechende Änderung in Ihrem Office 365 Mandanten zu aktiviertem freigegebenem SIP-Adressraum mit Ihrer lokalen Bereitstellung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="5847c-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="5847c-126">Um den freigegebenen SIP-Adressraum in Ihrem Office 365 Mandanten zu aktivieren, richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="5847c-126">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="5847c-127">Das SharedSipAddressSpace-Attribut muss "true" bleiben, bis der Wechsel zu Online abgeschlossen ist und keine Benutzer lokal verbleiben.</span><span class="sxs-lookup"><span data-stu-id="5847c-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="5847c-128">Um eine Remote-PowerShell-Sitzung mit Teams oder Skype for Business Online einzurichten, müssen Sie zuerst das Skype for Business Online-Connector-Modul für Windows PowerShell installieren, das Sie [hier](https://go.microsoft.com/fwlink/p/?LinkId=391911)erhalten können.</span><span class="sxs-lookup"><span data-stu-id="5847c-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="5847c-129">Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:</span><span class="sxs-lookup"><span data-stu-id="5847c-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="5847c-130">Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online und zur Verwendung des Skype for Business Online-Connector-Moduls finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5847c-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="5847c-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5847c-131">See also</span></span>

[<span data-ttu-id="5847c-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="5847c-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
