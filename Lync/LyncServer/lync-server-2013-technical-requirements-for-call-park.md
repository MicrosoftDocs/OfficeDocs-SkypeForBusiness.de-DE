---
title: 'Lync Server 2013: technische Anforderungen für das Parken von Anrufen'
description: 'Lync Server 2013: technische Anforderungen für das Parken von anrufen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577131"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Technische Anforderungen für das Parken von Anrufen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

In diesem Abschnitt werden die folgenden technischen Anforderungen für das Parken von Anrufen beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Anforderungen für Audiodateien

<div>

## <a name="hardware-requirements"></a>Hardwareanforderungen

Die Anwendung zum Parken von Anrufen hat die gleichen Hardwareanforderungen wie Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

</div>

<div>

## <a name="software-requirements"></a>Softwareanforderungen

Das Anwendung zum Parken von Anrufen hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Auf allen Front-End-Servern und Standard Edition-Servern, auf denen die Anwendung zum Parken von Anrufen bereitgestellt wird, muss die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. Für Windows Server 2008 R2 wird Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-(WMA-) Dateien erforderlich, die Park-Wiedergabe für Musik in der Warteschleife aufrufen.

</div>

<div>

## <a name="port-requirements"></a>Portanforderungen

Der Anwendung zum Parken von Anrufen verwendet den folgenden Port:

  - **Port 5075**     Wird für SIP-Überwachungsanforderungen verwendet.

<div>


> [!NOTE]  
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Das Anwendung zum Parken von Anrufen unterstützt nur Windows Media Audio-(WMA-) Dateien für die Wartemusik. Sie können Dateien für Wartemusik mit Microsoft Expression Encoder 4 anpassen. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter "Expression Encoder 4" unter [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) . Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren. Das empfohlene Format für Wartemusikdateien für die Anwendung zum Parken von Anrufen ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR oder 32 KBit/s.

<div>


> [!NOTE]  
> Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn diese mit 44 kHz aufgezeichnet wurde.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

