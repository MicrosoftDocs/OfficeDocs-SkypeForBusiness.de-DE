---
title: Planen für den Server für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Business Server 2015 für Persistent Chat Server in Skype planen.'
ms.openlocfilehash: 0380b5ebb43e198160faa3e7f10b1563b4def80f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie Business Server 2015 für Persistent Chat Server in Skype planen.
  
Persistent Chat-Server ist eine optionale Rolle, die mehrere Benutzer in Ihrer Organisation kann an Chatroom-Unterhaltungen, die über einen Zeitraum beibehalten teilnehmen. Obwohl sich die Benutzer während einer Chatsitzung in Echtzeit unterhalten können, bleibt der Inhalt jeder Sitzung – einschließlich Text, Links und Dateien – erhalten, sodass Benutzer alle Inhalte der Sitzung jederzeit aufrufen und durchsuchen können.
  
Persistent Chat-Server kann die Kommunikation innerhalb Ihrer Organisation durch verbessern:
  
- Ausweitung des Informationsbewusstseins und der Beteiligung innerhalb der Organisation
    
- Aktivierung einer effizienten Informationsfreigabe 
    
- Verbessern der Kommunikation zwischen Teams, einschließlich geografisch verteilten und funktionsübergreifenden teams
    
- Verringerung der Informationsüberlastung
    
- Einhaltung rechtlicher Vorschriften durch die optionale Bereitstellung des Kompatibilitätsdienstes für den beständigen Chat
    
## <a name="persistent-chat-server-high-level-architecture"></a>Allgemeine Architektur der permanenten Chatserver

Das folgende Diagramm zeigt eine grundlegende Übersicht über die Architektur von Persistent Chat Server. 
  
