---
title: Planen für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 den Server für beständigen Chat planen.'
ms.openlocfilehash: 3e485f938d2bd48dad5f1b9f0baa96d7f3f537d0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418280"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 planen.
  
Der beständige Chat Server ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroom-Unterhaltungen teilnehmen können, die im Laufe der Zeit fortbestehen. Obwohl sich die Benutzer während einer Chatsitzung in Echtzeit unterhalten können, bleibt der Inhalt jeder Sitzung – einschließlich Text, Links und Dateien – erhalten, sodass Benutzer alle Inhalte der Sitzung jederzeit aufrufen und durchsuchen können.
  
Der Server für beständigen Chat kann Ihnen helfen, die Kommunikation innerhalb Ihrer Organisation zu verbessern:
  
- Ausweitung des Informationsbewusstseins und der Beteiligung innerhalb der Organisation
    
- Aktivierung einer effizienten Informationsfreigabe 
    
- Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams
    
- Verringerung der Informationsüberlastung
    
- Einhaltung rechtlicher Vorschriften durch die optionale Bereitstellung des Kompatibilitätsdienstes für den beständigen Chat

> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Allgemeine Architektur der permanenten Chatserver

Das folgende Diagramm zeigt eine allgemeine Übersicht über die Server Architektur des beständigen Chats. 
  
