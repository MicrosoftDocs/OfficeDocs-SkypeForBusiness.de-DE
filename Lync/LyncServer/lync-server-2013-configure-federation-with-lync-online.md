---
title: 'Lync Server 2013: Konfigurieren der Föderation mit lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d690b21614ec416d82834761772cee05ee16f26e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="f1208-102">Konfigurieren des Verbunds von lync Server 2013 mit lync Online</span><span class="sxs-lookup"><span data-stu-id="f1208-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1208-103">_**Letztes Änderungsdatum des Themas:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="f1208-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="f1208-104">Führen Sie die Schritte in diesem Abschnitt aus, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f1208-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="f1208-105">Konfigurieren Ihres lokalen Edge-Diensts für den Verbund mit Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f1208-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="f1208-106">Mithilfe der Föderation können Benutzer in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrer Organisation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f1208-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="f1208-107">Führen Sie die folgenden Cmdlets aus, um den Verbund zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f1208-107">To configure federation, run the following cmdlets:</span></span>

   ```
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="f1208-108">Konfigurieren Ihres Skype for Business Online-Mandanten für einen freigegebenen SIP-Adressraum</span><span class="sxs-lookup"><span data-stu-id="f1208-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="f1208-109">Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="f1208-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="f1208-110">Bevor Sie versuchen, lync-Benutzer von lokal in Skype for Business Online zu verschieben, müssen Sie Ihren Office 365-Mandanten so konfigurieren, dass der SIP-Adressraum (Shared Session Initiation Protocol) für Ihre lokale Bereitstellung freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f1208-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="f1208-111">Wenn dies nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f1208-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="f1208-112">Move-CsUser: HostedMigration fault: Error=(510), Description=(Der Mandant dieses Benutzers ist nicht für den freigegebenen SIP-Adressbereich aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="f1208-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="f1208-113">Um einen freigegebenen SIP-Adressraum zu konfigurieren, richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f1208-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

<span data-ttu-id="f1208-114">Zum Einrichten einer PowerShell-Remotesitzung mit Skype for Business Online müssen Sie zunächst das Skype for Business Online-Modul für Windows PowerShell installieren, das Sie hier abrufen können: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span><span class="sxs-lookup"><span data-stu-id="f1208-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="f1208-115">Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:</span><span class="sxs-lookup"><span data-stu-id="f1208-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```
    Import-Module LyncOnlineConnector
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

<span data-ttu-id="f1208-116">Weitere Informationen zum Einrichten einer PowerShell-Remotesitzung mit Skype for Business Online finden Sie unter [Herstellen einer Verbindung mit Skype for Business Online mithilfe von Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1208-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="f1208-117">Weitere Informationen zur Verwendung des PowerShell-Moduls für Skype for Business Online finden Sie unter [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1208-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1208-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1208-118">See Also</span></span>


[<span data-ttu-id="f1208-119">Neu – CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="f1208-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

