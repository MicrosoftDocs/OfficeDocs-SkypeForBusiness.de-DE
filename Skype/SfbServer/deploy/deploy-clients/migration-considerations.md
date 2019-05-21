---
title: Überlegungen zur Skype Room System-Migration
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lesen Sie dieses Thema, um mehr über die Bereitstellung von Skype Room System in einer Umgebung zu erfahren, in der mehrere Versionen von Skype for Business Server und lync Server enthalten sind.
ms.openlocfilehash: 35dd7cff34134791ebaf62bf4d0fcd1cf3b83a4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293522"
---
# <a name="skype-room-system-migration-considerations"></a>Überlegungen zur Skype Room System-Migration
 
Lesen Sie dieses Thema, um mehr über die Bereitstellung von Skype Room System in einer Umgebung zu erfahren, in der mehrere Versionen von Skype for Business Server und lync Server enthalten sind.
  
## <a name="migration-considerations"></a>Überlegungen zur Migration

Dieser Abschnitt enthält Anleitungen für die Bereitstellung von Skype Room System in einer Multi-Pool-Umgebung, die unterschiedliche Versionen von Skype for Business Server oder lync Server umfasst. 
  
Die Benutzerreplikationskomponente (User Replicator; UR) in Lync Server erhält Benutzerobjekte aus Active Directory und legt sie in der Back-End-SQL-Serverdatenbank in Lync Server ab. Nur die ur in lync Server 2013 ist sich der Skype Room-System Objekte bewusst. Die UR in früheren Versionen von Lync Server und Office Communications Server erkennt nicht die Active Directory-Attribute zur Bezeichnung von LRS-Objekten, und nimmt sie dementsprechend auch nicht wahr. 
  
Wenn ein Skype Room-System Konto versucht, sich bei lync anzumelden und die automatische Ermittlung basierend auf SRV-Eintrag oder DNS ausführt, wird ein Eintrag nachschlagen, und wenn diese Konten auf eine frühere Version von lync Server oder Office Communications Server verweisen, erhält LRS eine Antwort vom 404 nicht gefunden.  der Legacy Pool. Der Legacy Pool kann das Skype Room-System nicht in seinen lync Server 2013-Home-Pool umleiten. 
  
Sie können diesem Problem mit folgenden Optionen begegnen: 
  
- Verweisen Sie Ihren AutoErmittlung-SRV-Eintrag (_sipinternaltls._tcp.contoso.com) auf den Lync Server 2013-Pool.
    
- Wenn die erste Option nicht möglich ist, müssen Sie LRS manuell konfigurieren und die lync Server 2013-Pool Adresse bereitstellen, indem Sie Sie direkt in der Skype Room System Console-Anwendung konfigurieren. 
    
- Wenn das Skype Room-System außerhalb des Unternehmensnetzwerks bereitgestellt wird und ein lync-Edgeserver bereitgestellt und so konfiguriert wurde, dass er auf einen Legacy Pool oder Director verweist, ist eine sekundäre Edgeserver-Website erforderlich, die auf den lync Server 2013-Pool verweist. Weitere Informationen zum Bereitstellen eines sekundären Edgeserver finden Sie in der Dokumentation zur Edge Server-Bereitstellung. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilität von Skype Room-Systemen mit einem lync Server 2010-Pool

Wenn ein Benutzer, der sich in einem lync Server 2010-Pool befindet, eine Besprechung plant und das Skype Room System-Konto einlädt, hat der Skype Room-System Client während der Migration nur begrenzte Funktionen, während er an der Besprechung teilnimmt. 
  
Wenn der Skype Room-System Client zu einem geplanten Konferenzanruf wechselt, der von einem Benutzer organisiert wurde, der sich in lync Server 2010 befindet, gelten für Skype Room System die folgenden Einschränkungen: 
  
- Skype Room System kann den Multi-View-Video Katalog nicht anzeigen.
    
- Wenn es sich bei dem Skype Room-System Client um den Referenten handelt, kann er keine Video Sperre für Teilnehmer anwenden.
    
- Skype Room System kann keine 1080p-Videoauflösung (eingehend oder ausgehend) anzeigen, selbst wenn die lync Server 2013-konferenzrichtlinie dies zulässt, und zwar aufgrund der folgenden Schritte: 
    
  - Lync Server 2010 unterstützt keine 1080p-Auflösung.
    
  - Das Skype-Raum System ist immer durch die Konferenzrichtlinien des Organisators für die Videoauflösung limitiert. Auch wenn der lync 2010-Pool eine 720p-Auflösung unterstützt, kann Skype Room System die 720p-Auflösung nicht nutzen, solange die Richtlinien von Organizer dies nicht unterstützen. 
    
- Lync 2013-Clients erkennen das Vorhandensein von LRS im Besprechungsraum und schalten sich selbst stumm, um Rückkopplungen im physischen Besprechungsraum zu vermeiden. Dieses Feature funktioniert nicht in Besprechungen, die auf Lync Server 2010 gehostet werden.
    
- Für die Leistungsfähigkeit von Desktopfreigaben für auf Lync Server 2010 gehosteten Besprechungen gelten Einschränkungen.
    
- Benutzer können nicht an privaten (eingeschränkten) Besprechungen teilnehmen, die in lync 2010 mit Skype Room System gehostet werden.
    

