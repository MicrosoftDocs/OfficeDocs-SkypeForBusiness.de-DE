---
title: Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, indem Sie Methoden wie die Gewährleistung von Hardwareredundanz, schutz vor Energieverlust, die routinemäßige Installation von Sicherheitsupdates und Antivirenmaßnahmen und Monitoring Server-Aktivitäten verwenden. Diese Methoden profitieren nicht nur von Ihrer Skype for Business Server Infrastruktur, sondern auch von Ihrem gesamten Netzwerk. Wenn Sie diese Methoden nicht implementiert haben, empfehlen wir, dies zu tun, bevor Sie Skype for Business Server bereitstellen.
ms.openlocfilehash: c3f07914f69881f4a9ce0c1f7d4451809b06f8e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737631"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
 
Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, indem Sie Methoden wie die Gewährleistung von Hardwareredundanz, schutz vor Energieverlust, die routinemäßige Installation von Sicherheitsupdates und Antivirenmaßnahmen und Monitoring Server-Aktivitäten verwenden. Diese Methoden profitieren nicht nur von Ihrer Skype for Business Server Infrastruktur, sondern auch von Ihrem gesamten Netzwerk. Wenn Sie diese Methoden nicht implementiert haben, empfehlen wir, dies zu tun, bevor Sie Skype for Business Server bereitstellen.
  
Um die Server in Ihrer Skype for Business Server Bereitstellung vor versehentlichen oder absichtlichen Schäden zu schützen, die zu Ausfallzeiten führen können, treffen Sie die folgenden Vorsichtsmaßnahmen:
  
- Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Das Abonnieren des Microsoft-Sicherheitsbenachrichtigungsdiensts trägt dazu bei, dass Sie sofortige Benachrichtigungen über Die Veröffentlichung von Sicherheitsbulletins für jedes Microsoft-Produkt erhalten. To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Stellen Sie sicher, dass die Zugriffsrechte ordnungsgemäß eingerichtet sind.
    
- Halten Sie Ihre Server in einer physischen Umgebung, die nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass auf allen Servern geeignete Antivirensoftware installiert ist. Halten Sie die Software stets mit den neuesten Virensignaturdateien auf dem aktuellen Stand. Verwenden Sie das Feature für automatische Aktualisierungen der Antivirenanwendung, um die Virensignaturen auf dem neuesten Stand zu halten.
    
- Es wird empfohlen, die Windows Server-Betriebssystemdienste zu deaktivieren, die auf den Computern, auf denen Sie Skype for Business Server installieren, nicht erforderlich sind.
    
- Verschlüsseln Sie Betriebssysteme und Datenträgerlaufwerke, auf denen Daten mit einem Verschlüsselungssystem mit vollständigem Volume gespeichert werden, es sei denn, Sie können eine konstante und vollständige Kontrolle über die Server, die vollständige physische Isolation und die ordnungsgemäße und sichere Außerbetriebnahme ersetzter oder ausgefallener Festplattenlaufwerke gewährleisten.
    
- Deaktivieren Sie alle externen DMA-Ports (Direct Memory Access) des Servers, es sei denn, Sie können eine sehr strenge Kontrolle über den physischen Zugriff auf die Server gewährleisten. DMA-basierte Angriffe, die relativ einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel verfügbar machen.
    

