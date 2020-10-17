---
title: 'Lync Server 2013: TLS und MTLS'
description: 'Lync Server 2013: TLS und MTLS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ccee47e635435dd5f0d5eae03711c0cd5e517b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541791"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS und MTLS für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

TLS-(Transport Layer Security) und MTLS-Protokolle (Mutual Transport Layer Security) bieten verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Microsoft lync Server 2013 verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen den Servern erfolgt über MTLS. Die SIP-Kommunikation von Client zu Server erfolgt über TLS.

Mit TLS können Benutzer über Ihre Client Software die lync Server 2013 Server authentifizieren, mit denen Sie eine Verbindung herstellen. Bei einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Ein gültiges Zertifikat muss von einer auch für den Client vertrauenswürdigen Zertifizierungsstelle ausgegeben worden sein, und der DNS-Name des Servers muss mit dem DNS-Namen des Zertifikats übereinstimmen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel zu verschlüsseln, die zur Kommunikation verwendet werden sollen, damit nur der ursprüngliche Besitzer des Zertifikats den privaten Schlüssel zum Entschlüsseln der Kommunikationsinhalte verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig, und im weiteren Verlauf wird keine Authentifizierung von anderen vertrauenswürdigen Servern oder Clients angefordert. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten auf TLS-Basis zugeordnet werden.

Server-zu-Server-Verbindungen basieren auf MTLS für die gegenseitige Authentifizierung. Bei einer MTLS-Verbindung wird der Server mit einer Nachricht und dem empfangenden Server mit Exchange-Zertifikaten von einer gegenseitig vertrauenswürdigen Zertifizierungsstelle verbunden. Die Zertifikate beweisen die Identität der einzelnen Server auf der anderen. In lync Server 2013 Bereitstellungen werden von der Unternehmenszertifizierungsstelle ausgestellte Zertifikate, die während des Gültigkeitszeitraums von der ausstellenden Zertifizierungsstelle nicht widerrufen werden, automatisch von allen internen Clients und Servern als gültig betrachtet, da alle Mitglieder einer Active Directory Domäne der Unternehmenszertifizierungsstelle in dieser Domäne vertrauen. In Verbundszenarien muss die ausstellende Zertifizierungsstelle von beiden Verbundpartnern als vertrauenswürdig eingestuft werden. Jeder Partner kann bei Bedarf eine andere Zertifizierungsstelle verwenden, solange die Zertifizierungsstelle auch vom anderen Partner als vertrauenswürdig eingestuft wird. Diese Vertrauensstellung kann am einfachsten durch die Edgeserver mit dem Zertifikat der Stammzertifizierungsstelle des Partners in ihren vertrauenswürdigen Stammzertifizierungsstellen oder durch die Verwendung einer Drittanbieter-Zertifizierungsstelle erreicht werden, die von beiden Seiten als vertrauenswürdig eingestuft wird.

TLS und MTLS helfen, Abhör-und man-in-the-Middle-Angriffe zu verhindern. Bei einem man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten über den Computer des Angreifers ohne das Wissen einer Partei weiter. TLS-und lync Server 2013 Spezifikation vertrauenswürdiger Server (nur die im Topologie-Generator angegebenen) mindern das Risiko eines man-in-the-Middle-Angriffs teilweise auf der Anwendungsebene mithilfe von End-to-End-Verschlüsselung, die mithilfe der Kryptografie mit öffentlichen Schlüsseln zwischen den beiden Endpunkten koordiniert wird. ein Angreifer muss über ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel verfügen und für den Namen des Diensts ausgegeben werden, mit dem der Client kommuniziert, um die Kommunikation zu entschlüsseln. Letztendlich müssen Sie jedoch die besten Sicherheitsmethoden mit Ihrer Netzwerkinfrastruktur befolgten (in diesem Fall Corporate DNS). Lync Server 2013 geht davon aus, dass der DNS-Server auf die gleiche Weise wie Domänencontrollern und globalen Katalogen als vertrauenswürdig eingestuft wird, aber DNS bietet eine Schutzebene gegen DNS-Hijack-Angriffe, indem verhindert, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den gefälschten Namen antwortet.

In der folgenden Abbildung wird auf einer hohen Ebene gezeigt, wie lync Server 2013 MTLS verwendet, um ein Netzwerk vertrauenswürdiger Server zu erstellen.

**Vertrauenswürdige Verbindungen in einem Lync Server-Netzwerk**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

