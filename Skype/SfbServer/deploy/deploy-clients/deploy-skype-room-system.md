---
title: Bereitstellen von Skype Room System in Skype for Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: Erfahren Sie, wie Sie  bereitstellen, eine Besprechungsraum-Lösung aus integrierter Hardware und Software, die für die Teilnahme an -Besprechungen optimiert ist.
ms.openlocfilehash: 11cbae1cdbdd0585a2ea67625179ee7862309723
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-system-in-skype-for-business-server"></a>Bereitstellen von Skype Room System in Skype for Business Server
 
Erfahren Sie, wie Sie  bereitstellen, eine Besprechungsraum-Lösung aus integrierter Hardware und Software, die für die Teilnahme an -Besprechungen optimiert ist.
  
> [!NOTE]
> Der Einfachheit halber wird im Rahmen dieses Themas  für SMART Room System, Crestron RL und Polycom CX8000 als  bezeichnet. 
  
 Skype Room System is a Skype for Business unified communications client that has been optimized for Skype for Business meetings in physical conference rooms.
  
The Skype Room System client was developed from the Skype for Business client by using the Skype for Business SDK. Der -Client wird im Modus mit teilweise unterdrückter Benutzeroberfläche im Hintergrund ausgeführt. Der -Client steuert die Videogalerie und das Inhaltsfenster auf dem Bildschirm vorn im Raum. Der -Client stellt für die Besprechungssteuerung auf der Schreibtischanzeige eine Konsole bereit. Skype Room System 
  
- One Touch-Teilnahme an Besprechungen
    
- Automatische Einrichtung der Videogalerie mit mehreren Ansichten 
    
- Whiteboard mit Fingereingabeunterstützung auf dem Bildschirm vorne im Raum 
    
- Kalenderintegration für den Zugriff auf geplante Besprechungen
    
- Inhaltsfreigabe und -wechsel 
    
This document guides you through provisioning Skype Room System in Skype for Business Server and Exchange Server. Weitere Informationen finden Sie auch im -Installationshandbuch, das von Ihrem Administrator bereitgestellt wird und Sie durch die Einrichtung des Anwendungs-PCs und der entsprechenden Geräte im Besprechungsraum führt. 
  
## <a name="prerequisites"></a>Voraussetzungen

Following are the requirements for Skype Room System: 
  
- Ein Exchange-Ressourcenpostfachkonto zur Erleichterung der Kalenderplanung für die Besprechungsräume mit aktiviertem AutoErmittlungsdienst auf Exchange Server (2013 bevorzugt).
    
- A Skype for Business-enabled Skype Room System account on a Skype for Business Server pool (Enterprise or Standard Edition).
    
- Ein Anwendungs-PC mit , auf dem die gesamte erforderliche Software installiert ist. Auf dem Anwendungs-PC muss das Betriebssystem Windows 7 Embedded Standard laufen. Entsprechende Hardware wird von OEM-Partnern komplett mit allen Geräten (Displays, Kamera, Mikrofon, Lautsprechern) bereitgestellt.
    
- Wenn Sie sich entschließen, den -Anwendungs-PC an eine „Active Directory Domain Services“-(AD DS-)Domäne anzuschließen, müssen Sie Gruppenrichtlinieneinstellungen angeben, die  nicht beeinträchtigen. Alternativ können Sie den Anwendungs-PC in der Arbeitsgruppe belassen. 
    
- Entsprechende Benutzerrechte zum Ausführen der in diesem Dokument angegebenen Cmdlets. Die „CsMeetingRoom“-Cmdlets sind nach dem Vorbild des „CsUser“-Cmdlets ausgebildet. Deshalb treffen alle für die Ausführung von CsUser-Cmdlets erforderlichen rollenbasierten Zugriffssteuerungsrollen (RBAC, Role-Based Access Control) auch für „CsMeetingRoom“-Cmdlets zu. 
    
## <a name="supported-topologies"></a>Unterstützte Topologien

Die folgende Tabelle zeigt -Client-Interoperabilität im Rahmen verschiedener Bereitstellungen von - und Exchange-Topologien, entweder lokal oder in der Cloud: 
  

|**Topologie**|**AD**|**Skype for Business**|**Exchange**|
|:-----|:-----|:-----|:-----|
|Lokal  <br/> |Lokal  <br/> |Lokal  <br/> |Lokal  <br/> |
|Office 365 Multi-tenant (O365MT)  <br/> |Online  <br/> |Online  <br/> |Online  <br/> |
|Office 365 Dedicated  <br/> Wenden Sie sich an Ihren Dienstanbieter.  <br/> |Lokal  <br/> |Online  <br/> |Online  <br/> |
|Hybrid (Getrennte Domäne)  <br/> Nicht unterstützt  <br/> |Lokal  <br/> Lokal  <br/> Lokal  <br/> |Lokal  <br/> Online  <br/> Online  <br/> |Online  <br/> Online  <br/> Lokal  <br/> |
   
Releases prior to Lync Server 2013 are partially supported. Versionen vor Lync Server 2013 werden teilweise unterstützt. In diesen Szenarien kann  an -Konferenzen teilnehmen (an denjenigen, die durch Nutzer unter Lync Server 2010 geplant werden), sofern diese Konferenzen „öffentlich“ sind. Das heißt, die Besprechungen dürfen nicht für den eingeschränkten Zugang angepasst sein. 
  
 kann nicht auf einer Lync-Serverversion vor Lync Server 2013 untergebracht werden. Wenn ein  keine Verbindung zu Exchange herstellen kann, um Kalendereinstellungen abzurufen (wenn zum Beispiel kein Exchange-Postfach für das -Konto konfiguriert oder wenn der Zugriff auf Exchange nicht möglich ist), funktionieren zwar Meet Now und Ad-hoc-Besprechungen, aber die Teilnahme an einer geplanten Besprechung funktioniert nicht. 
  
Die folgende Tabelle zeigt, welche Versionen von Exchange Server  unterstützen können: 
  

|**Exchange**|**Lokal**|**Online**|**Hybrid**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Ja (nur einzelne Gesamtstruktur)  <br/> |-  <br/> |-  <br/> |
|Exchange 2013  <br/> |Ja (Mehrfach-Gesamtstruktur-Unterstützung verfügbar für Exchange 2013 CU6 und höhere Versionen)  <br/> |Ja  <br/> |Ja  <br/> |
|Exchange 2016  <br/> |Yes (multi forest support available)  <br/> |Ja  <br/> |Ja  <br/> |
   

