---
title: Überwachen der Protokolldateien für die Ablaufverfolgung von IIS-Anfragen in Skype for Business Server 2015
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
description: 'Zusammenfassung: Erfahren Sie mehr über den Mobilitätsdienst (Mcx) in Skype for Business Server 2015-Unterstützung für Legacyclients.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823505"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Überwachen der Protokolldateien für die Ablaufverfolgung von IIS-Anfragen in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst (Mcx) in Skype for Business Server 2015-Unterstützung für Legacyclients.
  
Dieses Thema bezieht sich nur auf Bereitstellungen, die Lync 2010 Lync Mobile-Clients unterstützen, und ist für den Mobilitätsdienst (Mcx) vorgesehen.

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Wenn Sie die Ablaufverfolgung für Internetinformationsdienste (Internet Information Services, IIS) für den Skype for Business Server Mobility Service (Mcx) aktivieren, können die generierten Protokolldateien bis zu drei Gigabyte Festplattenspeicher pro Tag verbrauchen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass auf den Front-End-Servern nicht genügend Speicherplatz zur Verfügung steht. 
  
Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter "%SystemDrive%\inetpub\logs\LogFiles" gespeichert.
  
Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Weitere Informationen zum Befehl **"httpLogging"** finden Sie [in der Befehlsreferenz.](https://go.microsoft.com/fwlink/p/?linkId=234927)
  

