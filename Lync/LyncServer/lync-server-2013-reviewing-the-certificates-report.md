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
ms.openlocfilehash: 410e9e99fccae7378b5260c9aa3a2281a3004cd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Überprüfen des Berichts "Zertifikate" in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Der Bericht Zertifikate enthält alle Zertifikate, die in der empfohlenen lync Server 2013-Bereitstellung erforderlich sind. Das Planungs Tool berücksichtigt die eingegebenen Antragstellernamen und alternativen Subjektnamen. Nicht bearbeiteter Standardtext kann eine Herausforderung für das Team darstellen, das für das Anfordern und Ausstellen der Zertifikate verantwortlich ist. In den Zertifikatinformationen ist zudem angegeben, durch welche Stelle das Zertifikat typischerweise ausgestellt werden kann. Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden. Die Felder „Erweiterte Schlüsselverwendungen“ und „Zuweisen zu“ des Berichts sind äußerst nützlich und liefern Informationen zu Zweck und Speicherort der einzelnen Zertifikate.

![Zertifikatverwaltungsbericht](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Zertifikatverwaltungsbericht")

Überprüfen Sie die Verwendung und den Zweck der einzelnen Zertifikate innerhalb der Bereitstellung sorgfältig und stellen Sie sicher, dass Sie diese Informationen verstanden haben. Wenn Sie Fragen zum Zweck eines Zertifikats haben, ermitteln Sie, welcher Server oder Dienst mit welcher Komponente kommuniziert. Zertifikate in lync Server 2013 werden für zwei primäre Zwecke verwendet:

  - Mutual Transport Layer Security (MTLS) – Die Computer, die miteinander kommunizieren, belegen ihre Identität gegenüber den anderen Computern mithilfe eines Zertifikats. Dieser Vorgang wird als Serverauthentifizierung bezeichnet. Die Kommunikation ist erst möglich, wenn sämtliche Computer die Identität der anderen Computer als vertrauenswürdig eingestuft haben.

  - Verschlüsselung – Die Verschlüsselung (Secure Sockets Layer, SSL, und Transport Layer Security, TLS) ist eine wichtige Methode, um eine sichere Kommunikation und die Einhaltung von Datenschutzrichtlinien zu gewährleisten sowie ein vertrauenswürdiges System für Kommunikation und Zusammenarbeit zu erstellen.

<div>

## <a name="see-also"></a>Siehe auch


[Überprüfen der Administratorberichte in Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

