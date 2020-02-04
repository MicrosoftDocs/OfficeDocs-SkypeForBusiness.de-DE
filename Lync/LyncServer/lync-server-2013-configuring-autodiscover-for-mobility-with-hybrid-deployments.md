---
title: Konfigurieren der AutoErmittlung für Mobilität mit hybriden Bereitstellungen
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
ms.openlocfilehash: 0dd6c36afb89d1a8b354d072ee39ee3f6a2e7e93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="441b6-102">Konfigurieren der AutoErmittlung in Lync Server 2013 für Mobilität mit hybriden Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="441b6-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="441b6-103">_**Letztes Änderungsdatum des Themas:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="441b6-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="441b6-104">Hybrid Bereitstellungen sind Konfigurationen, die sowohl den Microsoft lync Online-clouddienst als auch die lokale Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="441b6-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="441b6-105">Bei dieser Art von Konfiguration muss der AutoErmittlungsdienst in der Lage sein, zu ermitteln, wo sich der Benutzer gerade befindet.</span><span class="sxs-lookup"><span data-stu-id="441b6-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="441b6-106">Das heißt, die AutoErmittlung unterstützt Sie bei der Suche nach dem Benutzerkonto und dem Server, auf dem sich das Konto des Benutzers befindet, unabhängig davon, ob es sich um die lokale Bereitstellung oder die lync Online-Bereitstellung handelt.</span><span class="sxs-lookup"><span data-stu-id="441b6-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="441b6-107">Wenn beispielsweise das Konto eines Benutzers auf einem Server in lync online gehostet wird, erfolgt der Versuch, den Benutzer zu finden, in einem Vorgang, der als *Auffindbarkeit*bekannt ist, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="441b6-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="441b6-108">Der Benutzer initiiert einen Verbindungsversuch mit der lokalen Bereitstellung, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="441b6-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="441b6-109">Der Versuch wird an lyncdiscover.contoso.com gesendet, dem DNS-Namen, der dem AutoErmittlungsdienst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="441b6-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="441b6-110">Die AutoErmittlung bezieht sich auf den angenommenen Registrierungspool bei der contoso.com-Bereitstellung und erhält Informationen über den tatsächlichen Stammserver des Benutzers, der in lync online gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="441b6-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="441b6-111">Der AutoErmittlungsdienst sendet dem Benutzer dann einen Verweis an den **lync.com** Online-AutoErmittlungsdienst.</span><span class="sxs-lookup"><span data-stu-id="441b6-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="441b6-112">Der Benutzer initiiert einen Verbindungsversuch mit dem lync.com Online-AutoErmittlungsdienst und kann das Konto des Benutzers und den Stammserver des Benutzers finden.</span><span class="sxs-lookup"><span data-stu-id="441b6-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="441b6-113">Damit Mobile Clients die Bereitstellung ermitteln können, auf der sich der Benutzerstamm Server befindet, müssen Sie den AutoErmittlungsdienst mit einem neuen URL (Uniform Resource Locator) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="441b6-113">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="441b6-114">Gehen Sie wie folgt vor, um den AutoErmittlungsdienst zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="441b6-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="441b6-115">Konfigurieren der AutoErmittlung für Hybrid Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="441b6-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="441b6-116">Sie verwenden Get-CsHostingProvider, um den Wert des Attributs ProxyFQDN abzurufen.</span><span class="sxs-lookup"><span data-stu-id="441b6-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="441b6-117">Geben Sie in der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="441b6-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="441b6-118">Wobei \[Identity\] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="441b6-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="441b6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="441b6-119">See Also</span></span>


<span data-ttu-id="441b6-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="441b6-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="441b6-121">[Satz-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="441b6-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

