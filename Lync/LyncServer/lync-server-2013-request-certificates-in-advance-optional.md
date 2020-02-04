---
title: 'Lync Server 2013: Vorabanforderung von Zertifikaten (optional)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Vorabanforderung von Zertifikaten (optional) für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Zertifikate sind für alle internen Server erforderlich, auf denen lync Server 2013 ausgeführt wird, darunter jeder Enterprise Edition-Front-End-Server, Standard Edition-Server, Director, Edge-Server und eigenständiger Vermittlungsserver. Obwohl eine interne Unternehmenszertifizierungsstelle für interne Server empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden. Ausführliche Informationen zu Zertifikatanforderungen und zur Verwendung einer öffentlichen Zertifizierungsstelle finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Das Setup von lync Server 2013 umfasst den Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten während der Bereitstellung vereinfacht. Wenn Sie vor dem Installieren von Servern Zertifikate anfordern möchten (beispielsweise um Zeit während der eigentlichen Bereitstellung von Servern zu sparen), können Sie dies mithilfe eines Computers, auf dem die lync Server 2013-Verwaltungstools installiert sind, oder mithilfe einer Zertifikatanforderung ausführen. in Ihrer Organisation definierte Prozedur, sofern Sie sicherstellen, dass die Zertifikate exportierbar sind und alle erforderlichen Alternativen Betreff-Namen enthalten. Das Anfordern von Zertifikaten im Voraus ist optional. Wenn Sie diese nicht im Voraus anfordern, müssen Sie Sie im Rahmen der Einrichtung jedes Servers anfordern, für den ein Zertifikat erforderlich ist.

Diese Bereitstellungsdokumentation enthält Verfahren für die Verwendung des Zertifikat-Assistenten zum Anfordern von Zertifikaten als Teil des Setupvorgangs, wie in den Abschnitten [Konfigurieren von Zertifikaten für Server in lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Konfigurieren von Zertifikaten für den Director in lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)und [Installieren der Dateien für den Vermittlungsserver in den Abschnitten lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) dieser Bereitstellungsdokumentation beschrieben. Wenn Sie Zertifikate im Voraus anfordern, müssen Sie die Zertifikat Bereitstellungsverfahren in diesen Abschnitten nach Bedarf ändern, um die Zertifikate zu importieren und zuzuweisen, anstatt Sie zum Zeitpunkt der Bereitstellung anzufordern.

<div>


> [!NOTE]  
> Lync Server 2013 enthält Unterstützung für SHA-256-Zertifikate für Verbindungen von Clients, auf denen Windows Vista&nbsp;, Windows Server 2008&nbsp;,&nbsp;Windows Server 2008 R2 und Windows 7-Betriebssysteme und lync Phone Edition ausgeführt werden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.



</div>

</div>

<span> </span>

</div>

</div>

</div>

