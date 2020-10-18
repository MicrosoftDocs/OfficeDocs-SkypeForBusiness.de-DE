---
title: 'Lync Server 2013: Anfordern von Zertifikaten im Voraus (optional)'
description: 'Lync Server 2013: fordern Sie Zertifikate vorab an (optional).'
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
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579031"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Anfordern von Zertifikaten im Voraus (optional) für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Zertifikate sind für alle internen Server mit lync Server 2013 erforderlich, einschließlich der einzelnen Enterprise Edition-Front-End-Server, Standard Edition-Server, Director, Edgeserver und eigenständigen Vermittlungsserver. Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden. Ausführliche Informationen zu Zertifikatanforderungen und zur Verwendung einer öffentlichen Zertifizierungsstelle finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Lync Server 2013-Setup umfasst den Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten während der Bereitstellung erleichtert. Wenn Sie Zertifikate vor dem Installieren von Servern anfordern möchten (beispielsweise, um Zeit bei der tatsächlichen Bereitstellung von Servern zu sparen), können Sie dies über einen Computer verwenden, auf dem die lync Server 2013 Verwaltungstools installiert sind, oder indem Sie ein in Ihrer Organisation definiertes Zertifikat Anforderungsverfahren verwenden, solange Sie sicherstellen, dass die Zertifikate exportierbar sind und alle erforderlichen alternativen Antragstellernamen enthalten. Das Anfordern von Zertifikaten im Voraus ist optional. Wenn Sie diese nicht im Voraus anfordern, müssen Sie Sie im Rahmen der Einrichtung jedes Servers anfordern, für den ein Zertifikat erforderlich ist.

In dieser Bereitstellungsdokumentation finden Sie Verfahren für die Verwendung des Zertifikat-Assistenten zum Anfordern von Zertifikaten als Teil des Installationsvorgangs, wie im Abschnitt [Konfigurieren von Zertifikaten für Server in lync Server 2013](lync-server-2013-configure-certificates-for-servers.md)beschrieben, [Konfigurieren von Zertifikaten für den Director in lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)und [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) Abschnitten dieser Bereitstellungsdokumentation. Wenn Sie Zertifikate vorab anfordern, müssen Sie die Zertifikat Bereitstellungsverfahren in diesen Abschnitten entsprechend dem Importieren und Zuweisen der Zertifikate ändern, anstatt Sie zum Zeitpunkt der Bereitstellung anzufordern.

<div>


> [!NOTE]  
> Lync Server 2013 enthält Unterstützung für SHA-256-Zertifikate für Verbindungen von Clients, auf denen die Windows Vista, Windows Server &nbsp; 2008, Windows Server &nbsp; 2008 &nbsp; R2 und Windows 7-Betriebssysteme sowie lync Phone Edition ausführen. Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.



</div>

</div>

<span> </span>

</div>

</div>

</div>

