---
title: Überwachen der Protokolldateien der IIS-Anforderungsablaufverfolgung in Skype for Business Server 2015
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
ms.openlocfilehash: 74aaca832bc7f6cfa1b9e3afbc08942ac0eceee3a655f36abb1347eab9ea5cfd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297151"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Überwachen der Protokolldateien der IIS-Anforderungsablaufverfolgung in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst (Mcx) in Skype for Business Server 2015-Unterstützung für Legacyclients.
  
Dieses Thema gilt nur für Bereitstellungen, die Lync 2010 Lync Mobile-Clients unterstützen, und ist für den Mobilitätsdienst (Mcx) vorgesehen.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
Wenn Sie Internetinformationsdienste (IIS)-Anforderungsablaufverfolgung für den Skype for Business Server Mobility Service (Mcx) aktivieren, können die generierten Protokolldateien bis zu drei Gigabyte Speicherplatz pro Tag belegen. Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert. Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass ihnen nicht der Speicherplatz ausläuft. 
  
Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter "%SystemDrive%\inetpub\logs\LogFiles" gespeichert.
  
Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Ausführliche Informationen zum **Befehl "httpLogging"** finden Sie [in der Befehlsreferenz.](/previous-versions/iis/settings-schema/aa347466(v=vs.90))
