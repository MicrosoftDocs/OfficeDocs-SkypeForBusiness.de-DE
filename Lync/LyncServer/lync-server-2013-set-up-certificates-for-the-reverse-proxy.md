---
title: 'Lync Server 2013: Einrichten von Zertifikaten für den Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e5bf87e02dbcdebeb8b1bb5a7a360c2c91ab00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509872"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Einrichten von Zertifikaten für den Reverseproxy in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Jeder Reverseproxyserver erfordert ein Webserverzertifikat zur Verwendung durch den Überwachungsdienst. Das Webserverzertifikat muss von einer öffentlichen Zertifizierungsstelle ausgestellt werden.

Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>So richten Sie ein Webdienstezertifikat für den Reverseproxy ein

  - Der Reverseproxy sollte bereits eingerichtet sein (einschließlich des Webdienstezertifikats). Wenn Sie dies nicht vor dem Starten der Bereitstellung Ihrer Edgeserver getan haben, verwenden Sie die Verfahren unter [Einrichten von Reverseproxy-Servern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) , um die Anforderung zu erstellen und das Webdienste Zertifikat zu installieren, und erstellen Sie dann jede Webveröffentlichungsregel, und konfigurieren Sie Sie für die Verwendung des Zertifikats.

</div>

</div>

<span> </span>

</div>

</div>

</div>

