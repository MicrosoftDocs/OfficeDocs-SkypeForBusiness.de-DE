---
title: Überwachen von IIS-Anforderungsprotokolldateien in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Zusammenfassung: Erfahren Sie mehr über den Mobility Service (Mcx) in Skype for Business Server 2015-Unterstützung für Legacyclients.'
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118634"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Überwachen von IIS-Anforderungsprotokolldateien in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst (Mcx) in Skype for Business Server 2015-Unterstützung für Legacyclients.
  
Dieses Thema gilt nur für Bereitstellungen, die Lync 2010 Lync Mobile-Clients unterstützen, und ist für den Mobilitätsdienst (Mobility Service, Mcx) vorgesehen.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Wenn Sie die IiS-Anforderungsablaufverfolgung (Internet Information Services) für den Skype for Business Server Mobility Service (Mcx) aktivieren, können die generierten Protokolldateien bis zu drei Gigabyte Speicherplatz pro Tag verbrauchen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass der Speicherplatz nicht zu ende ist. 
  
Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter "%SystemDrive%\inetpub\logs\LogFiles" gespeichert.
  
Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Weitere Informationen zum **HttpLogging-Befehl** finden Sie in [der Befehlsreferenz](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).
