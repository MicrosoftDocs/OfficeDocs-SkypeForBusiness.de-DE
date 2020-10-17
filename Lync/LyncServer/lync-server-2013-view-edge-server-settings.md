---
title: 'Lync Server 2013: Anzeigen von Edgeserver Einstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3f536a0aadb181b1b740d74c8f61715efed21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506392"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="6e2d6-102">Anzeigen von Edgeserver Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e2d6-102">View Edge Server settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e2d6-103">_**Letztes Änderungsstand des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="6e2d6-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="6e2d6-104">Allgemeine Edgeserver Konfigurationen sollten anhand der Daten in der Konfigurationsverwaltungsdatenbank überprüft werden, damit sichergestellt ist, dass alle Änderungen gemäß den definierten Änderungskontrollverfahren dokumentiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6e2d6-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="6e2d6-105">Weitere Überprüfungen könnten die in den folgenden Abschnitten beschriebenen umfassen:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="6e2d6-106">Überprüfen der Zulassungs-und Sperrlisten</span><span class="sxs-lookup"><span data-stu-id="6e2d6-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="6e2d6-107">Überprüfen Sie die Listen SIP-URI "zulassen" und "blockieren" für Verbunddomänen, um zu ermitteln, ob aufgelistete Namespaces noch gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6e2d6-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="6e2d6-108">Sie können Windows PowerShell verwenden, um die zulässigen und blockierten Listen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e2d6-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="6e2d6-109">Um die Domänen in der Liste zugelassene Domänen zu überprüfen, führen Sie den folgenden Windows PowerShell Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="6e2d6-110">Dieser Befehl gibt Informationen wie diese für die Domänen in der Liste der zugelassenen Domänen zurück:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="6e2d6-111">Identity: contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e2d6-111">Identity : contoso.com</span></span>

<span data-ttu-id="6e2d6-112">Domäne: contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e2d6-112">Domain : contoso.com</span></span>

<span data-ttu-id="6e2d6-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="6e2d6-113">ProxyFqdn :</span></span>

<span data-ttu-id="6e2d6-114">Kommentar</span><span class="sxs-lookup"><span data-stu-id="6e2d6-114">Comment :</span></span>

<span data-ttu-id="6e2d6-115">MarkForMonitoring: false</span><span class="sxs-lookup"><span data-stu-id="6e2d6-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="6e2d6-116">Kommentar</span><span class="sxs-lookup"><span data-stu-id="6e2d6-116">Comment :</span></span>

<span data-ttu-id="6e2d6-117">Verwenden Sie den folgenden Befehl, um die Domänen in der Liste blockierter Domänen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="6e2d6-118">Sie erhalten wiederum Informationen wie diese für jede blockierte Domäne:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="6e2d6-119">Identity: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="6e2d6-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="6e2d6-120">Domäne: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="6e2d6-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="6e2d6-121">Mit Windows PowerShell können Sie auch überprüfen, ob Sie eine Verbindung mit den Domänen in der Liste der zugelassenen Domänen herstellen können.</span><span class="sxs-lookup"><span data-stu-id="6e2d6-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="6e2d6-122">Mit diesem Befehl wird beispielsweise die Verbindung zwischen dem Edgeserver (TargetFqdn) und der contoso.com der Verbunddomäne überprüft:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="6e2d6-123">Mit diesem Befehl wird die Verbindung zwischen Ihrem Edgeserver und allen Domänen überprüft, die in der Liste der zugelassenen Domänen gefunden werden:</span><span class="sxs-lookup"><span data-stu-id="6e2d6-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="6e2d6-124">Überprüfen, ob mehrere Edgeserver identisch sind</span><span class="sxs-lookup"><span data-stu-id="6e2d6-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="6e2d6-125">Wenn mehrere Edgeserver in einem Lastenausgleichsarray bereitgestellt werden, sollten Sie überprüfen, ob alle Edgeserver im Array auf die gleiche Weise konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="6e2d6-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="6e2d6-126">Sie können Einstellungen für Edgeserver im Detailbereich der lync Server 2013-Erweiterung für das Snap-in "Computer Verwaltung" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e2d6-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e2d6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e2d6-127">See Also</span></span>


[<span data-ttu-id="6e2d6-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="6e2d6-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="6e2d6-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="6e2d6-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="6e2d6-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="6e2d6-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

