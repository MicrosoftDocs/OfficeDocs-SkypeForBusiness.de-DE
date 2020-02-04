---
title: 'Lync Server 2013: TLS und MTLS'
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
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS und MTLS für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Die Protokolle „Transport Layer Security“ (TLS) und „Mutual Transport Layer Security“ (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Microsoft lync Server 2013 verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt. SIP-Kommunikation vom Client zum Server findet über TLS statt.

TLS ermöglicht Benutzern über Ihre Client Software, die lync Server 2013-Server zu authentifizieren, mit denen Sie eine Verbindung herstellen. In einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Damit das Zertifikat gültig ist, muss es von einer Zertifizierungsstelle ausgestellt sein, die auch für den Client vertrauenswürdig ist, und der DNS-Name des Servers muss dem DNS-Namen auf dem Zertifikat entsprechen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an nicht von anderen vertrauenswürdigen Servern oder Clients angezweifelt. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten als TLS-basiert zugeordnet werden.

Server-zu-Server-Verbindungen nutzen MTLS für die gegenseitige Authentifizierung. Bei einer MTLS-Verbindung tauschen der Server, von dem eine Nachricht stammt, und der Server, der diese empfängt, Zertifikate von einer beiderseits vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate beweisen jedem Server die Identität des anderen. In lync Server 2013-Bereitstellungen werden von der Unternehmenszertifizierungsstelle ausgestellte Zertifikate, die sich während Ihres Gültigkeitszeitraums befinden und von der ausstellenden Zertifizierungsstelle nicht widerrufen werden, automatisch für alle internen Clients und Server als gültig erachtet, weil alle Mitglieder einer Active Directory-Domäne Vertrauen Sie der Unternehmenszertifizierungsstelle in dieser Domäne. In Verbundszenarien muss die ausstellende Zertifizierungsstelle für beide Verbundpartner vertrauenswürdig sein. Jeder Partner kann auf Wunsch eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch für den anderen Partner vertrauenswürdig ist. Diese Vertrauenswürdigkeit wird am einfachsten erreicht, wenn die Edgeserver das Zertifikat der Stammzertifizierungsstelle des Partners in den vertrauenswürdigen Stammzertifizierungsstellen haben oder eine Zertifizierungsstelle von Drittanbietern verwendet wird, die für beide Beteiligte vertrauenswürdig ist.

TLS und MTLS verhindern Lauschangriffe und Man-in-the-Middle-Angriffe. Ein Man-in-the-Middle-Angriff leitet die Kommunikation zwischen zwei Netzwerkeinheiten ohne Wissen einer der beiden Parteien über den Computer des Angreifers um. TLS-und lync Server 2013-Spezifikation von vertrauenswürdigen Servern (nur die im Topologie-Generator angegebenen) verringern das Risiko eines man-in-the-Middle-Angriffs teilweise auf der Anwendungsschicht, indem die durchgängige Verschlüsselung mithilfe der Kryptografie mit öffentlichem Schlüssel koordiniert wird. zwischen den beiden Endpunkten und ein Angreifer ein gültiges und vertrauenswürdiges Zertifikat mit dem zugehörigen privaten Schlüssel haben und für den Namen des Diensts ausgestellt werden muss, zu dem der Client kommuniziert, um die Kommunikation zu entschlüsseln. Letztendlich müssen Sie jedoch die besten Sicherheitsmethoden für Ihre Netzwerkinfrastruktur (in diesem Fall Corporate DNS) befolgen. Lync Server 2013 geht davon aus, dass der DNS-Server auf die gleiche Weise als vertrauenswürdig eingestuft wird wie Domänencontroller und globale Kataloge, doch DNS bietet eine Schutzebene gegen DNS-Hijack-Angriffe, indem verhindert wird, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den gefälschten Namen.

Die folgende Abbildung zeigt auf einer hohen Ebene, wie lync Server 2013 die Verwendung von MTLS zum Erstellen eines Netzwerks vertrauenswürdiger Server verwendet.

**Vertrauenswürdige Verbindungen in einem lync Server-Netzwerk**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

