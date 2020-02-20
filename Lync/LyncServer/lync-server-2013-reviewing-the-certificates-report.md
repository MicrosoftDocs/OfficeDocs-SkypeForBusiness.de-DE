---
title: 'Lync Server 2013: Überprüfen des Zertifikats Berichts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a584f331deaf702305367042c6c40679ffb7099f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Überprüfen des Zertifikat Berichts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Der Zertifikat Bericht enthält alle Zertifikate, die in der empfohlenen lync Server 2013-Bereitstellung erforderlich sind. Das Planungs Tool Konten für die eingegebenen Antragstellernamen und alternativen Antragstellernamen. Der Standardtext, der unbearbeitet bleibt, stellt möglicherweise eine potenzielle Herausforderung für das Team dar, das für das anfordern und ausgeben der Zertifikate zuständig ist. In den Zertifikatinformationen ist zudem angegeben, von welcher Stelle das Zertifikat typischerweise ausgestellt werden kann. Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden. Die Felder "Erweiterte Schlüsselverwendungen" und "Zuweisen zu" des Berichts sind äußerst nützlich und liefern Informationen zum Zweck und Speicherort der einzelnen Zertifikate.

![Zertifikat Administrator Bericht](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Zertifikat Administrator Bericht")

Überprüfen Sie sorgfältig die Verwendung und den Zweck jedes Zertifikats in der Bereitstellung, und achten Sie darauf, dass Sie dies verstehen. Wenn es eine Frage zu dem, was ein Zertifikat ist, ermitteln, welche Server oder Dienst mit was gesprochen wird. Zertifikate in lync Server 2013 werden für zwei primäre Zwecke verwendet:

  - Mutual Transport Layer Security (MTLS) – die an der Kommunikation beteiligten Computer stellen ein Zertifikat dar, das Ihre Identität für einen anderen Computer prüft. Dies wird als Serverauthentifizierung bezeichnet. Die Kommunikation kann erst begonnen werden, wenn jeder Computer der Identität des anderen Computers vertraut.

  - Verschlüsselung – Die Verschlüsselung (Secure Sockets Layer, SSL, und Transport Layer Security, TLS) ist eine wichtige Methode, um eine sichere Kommunikation und die Einhaltung von Datenschutzrichtlinien zu gewährleisten sowie ein vertrauenswürdiges System für Kommunikation und Zusammenarbeit zu erstellen.

<div>

## <a name="see-also"></a>Siehe auch


[Überprüfen der Administrator Berichte in lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

