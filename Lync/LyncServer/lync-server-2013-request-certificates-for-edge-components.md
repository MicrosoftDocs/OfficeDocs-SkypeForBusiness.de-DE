---
title: 'Lync Server 2013: Anfordern von Zertifikaten für Edgekomponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Anfordern von Zertifikaten für Edgekomponenten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Die für die Unterstützung des Zugriffs durch externe Benutzer erforderlichen Zertifikate umfassen Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden, sowie Zertifikate, die von einer internen Unternehmenszertifizierungsstelle ausgestellt wurden:

  - Zertifikate, die für die externe Schnittstelle des Edge-Servers und des Reverse-Proxys erforderlich sind, müssen von einer öffentlichen Zertifizierungsstelle ausgestellt werden.

  - Für die interne Schnittstelle erforderliche Zertifikate können entweder von einer öffentlichen Zertifizierungsstelle oder einer internen Unternehmenszertifizierungsstelle ausgestellt werden. Es wird empfohlen, eine interne Windows Server 2008-Zertifizierungsstelle, Windows Server 2008 R2 ca, Windows Server 2012 ca oder Windows Server 2012 R2 ca zum Erstellen dieser Zertifikate zu verwenden, um die Kosten für die Verwendung öffentlicher Zertifikate zu sparen.

<div>


> [!IMPORTANT]  
> Es kann einige Zeit dauern, bis Zertifikatanforderungen, insbesondere Anforderungen an öffentliche Zertifizierungsstellen, verarbeitet werden, daher sollten Sie Zertifikate für Ihre Edgeserver früh genug anfordern, um sicherzustellen, dass Sie verfügbar sind, wenn Sie die Bereitstellung Ihrer Edgeserver-Komponenten starten. Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013</A>.



</div>

Obwohl Sie eine öffentliche Zertifizierungsstelle für das interne Edge-Zertifikat verwenden können, empfiehlt es sich, stattdessen eine interne Unternehmenszertifizierungsstelle für diese anderen Zertifikate zu verwenden, um die Kosten für Zertifikate zu minimieren. Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Wenn Sie einen Edgeserver installieren, enthält Setup einen Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten vereinfacht, wie im Abschnitt <A href="lync-server-2013-set-up-edge-certificates.md">Einrichten von Edge-Zertifikaten für lync Server 2013</A> beschrieben. Wenn Sie vor der Installation eines Edge-Servers Zertifikate anfordern möchten (beispielsweise um Zeit während der eigentlichen Bereitstellung von Edge-Server-Komponenten zu sparen), können Sie dies mit internen Servern tun, sofern Sie sicherstellen, dass die Zertifikate exportierbar sind und alle Erforderlicher Betreff-alternativer Name In dieser Dokumentation werden keine Verfahren für die Verwendung interner Server zum Anfordern von Zertifikaten bereitgestellt.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Anfordern von Zertifikaten von einer öffentlichen Zertifizierungsstelle

Für die Bereitstellung von Edge-Servern ist ein einzelnes öffentliches Zertifikat für die externen Schnittstellen von Edgeserver erforderlich, das für den Access Edge-Dienst, den Webkonferenz-Edgedienst und für einen/V-Authentifizierungsdienst verwendet wird. Dieses Zertifikat muss über einen exportierbaren privaten Schlüssel verfügen, um sicherzustellen, dass der A/V-Authentifizierungsdienst die gleichen Schlüssel auf allen Edge-Servern in einem Pool verwendet. Der Reverse-Proxy, der mit Microsoft Internet Security and Acceleration (ISA) Server 2006 oder Microsoft Forefront Threat Management Gateway 2010 verwendet wird, erfordert ebenfalls ein öffentliches Zertifikat.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Anfordern von Zertifikaten von einer internen Unternehmenszertifizierungsstelle

Die für die interne Edge-Schnittstelle erforderlichen Zertifikate können entweder von einer öffentlichen Zertifizierungsstelle (Certification Authority, ca) oder einer internen Zertifizierungsstelle ausgestellt werden. Sie können eine interne Unternehmenszertifizierungsstelle verwenden, um die Kosten für Zertifikate zu minimieren. Wenn in Ihrer Organisation eine interne Zertifizierungsstelle bereitgestellt wurde, sollten die Zertifikate für den internen Edge von der internen Zertifizierungsstelle ausgestellt werden. Durch die Verwendung einer internen Unternehmenszertifizierungsstelle für interne Zertifikate können die Kosten für Zertifikate reduziert werden.

Eine Zusammenfassung der Zertifikatanforderungen für Edge-Komponenten finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Informationen zum Verwenden einer öffentlichen Zertifizierungsstelle zum Abrufen von Zertifikaten finden Sie unter [anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Details zum anfordern, installieren und Zuweisen von Zertifikaten finden Sie unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

