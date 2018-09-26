---
title: Konfigurieren von Skype für hybride Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.'
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030721"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="ab9f9-103">Konfigurieren von Skype für hybride Business</span><span class="sxs-lookup"><span data-stu-id="ab9f9-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="ab9f9-104">Um Skype für hybride Business zu konfigurieren, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="ab9f9-105">Konfigurieren des Verbunds</span><span class="sxs-lookup"><span data-stu-id="ab9f9-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="ab9f9-106">Konfigurieren Sie einen freigegebenen Adressraum Session Initiation Protocol (SIP)</span><span class="sxs-lookup"><span data-stu-id="ab9f9-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="ab9f9-107">Konfigurieren der Server-zu-Server-Authentifizierung bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="ab9f9-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="ab9f9-108">Konfigurieren Sie Ihrer lokalen Edge-Dienst für den Verbund mit Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="ab9f9-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="ab9f9-109">Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrer Organisation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="ab9f9-110">Um den Verbund zu konfigurieren, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="ab9f9-111">Konfigurieren Sie Ihrer Skype für Business Online Mandanten für einen freigegebenen SIP-Adressraum</span><span class="sxs-lookup"><span data-stu-id="ab9f9-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="ab9f9-112">Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="ab9f9-113">Bevor Sie versuchen, den Benutzer aus der lokalen in Skype für Business Online zu verschieben, müssen Sie Ihre Office 365-Mandanten zum Freigeben von des Adressraums Shared Session Initiation Protocol (SIP) mit der lokalen Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="ab9f9-114">Wenn dies nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="ab9f9-115">Move-CsUser: HostedMigration Fehler: Error=(510), Beschreibung = (Mandant des Benutzers ist für freigegebenen Sip-Adressraum nicht aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="ab9f9-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="ab9f9-116">Zum Konfigurieren eines freigegebenen SIP-Adressraums herstellen Sie eine remote-PowerShell-Sitzung mit Skype für Business Online, und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="ab9f9-117">Das Attribut „SharedSipAddressSpace“ muss auf „True“ festgelegt bleiben, bis die Verschiebung in die lokale Bereitstellung abgeschlossen ist und keine lokalen Benutzer mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="ab9f9-118">Um eine remote-PowerShell-Sitzung mit Skype für Business Online eingerichtet haben, müssen Sie zuerst die Skype für Business Online Connector-Modul für Windows PowerShell installiert werden Sie erhalten [hier](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="ab9f9-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="ab9f9-119">Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="ab9f9-120">Weitere Informationen dazu, wie eine remote-PowerShell-Sitzung mit Skype für Business Online herstellen, und wie die Skype für Business Online Connector Modul verwendet finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab9f9-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="ab9f9-121">Konfigurieren der Server-zu-Server-Authentifizierung bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="ab9f9-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="ab9f9-122">Je nach Typ des hybridumgebung, den Sie konfigurieren, müssen Sie die Server-zu-Server-Authentifizierung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="ab9f9-123">Weitere Informationen finden Sie unter [Manage Server-zu-Server-Authentifizierung in Skype für Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span><span class="sxs-lookup"><span data-stu-id="ab9f9-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="ab9f9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab9f9-124">See also</span></span>

[<span data-ttu-id="ab9f9-125">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ab9f9-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