![Allgemeine Architektur der permanenten Chatserver](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Der beständige Chat besteht aus einer Front-End-Serverrolle, mit der die Dienste des beständigen Chats bereitgestellt werden, und einer Back-End-SQL-Datenbankkomponente. Die Front-End- und die Back-End-Komponente sind in einem dezidierten Pool für den beständigen Chat enthalten. Jeder Computer, auf dem ein beständiger Chat Server gehostet wird, muss auf eine vorhandene Skype for Business Server 2015-Topologie zugreifen können. In diesem Diagramm gibt es einen Serverpool für beständigen Chat (a), der von Skype for Business Serverpool a für das Weiterleiten von Nachrichten abhängig ist.
  
Sie können einen oder mehrere beständige Chat Server Pools mit bis zu vier aktiven beständigen Chatservern bereitstellen, die bis zu 80K gleichzeitige Benutzer unterstützen.
  
Skype for Business Server 2015 kommuniziert mit dem beständigen Chat Dienst unter Verwendung des Session Initiation Protocol (SIP) für die Registrierung und der erweiterbaren Chat-Kommunikation über SIP-Protokoll (XCCOS) für Chats. 
  
## <a name="persistent-chat-services"></a>Dienste für beständigen Chat

Das folgende Diagramm zeigt die Front-End-Dienste des beständigen Chat Servers und wie diese Dienste mit den Komponenten der Back-End-Datenbank kommunizieren. Zu den Front-End-Komponenten gehören die Dienste für den beständigen Chat sowie der Kompatibilitätsdienst. Zu den Back-End-Komponenten gehören der Speicher für beständigen Chat und der Kompatibilitätsspeicher für beständigen Chat.
  
![Allgemeine Dienste der permanenten Chatserver](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Chatdienst

Der auch Channeldienst genannte Chatdienst ist der Kerndienst, der für den Server für beständigen Chat verantwortlich ist. Der Chatdienst stellt folgende Funktionen bereit:
  
- Annahme eingehender Nachrichten
    
- Registrierung und Auflistung der Online-Teilnehmer in einem Chatroom für beständigen Chat
    
- Neuübermittlung von Nachrichten an andere Abonnenten des Kanals
    
- Implementierung der Logik für Kanalverwaltung, Chatroomeinladungen, Suche und Benachrichtigungen über neue Inhalte
    
Der beständige Chatdienst speichert und greift auf Chatroom-Inhalte und andere Systemmetadaten (Autorisierungsregeln usw.) mithilfe des beständigen Chat Speichers zu. Der Dienst speichert Dateien, die in Chatrooms im persistenten Chat-Dateispeicher hochgeladen werden.
  
### <a name="compliance-service"></a>Kompatibilitätsdienst

Wenn es in Ihrer Organisation Vorschriften gibt, nach denen Aktivitäten des beständigen Chats zu archivieren sind, können Sie den optionalen Kompatibilitätsdienst für beständigen Chat bereitstellen. Der Kompatibilitätsdienst steuert die Archivierung von Chatinhalten und -ereignissen wie das Betreten und Verlassen von Räumen im Dateispeicher für beständigen Chat. Der Kompatibilitätsdienst wird auf jedem beständigen Chat Server in einem beständigen Chat-Pool installiert. 
  
### <a name="web-services"></a>Webdienste

Die beständigen Chat-Webdienste werden auf den Skype for Business-Front-End-Servern ausgeführt. Die Webdienste hängen von Internetinformationsdiensten (IIS) ab und sind als Webkomponenten implementiert:
  
- Webdienste des beständigen Chats zum Hochladen und Herunterladen von Dateien steuern das Posten und Abrufen von Dateien aus Chatrooms.
    
- Webdienste für den beständigen Chat zur Chatroomverwaltung sind verantwortlich dafür, dass Benutzer ihre Chatrooms verwalten und neue Chatrooms erstellen können.
    
## <a name="defining-requirements-for-your-organization"></a>Festlegen von Anforderungen für Ihre Organisation

Wenn Sie sich entscheiden, den Server für beständigen Chat bereitzustellen, müssen Sie die geschäftlichen Anforderungen Ihrer Organisation ermitteln und dann die Topologie, Infrastruktur und technischen Anforderungen definieren, um Ihre geschäftlichen Anforderungen zu unterstützen. Zur Optimierung Ihrer Bereitstellung müssen Sie die folgenden Fragen beantworten:
  
- Migrieren Sie von einer früheren Version des Gruppen-Chat Servers oder einer früheren Version des beständigen Chat Servers, oder stellen Sie zum ersten Mal einen beständigen Chat Server bereit?
    
- Wer kann den Server für beständigen Chat verwenden? Sie legen Richtlinien für den beständigen Chat fest, um den Benutzerzugriff auf globaler Ebene, Standortebene oder Benutzerebene zu regeln.
    
- Wie viele Benutzer werden Zugriff auf den Server für beständigen Chat benötigen? Der Server für beständigen Chat unterstützt 150.000 bereitgestellte Benutzer (durch die Richtlinie aktiviert) und maximal 80.000 Benutzer gleichzeitig. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen und ein Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer bedienen.
    
- Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Mithilfe von Kategorien können Sie diese Grenzen ziehen und auswählen, welche Benutzer auf die Räume zugreifen können, die in den einzelnen Kategorien erstellt werden.
    
- Wie soll kontrolliert werden, wer Räume erstellen kann? Sie können Ersteller definieren, die Chatrooms erstellen können. Ersteller können für die laufende Verwaltung der Räume andere Mitglieder als Chatroommanager bestimmen.
    
- Wie möchten Sie Räume erstellen? Der Server für beständigen Chat bietet ein webbasiertes Feature zum Erstellen und Verwalten von Räumen. Dies kann über den Skype for Business-Client gestartet werden. Sie können eine Kundenlösung definieren, die Ihre geschäftlichen Anforderungen und Workflows implementiert, und den beständigen Chat Server so konfigurieren, dass Benutzer auf Ihre benutzerdefinierte Lösung verweisen.
    
- Welche Arten von Add-Ins möchten Sie bereitstellen? Add-Ins erweitern die Möglichkeiten in Räumen, indem sie den Erweiterbarkeitsbereich im Skype for Business-Client nutzen, um relevanten Kontext für den Raum bereitzustellen. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen. 
    
- Welche Vorkehrungen wurden bezüglich der Anforderungen an hohe Verfügbarkeit sowie der Notfallwiederherstellung getroffen? Der beständige Chat Server unterstützt die SQL Server-Spiegelung und SQL Server-Clustering für eine höhere Verfügbarkeit. Bei der Disaster Recovery unterstützt der beständige Chat Server bis zu 8 Server (4 Active und 4 Standby) in einem gedehnten Pool mit SQL Server-Protokollversand. 
    
- Bestehen gesetzliche Vorschriften? Wenn sich Ihr Unternehmen in einem Land oder einer Region befindet, in dem Daten im Land aufbewahrt werden müssen, müssen Sie möglicherweise mehrere beständige Chat Server Pools bereitstellen, die jeweils lokal in einer bestimmten geografischen Umgebung gespeichert sind. In einem Raum, einer Kategorie oder einem Add-in sind keine Pools zu finden--es gehört nur einem beständigen Chat Server Pool. 
    
    > [!NOTE]
    > Wenn Sie über mehrere Server Pools für beständigen Chat verfügen, können Sie nicht mehr skalieren (Sie können immer noch nur 80.000 gleichzeitige Benutzer in allen beständigen Chat-Server Pools haben). Der Hauptgrund für die Unterstützung mehrerer beständiger Chat Server Pools ist die Unterstützung behördlicher Bedenken. 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen über das Installieren und Konfigurieren des Servers für beständigen Chat finden Sie in den folgenden Themen:
  
- Ausführliche Informationen zum Bereitstellen von beständigen Chatservern finden Sie unter [Bereitstellen eines beständigen Chat Servers in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Informationen zum Konfigurieren von Einstellungen für die Bereitstellung von beständigen Chatservern finden Sie unter [Verwalten des beständigen Chat Servers in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

