---
title: 'Lync Server 2013: technische Anforderungen für die Ankündigungsanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a1a752159f27cf2d1bdadc149c2f26131c5ab06
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Technische Anforderungen für die Ankündigungsanwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

In diesem Abschnitt werden die folgenden technischen Anforderungen für die Ankündigungsanwendung beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Anforderungen für Audiodateien

<div>

## <a name="hardware-requirements"></a>Hardwareanforderungen

Die Ankündigungsanwendung hat die gleichen Hardwareanforderungen wie Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

</div>

<div>

## <a name="software-requirements"></a>Softwareanforderungen

Das Ankündigungsanwendung hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen der Ankündigungsanwendung ausgeführt wird, muss die Windows Media Format-Laufzeitumgebung für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server installiert sein, auf denen Windows Server 2012 ausgeführt wird, oder Windows Server 2012 R2. Für Windows Server 2008 R2 wird die Windows Media Format-Laufzeitkomponente als Teil der Windows-Desktop Umgebung installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-(WMA-) Dateien erforderlich, die das Ankündigungsanwendung für Ankündigungen und Musik abspielt.

</div>

<div>

## <a name="port-requirements"></a>Portanforderungen

Der Ankündigungsanwendung verwendet den folgenden Port:

  - **Port 5071**   wird für SIP-Überwachungsanforderungen verwendet

<div>


> [!NOTE]  
> Dieser Port ist die Standardeinstellung, die Sie ändern können, indem Sie das Cmdlet "Cmdlet <STRONG>festlegen-CsApplicationServer</STRONG> " verwenden. Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Das Ankündigungsanwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-(WMA-) Dateiformat für Musik und Ankündigungen. Die Anforderungen an die Audiodateien für die Ankündigungsanwendung entsprechen denen für die Reaktionsgruppenanwendung. Ausführliche Informationen finden Sie unter [Technical Requirements for Response Group in lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

