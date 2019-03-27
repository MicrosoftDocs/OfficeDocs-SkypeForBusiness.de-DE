---
title: Bewährte Methoden für die Hauptinfrastruktur in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet. Diese Methoden profitieren nicht nur Ihre Skype für Business Server-Infrastruktur, sondern auch das gesamte Netzwerk. Wenn Sie diese Verfahren nicht umgesetzt haben, wird empfohlen, dass Sie dies tun, vor der Bereitstellung von Skype für Business Server.
ms.openlocfilehash: 86d18e1d9d34b5f65f4cb938e13a9829af1646bb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885806"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Bewährte Methoden für die Hauptinfrastruktur in Skype für Business Server
 
Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet. Diese Methoden profitieren nicht nur Ihre Skype für Business Server-Infrastruktur, sondern auch das gesamte Netzwerk. Wenn Sie diese Verfahren nicht umgesetzt haben, wird empfohlen, dass Sie dies tun, vor der Bereitstellung von Skype für Business Server.
  
Um die Server in Ihrer Skype für Business Server-Bereitstellung vor unbeabsichtigten oder beabsichtigten Beschädigungen zu schützen, die Ausfallzeiten führen können, sollten Sie die folgenden Maßnahmen ergreifen:
  
- Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Mit einem Abonnement für den Microsoft Security Notification Service können Sie sicherstellen, dass Sie bei Veröffentlichungen von Sicherheitsbulletins für alle Microsoft-Produkte sofort benachrichtigt werden. Zum Abonnieren wechseln Sie zur [Microsoft Technical Security Notifications Website](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Achten Sie darauf, dass Zugriffsrechte ordnungsgemäß eingerichtet sind.
    
- Stellen Sie Ihre Server in einer physischen Umgebung auf, die einen nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist. Halten Sie die Software mit den neuesten Virussignaturdateien auf dem neuesten Stand. Verwenden Sie die Funktion für automatische Updates Ihrer Antivirenanwendung, um die Virussignaturen aktuell zu halten.
    
- Es wird empfohlen, dass Sie die Dienste der Betriebssysteme Windows Server, die nicht auf den Computern erforderlich sind deaktivieren, auf denen Sie Skype für Business Server installieren.
    
- Verschlüsseln Sie Betriebssysteme und Festplattenlaufwerke, auf denen Daten gespeichert sind, mit einem Verschlüsselungssystem für das gesamte Volume, es sei denn, Sie können eine beständige und vollständige Kontrolle der Server, vollkommene physische Isolation und das ordnungsgemäße und sichere Außerbetriebsetzen von ausgetauschten oder ausgefallenen Festplattenlaufwerken sicherstellen.
    
- Deaktivieren Sie alle externen Ports für den direkten Speicherzugriff des Servers, es sei denn, Sie können eine sehr enge Kontrolle des physischen Zugriffs auf die Server sicherstellen. Angriffe auf der Basis von direktem Speicher, die realtiv einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel offenlegen.
    

