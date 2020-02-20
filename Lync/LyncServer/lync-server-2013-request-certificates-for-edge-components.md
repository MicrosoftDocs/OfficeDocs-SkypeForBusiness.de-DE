---
title: 'Lync Server 2013: Anfordern von Zertifikaten für Edge-Komponenten'
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
ms.openlocfilehash: 473d526bbdf8f556f167c80cc3b654f336f78070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Die erforderlichen Zertifikate für die Unterstützung des Zugriffs durch externe Benutzer umfassen Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden, sowie Zertifikate, die von einer internen Unternehmenszertifizierungsstelle ausgestellt wurden:

  - Zertifikate, die für die externe Schnittstelle von Edgeserver und des Reverseproxys erforderlich sind, müssen von einer öffentlichen Zertifizierungsstelle ausgestellt werden.

  - Die für die interne Schnittstelle benötigten Zertifikate können entweder von einer öffentlichen oder von einer internen Unternehmenszertifizierungsstelle ausgestellt werden. Es wird empfohlen, eine interne Windows Server 2008 Zertifizierungsstelle, Windows Server 2008 R2 Zertifizierungsstelle, Windows Server 2012 Zertifizierungsstelle oder Windows Server 2012 R2-Zertifizierungsstelle zum Erstellen dieser Zertifikate zu verwenden, um die Kosten der Verwendung öffentlicher Zertifikate zu sparen.

<div>


> [!IMPORTANT]  
> Da die Verarbeitung von Zertifikatanforderungen (insbesondere bei Anforderungen an öffentliche Zertifizierungsstellen) mit einem gewissen Zeitaufwand verbunden sein kann, sollten Sie die Zertifikate für Ihre Edgeserver frühzeitig anfordern, um ihre Verfügbarkeit sicherzustellen, wenn Sie mit der Bereitstellung Ihrer Edgeserverkomponenten beginnen. Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for external User Access in lync Server 2013</A>.



</div>

Wenngleich Sie eine öffentliche Zertifizierungsstelle für das interne Edgezertifikat verwenden können, wird die Verwendung einer internen Unternehmenszertifizierungsstelle für diese anderen Zertifikate empfohlen, um die Kosten für Zertifikate zu minimieren. Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Wenn Sie ein Edgeserver installieren, enthält das Setup einen Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten erleichtert, wie im Abschnitt <A href="lync-server-2013-set-up-edge-certificates.md">Einrichten von Edge-Zertifikaten für lync Server 2013</A> beschrieben. Wenn Sie vor der Installation eines Edgeserver Zertifikate anfordern möchten (beispielsweise um Zeit bei der tatsächlichen Bereitstellung von Edgeserver Komponenten zu sparen), können Sie dies mithilfe von internen Servern tun, solange Sie sicherstellen, dass die Zertifikate exportierbar sind und alle erforderliche alternative Antragstellernamen. In dieser Dokumentation werden keine Verfahren für die Verwendung interner Server zum Anfordern von Zertifikaten bereitgestellt.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Anfordern von Zertifikaten von einer öffentlichen Zertifizierungsstelle

Für die Edgeserver-Bereitstellung ist ein einzelnes öffentliches Zertifikat für die externen Schnittstellen von Edgeserver erforderlich, das für die Zugriffs-Edgedienst, die Webkonferenz-Edgedienst und für den a/V-Authentifizierungsdienst verwendet wird. Dieses Zertifikat muss über einen exportierbaren privaten Schlüssel verfügen, um sicherzustellen, dass der A/V-Authentifizierungsdienst dieselben Schlüssel auf allen Edgeserver in einem Pool verwendet. Für den Reverseproxy, der mit ISA (Microsoft Internet Security and Acceleration Server) 2006 oder Microsoft Forefront Threat Management Gateway 2010 verwendet wird, ist ebenfalls ein öffentliches Zertifikat erforderlich.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Anfordern von Zertifikaten von einer internen Unternehmenszertifizierungsstelle

Die für die interne Edgeschnittstelle benötigten Zertifikate können entweder von einer öffentlichen oder von einer internen Zertifizierungsstelle ausgestellt werden. Mithilfe einer internen Unternehmenszertifizierungsstelle können Sie die Kosten für Zertifikate minimieren. Wenn in Ihrer Organisation eine interne Zertifizierungsstelle bereitgestellt wurde, sollten die Zertifikate für die interne Edgeschnittstelle durch die interne Zertifizierungsstelle ausgegeben werden. Das Verwenden einer internen Unternehmenszertifizierungsstelle für interne Zertifikate kann zu einer erheblichen Senkung der Kosten für Zertifikate beitragen.

Eine Zusammenfassung der Zertifikatanforderungen für Edge-Komponenten finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Ausführliche Informationen zur Verwendung einer öffentlichen Zertifizierungsstelle zum Abrufen von Zertifikaten finden Sie unter [anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Ausführliche Informationen zum anfordern, installieren und Zuweisen von Zertifikaten finden Sie unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

