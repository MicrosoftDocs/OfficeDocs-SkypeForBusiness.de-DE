---
title: Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Wahrscheinlich haben Sie bereits Schritte zum Entwerfen der Fehlertoleranz in Ihrem System unter Verwendung von Methoden wie der Sicherstellung von Hardwareredundanz, Schutz vor Stromausfall, routinemäßiger Installation von Sicherheitsupdates und Antivirenmaßnahmen und Monitoring Server-Aktivitäten unternommen. Diese Vorgehensweisen profitieren nicht nur von Ihrer Skype for Business Server-Infrastruktur, sondern auch von Ihrem gesamten Netzwerk. Wenn Sie diese Methoden nicht implementiert haben, wird empfohlen, dies vor der Bereitstellung von Skype for Business Server zu tun.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832245"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
 
Wahrscheinlich haben Sie bereits Schritte zum Entwerfen der Fehlertoleranz in Ihrem System unter Verwendung von Methoden wie der Sicherstellung von Hardwareredundanz, Schutz vor Stromausfall, routinemäßiger Installation von Sicherheitsupdates und Antivirenmaßnahmen und Monitoring Server-Aktivitäten unternommen. Diese Vorgehensweisen profitieren nicht nur von Ihrer Skype for Business Server-Infrastruktur, sondern auch von Ihrem gesamten Netzwerk. Wenn Sie diese Methoden nicht implementiert haben, wird empfohlen, dies vor der Bereitstellung von Skype for Business Server zu tun.
  
Um die Server in Ihrer Skype for Business Server-Bereitstellung vor versehentlichen oder unbeabsichtigten Schäden zu schützen, die zu Ausfallzeiten führen können, ergreifen Sie die folgenden Vorsichtsmaßnahmen:
  
- Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Durch das Abonnieren des Microsoft Security Notification Service können Sie sicherstellen, dass Sie sofortige Benachrichtigungen über Veröffentlichungen von Sicherheitsbulletinen für alle Microsoft-Produkte erhalten. Um ein Abonnement zu erstellen, wechseln Sie zur [Microsoft Technical Security Notifications-Website.](https://go.microsoft.com/fwlink/p/?LinkId=145202)
    
- Stellen Sie sicher, dass die Zugriffsrechte ordnungsgemäß eingerichtet sind.
    
- Halten Sie Ihre Server in einer physischen Umgebung, die nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass auf allen Servern geeignete Antivirensoftware installiert ist. Halten Sie die Software stets mit den neuesten Virensignaturdateien auf dem aktuellen Stand. Verwenden Sie das Feature für automatische Aktualisierungen der Antivirenanwendung, um die Virensignaturen auf dem neuesten Stand zu halten.
    
- Es wird empfohlen, die Windows Server-Betriebssystemdienste zu deaktivieren, die auf den Computern, auf denen Sie Skype for Business Server installieren, nicht erforderlich sind.
    
- Verschlüsseln Sie Betriebssysteme und Festplattenlaufwerke, auf denen Daten mit einem vollständigen Verschlüsselungssystem gespeichert werden, es sei denn, Sie können eine konstante und vollständige Kontrolle über die Server, die vollständige physische Isolation und die ordnungsgemäße und sichere Außerbetriebnahme ersetzter oder ausgefallener Festplattenlaufwerke garantieren.
    
- Deaktivieren Sie alle externen Ports für den direkten Arbeitsspeicherzugriff (Direct Memory Access, DMA) des Servers, es sei denn, Sie können eine sehr strenge Kontrolle über den physischen Zugriff auf die Server garantieren. DMA-basierte Angriffe, die relativ einfach initiiert werden können, können sehr vertrauliche Informationen verfügbar machen, z. B. private Verschlüsselungsschlüssel.
    

