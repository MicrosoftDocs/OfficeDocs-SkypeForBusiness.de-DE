---
title: 'Lync Server 2013: Anzeigen von Edgeserver-Einstellungen'
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
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="cfe20-102">Anzeigen von Edgeserver-Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfe20-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfe20-103">_**Letztes Änderungsdatum des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="cfe20-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="cfe20-104">Allgemeine Edgeserver-Konfigurationen sollten anhand der Daten in der Konfigurationsverwaltungsdatenbank überprüft werden, um sicherzustellen, dass alle Änderungen gemäß den definierten Änderungskontrollverfahren dokumentiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cfe20-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="cfe20-105">Weitere Prüfungen können die in den folgenden Abschnitten beschriebenen enthalten:</span><span class="sxs-lookup"><span data-stu-id="cfe20-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="cfe20-106">Überprüfen der Listen "zulassen" und "blockieren"</span><span class="sxs-lookup"><span data-stu-id="cfe20-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="cfe20-107">Überprüfen Sie die SIP-URI-Listen "zulassen" und "blockieren" für Verbunddomänen, um zu ermitteln, ob aufgelistete Namespaces weiterhin gültig sind.</span><span class="sxs-lookup"><span data-stu-id="cfe20-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="cfe20-108">Sie können Windows PowerShell verwenden, um die zulässigen und blockierten Listen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfe20-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="cfe20-109">Führen Sie den folgenden Windows PowerShell-Befehl aus, um die Domänen in der Liste zugelassene Domänen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="cfe20-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="cfe20-110">Dieser Befehl gibt ähnliche Informationen für die Domänen in der Liste der zulässigen Domänen zurück:</span><span class="sxs-lookup"><span data-stu-id="cfe20-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="cfe20-111">Identität: contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfe20-111">Identity : contoso.com</span></span>

<span data-ttu-id="cfe20-112">Domäne: contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfe20-112">Domain : contoso.com</span></span>

<span data-ttu-id="cfe20-113">ProxyFqdn :</span><span class="sxs-lookup"><span data-stu-id="cfe20-113">ProxyFqdn :</span></span>

<span data-ttu-id="cfe20-114">Kommentar</span><span class="sxs-lookup"><span data-stu-id="cfe20-114">Comment :</span></span>

<span data-ttu-id="cfe20-115">MarkForMonitoring: falsch</span><span class="sxs-lookup"><span data-stu-id="cfe20-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="cfe20-116">Kommentar</span><span class="sxs-lookup"><span data-stu-id="cfe20-116">Comment :</span></span>

<span data-ttu-id="cfe20-117">Verwenden Sie den folgenden Befehl, um die Domänen in der Liste der blockierten Domänen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="cfe20-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="cfe20-118">Sie erhalten wiederum Informationen wie diesen für jede blockierte Domäne:</span><span class="sxs-lookup"><span data-stu-id="cfe20-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="cfe20-119">Identität: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="cfe20-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="cfe20-120">Domäne: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="cfe20-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="cfe20-121">Mit Windows PowerShell können Sie auch überprüfen, ob Sie eine Verbindung mit den Domänen in der Liste der zulässigen Domänen herstellen können.</span><span class="sxs-lookup"><span data-stu-id="cfe20-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="cfe20-122">Mit diesem Befehl wird beispielsweise die Verbindung zwischen Ihrem Edgeserver (dem TargetFqdn) und dem Verbunddomänen-contoso.com überprüft:</span><span class="sxs-lookup"><span data-stu-id="cfe20-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="cfe20-123">Dieser Befehl überprüft die Verbindung zwischen Ihrem Edgeserver und allen Domänen, die in der Liste der zulässigen Domänen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="cfe20-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="cfe20-124">Überprüfen, ob mehrere Edgeserver identisch sind</span><span class="sxs-lookup"><span data-stu-id="cfe20-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="cfe20-125">Wenn mehrere Edgeserver in einem Lastenausgleichsarray bereitgestellt werden, sollten Sie überprüfen, ob alle Edgeserver im Array auf die gleiche Weise konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cfe20-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="cfe20-126">Sie können die Einstellungen für Edgeserver im Detailbereich der lync Server 2013-Erweiterung für das Computerverwaltungs-Snap-in anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfe20-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfe20-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfe20-127">See Also</span></span>


[<span data-ttu-id="cfe20-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="cfe20-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="cfe20-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="cfe20-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="cfe20-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="cfe20-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

