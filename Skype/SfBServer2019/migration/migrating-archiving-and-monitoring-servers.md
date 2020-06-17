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
description: Wenn Sie Archivierungsserver und Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor dem migrieren die Archivierung und Überwachung zu Ihrem Skype for Business Server 2019-Pilot Pool hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752667"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungservern und Monitoring Servern

Wenn Sie Archivierungsserver und Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor dem migrieren die Archivierung und Überwachung zu Ihrem Skype for Business Server 2019-Pilot Pool hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht. 
  
Wenn Sie während des Migrationsvorgangs Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:
  
- Das Archivieren von Daten und Überwachungsdaten wird nicht in die Skype for Business Server 2019-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebnahme der Vorgänger Umgebung sichern, sind die Historie der Aktivitäten in der Legacyumgebung.
    
- Die ältere Version von Archivierungsserver und Monitoring Server kann nur mit einem Legacy Front-End-Pool verknüpft werden. In Skype for Business Server 2019 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in die Front-End-Pool Skype for Business Server 2019 integriert sind.
    
- Während der Zeit, in der Ihre Legacy-und Skype for Business Server 2019-Bereitstellungen nebeneinander bestehen, sammeln die Legacy Version von Archivierungsserver und Monitoring Server Daten für Benutzer, die in älteren Pools verwaltet werden. Archivierung und Überwachung in Skype for Business Server 2019 Sammeln von Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.
    
    > [!NOTE]
    > Während der Migrationsphase, in der Sie weiterhin den Legacy-Edgeserver mit dem neuen Skype for Business Server 2019-Pilot Pool verwenden, sammelt die Vorgängerversion von Archivierungsserver weiterhin Daten für Benutzer, die in älteren Pools verwaltet werden, und archiviert in Skype for Business Server 2019 sammelt Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden. 
  
- Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit der Archivierung und Überwachung in Skype for Business Server 2019 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung mit Skype for Business Server 2019 integrieren müssen.
    

