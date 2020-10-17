---
title: 'Lync Server 2013: Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter'
description: 'Lync Server 2013: Konfigurieren Sie den Partnerverbund für einen Audiokonferenz-Anbieter.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553321"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="6a403-103">Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a403-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a403-104">_**Letztes Änderungsstand des Themas:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="6a403-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="6a403-105">Wenn Sie einen Audiokonferenz-Anbieter (ACP) in ihrer hybridbereitstellung (lync Server lokal mit lync Online) verwenden möchten, müssen Sie den Verbund zwischen Ihrer lokalen lync-Bereitstellung und dem ACP-Partner als zulässigen Partner Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6a403-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="6a403-106">Sie können den Verbund durch Hinzufügen der AKP-Partnerdomäne und des Edge-Servers (Dies kann auch als Zugriffs Proxy bezeichnet werden) zur Liste der Verbunddomänen für Ihre lokale Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6a403-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="6a403-107">Der AKP-Partner muss dann den FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6a403-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="6a403-108">Wenden Sie sich an ihren AKP-Anbieter für zusätzlichen detailsYour ACP-Partner anschließend muss der FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6a403-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="6a403-109">**Hinzufügen der ACP-Domäne und Edgeserver als zugelassene Verbunddomäne**</span><span class="sxs-lookup"><span data-stu-id="6a403-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="6a403-110">Wenn Sie die ACP-Domäne als zulässigen Partner Server (zugelassene Verbunddomäne) hinzufügen möchten, führen Sie die Schritte unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)aus.</span><span class="sxs-lookup"><span data-stu-id="6a403-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="6a403-111">Fügen Sie für die Edgeserver den FQDN des Edgeserver des AKP-Partners hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a403-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="6a403-112">Möglicherweise müssen Sie sich an ihren AKP-Partner wenden, um den FQDN für Ihre Edgeserver zu erhalten, die auch von Ihrem ACP als Zugriffs Proxy bezeichnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6a403-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="6a403-113">**Bereitstellen des FQDN des Edgeserver Pools für den AKP-Partner**</span><span class="sxs-lookup"><span data-stu-id="6a403-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="6a403-114">Der AKP-Partner muss den Verbund so konfigurieren, dass die lokale Domäne als zulässiger Partner Server hinzugefügt wird, indem der FQDN des Edgeserver Pools als zugelassene Verbunddomäne hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6a403-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

