---
title: Konfigurieren eines Partnerverbunds in Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.'
ms.openlocfilehash: 6a48e3cc579fd3827cc95f7f36d0c637d540ed56
ms.sourcegitcommit: 8a34b5f0295fc6059852dab6971429fda4d30b67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "20176119"
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="f917b-103">Konfigurieren eines Partnerverbunds in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f917b-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="f917b-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="f917b-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="f917b-105">Führen Sie die Schritte in diesem Abschnitt, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f917b-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="f917b-106">Konfigurieren Sie Ihrer lokalen Edge-Dienst für den Verbund mit Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="f917b-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="f917b-107">Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrer Organisation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f917b-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="f917b-108">Um den Verbund zu konfigurieren, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="f917b-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="f917b-109">Konfigurieren Sie Ihrer Skype für Business Online Mandanten für einen freigegebenen SIP-Adressraum</span><span class="sxs-lookup"><span data-stu-id="f917b-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="f917b-110">Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="f917b-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="f917b-111">Bevor Sie versuchen, den Benutzer aus der lokalen in Skype für Business Online zu verschieben, müssen Sie Ihre Office 365-Mandanten zum Freigeben von des Adressraums Shared Session Initiation Protocol (SIP) mit der lokalen Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f917b-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="f917b-112">Wenn dies nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f917b-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="f917b-113">Move-CsUser: HostedMigration Fehler: Error=(510), Beschreibung = (Mandant des Benutzers ist für freigegebenen Sip-Adressraum nicht aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="f917b-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="f917b-114">Zum Konfigurieren eines freigegebenen SIP-Adressraums herstellen Sie eine remote-PowerShell-Sitzung mit Skype für Business Online, und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f917b-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="f917b-115">Das Attribut „SharedSipAddressSpace“ muss auf „True“ festgelegt bleiben, bis die Verschiebung in die lokale Bereitstellung abgeschlossen ist und keine lokalen Benutzer mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f917b-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="f917b-116">Um eine remote-PowerShell-Sitzung mit Skype für Business Online eingerichtet haben, müssen Sie zuerst die Skype für Business Online Connector-Modul für Windows PowerShell installiert werden Sie hier erhalten können: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="f917b-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="f917b-117">Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:</span><span class="sxs-lookup"><span data-stu-id="f917b-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="f917b-118">Weitere Informationen zum Verwenden von PowerShell mit Skype für Business Online finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f917b-118">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="f917b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f917b-119">See also</span></span>

[<span data-ttu-id="f917b-120">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="f917b-120">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)