---
title: Migrieren von Archivierungsservern und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie in der vorgängerumgebung Archivierungsserver und Monitoring Server bereitgestellt haben, können Sie diese Server nach dem Migrieren der Front-End-Pools in Ihrer Skype für Business Server 2019 Umgebung bereitstellen. Wenn die Archivierung und Überwachung von Funktionen für Ihre Organisation unternehmenskritisch sind, jedoch sollten Sie hinzufügen, Archivierung und Überwachung auf Ihre Skype für Business Server 2019 pilot Pool vor der Migration, damit die Funktionalität während des Migrationsprozesses verfügbar ist.
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896092"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungsservern und Monitoring Servern

Wenn Sie in der vorgängerumgebung Archivierungsserver und Monitoring Server bereitgestellt haben, können Sie diese Server nach dem Migrieren der Front-End-Pools in Ihrer Skype für Business Server 2019 Umgebung bereitstellen. Wenn die Archivierung und Überwachung von Funktionen für Ihre Organisation unternehmenskritisch sind, jedoch sollten Sie hinzufügen, Archivierung und Überwachung auf Ihre Skype für Business Server 2019 pilot Pool vor der Migration, damit die Funktionalität während des Migrationsprozesses verfügbar ist. 
  
Wenn Sie während des Migrationsvorgangs Archivierungs-und möchten, beachten Sie folgende Aspekte beachten:
  
- Archivieren von Daten und Überwachung von Daten werden nicht in der Skype für Business Server 2019 Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebnahme der Vorversionen Umgebung sichern werden aufgezeichnete Aktivität in der Vorversion-Umgebung.
    
- Die ältere Version des Archivierungsservers und Monitoring Server kann nur einen legacy-Front-End-Pool zugeordnet werden. In Skype für Business Server 2019 sind Archivierung und Überwachung nicht mehr Serverrollen, aber Services integriert die Skype für Business Server 2019 Front-End-Pool.
    
- Während der Zeit, die Ihre Legacy und Skype für Business Server 2019 Bereitstellungen möglich ist, die ältere Version des Archivierungsservers und Monitoring Server Erfassen von Daten für Benutzer in alten Pools verwaltet. Archivierung und Überwachung in Skype für Business Server 2019 sammeln, dass Daten für Benutzer in Skype für Business Server 2019 Pools verwaltet.
    
    > [!NOTE]
    > Während der Phase der Migration, wenn Sie sind weiterhin mit dem von der legacy-Edge-Server mit der neuen Skype für Business Server 2019 pilot Pool, die ältere Version des Archivierungsservers zum Erfassen von Daten für Benutzer weiterhin in alten Pools verwaltet und Archivierung in Skype für Unternehmen Server 2019 sammelt Daten für Benutzer in Skype für Business Server 2019 Pools verwaltet. 
  
- Wenn Sie einen Drittanbieter-Archivierung und Überwachung der Lösung in Verbindung mit der Archivierung und Überwachung in Skype für Business Server 2019 verwenden, wenden Sie sich an Ihren Händler wann und wie Sie die Drittanbieter-Lösung mit Skype für Business Server 2019 integrieren müssen.
    

