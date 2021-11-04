---
title: Plan for Persistent Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 planen.'
ms.openlocfilehash: a697337570dfbf66e752234435d1335661638c54
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763463"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plan for Persistent Chat Server in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 planen.
  
Der Server für beständigen Chat ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroomunterhaltungen teilnehmen können, die im Laufe der Zeit bestehen bleiben. Obwohl Benutzer während einer Chatsitzung in Echtzeit kommunizieren können, ist der Inhalt jeder Sitzung – einschließlich Text, Links und Dateien – beständig, was bedeutet, dass Benutzer alle Inhalte der Sitzung jederzeit anzeigen und durchsuchen können.
  
Der Server für beständigen Chat kann dazu beitragen, die Kommunikation innerhalb Ihrer Organisation durch Folgendes zu verbessern:
  
- Erweitern des Informationsbewusstseins und der Beteiligung in der gesamten Organisation
    
- Aktivieren der effizienten Informationsfreigabe 
    
- Verbesserung der Kommunikation zwischen Teams, einschließlich geografisch verteilter und funktionsübergreifender Teams
    
- Reduzieren der Informationsüberlastung
    
- Befolgen von Compliance-Bestimmungen durch optionale Bereitstellung des Compliancediensts für beständigen Chat

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Allgemeine Architektur des Servers für beständigen Chat

Das folgende Diagramm zeigt eine allgemeine Ansicht der Architektur des Servers für beständigen Chat. 
  
