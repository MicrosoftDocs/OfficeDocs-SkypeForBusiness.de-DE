---
title: 'Lync Server 2013: Konfigurieren der automatischen Clientanmeldung zur Verwendung des Directors'
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
ms.openlocfilehash: b9a6d9090796b2c6c2271025ed4d17a134943c11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="27863-102">Konfigurieren der automatischen Clientanmeldung zur Verwendung des Directors in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27863-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27863-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="27863-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="27863-104">Wenn Sie einen lync Server 2013, Director oder einen Pool von Directors bereitstellen, empfehlen wir, die automatische Client Anmeldung als bewährte Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="27863-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="27863-105">Details zum Konfigurieren von DNS-Servern für die automatische Clientanmeldung finden Sie unter [DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="27863-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="27863-106">Wenn Sie die automatische Client Anmeldung bereits bereitgestellt haben, lesen Sie die folgenden Abschnitte, um Sie für Ihre Directors zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="27863-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="27863-107">Einzelne Director-Instanz</span><span class="sxs-lookup"><span data-stu-id="27863-107">Single Director Instance</span></span>

<span data-ttu-id="27863-108">Wenn Sie bereits die automatische Client Anmeldung bereitgestellt haben und auf einen Front-End-Server oder einen Front-End-Pool verweisen, müssen Sie den DNS-SRV-Eintrag so ändern, dass er auf den Director verweist.</span><span class="sxs-lookup"><span data-stu-id="27863-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="27863-109">Director-Pool</span><span class="sxs-lookup"><span data-stu-id="27863-109">Director Pool</span></span>

<span data-ttu-id="27863-110">Wenn Sie bereits die automatische Client Anmeldung bereitgestellt haben und auf einen Front-End-Server oder einen Front-End-Pool verweisen, müssen Sie den DNS-SRV-Eintrag so ändern, dass er auf den Director-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="27863-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

