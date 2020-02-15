---
title: 'Lync Server 2013: Überprüfen der System Einstellungen des Domänennamens für den Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc1766ad11a5a6b7933d95b2c3e1182ff8ffc6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="f4f01-102">Validieren von Domänennamen-System Einstellungen für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4f01-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4f01-103">_**Letztes Änderungsstand des Themas:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="f4f01-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="f4f01-p101">Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. pool01.contoso.com) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Schließen Sie nur die IP-Adressen von Servern ein, die gegenwärtig bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="f4f01-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="f4f01-106">Außerdem sind die folgenden DNS-Einträge erforderlich, wenn Sie den DNS-Lastenausgleich für die Edge-Pools verwenden:</span><span class="sxs-lookup"><span data-stu-id="f4f01-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="f4f01-107">Für die lync Server Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="f4f01-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f4f01-108">Jeder Eintrag muss den FQDN des lync Server Zugriffs-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse der lync Server Zugriffs-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="f4f01-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f4f01-109">Für die lync Server Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="f4f01-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f4f01-110">Jeder Eintrag muss den FQDN des lync Server Webkonferenz-Edgedienst (beispielsweise webconf.contoso.com) in die IP-Adresse der lync Server Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="f4f01-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f4f01-111">Für den lync Server Audio/Video-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="f4f01-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f4f01-112">Jeder Eintrag muss den FQDN des lync Server Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des lync Server Audio/Video Edge-Diensts auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="f4f01-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f4f01-113">Wenn Sie den DNS-Lastenausgleich für die interne Schnittstelle des Edgepool verwenden möchten, müssen Sie einen DNS-Eintrag hinzufügen, der den internen FQDN des Edgepool in die IP-Adresse jedes Servers im Pool auflöst.</span><span class="sxs-lookup"><span data-stu-id="f4f01-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="f4f01-114">Um zu überprüfen, ob DNS die korrekten Werte für den DNS-Lastenausgleich zurückgibt, sollten Sie das Nslookup-Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4f01-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="f4f01-115">Wenn Sie alle Werte für einen DNS-Eintrag mit nslookup zurückgeben möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f4f01-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="f4f01-116">Sie führen diesen Befehl für jeden FQDN aus, der in der Konfiguration des DNS-Lastenausgleichs verwendet wurde, um zu überprüfen, ob alle Datensätze für den DNS-Lastenausgleich alle korrekten Einträge zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f4f01-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