![Architektur des Servers für beständigen Chat High-Level.](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Der beständige Chat besteht aus einer Front-End-Serverrolle, die die Dienste für beständigen Chat sowie eine Back-End-SQL-Datenbankkomponente bereitstellt. Sowohl Front-End- als auch Back-End-Komponenten sind in einem dedizierten Pool für beständigen Chat enthalten. Jeder Computer, der den Server für beständigen Chat hostet, muss Zugriff auf eine vorhandene Skype for Business Server 2015-Topologie haben. In diesem Diagramm gibt es einen Serverpool für beständigen Chat (A), der von Skype for Business Server Pool A für das Weiterleiten von Nachrichten an ihn abhängig ist.
  
Sie können einen oder mehrere Serverpools für beständigen Chat mit jeweils bis zu vier aktiven Servern für beständigen Chat bereitstellen, die bis zu 80.000 gleichzeitige Benutzer unterstützen.
  
Skype for Business Server 2015 kommuniziert mit dem Dienst für beständigen Chat über das Session Initiation Protocol (SIP) für die Registrierung und das Extensible Chat Communication Over SIP-Protokoll (XCCOS) für den Chat. 
  
## <a name="persistent-chat-services"></a>Dienste für beständigen Chat

Das folgende Diagramm zeigt die Front-End-Dienste des Servers für beständigen Chat und wie diese Dienste mit den Back-End-Datenbankkomponenten kommunizieren. Zu den Front-End-Komponenten gehören die Dienste für beständigen Chat und der Compliancedienst. Zu den Back-End-Komponenten gehören der Speicher für beständigen Chat und der Konformitätsspeicher für beständigen Chat.
  
![Server für beständigen Chat High-Level Dienste.](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Chatdienst

Der Chatdienst, auch Kanaldienst genannt, ist der Kerndienst, der für den Server für beständigen Chat verantwortlich ist. Der Chatdienst bietet die folgenden Funktionen:
  
- Annahme eingehender Nachrichten
    
- Registrieren und Auflisten von Onlineteilnehmern innerhalb eines Chatrooms für beständigen Chat
    
- Neuübermittlung von Nachrichten an andere Abonnenten des Kanals
    
- Implementiert Logik für kanalverwaltung, Chatroom-Einladungen, Suche und neue Inhaltsbenachrichtigungen
    
Der Dienst für beständigen Chat speichert und greift mithilfe des Speichers für beständigen Chat auf Chatroominhalte und andere Systemmetadaten (Autorisierungsregeln usw.) zu. Der Dienst speichert Dateien, die in Chatrooms hochgeladen werden, im Dateispeicher für beständigen Chat.
  
### <a name="compliance-service"></a>Dienst für die Einhaltung von Bestimmungen

Wenn Ihre Organisation Vorschriften hat, die die Archivierung von Aktivitäten für beständigen Chat erfordern, können Sie den optionalen Konformitätsdienst für beständigen Chat bereitstellen. Der Compliancedienst ist für die Archivierung von Chatinhalten und -ereignissen, z. B. das Beitreten und Verlassen von Chatrooms, zum Dateispeicher für beständigen Chat verantwortlich. Der Kompatibilitätsdienst wird auf jedem Server für beständigen Chat in einem Pool für beständigen Chat installiert. 
  
### <a name="web-services"></a>Webdienste

Die Webdienste für beständigen Chat werden auf den Skype for Business Front-End-Servern ausgeführt. Die Webdienste sind von Internetinformationsdienste (IIS) abhängig und werden als Webkomponenten implementiert:
  
- Webdienste für beständigen Chat für das Hochladen und Herunterladen von Dateien sind für das Veröffentlichen und Abrufen von Dateien aus Chatrooms verantwortlich.
    
- Webdienste für beständigen Chat für die Chatroomverwaltung sind dafür verantwortlich, Benutzern die Möglichkeit zu bieten, ihre Chatrooms zu verwalten und neue Chatrooms zu erstellen.
    
## <a name="defining-requirements-for-your-organization"></a>Definieren der Anforderungen für Ihre Organisation

Wenn Sie sich für die Bereitstellung des Servers für beständigen Chat entscheiden, müssen Sie die Geschäftlichen Anforderungen Ihrer Organisation ermitteln und dann die Topologie, Infrastruktur und technischen Anforderungen definieren, um Ihre Geschäftlichen Anforderungen zu unterstützen. Um Ihre Bereitstellung zu optimieren, müssen Sie die folgenden Fragen beantworten:
  
- Migrieren Sie von einer früheren Version des Gruppenchatservers oder einer früheren Version des Servers für beständigen Chat oder stellen Sie den Server für beständigen Chat zum ersten Mal bereit?
    
- Wer können den Server für beständigen Chat verwenden? Sie geben Richtlinien für beständigen Chat an, um den Benutzerzugriff auf globaler, Standort- oder Benutzerebene zu bestimmen.
    
- Wie viele Benutzer benötigen Zugriff auf den Server für beständigen Chat? Der Server für beständigen Chat unterstützt 150.000 bereitgestellte Benutzer (aktiviert durch die Richtlinie) und maximal 80.000 gleichzeitige Benutzer. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen, und ein einzelner Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer haben.
    
- Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Sie können Kategorien definieren, um diese Grenzen zu trennen, und auswählen, wer sich in Räumen befinden darf, die in jeder dieser Kategorien erstellt werden.
    
- Wie möchten Sie steuern, wer Räume erstellen kann? Sie können Ersteller definieren, die Räume erstellen können. Ersteller können andere Mitglieder als Chatroommanager für die laufende Verwaltung der Chatrooms zuweisen.
    
- Wie möchten Sie Räume erstellen? Der Server für beständigen Chat bietet ein webbasiertes Feature zum Erstellen und Verwalten von Chatrooms. Dies kann über den Skype for Business-Client gestartet werden. Sie können eine Kundenlösung definieren, die Ihre Geschäftlichen Anforderungen und Workflows implementiert, und den Server für beständigen Chat so konfigurieren, dass Benutzer zu Ihrer benutzerdefinierten Lösung gelangen.
    
- Welche Arten von Add-Ins möchten Sie bereitstellen? Add-Ins verbessern die Raumerfahrung, indem sie den Erweiterungsbereich im Skype for Business-Client nutzen, um Kontext bereitzustellen, der für den Raum relevant ist. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen. 
    
- Welche Vorkehrungen wurden bezüglich der Anforderungen an die Hochverfügbarkeit sowie der Notfallwiederherstellung getroffen? Der Server für beständigen Chat unterstützt SQL Server Spiegelung und SQL Server Clustering für hohe Verfügbarkeit. Für die Notfallwiederherstellung unterstützt der Server für beständigen Chat bis zu 8 Server (4 aktive und 4 Standby-Server) in einem gestreckten Pool mit SQL Server Protokollversand. 
    
- Gibt es gesetzliche Anforderungen? Wenn sich Ihr Unternehmen in einem Land oder einer Region befindet, in dem Daten innerhalb des Landes gespeichert werden müssen, müssen Sie möglicherweise mehrere Serverpools für beständigen Chat bereitstellen, die jeweils in einer bestimmten Region gespeichert sind. Ein Raum, eine Kategorie oder ein Add-In umfasst keine Pools– es gehört nur zu einem Serverpool für beständigen Chat. 
    
    > [!NOTE]
    > Mit mehreren Pools für den Server für beständigen Chat erhalten Sie nicht mehr Skalierung (Sie können immer noch nur 80.000 gleichzeitige Benutzer in allen Pools des Servers für beständigen Chat haben). Der Hauptgrund für die Unterstützung mehrerer Serverpools für beständigen Chat ist die Unterstützung behördlicher Bedenken. 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zum Installieren und Konfigurieren des Servers für beständigen Chat finden Sie in den folgenden Themen:
  
- Ausführliche Informationen zum Bereitstellen des Servers für beständigen Chat finden Sie unter [Deploy Persistent Chat Server in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md) 
    
- Ausführliche Informationen zum Konfigurieren von Einstellungen für die Bereitstellung des Servers für beständigen Chat finden Sie unter Verwalten des [Servers für beständigen Chat in Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md)
    

