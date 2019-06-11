---
title: 'Lync Server 2013: Technische Anforderungen für die Ankündigungsanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Technische Anforderungen für die Ankündigungsanwendung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

In diesem Abschnitt werden die folgenden technischen Voraussetzungen für die Ankündigungs Anwendung beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Audiodatei-Anforderungen

<div>

## <a name="hardware-requirements"></a>Hardware Anforderungen

Die Ankündigungs Anwendung hat die gleichen Hardwareanforderungen wie Front-End-Server. Details zu den Hardwareanforderungen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.

</div>

<div>

## <a name="software-requirements"></a>Software Anforderungen

Die Ankündigungs Anwendung verfügt über die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen die Ankündigungs Anwendung ausgeführt wird, muss die Windows Media-Format Laufzeit für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 Bei Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-Dateien (WMA) erforderlich, die von der Ankündigungs Anwendung für Ankündigungen und Musik wiedergegeben werden.

</div>

<div>

## <a name="port-requirements"></a>Portanforderungen

Die Ankündigungs Anwendung verwendet den folgenden Port:

  - **Port 5071**   für SIP-Abhör Anforderungen

<div>


> [!NOTE]  
> Dieser Port ist die Standardeinstellung, kann aber mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> geändert werden. Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Ankündigungs Anwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-Dateiformat (WMA) für Musik und Ankündigungen. Die Anforderungen an die Audiodateien für die Ankündigungs Anwendung sind identisch mit der Antwortgruppen Anwendung. Ausführliche Informationen finden Sie unter [Technische Voraussetzungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

