---
title: Unterstützung von lync Server 2013 Zertifikatinfrastruktur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1009fbe40092d9b6e6692ad2bc4d5305d7fbf375
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Unterstützung der Zertifikatinfrastruktur in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS (Transport Layer Security) und MTLS-Verbindungen (Mutual TLS). Standardmäßig ist lync Server 2013 für die Verwendung von TLS für Client-zu-Server-Verbindungen konfiguriert. MTLS wird für Verbindungen zwischen Servern verwendet.

MTLS-Zertifikate müssen von vertrauenswürdigen Zertifizierungsstellen (Certification Authorities, CAS) für lync Server 2013 ausgestellt werden. Lync Server unterstützt Zertifikate, die von folgenden CAS ausgestellt werden:

  - Zertifikate, die von einer internen Zertifizierungsstelle ausgestellt wurden:
    
      - Die Windows Server 2003-Betriebssystem-Zertifizierungsstelle
    
      - Die Windows Server 2008-Betriebssystem-Zertifizierungsstelle
    
      - Die Windows Server 2008 R2-Betriebssystem-Zertifizierungsstelle
    
      - Die Windows Server 2012-Betriebssystem-Zertifizierungsstelle
    
      - Die Windows Server 2012 R2-Betriebssystem-Zertifizierungsstelle

  - Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden

Für die Kommunikation mit anderen Anwendungen und Servern wie Exchange 2013 ist ein Zertifikat erforderlich, das von den anderen Anwendungen und Produkten unterstützt wird. Für das 2013-Release, lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, wird das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung unterstützt. Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

Für Verbindungen von Clients, die Windows 7 Betriebssystem, Windows Server 2008 R2-Betriebssystem und Microsoft Office Communicator 2007 Phone Edition ausführen, enthält lync Server 2013 Unterstützung für (jedoch nicht erforderliche) Zertifikate, die mit dem SHA-256 signiert wurden. kryptografische Hashfunktion. Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.

Ausführliche Informationen zu den Zertifikatanforderungen finden Sie unter [Certificate Infrastructure Requirements for lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Platzhalterzeichen mit Zertifikaten finden Sie unter [Wildcard Certificate Support in lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in der Unterstützungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

