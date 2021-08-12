---
title: Migrieren von Archivierungservern und Monitoring Servern
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn Sie den Archivierungsserver und den Monitoring Server in Ihrer älteren Umgebung bereitgestellt haben, können Sie diese Server nach der Migration ihrer Front-End-Pools in Ihrer Skype for Business Server 2019-Umgebung bereitstellen. Wenn Archivierungs- und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie dem Skype for Business Server 2019-Pilotpool vor der Migration jedoch die Archivierung und Überwachung hinzufügen, damit die Funktionalität während des Migrationsprozesses verfügbar ist.
ms.openlocfilehash: b1f497019d2043a7ea43c1134af615ae4db6183cd3d16593bfab6e835fa4db32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303549"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungservern und Monitoring Servern

Wenn Sie den Archivierungsserver und den Monitoring Server in Ihrer älteren Umgebung bereitgestellt haben, können Sie diese Server nach der Migration ihrer Front-End-Pools in Ihrer Skype for Business Server 2019-Umgebung bereitstellen. Wenn Archivierungs- und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie dem Skype for Business Server 2019-Pilotpool vor der Migration jedoch die Archivierung und Überwachung hinzufügen, damit die Funktionalität während des Migrationsprozesses verfügbar ist. 
  
Wenn Sie während des Migrationsvorgangs Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:
  
- Archivierungsdaten und Überwachungsdaten werden nicht in die Skype for Business Server 2019-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebnahme der Legacyumgebung sichern, sind Ihre Aktivitäten in der Legacyumgebung.
    
- Die Legacyversion von Archivierungsserver und Monitoring Server kann nur einem älteren Front-End-Pool zugeordnet werden. In Skype for Business Server 2019 sind Archivierung und Überwachung keine Serverrollen mehr, sondern Dienste, die in den Front-End-Pool Skype for Business Server 2019 integriert sind.
    
- In der Zeit, in der Ihre Legacy- und Skype for Business Server 2019-Bereitstellungen koexistieren, sammelt die Legacyversion von Archivierungsserver und Monitoring Server Daten für Benutzer, die in älteren Pools verwaltet werden. Archivierung und Überwachung in Skype for Business Server 2019 sammeln Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.
    
    > [!NOTE]
    > Während der Migrationsphase, in der Sie ihren älteren Edgeserver noch mit dem neuen Skype for Business Server 2019-Pilotpool verwenden, sammelt die Legacyversion des Archivierungsservers weiterhin Daten für Benutzer, die in älteren Pools verwaltet werden, und die Archivierung in Skype for Business Server 2019 sammelt Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden. 
  
- Wenn Sie eine Archivierungs- und Überwachungslösung von Drittanbietern in Verbindung mit der Archivierung und Überwachung in Skype for Business Server 2019 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung in Skype for Business Server 2019 integrieren müssen.
    

