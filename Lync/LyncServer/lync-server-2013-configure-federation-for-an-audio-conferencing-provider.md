---
title: 'Lync Server 2013: Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter'
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
ms.openlocfilehash: cebbac17955f812bf07a368064156b57b0c0ddd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537092"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-24_

Wenn Sie einen Audiokonferenz-Anbieter (ACP) in ihrer hybridbereitstellung (lync Server lokal mit lync Online) verwenden möchten, müssen Sie den Verbund zwischen Ihrer lokalen lync-Bereitstellung und dem ACP-Partner als zulässigen Partner Server konfigurieren. Sie können den Verbund durch Hinzufügen der AKP-Partnerdomäne und des Edge-Servers (Dies kann auch als Zugriffs Proxy bezeichnet werden) zur Liste der Verbunddomänen für Ihre lokale Bereitstellung konfigurieren. Der AKP-Partner muss dann den FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzufügen. Wenden Sie sich an ihren AKP-Anbieter für zusätzlichen detailsYour ACP-Partner anschließend muss der FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzugefügt werden.

  - **Hinzufügen der ACP-Domäne und Edgeserver als zugelassene Verbunddomäne**
    
    Wenn Sie die ACP-Domäne als zulässigen Partner Server (zugelassene Verbunddomäne) hinzufügen möchten, führen Sie die Schritte unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)aus. Fügen Sie für die Edgeserver den FQDN des Edgeserver des AKP-Partners hinzu. Möglicherweise müssen Sie sich an ihren AKP-Partner wenden, um den FQDN für Ihre Edgeserver zu erhalten, die auch von Ihrem ACP als Zugriffs Proxy bezeichnet werden kann.

  - **Bereitstellen des FQDN des Edgeserver Pools für den AKP-Partner**
    
    Der AKP-Partner muss den Verbund so konfigurieren, dass die lokale Domäne als zulässiger Partner Server hinzugefügt wird, indem der FQDN des Edgeserver Pools als zugelassene Verbunddomäne hinzugefügt wird.

</div>

<span> </span>

</div>

</div>

</div>

