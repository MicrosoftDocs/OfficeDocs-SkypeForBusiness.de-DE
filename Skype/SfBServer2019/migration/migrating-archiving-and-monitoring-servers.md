---
title: Migrieren von Archivierungs-und Überwachungs Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie den Archivierungsserver und den Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration dem Skype for Business Server 2019-Pilot Pool Archivierungs-und Überwachungsfunktionen hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298197"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungs-und Überwachungs Servern

Wenn Sie den Archivierungsserver und den Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration dem Skype for Business Server 2019-Pilot Pool Archivierungs-und Überwachungsfunktionen hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht. 
  
Wenn Sie während des Migrationsprozesses Archivierungs-und Überwachungsfunktionen wünschen, sollten Sie die folgenden Aspekte berücksichtigen:
  
- Archivierungsdaten und Überwachungsdaten werden nicht in die Skype for Business Server 2019-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebnahme der Legacyumgebung sichern, sind Ihr Aktivitätsverlauf in der Legacyumgebung.
    
- Die Legacy Version des Archivierungsservers und des Überwachungsservers kann nur einem Legacy-Front-End-Pool zugeordnet werden. In Skype for Business Server 2019 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in den Front-End-Pool von Skype for Business Server 2019 integriert sind.
    
- In der Zeit, in der Ihre Legacy-und Skype for Business Server 2019-Bereitstellungen koexistieren, sammeln die Legacy Version des Archivierungsservers und des Überwachungsservers Daten für Benutzer, die in Legacy Pools verwaltet werden. Archivierung und Überwachung in Skype for Business Server 2019 sammeln Sie Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.
    
    > [!NOTE]
    > Während der Migrationsphase, wenn Sie Ihren Legacy-Edgeserver weiterhin mit dem neuen Skype for Business Server 2019-Pilot Pool verwenden, sammelt die Legacy Version des Archivierungsservers weiterhin Daten für Benutzer, die sich in Legacy Pools befinden und in Skype for Business archiviert werden. Server 2019 sammelt Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden. 
  
- Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit Archivierung und Überwachung in Skype for Business Server 2019 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung in Skype for Business Server 2019 integrieren müssen.
    