![Allgemeine Architektur der permanenten Chatserver](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Der beständige Chat besteht aus einer Front-End-Serverrolle, mit der die Dienste des beständigen Chats bereitgestellt werden, und einer Back-End-SQL-Datenbankkomponente. Die Front-End- und die Back-End-Komponente sind in einem dezidierten Pool für den beständigen Chat enthalten. Jeder Computer, der Persistent Chat Server gehostet wird, benötigen Zugriff auf eine vorhandene Skype für Business Server 2015 Topologie. In diesem Diagramm Sie Skype für Business Server-Pool A für die Weiterleitung von Nachrichten an diese abhängig ist ein Persistent Chat Server Pool (A), vorhanden ist.
  
Sie können eine oder mehrere Persistent Chat Server-Pools, jeweils mit bis zu vier aktiven Persistent Chatserver unterstützt bis zu 80 K gleichzeitige Benutzer bereitstellen.
  
Skype für Business Server 2015 kommuniziert mit dem Persistent Chat-Dienst mithilfe von Session Initiation Protocol (SIP) für die Registrierung und das erweiterbare Chat Kommunikation über SIP-Protokoll (XCCOS) für Chat. 
  
## <a name="persistent-chat-services"></a>Dienste für beständigen Chat

Das folgende Diagramm zeigt die Persistent Chat Server-Front-End-Dienste, und wie diese Dienste mit den Komponenten der Back-End-Datenbank zu kommunizieren. Zu den Front-End-Komponenten gehören die Dienste für den beständigen Chat sowie der Kompatibilitätsdienst. Zu den Back-End-Komponenten gehören der Speicher für beständigen Chat und der Kompatibilitätsspeicher für beständigen Chat.
  
![Allgemeine Dienste der permanenten Chatserver](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Chatdienst

Der auch Channeldienst genannte Chatdienst ist der Kerndienst, der für den Server für beständigen Chat verantwortlich ist. Der Chatdienst stellt folgende Funktionen bereit:
  
- Annahme eingehender Nachrichten
    
- Registrierung und Auflistung der online-Teilnehmer in einem Raum beständigen Chat
    
- Überträgt die Nachrichten an andere Abonnenten des Kanals neu
    
- Implementierung der Logik für Kanalverwaltung, Chatroomeinladungen, Suche und Benachrichtigungen über neue Inhalte
    
Der Persistent Chat-Dienst speichert und greift auf den Chatroom Content und andere Systemmetadaten (Autorisierungsregeln usw.) speichern, indem Sie den beständigen Chat. Der Dienst speichert Dateien, die in Chatrooms in den Dateispeicher für beständigen Chat hochgeladen werden.
  
### <a name="compliance-service"></a>Kompatibilitätsdienst

Wenn es in Ihrer Organisation Vorschriften gibt, nach denen Aktivitäten des beständigen Chats zu archivieren sind, können Sie den optionalen Kompatibilitätsdienst für beständigen Chat bereitstellen. Der Kompatibilitätsdienst steuert die Archivierung von Chatinhalten und -ereignissen wie das Betreten und Verlassen von Räumen im Dateispeicher für beständigen Chat. Die Einhaltung von Bestimmungen wird auf jedem Persistent Chat Server in einem Pool beständigen Chat installiert. 
  
### <a name="web-services"></a>Webdienste

Die Persistent Chat-Webdienste führen Sie auf der Skype für Business Front-End-Server. Die Webdienste hängen von Internetinformationsdiensten (IIS) ab und sind als Webkomponenten implementiert:
  
- Webdienste des beständigen Chats zum Hochladen und Herunterladen von Dateien steuern das Posten und Abrufen von Dateien aus Chatrooms.
    
- Webdienste für den beständigen Chat zur Chatroomverwaltung sind verantwortlich dafür, dass Benutzer ihre Chatrooms verwalten und neue Chatrooms erstellen können.
    
## <a name="defining-requirements-for-your-organization"></a>Festlegen von Anforderungen für Ihre Organisation

Wenn Sie beschließen, Persistent Chat Server bereitstellen, müssen Sie die geschäftlichen Anforderungen Ihrer Organisation bestimmen und dann die Topologie, Infrastruktur und technische Anforderungen zur Unterstützung Ihrer geschäftlichen Anforderungen zu definieren. Zur Optimierung Ihrer Bereitstellung benötigen Sie die folgenden Fragen beantworten:
  
- Führen Sie eine Migration von einer früheren Version von Gruppenchat-Server oder einer früheren Version von Persistent Chat Server, oder Sie Persistent Chat Server zum ersten Mal bereitstellen?
    
- Wer kann den Server für beständigen Chat verwenden? Sie legen Richtlinien für den beständigen Chat fest, um den Benutzerzugriff auf globaler Ebene, Standortebene oder Benutzerebene zu regeln.
    
- Wie viele Benutzer werden Zugriff auf den Server für beständigen Chat benötigen? Der Server für beständigen Chat unterstützt 150.000 bereitgestellte Benutzer (durch die Richtlinie aktiviert) und maximal 80.000 Benutzer gleichzeitig. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen und ein Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer bedienen.
    
- Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Mithilfe von Kategorien können Sie diese Grenzen ziehen und auswählen, welche Benutzer auf die Räume zugreifen können, die in den einzelnen Kategorien erstellt werden.
    
- Wie soll kontrolliert werden, wer Räume erstellen kann? Sie können Ersteller definieren, die Chatrooms erstellen können. Ersteller können für die laufende Verwaltung der Räume andere Mitglieder als Chatroommanager bestimmen.
    
- Wie möchten Sie Räume zu erstellen? Persistent Chat Server bietet eine webbasierte Feature für das Erstellen und Verwalten von Chatrooms. Dies kann von der Skype für Business-Client gestartet werden. Sie können auch eine Lösung Kunden zu definieren, die Ihrer geschäftlichen Anforderungen und Workflows implementiert und Persistent Chat Server stellt Benutzern für Ihre benutzerdefinierte Lösung konfiguriert.
    
- Welche Arten von Add-Ins möchten Sie bereitstellen? Add-Ins erweitern die Möglichkeiten in Räumen, indem sie den Erweiterbarkeitsbereich im Skype for Business-Client nutzen, um relevanten Kontext für den Raum bereitzustellen. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen. 
    
- Welche Vorkehrungen wurden bezüglich der Anforderungen an hohe Verfügbarkeit sowie der Notfallwiederherstellung getroffen? Persistent Chat-Server unterstützt SQL Server-Spiegelung und SQL Server-clustering für hohe Verfügbarkeit. Für die Disaster Recovery unterstützt Persistent Chat Server bis zu 8 Server (4 aktiv und 4 Standby) in einem Pool gestreckte mit SQL Server-Protokollversand. 
    
- Bestehen gesetzliche Vorschriften? Wenn Ihr Unternehmen in einem Land oder Region ist, in denen Daten innerhalb des Landes gehalten werden müssen, müssen Sie mehrere Persistent Chat Server-Pools, jede lokale für eine bestimmte Region bereitstellen. Raum-, Kategorie, oder -add-ins umfassen nicht Pools – es nur einen Persistent Chat Server Pool gehört. 
    
    > [!NOTE]
    > Mit mehreren Persistent Chat Server-Pools ist Ihnen nicht die weitere Skalierung (nur 80.000 gleichzeitige Benutzer können weiterhin über alle Persistent Chat Server-Pools müssen). Der Hauptgrund für die Unterstützung mehrerer Persistent Chat Server-Pools ist zur Unterstützung von behördlicher Bedenken. 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen über das Installieren und Konfigurieren des Servers für beständigen Chat finden Sie in den folgenden Themen:
  
- Ausführliche Informationen zum Bereitstellen von Persistent Chat Server finden Sie unter [Bereitstellen von Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Ausführliche Informationen zum Konfigurieren von Einstellungen für die Persistent Chat Server-Bereitstellung finden Sie unter [Verwalten von Persistent Chat Server in Skype für Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

