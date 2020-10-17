---
title: 'Lync Server 2013: Überwachen von Protokolldateien für die Protokollierung von IIS-Anforderungen'
description: 'Lync Server 2013: Überwachung von Protokolldateien für die Protokollierung von IIS-Anforderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09692b79b1cc59ad18ad520885c0a795736b53cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569951"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Überwachen von Protokolldateien für die Protokollierung von IIS-Anforderungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Wenn Sie Internet Information Services (IIS) Anforderungs Ablaufverfolgung für den lync Server Mobilitätsdienst (MCX) aktivieren, können die generierten Protokolldateien pro Tag bis zu drei Gigabyte Speicherplatz beanspruchen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass nicht genügend Speicherplatz zur Verfügung steht.

Standardmäßig speichert IIS die Protokolldateien in% System Drive% \\ Verzeichnis Inetpub \\ Logs \\ Logfiles.

Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Ausführliche Informationen zum **httpLogging** -Befehl finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) .

</div>

<span> </span>

</div>

</div>

</div>

