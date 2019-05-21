---
title: Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet. Diese Vorgehensweisen sind nicht nur für Ihre Skype for Business Server-Infrastruktur, sondern auch für Ihr gesamtes Netzwerk vorteilhaft. Wenn Sie diese Methoden nicht implementiert haben, empfiehlt es sich, dies vor der Bereitstellung von Skype for Business Server zu tun.
ms.openlocfilehash: c1f6a6ebe31276b8dbcd9037fa373baffc055fde
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296966"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
 
Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet. Diese Vorgehensweisen sind nicht nur für Ihre Skype for Business Server-Infrastruktur, sondern auch für Ihr gesamtes Netzwerk vorteilhaft. Wenn Sie diese Methoden nicht implementiert haben, empfiehlt es sich, dies vor der Bereitstellung von Skype for Business Server zu tun.
  
Gehen Sie wie folgt vor, um die Server in Ihrer Skype for Business Server-Bereitstellung vor versehentlichen oder zielgerichteten Verletzungen zu schützen, die zu Ausfallzeiten führen können:
  
- Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Mit einem Abonnement für den Microsoft Security Notification Service können Sie sicherstellen, dass Sie bei Veröffentlichungen von Sicherheitsbulletins für alle Microsoft-Produkte sofort benachrichtigt werden. Wenn Sie sich anmelden möchten, wechseln Sie zur [Website Microsoft Technical Security Notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Achten Sie darauf, dass Zugriffsrechte ordnungsgemäß eingerichtet sind.
    
- Stellen Sie Ihre Server in einer physischen Umgebung auf, die einen nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist. Halten Sie die Software mit den neuesten Virussignaturdateien auf dem neuesten Stand. Verwenden Sie die Funktion für automatische Updates Ihrer Antivirenanwendung, um die Virussignaturen aktuell zu halten.
    
- Wir empfehlen, dass Sie die Windows Server-Betriebssystemdienste deaktivieren, die auf den Computern, auf denen Sie Skype for Business Server installieren, nicht erforderlich sind.
    
- Verschlüsseln Sie Betriebssysteme und Festplattenlaufwerke, auf denen Daten gespeichert sind, mit einem Verschlüsselungssystem für das gesamte Volume, es sei denn, Sie können eine beständige und vollständige Kontrolle der Server, vollkommene physische Isolation und das ordnungsgemäße und sichere Außerbetriebsetzen von ausgetauschten oder ausgefallenen Festplattenlaufwerken sicherstellen.
    
- Deaktivieren Sie alle externen Ports für den direkten Speicherzugriff des Servers, es sei denn, Sie können eine sehr enge Kontrolle des physischen Zugriffs auf die Server sicherstellen. Angriffe auf der Basis von direktem Speicher, die realtiv einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel offenlegen.
    

