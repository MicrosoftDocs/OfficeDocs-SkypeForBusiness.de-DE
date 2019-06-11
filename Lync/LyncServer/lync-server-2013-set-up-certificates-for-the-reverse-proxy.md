---
title: 'Lync Server 2013: Einrichten der Zertifikate für den Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Einrichten der Zertifikate für den Reverseproxy in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Für jeden Reverse-Proxy Server ist ein Webserverzertifikat zur Verwendung durch den Überwachungsdienst erforderlich. Das Webserverzertifikat muss von einer öffentlichen Zertifizierungsstelle (Certification Authority, ca) ausgestellt werden.

Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>So richten Sie ein Webdienste-Zertifikat für den Reverse-Proxy ein

  - Sie sollten ihren Reverse-Proxy bereits eingerichtet haben, einschließlich der Einrichtung des Webdienste-Zertifikats. Wenn Sie dies nicht getan haben, bevor Sie die Bereitstellung Ihrer Edgeserver gestartet haben, verwenden Sie die Verfahren unter [Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) , um die Anforderung zu erstellen und das Webdienst Zertifikat zu installieren, und erstellen Sie dann jede Webveröffentlichungsregel, und Konfigurieren Sie die Anwendung für die Verwendung des Zertifikats.

</div>

</div>

<span> </span>

</div>

</div>

</div>

