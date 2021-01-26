---
title: Planen des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 planen.'
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813665"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planen des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 planen.
  
Der Server für beständigen Chat ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroomunterhaltungen teilnehmen können, die im Laufe der Zeit bestehen bleiben. Obwohl Benutzer während einer Chatsitzung in Echtzeit kommunizieren können, ist der Inhalt jeder Sitzung – einschließlich Text, Links und Dateien – beständig, was bedeutet, dass Benutzer den inhalt der Sitzung jederzeit anzeigen und durchsuchen können.
  
Der Server für beständigen Chat kann die Kommunikation innerhalb Ihrer Organisation verbessern, indem er:
  
- Erweitern des Informationsbewusstseins und der Beteiligung in der gesamten Organisation
    
- Aktivieren einer effizienten Informationsfreigabe 
    
- Verbesserung der Kommunikation zwischen Teams, einschließlich geografisch verteilter und funktionsübergreifender Teams
    
- Reduzieren der Informationsüberlastung
    
- Einhaltung von Vorschriften durch optionale Bereitstellung des Kompatibilitätsdiensts für beständigen Chat

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architektur des Servers für beständigen Chat

Das folgende Diagramm zeigt eine Oberansicht der Architektur des Servers für beständigen Chat. 
  
![Allgemeine Architektur der permanenten Chatserver](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Der beständigen Chat besteht aus einer Front-End-Serverrolle, die die Dienste für beständigen Chat sowie eine Back-End-SQL bietet. Sowohl Front-End- als auch Back-End-Komponenten sind in einem dedizierten Pool für beständigen Chat enthalten. Jeder Computer, der den Server für beständigen Chat hostet, muss Zugriff auf eine vorhandene Skype for Business Server 2015-Topologie haben. In diesem Diagramm ist ein Pool für den Server für beständigen Chat (A) vorhanden, der vom Skype for Business Server Pool A zum Weiterleiten von Nachrichten an diesen Pool abhängig ist.
  
Sie können einen oder mehrere Pools für den Server für beständigen Chat mit jeweils bis zu vier aktiven Servern für beständigen Chat bereitstellen, die bis zu 80.000 gleichzeitige Benutzer unterstützen.
  
Skype for Business Server 2015 kommuniziert mit dem Dienst für beständigen Chat mit dem Session Initiation Protocol (SIP) für die Registrierung und dem Extensible Chat Communication Over SIP Protocol (XCCOS) für Chats. 
  
## <a name="persistent-chat-services"></a>Dienste für beständigen Chat

Das folgende Diagramm zeigt die Front-End-Dienste des Servers für beständigen Chat und die Kommunikation dieser Dienste mit den Back-End-Datenbankkomponenten. Zu den Front-End-Komponenten gehören die Dienste für beständigen Chat und der Kompatibilitätsdienst. Zu den Back-End-Komponenten gehören der Speicher für beständigen Chat und der Konformitätsspeicher für beständigen Chat.
  
![Allgemeine Dienste der permanenten Chatserver](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Chatdienst

Der Dienst für beständigen Chat, der auch Kanaldienst genannt wird, ist der Hauptdienst für den Server für beständigen Chat. Der Chatdienst stellt die folgenden Funktionen zur Verfügung:
  
- Annahme eingehender Nachrichten
    
- Registrieren und Auflisten von Onlineteilnehmern in einem Chatroom für beständigen Chat
    
- Neuübermittlung von Nachrichten an andere Abonnenten des Kanals
    
- Implementiert Logik für Kanalverwaltung, Chatroomeinladungen, Suche und neue Inhaltsbenachrichtigungen
    
Der Dienst für beständigen Chat speichert Chatroominhalte und andere Systemmetadaten (Autorisierungsregeln und so weiter) mithilfe des Speichers für beständigen Chat und stürzt auf diese zu. Der Dienst speichert Dateien, die in Chatrooms hochgeladen werden, im Dateispeicher für beständigen Chat.
  
### <a name="compliance-service"></a>Dienst für die Einhaltung von Bestimmungen

Wenn es in Ihrer Organisation Vorschriften gibt, die die Archivierung von Aktivitäten für beständigen Chat erfordern, können Sie den optionalen Kompatibilitätsdienst für beständigen Chat bereitstellen. Der Kompatibilitätsdienst ist für die Archivierung von Chatinhalten und -ereignissen, z. B. das Beitreten und Verlassen von Chatrooms, im Dateispeicher für die Kompatibilität des beständigen Chats verantwortlich. Der Kompatibilitätsdienst wird auf jedem Server für beständigen Chat in einem Pool für beständigen Chat installiert. 
  
### <a name="web-services"></a>Webdienste

Die Webdienste für beständigen Chat werden auf den Skype for Business-Front-End-Servern ausgeführt. Die Webdienste sind von Internetinformationsdienste (Internet Information Services, IIS) abhängig und werden als Webkomponenten implementiert:
  
- Webdienste für beständigen Chat für das Hochladen und Herunterladen von Dateien sind für das Veröffentlichen und Abrufen von Dateien aus Chatrooms verantwortlich.
    
- Webdienste für beständigen Chat für die Verwaltung von Chatrooms sind dafür verantwortlich, Benutzern die Möglichkeit zu bieten, ihre Chatrooms zu verwalten und neue Chatrooms zu erstellen.
    
## <a name="defining-requirements-for-your-organization"></a>Definieren von Anforderungen für Ihre Organisation

Wenn Sie sich für die Bereitstellung des Servers für beständigen Chat entscheiden, müssen Sie die Geschäftlichen Anforderungen Ihrer Organisation bestimmen und dann die Topologie, die Infrastruktur und die technischen Anforderungen zur Unterstützung Ihrer Geschäftsanforderungen definieren. Um Ihre Bereitstellung zu optimieren, müssen Sie die folgenden Fragen beantworten:
  
- Migrieren Sie von einer früheren Version des Gruppenchatservers oder einer früheren Version des Servers für beständigen Chat, oder stellen Sie den Server für beständigen Chat zum ersten Mal zur Bereitstellung vor?
    
- Wer kann den Server für beständigen Chat verwenden? Sie geben Richtlinien für beständigen Chat an, um den Benutzerzugriff auf globaler, Standort- oder Benutzerebene zu bestimmen.
    
- Wie viele Benutzer benötigen Zugriff auf den Server für beständigen Chat? Der Server für beständigen Chat unterstützt 150.000 bereitgestellte Benutzer (durch Richtlinien aktiviert) und maximal 80.000 gleichzeitige Benutzer. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen, und ein einzelner Serverpool für beständigen Chat kann bis zu vier aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer haben.
    
- Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Sie können Kategorien definieren, um diese Grenzen zu trennen, und auswählen, wer in Räumen sein darf, die in jeder dieser Kategorien erstellt werden.
    
- Wie soll kontrolliert werden, wer Räume erstellen kann? Sie können Ersteller definieren, die Räume erstellen können. Ersteller können andere Mitglieder als Chatroommanager für die fortlaufende Verwaltung der Räume zuweisen.
    
- Wie möchten Sie Räume erstellen? Der Server für beständigen Chat bietet ein webbasiertes Feature zum Erstellen und Verwalten von Chatrooms. Dies kann über den Skype for Business-Client gestartet werden. Sie können eine Kundenlösung definieren, die Ihre Geschäftlichen Anforderungen und Workflows implementiert und den Server für beständigen Chat so konfiguriert, dass Benutzer zu Ihrer benutzerdefinierten Lösung umge leitet werden.
    
- Welche Arten von Add-Ins möchten Sie bereitstellen? Add-Ins verbessern die Raumerfahrung, indem sie den Erweiterbarkeitsbereich im Skype for Business-Client nutzen, um kontextrelevante Kontexte für den Raum zu bieten. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen. 
    
- Welche Vorkehrungen wurden bezüglich der Anforderungen an die Hochverfügbarkeit sowie der Notfallwiederherstellung getroffen? Der Server für beständigen Chat unterstützt SQL Server spiegelung und SQL Server für hohe Verfügbarkeit. Für die Notfallwiederherstellung unterstützt der Server für beständigen Chat bis zu 8 Server (4 aktive und 4 Standbyserver) in einem gestreckten Pool mit SQL Server Protokollversand. 
    
- Gibt es gesetzliche Anforderungen? Wenn sich Ihr Unternehmen in einem Land oder einer Region befindet, in dem Daten innerhalb des Landes gespeichert werden müssen, müssen Sie möglicherweise mehrere Pools für den Server für beständigen Chat bereitstellen, die jeweils lokal in einer bestimmten Region gespeichert werden. Ein Raum, eine Kategorie oder ein Add-in erstreckt sich nicht über Pools – es gehört nur zu einem Pool für den Server für beständigen Chat. 
    
    > [!NOTE]
    > Mehrere Pools für den Server für beständigen Chat bieten nicht mehr Skalierung (sie können weiterhin nur 80.000 gleichzeitige Benutzer in allen Pools des Servers für beständigen Chat verwenden). Der Hauptgrund für die Unterstützung mehrerer Pools für den Server für beständigen Chat ist die Unterstützung gesetzlicher Bedenken. 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zum Installieren und Konfigurieren des Servers für beständigen Chat finden Sie in den folgenden Themen:
  
- Weitere Informationen zum Bereitstellen des Servers für beständigen Chat finden Sie unter [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Weitere Informationen zum Konfigurieren von Einstellungen für die Bereitstellung des Servers für beständigen Chat finden Sie unter ["Manage Persistent Chat Server in Skype for Business Server 2015 "Manage Persistent Chat Server"](../../manage/persistent-chat/persistent-chat.md)(Verwalten des Servers für beständigen Chat in Skype for Business Server 2015).
    

