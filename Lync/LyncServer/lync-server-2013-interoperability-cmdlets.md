---
title: 'Lync Server 2013: Interoperabilitäts-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability cmdlets
ms:assetid: 18444a0b-7b66-4540-a262-775ea10b3b7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204714(v=OCS.15)
ms:contentKeyID: 48183527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9509fe93e1efbde72896cead2f06ab907bbe46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498452"
---
# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0e4bb-102">Interoperabilitäts-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e4bb-102">Interoperability cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e4bb-103">_**Letztes Änderungsstand des Themas:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="0e4bb-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="0e4bb-104">Die Cmdlets für die Interoperabilität werden verwendet, um die Server-zu-Server-Authentifizierung und-Autorisierung zwischen Microsoft lync Server 2013 und anderen Serverprodukten wie Microsoft Exchange Server 2013 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0e4bb-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="0e4bb-105">Die Server-zu-Server-Authentifizierung und die Autorisierung ermöglichen diesen Servern das nahtlose Austauschen und Freigeben von Daten.</span><span class="sxs-lookup"><span data-stu-id="0e4bb-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="0e4bb-106">Interoperabilitäts-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0e4bb-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="0e4bb-107">Im folgenden finden Sie eine Liste der Cmdlets, die direkt mit der Konfiguration und Verwaltung der Interoperabilität zwischen Microsoft lync Server 2013 und anderen Server Produkten in Zusammenhangstehen:</span><span class="sxs-lookup"><span data-stu-id="0e4bb-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="0e4bb-108">**Interoperabilitäts-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="0e4bb-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="0e4bb-109">[Get-csoauthconfiguration "](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-110">[Gruppe-csoauthconfiguration "](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e4bb-111">[Get-csoauthserver "](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-111">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-112">[New-csoauthserver "](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-112">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-113">[Remove-csoauthserver "](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-114">[Gruppe-csoauthserver "](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e4bb-115">[Get-cspartnerapplication "](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-115">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-116">[New-cspartnerapplication "](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-116">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-117">[Remove-cspartnerapplication "](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="0e4bb-118">[Gruppe-cspartnerapplication "](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e4bb-118">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

