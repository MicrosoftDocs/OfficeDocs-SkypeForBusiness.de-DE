---
title: Überlegungen zur Migration von Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: In diesem Thema erfahren Sie, wie Sie Skype Room System in einer Umgebung mit mehreren Versionen von Skype for Business Server und Lync Server bereitstellen.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805785"
---
# <a name="skype-room-system-migration-considerations"></a>Überlegungen zur Migration von Skype Room System
 
In diesem Thema erfahren Sie, wie Sie Skype Room System in einer Umgebung mit mehreren Versionen von Skype for Business Server und Lync Server bereitstellen.
  
## <a name="migration-considerations"></a>Überlegungen zur Migration

Dieser Abschnitt enthält Anleitungen für die Bereitstellung von Skype Room System in einer Umgebung mit mehreren Pools, die unterschiedliche Versionen von Skype for Business Server oder Lync Server umfasst. 
  
Die Benutzerreplikatetorkomponente (UR) in Lync Server ruft Benutzerobjekte aus Active Directory ab und platziert sie in der Lync Server-Back-End-SQL Server Datenbank. Nur der UR in Lync Server 2013 sind Skype Room System-Objekte bekannt. Die UR in früheren Versionen von Lync Server und Office Communications Server erkennt nicht die Active Directory-Attribute, die LRS-Objekte kennzeichnen, und war daher nicht darauf aufmerksam. 
  
Wenn ein Skype Room System-Konto versucht, sich bei Lync anmeldet und die automatische Ermittlung basierend auf srV-Eintrag oder DNS-A-Eintrag durchführt und diese Konten auf eine frühere Version von Lync Server oder Office Communications Server verweisen, erhält LRS eine 404 Not Found-Antwort vom Legacypool. Der Legacypool kann Skype Room System nicht zu seinem Lync Server 2013-Homepool umleiten. 
  
Sie können dieses Problem mit den folgenden Optionen beheben: 
  
- Verweisen Sie Ihren AutoErmittlungs-SRV-Eintrag (_sipinternaltls._tcp.contoso.com) auf den Lync Server 2013-Pool.
    
- Wenn die erste Option nicht möglich ist, müssen Sie LRS manuell konfigurieren und die Lync Server 2013-Pooladresse angeben, indem Sie sie direkt in der Skype Room System-Konsolenanwendung konfigurieren. 
    
- Wenn Skype Room System außerhalb des Unternehmensnetzwerks bereitgestellt wird und ein Lync-Edgeserver bereitgestellt und so konfiguriert wurde, dass er auf einen Legacypool oder Director verweist, ist ein sekundärer Edgeserverstandort erforderlich, der auf den Lync Server 2013-Pool verweist. Weitere Informationen zum Bereitstellen eines sekundären Edgeservers finden Sie in der Dokumentation zur Edgeserverbereitstellung. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilität von Skype Room System mit einem Lync Server 2010-Pool

Wenn während der Migration ein Benutzer, der in einem Lync Server 2010-Pool gespeichert ist, eine Besprechung plant und das Skype Room System-Konto einlähmt, verfügt der Skype Room System-Client während der Teilnahme an der Besprechung über eingeschränkte Funktionen. 
  
Wenn der Skype Room System-Client einem geplanten Konferenzanruf beitritt, der von einem In Lync Server 2010-Benutzer organisiert wurde, gelten für Skype Room System die folgenden Besprechungseinschränkungen: 
  
- Skype Room System kann die Videogalerie mit mehreren Ansichtsansichten nicht anzeigen.
    
- Wenn der Skype Room System-Client der Presenter ist, kann er keine Videosperre auf Teilnehmer anwenden.
    
- Skype Room System kann keine Videoauflösung von 1080p (ein- oder ausgehend) anzeigen, selbst wenn die Lync Server 2013-Konferenzrichtlinie dies zulässt, aufgrund der folgenden Punkte: 
    
  - Lync Server 2010 unterstützt keine Auflösung von 1080p.
    
  - Skype Room System ist immer durch die Konferenzrichtlinie des Organisators für die Videoauflösung beschränkt. Selbst wenn der Lync 2010-Pool eine Auflösung von 720p unterstützt, kann Skype Room System daher die Auflösung von 720p nicht nutzen, solange die Richtlinie des Organisators dies nicht unterstützt. 
    
- Lync 2013-Clients erkennen die Anwesenheit von LRS im Besprechungsraum und stummschalten automatisch, um Echo im physischen Besprechungsraum zu vermeiden. Dieses Feature funktioniert nicht in Besprechungen, die auf Lync Server 2010 gehostet werden.
    
- Es gibt Einschränkungen bei der Desktopfreigabeleistung für Besprechungen, die auf Lync Server 2010 gehostet werden.
    
- Benutzer können nicht an privaten (eingeschränkten) Besprechungen teilnehmen, die in Lync 2010 mit Skype Room System gehostet werden.
    

