---
title: 'Lync Server 2013: Überwachen von IIS-Anforderungs Protokollierungs Protokolldateien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Überwachen von IIS-Anforderungs Protokollierungs Protokolldateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Wenn Sie die Ablaufverfolgung für Internet Informationsdienste (IIS) für den lync Server Mobility Service (MCX) aktivieren, können die generierten Protokolldateien pro Tag bis zu drei Gigabyte Speicherplatz belegen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass der Speicherplatz nicht ausgeht.

Standardmäßig speichert IIS die Protokolldateien unter% Drive%\\Inetpub\\log\\Logfiles.

Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Details zum Befehl **httpLogging** finden Sie unter [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).

</div>

<span> </span>

</div>

</div>

</div>

