---
title: 'Lync Server 2013: Konfigurieren Sie den Verbund mit lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ce178e57b850ee4003f2596ee075d68ea14e00a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="15f08-102">Konfigurieren des Verbund lync Server 2013 mit lync Online</span><span class="sxs-lookup"><span data-stu-id="15f08-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15f08-103">_**Letztes Änderungsstand des Themas:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="15f08-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="15f08-104">Führen Sie die Schritte in diesem Abschnitt aus, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="15f08-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="15f08-105">Konfigurieren des lokalen Edge-Diensts für den Verbund mit Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="15f08-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="15f08-106">Mit dem Partnerverbund können Benutzer in Ihrer lokalen Bereitstellung mit Microsoft 365 oder Office 365 Benutzern in Ihrer Organisation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="15f08-106">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="15f08-107">Führen Sie die folgenden Cmdlets aus, um den Verbund zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="15f08-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="15f08-108">Konfigurieren des Skype for Business Online Mandanten für einen freigegebenen SIP-Adressraum</span><span class="sxs-lookup"><span data-stu-id="15f08-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="15f08-109">Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="15f08-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="15f08-110">Bevor Sie lync-Benutzer von lokal in Skype for Business Online verschieben, müssen Sie Ihre Microsoft 365-oder Office 365-Organisation so konfigurieren, dass der SIP-Adressraum (Shared Session Initiation Protocol) mit Ihrer lokalen Bereitstellung freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="15f08-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="15f08-111">Wenn diese nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="15f08-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="15f08-112">Verschieben-CsUser: HostedMigration Fault: Error = (510), Description = (der Mandant des Benutzers ist für den freigegebenen SIP-Adressraum nicht aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="15f08-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="15f08-113">Zum Konfigurieren eines freigegebenen SIP-Adressraums richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="15f08-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="15f08-114">Um eine Remote-PowerShell-Sitzung mit Skype for Business Online einzurichten, müssen Sie zunächst das Skype for Business Online-Modul für Windows PowerShell installieren, das Sie hier abrufen können: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="15f08-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="15f08-115">Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:</span><span class="sxs-lookup"><span data-stu-id="15f08-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="15f08-116">Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online finden Sie unter [Herstellen einer Verbindung mit Skype for Business Online mithilfe von Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="15f08-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="15f08-117">Weitere Informationen zum Verwenden des Skype for Business Online-PowerShell-Moduls finden Sie unter [using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="15f08-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15f08-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15f08-118">See Also</span></span>


[<span data-ttu-id="15f08-119">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="15f08-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
