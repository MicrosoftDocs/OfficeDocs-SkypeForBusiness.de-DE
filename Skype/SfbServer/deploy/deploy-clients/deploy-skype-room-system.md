---
title: Übersicht über die Bereitstellung für Skype Raum System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
ms.collection: M365-voice
description: Lesen Sie dazu, wie Sie sollten Sie Skype Raum System, einer Besprechung bereitstellen Raum-Lösung mit integrierter Hardware und Software, die Skype für Business-Besprechungen teilnehmen optimiert ist.
ms.openlocfilehash: 26ce5f6e50d26b408a8bce5d167e4e7b6046e514
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012567"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a>Planen der Bereitstellung für Skype Raum System in Skype für Unternehmen
 
Lesen Sie dazu, wie Sie sollten Sie Skype Raum System, einer Besprechung bereitstellen Raum-Lösung mit integrierter Hardware und Software, die Skype für Business-Besprechungen teilnehmen optimiert ist.
  
> [!NOTE]
> Im Rahmen dieser Inhalte Skype für Unternehmen für intelligente Raum-System, Crestron RL, and Polycom CX8000 werden als Skype Raum System bezeichnet. 

> [!NOTE]
> Microsoft-Teams Chatrooms ist ein anderes Produkt mit verschiedenen Abhängigkeiten und Bereitstellungsverfahren. Informationen zu Microsoft-Teams Chatrooms finden Sie unter [Planen von Microsoft Teams Chatrooms](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md).
  
 Skype Raum System ist eine Skype für Business unified Communications-Client, der für Skype für Besprechungen in physischen Konferenzräume Business optimiert wurde.
  
Der Client Skype Raum System wurde aus der Skype für Business Client mithilfe der Skype für Business SDK entwickelt. Die Skype für Business-Client im Hintergrund im teilweise unterdrückt Benutzeroberflächenmodus ausgeführt wird. Die Skype für Business Client steuert die video-Katalog und Stufe für Inhalt auf dem Bildschirm am Anfang des Raums. Der Client Skype Raum System bietet die Konsole auf die Anzeige als Desktop für Besprechungen steuern. Skype-Chatroom-System bietet: 
  
- One Touch-Teilnahme an Besprechungen
    
- Automatische Einrichtung der Videogalerie mit mehreren Ansichten 
    
- Whiteboard mit Fingereingabeunterstützung auf dem Bildschirm vorne im Raum 
    
- Kalenderintegration für den Zugriff auf geplante Besprechungen
    
- Inhaltsfreigabe und -wechsel 
    
Dieses Dokument leitet Sie durch eine Skype Raum System in Skype für Business Server und Exchange Server-Bereitstellung. Siehe auch das Skype Raum System Installationshandbuch von Ihrem Administrator, der Sie beim Einrichten der Appliance PCs und Geräte im Besprechungsraum führt. 
  
## <a name="prerequisites"></a>Voraussetzungen

Im folgenden sind die Anforderungen für Skype Raum System: 
  
- Ein Exchange-Ressourcenpostfachkonto zur Erleichterung der Kalenderplanung für die Besprechungsräume mit aktiviertem AutoErmittlungsdienst auf Exchange Server (2013 bevorzugt).
    
- Eine Skype für Business-aktivierten Skype Raum Systemkonto auf einen Skype für Business Serverpool (Enterprise oder Standard Edition).
    
- Eine Skype Raum System Client Appliance PC mit erforderlichen Softwareprogramme installiert. Auf dem Anwendungs-PC muss das Betriebssystem Windows 7 Embedded Standard laufen. Entsprechende Hardware wird von OEM-Partnern komplett mit allen Geräten (Displays, Kamera, Mikrofon, Lautsprechern) bereitgestellt.
    
- Wenn Sie die Skype Raum System Appliance PC in einer Active Directory-Domänendienste (AD DS) Domäne einbinden möchten, müssen Sie gruppenrichtlinieneinstellungen angeben, die Skype Raum System nicht stören. Alternativ können Sie den Anwendungs-PC in der Arbeitsgruppe belassen. 
    
- Entsprechende Benutzerrechte zum Ausführen der in diesem Dokument angegebenen Cmdlets. Die „CsMeetingRoom“-Cmdlets sind nach dem Vorbild des „CsUser“-Cmdlets ausgebildet. Deshalb treffen alle für die Ausführung von CsUser-Cmdlets erforderlichen rollenbasierten Zugriffssteuerungsrollen (RBAC, Role-Based Access Control) auch für „CsMeetingRoom“-Cmdlets zu. 
    
## <a name="supported-topologies"></a>Unterstützte Topologien

In der folgenden Tabelle angegeben Skype Raum System-Client-Interoperabilität zwischen verschiedenen Bereitstellungen von Skype für Geschäfts- und Exchange-Topologien, entweder lokal oder in der Cloud: 
  

|**Topologie**|**AD**|**Skype for Business**|**Exchange**|
|:-----|:-----|:-----|:-----|
|Lokal  <br/> |Lokal  <br/> |Lokal  <br/> |Lokal  <br/> |
|Office 365 mit mehreren Mandanten (O365MT)  <br/> |Online  <br/> |Online  <br/> |Online  <br/> |
|Office 365 Dedicated  <br/> (Wenden Sie sich an Ihren Dienstanbieter)  <br/> |Lokal  <br/> |Online  <br/> |Online  <br/> |
|Hybrid (Getrennte Domäne)  <br/> Nicht unterstützt  <br/> |Lokal  <br/> Lokal  <br/> Lokal  <br/> |Lokal  <br/> Online  <br/> Online  <br/> |Online  <br/> Online  <br/> Lokal  <br/> |
   
Versionen vor der Lync Server 2013 werden teilweise unterstützt. In diesen Szenarien Skype Raum System in Skype für Business-Konferenzen (die, die von Benutzern geplant werden, die sich in Lync Server 2010) teilnehmen können, solange die Konferenzen "öffentlich" sind, d. h., die Konferenzen werden nicht speziell für das beschränktem Zugriff. 
  
Skype-Chatroom-System kann nicht früher als Lync Server 2013 in einer Lync Server-Version verwaltet werden. Beim Herstellen der Verbindung einen Skype Raum-System zu Exchange kalendereinstellungen – abrufen kann nicht beispielsweise Exchange kann nicht zugegriffen werden--oder ist kein Exchange-Postfach konfiguriert für das Konto Skype Raum System jetzt besprechen und ad-hoc-Konferenzen funktioniert, aber zu einer geplante Besprechung wird nicht. 
  
In der folgenden Tabelle angegeben Skype Raum System Client Supportability mit Versionen von Exchange Server: 
  

|**Exchange**|**Lokal**|**Online**|**Hybrid**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Ja (nur einzelne Gesamtstruktur)  <br/> |n/v  <br/> |-  <br/> |
|Exchange 2013  <br/> |Ja (Mehrfach-Gesamtstruktur-Unterstützung verfügbar für Exchange 2013 CU6 und höhere Versionen)  <br/> |Ja  <br/> |Ja   <br/> |
|Exchange 2016  <br/> |Ja (mit mehreren Gesamtstrukturen Unterstützung verfügbar)  <br/> |Ja   <br/> |Ja  <br/> |
   

