---
title: Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst ("MCX") in Skype für die Unterstützung für Clients von Vorversionen Business Server 2015.'
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst ("MCX") in Skype für Business Server 2015 Unterstützung für Clients von Vorversionen.
  
Dieses Thema gilt nur für Bereitstellungen, die Lync 2010 Lync Mobile-Clients unterstützen und ist für den Mobilitätsdienst (Mcx) vorgesehen.
  
Wenn Sie Internetinformationsdienste (Internet Information Services, IIS) Request Tracing für Business Server-Mobilitätsdienst ("MCX") für die Skype aktivieren, können die Protokolldateien, die generiert werden bis zu drei Gigabyte Speicherplatz pro Tag nutzen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Überwachen Sie den Front-End-Servern dafür sorgen, dass diese nicht mehr Festplattenspeicherplatz ausgeführt werden. 
  
Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter „%SystemDrive%\inetpub\logs\LogFiles“ gespeichert.
  
Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Ausführliche Informationen zum Befehl **HttpLogging** finden Sie unter [der Befehlsverzeichnis](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

