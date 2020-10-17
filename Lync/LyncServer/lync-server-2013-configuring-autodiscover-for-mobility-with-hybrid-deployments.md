---
title: Konfigurieren der AutoErmittlung für Mobilität mit hybridbereitstellungen
description: Konfigurieren der AutoErmittlung für Mobilität mit hybridbereitstellungen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a66f0045ec1fce65b8e21b6a6f4494b96c93912
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562461"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="9bc2d-103">Konfigurieren der AutoErmittlung in lync Server 2013 für Mobilität mit hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="9bc2d-103">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc2d-104">_**Letztes Änderungsstand des Themas:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="9bc2d-104">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="9bc2d-105">Hybrid Bereitstellungen sind Konfigurationen, die sowohl den Microsoft lync Online Cloud-Dienst als auch die lokale Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="9bc2d-106">Bei dieser Art von Konfiguration muss der AutoErmittlungsdienst in der Lage sein, zu ermitteln, wo sich der Benutzer tatsächlich befindet.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="9bc2d-107">Das heißt, AutoErmittlung unterstützt das Suchen nach dem Benutzerkonto und dem Server, auf dem das Konto des Benutzers gehostet wird, unabhängig davon, ob es sich in der lokalen Bereitstellung oder in der lync Online-Bereitstellung befindet.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="9bc2d-108">Wenn beispielsweise das Konto eines Benutzers auf einem Server in lync online gehostet wird, geschieht der Versuch, den Benutzer zu finden, wie folgt, in einem Prozess, der als *Auffindbarkeit*bezeichnet wird:</span><span class="sxs-lookup"><span data-stu-id="9bc2d-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="9bc2d-109">Der Benutzer initiiert einen Verbindungsversuch zur lokalen Bereitstellung, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="9bc2d-110">Der Versuch wird an lyncdiscover.contoso.com gesendet, dem DNS-Namen, der dem AutoErmittlungsdienst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="9bc2d-111">Die AutoErmittlung bezieht sich auf den angenommenen Registrierungspool an der contoso.com-Bereitstellung und erhält Informationen über den tatsächlichen Stammserver des Benutzers, der in lync online gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="9bc2d-112">Die AutoErmittlung sendet dem Benutzer dann einen Verweis auf den **lync.com** Online AutoErmittlungsdienst.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="9bc2d-113">Der Benutzer initiiert einen Verbindungsversuch mit dem lync.com Online AutoErmittlungsdienst und kann das Konto des Benutzers und den Stammserver des Benutzers finden.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="9bc2d-114">Damit Mobile Clients die Bereitstellung ermitteln können, auf der sich der Benutzerstamm Server befindet, müssen Sie den AutoErmittlungsdienst mit einer neuen URL (Uniform Resource Locator) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-114">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="9bc2d-115">Führen Sie die folgenden Schritte aus, um den AutoErmittlungsdienst zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-115">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="9bc2d-116">Konfigurieren der AutoErmittlung für Hybrid Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="9bc2d-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="9bc2d-117">Verwenden Sie Get-CsHostingProvider, um den Wert des Attributs ProxyFQDN abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-117">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="9bc2d-118">Geben Sie im lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9bc2d-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="9bc2d-119">Wobei \[ Identity \] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="9bc2d-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9bc2d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bc2d-120">See Also</span></span>


<span data-ttu-id="9bc2d-121">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9bc2d-121">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="9bc2d-122">[Gruppe-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9bc2d-122">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

