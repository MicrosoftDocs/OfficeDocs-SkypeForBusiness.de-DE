---
title: 'Lync Server 2013: Konfigurieren der automatischen Client Anmeldung zur Verwendung des Directors'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad7a81a662e4d69ac8ee88cfdbce2f5448d195ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="80755-102">Konfigurieren der automatischen Client Anmeldung zur Verwendung des Directors in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80755-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80755-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="80755-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="80755-104">Wenn Sie eine lync Server 2013, einen Director oder einen Director-Pool bereitstellen, wird empfohlen, die automatische Client Anmeldung als bewährte Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="80755-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="80755-105">Ausführliche Informationen zum Konfigurieren von DNS-Servern für die automatische Clientanmeldung finden Sie unter [DNS Requirements for Automatic Client Sign-in in lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="80755-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="80755-106">Wenn Sie die automatische Clientanmeldung bereits bereitgestellt haben, finden Sie in den folgenden Abschnitten Informationen zur Konfiguration dieser Funktion für Ihre Director-Server.</span><span class="sxs-lookup"><span data-stu-id="80755-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="80755-107">Einzelne Director-Instanz</span><span class="sxs-lookup"><span data-stu-id="80755-107">Single Director Instance</span></span>

<span data-ttu-id="80755-108">Wenn Sie die automatische Client Anmeldung bereits bereitgestellt haben und auf ein Front-End-Server oder ein Front-End-Pool zeigt, müssen Sie den DNS-SRV-Eintrag so ändern, dass er auf den Director verweist.</span><span class="sxs-lookup"><span data-stu-id="80755-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="80755-109">Director-Pool</span><span class="sxs-lookup"><span data-stu-id="80755-109">Director Pool</span></span>

<span data-ttu-id="80755-110">Wenn Sie die automatische Client Anmeldung bereits bereitgestellt haben und auf ein Front-End-Server oder ein Front-End-Pool zeigt, müssen Sie den DNS-SRV-Eintrag so ändern, dass er auf das Directorpool verweist.</span><span class="sxs-lookup"><span data-stu-id="80755-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

