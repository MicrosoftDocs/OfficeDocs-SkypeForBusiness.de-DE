---
title: Überlegungen zur Skype Room System-Migration
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lesen Sie dieses Thema, um Informationen über die Bereitstellung von Skype Raum System in einer Umgebung, in denen mehrere Versionen von Skype Business Server und Lync Server.
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a>Überlegungen zur Skype Room System-Migration
 
Lesen Sie dieses Thema, um Informationen über die Bereitstellung von Skype Raum System in einer Umgebung, in denen mehrere Versionen von Skype Business Server und Lync Server.
  
## <a name="migration-considerations"></a>Überlegungen zur Migration

Dieser Abschnitt enthält Hinweise, wenn Sie Skype Raum System in einer Umgebung mit mehreren Pools bereitstellen, die verschiedene Versionen von Skype für Business Server, Lync Server oder Office Communications Server 2007 R2 enthält. 
  
Die Benutzerreplikationskomponente (User Replicator; UR) in Lync Server erhält Benutzerobjekte aus Active Directory und legt sie in der Back-End-SQL-Serverdatenbank in Lync Server ab. Nur der BENUTZERREPLIKATIONSDIENST in Lync Server 2013 kennt Skype Raum Systemobjekte. Die UR in früheren Versionen von Lync Server und Office Communications Server erkennt nicht die Active Directory-Attribute zur Bezeichnung von LRS-Objekten, und nimmt sie dementsprechend auch nicht wahr. 
  
Wenn ein Skype Raum Systemkonto zur Anmeldung bei Lync versucht, und führt basierend auf SRV-Eintrag oder DNS-A-Eintrag Nachschlagen AutoErmittlung, und zeigen Sie diese Konten zu einer früheren Version von Lync Server oder Office Communications Server, erhält LRS eine 404 nicht gefunden-Antwort vom  Pool der Vorgängerversion. Pool der Vorgängerversion möglich zur Umleitung von Skype Raum System an die Lync Server 2013 home-Pool nicht. 
  
Sie können diesem Problem mit folgenden Optionen begegnen: 
  
- Verweisen Sie Ihren AutoErmittlung-SRV-Eintrag (_sipinternaltls._tcp.contoso.com) auf den Lync Server 2013-Pool.
    
- Ist die erste Option nicht möglich, müssen Sie manuell konfigurieren LRS und geben Sie die Lync Server 2013-Pool-Adresse durch Konfigurieren sie direkt in die Konsolenanwendung Skype Raum System. 
    
- Skype Raum System außerhalb des Unternehmensnetzwerks bereitgestellt wird, und einen Lync-Edge-Server bereitgestellt und zeigen Sie auf einem vorversionspool oder Director konfiguriert wurde, ein sekundärer Standort Edge-Server ist erforderlich, der auf dem Lync Server 2013-Pool verweist. Finden Sie in der Dokumentation zur Bereitstellung von Edge-Server für Weitere Informationen zum Bereitstellen einer sekundären Edge-Server. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype-Raum Systeminteroperabilität mit einem Lync Server 2010-Pool

Während der Migration Wenn ein Benutzer, der auf einem Lync Server 2010-Pool verwaltet wird eine Besprechung plant und das Systemkonto Raum Skype lädt der Client Skype Raum System eingeschränkte Funktionalität auf haben während die Besprechung teilnehmen. 
  
Wenn der Client Skype Raum System eine geplante Telefonkonferenz teilnimmt, die durch organisiert wurden, hat ein Benutzer auf Lync Server 2010, verwaltet, Skype Raum System weist die folgenden in der Besprechung Nachteile: 
  
- Skype Raum System kann nicht Videogalerie mit Mehrfachansicht angezeigt werden.
    
- Es kann nicht auf Teilnehmer video Sperre anwenden, wenn der Client Skype Raum System der Referent ist.
    
- Skype Raum System kann nicht 1080p Auflösung (eingehend oder ausgehend), angezeigt werden, selbst wenn die konferenzrichtlinie für Lync Server 2013 es, aufgrund der folgenden ermöglicht: 
    
  - Lync Server 2010 unterstützt keine 1080p-Lösung.
    
  - Skype Raum System wird immer durch der Organisator konferenzrichtlinie für videoauflösung begrenzt. Aus diesem Grund, auch wenn der Lync 2010-Pool 720p Lösung unterstützt, werden Skype Raum System nicht 720p-Auflösung nutzen, solange des Organisators Richtlinie nicht unterstützt. 
    
- Lync 2013-Clients erkennen das Vorhandensein von LRS im Besprechungsraum und schalten sich selbst stumm, um Rückkopplungen im physischen Besprechungsraum zu vermeiden. Dieses Feature funktioniert nicht in Besprechungen, die auf Lync Server 2010 gehostet werden.
    
- Für die Leistungsfähigkeit von Desktopfreigaben für auf Lync Server 2010 gehosteten Besprechungen gelten Einschränkungen.
    
- Benutzer möglich nicht, private (eingeschränkte) an Besprechungen teilzunehmen, die gehostet werden für Lync 2010 mit Skype Raum System.
    

