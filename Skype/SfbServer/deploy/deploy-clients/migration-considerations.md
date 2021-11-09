---
title: Skype Überlegungen zur Migration des Raumsystems
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer Umgebung mit mehreren Versionen von Skype for Business Server und Lync Server bereitstellen.
ms.openlocfilehash: 1b57115a332a647143fc0a3a7ca2c1ee178ad5fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850508"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Überlegungen zur Migration des Raumsystems
 
In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer Umgebung mit mehreren Versionen von Skype for Business Server und Lync Server bereitstellen.
  
## <a name="migration-considerations"></a>Überlegungen zur Migration

Dieser Abschnitt enthält Anleitungen, wenn Sie Skype Raumsystem in einer Umgebung mit mehreren Pools bereitstellen, die unterschiedliche Versionen von Skype for Business Server oder Lync Server enthält. 
  
Die BENUTZERreplikationskomponente (USER Replicator, UR) in Lync Server ruft Benutzerobjekte aus Active Directory ab und platziert sie in der Back-End-SQL Server-Datenbank von Lync Server. Nur die UR in Lync Server 2013 erkennt Skype Room System-Objekte. Die UR in früheren Versionen von Lync Server und Office Communications Server erkennt nicht die Active Directory-Attribute, die LRS-Objekte kennzeichnen, und war ihnen daher nicht bekannt. 
  
Wenn ein Skype Room System-Konto versucht, sich bei Lync anzumelden, und die automatische Ermittlung basierend auf dem SRV-Eintrag oder dem DNS-A-Eintragssuche durchführt und diese Konten auf eine frühere Version von Lync Server oder Office Communications Server verweisen, erhält LRS eine Antwort vom Legacypool "404 Not Found". Der Legacypool kann Skype Room System nicht zu seinem Lync Server 2013-Homepool umleiten. 
  
Sie können dieses Problem mit den folgenden Optionen beheben: 
  
- Verweisen Sie den AutoErmittlungs-SRV-Eintrag (_sipinternaltls._tcp.contoso.com) auf den Lync Server 2013-Pool.
    
- Wenn die erste Option nicht möglich ist, müssen Sie LRS manuell konfigurieren und die Lync Server 2013-Pooladresse angeben, indem Sie sie direkt in der Skype Room System-Konsolenanwendung konfigurieren. 
    
- Wenn Skype Raumsystem außerhalb des Unternehmensnetzwerks bereitgestellt wird und ein Lync-Edgeserver bereitgestellt und so konfiguriert wurde, dass er auf einen Legacypool oder Director verweist, ist ein sekundärer Edgeserverstandort erforderlich, der auf den Lync Server 2013-Pool verweist. Weitere Informationen zum Bereitstellen eines sekundären Edgeservers finden Sie in der Edgeserver-Bereitstellungsdokumentation. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Raumsysteminteroperabilität mit einem Lync Server 2010-Pool

Wenn ein Benutzer, der in einem Lync Server 2010-Pool verwaltet wird, während der Migration eine Besprechung plant und das Skype Raumsystemkonto einlädt, hat der Skype Room System-Client während der Teilnahme an der Besprechung eingeschränkte Funktionen. 
  
Wenn der Skype Room System-Client an einem geplanten Konferenzanruf teilnimmt, der von einem Benutzer in Lync Server 2010 organisiert wurde, gelten für Skype Raumsystem die folgenden Einschränkungen bei Besprechungen: 
  
- Skype Room System kann den Videokatalog mit mehreren Ansichten nicht anzeigen.
    
- Wenn der Skype Room System-Client der Referent ist, kann die Videosperre nicht auf Teilnehmer angewendet werden.
    
- Skype Room System kann die Videoauflösung von 1080p (eingehend oder ausgehend) nicht anzeigen, auch wenn die Lync Server 2013-Konferenzrichtlinie dies zulässt, aufgrund der folgenden Punkte: 
    
  - Lync Server 2010 unterstützt keine Auflösung von 1080p.
    
  - Skype Das Raumsystem ist immer durch die Konferenzrichtlinie des Organisators für die Videoauflösung beschränkt. Selbst wenn der Lync 2010-Pool die Auflösung von 720p unterstützt, kann Skype Raumsystem daher die 720p-Auflösung nicht nutzen, solange die Richtlinie des Organisators sie nicht unterstützt. 
    
- Lync 2013-Clients erkennen die LRS-Anwesenheit im Besprechungsraum und schalten sich automatisch stumm, um Echo im physischen Besprechungsraum zu vermeiden. Dieses Feature funktioniert nicht in Besprechungen, die auf Lync Server 2010 gehostet werden.
    
- Für Besprechungen, die in Lync Server 2010 gehostet werden, gelten Einschränkungen bei der Leistung der Desktopfreigabe.
    
- Benutzer können nicht an privaten (eingeschränkten) Besprechungen teilnehmen, die in Lync 2010 mit Skype Room System gehostet werden.
    

