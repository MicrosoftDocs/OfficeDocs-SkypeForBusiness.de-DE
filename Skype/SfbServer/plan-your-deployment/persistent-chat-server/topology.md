---
title: Topologieplanung für den Server für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu beständigen Chat Server Komponenten und-Topologien in Skype for Business Server 2015 zu erhalten.'
ms.openlocfilehash: c31cb8b0ada280b52d902e975f1bacf947fd19e7
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418273"
---
# <a name="plan-persistent-chat-server-topology"></a>Topologieplanung für den Server für beständigen Chat
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zu beständigen Chat Server Komponenten und-Topologien in Skype for Business Server 2015 zu erhalten.
  
Der beständige Chat Server unterstützt Konfigurationen mit einem oder mehreren Servern. Sie können den Server für beständigen Chat entweder auf einem Skype for Business Server 2015 Enterprise Edition-oder Standard Edition-Server installieren. 

> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
  
## <a name="persistent-chat-server-components"></a>Server Komponenten für beständigen Chat

Der permanente Chatserver besteht aus folgenden Komponenten:
  
- Auf einem oder mehreren Computern, auf denen der beständige Chat Server ausgeführt wird und die folgenden Dienste bereitstellen:
    
  - Beständiger Chat Dienst
    
  - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    
- Einen oder mehrere Server (mehr als eine, wenn Spiegelung verwendet wird), die die SQL Server-Back-End-Datenbank zum Hosten der Inhaltsdatenbank für beständigen Chat ausführt, in der Chatroom-Inhalte,-Räume und-Kategorien gespeichert sind.
    
    > [!NOTE]
    > Die Back-End-Datenbank speichert Chatverlaufs Daten, einschließlich Informationen zu Kategorien und beständigen Chatrooms, die erstellt werden. 
  
- Wenn Compliance aktiviert ist, wird ein oder mehrere Server (mehr als eine bei Verwendung der Spiegelung) ausgeführt, wobei die SQL Server-Back-End-Datenbank zum Hosten der beständigen Chat-Kompatibilitätsdatenbank ausgeführt wird, in der Compliance-Ereignisse und Chat Inhalte zum Zwecke der Compliance gespeichert werden.
    
Details zu den Hardware-und Softwareanforderungen für den Server für beständigen Chat finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Server-Topologien für beständigen Chat

Sie können den Server für beständigen Chat in Pools mit einem oder mehreren Servern und mit einer Topologie mit einem Pool oder mehreren Pools bereitstellen. Der beständige Chat Server unterstützt die folgenden Topologien:
  
-  Standard Edition-Server mit auf dem Front-End-Server bereitgestelltem Server für beständigen Chat
    
-  Standard Edition-Server mit beständigem Chat Server auf einem separaten Server
    
-  Enterprise Edition-Server mit einem einzelnen beständigen Chat Server auf einem separaten Server
    
-  Enterprise Edition-Server mit mehr als einem beständigen Chat Server auf separaten Servern
    
Zwar können Sie den Server für beständigen Chat auf einem Standard Edition-Server bereitstellen, doch beachten Sie, dass Leistung und Skalierung davon betroffen sind und eine Hochverfügbarkeit nicht möglich ist. Daher empfiehlt es sich, den beständigen Chat auf einem Standard Edition-Server in erster Linie zum Nachweis von Konzept-und Evaluierungszwecken bereitzustellen. 
  
Skype for Business Server 2015 unterstützt eine Vielzahl von Szenarien für die Zusammenstellung, die Ihnen die Flexibilität bieten, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie über eine kleine Organisation verfügen) oder einzelne Komponenten auf unterschiedlichen Servern ausführen ( Wenn Sie über eine größere Organisation verfügen, die Skalierbarkeit und Leistung benötigt). Sie sollten Skalierbarkeits Faktoren berücksichtigen, bevor Sie entscheiden, ob Sie Komponenten collocate. Für Skype for Business Server 2015 Enterprise Edition-und Standard Edition-Server unterscheiden sich die Szenarien für die Zusammenfassung. 
  
In den folgenden Abschnitten werden die Topologien im Detail beschrieben und Kollokationsszenarien sowie Optionen für die Back-End-Datenbankserver erläutert. Ausführliche Informationen zur Anordnung aller Serverrollen und Datenbanken finden Sie unter [Topologie-Grundlagen für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition-Server mit auf dem Front-End-Server bereitgestelltem Server für beständigen Chat

Mit der Standard Edition können Sie den beständigen Chat auf dem Front-End-Server collocate. Dies ist die einfachste und grundlegendste Konfiguration. Sie müssen sicherstellen, dass der vorhandene Front-End-Server über genügend Kapazität in Bezug auf physische Ressourcen verfügt: CPU, Arbeitsspeicher, Festplattenspeicher usw.
  
Darüber hinaus können Sie den collocate-Back-End-Server und die beständige Chat-Kompatibilitätsdatenbank (sofern aktiviert) auf dem lokalen SQL Server Express-Back-End-Server ablegen. Sie können auch einen separaten Server mit SQL Server mit einer dedizierten Instanz verwenden. 
  
> [!IMPORTANT]
> Sie können einem beständigen Chat Serverpool keine weiteren Server hinzufügen, wenn der erste beständige Chat Server mit einem Standard Edition-Front-End-Server ausgestattet ist. Es wird empfohlen, dass Sie den ersten Server als eigenständige Instanz installieren, damit Sie bei Bedarf später weitere Server hinzufügen können. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition-Server mit auf einem separaten Server installiertem Server für beständigen Chat

Bei der Standard Edition können Sie Server für beständigen Chat als eine eigenständige Instanz installieren und später bei Bedarf weitere Server hinzufügen.   
  
Sie können den collocate-Back-End-Server des beständigen Chat Servers und die Datenbank für beständigen Chat (sofern aktiviert) auf dem lokalen SQL Server Express-Back-End-Server übernehmen. Sie können auch einen separaten Server mit SQL Server mit einer dedizierten Instanz verwenden. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition-Server mit einem einzelnen Server für beständigen Chat

Mit Enterprise Edition müssen Sie den Server für beständigen Chat auf einem separaten Computer installieren. Das heißt, Sie können den Server für beständigen Chat nicht auf dem Enterprise Edition-Front-End-Server ausführen. Diese Bereitstellung erfordert einen separaten Server, auf dem der beständige Chat Server ausgeführt wird, und der Kompatibilitätsdienst (sofern aktiviert).
  
Sie können jedoch die SQL Server-Datenbank für beständigen Chat Server in der Back-End-Datenbank eines Enterprise Edition-Front-End-Pools collocate.
  
> [!NOTE]
> Wenn Sie SQL AlwaysOn-Verfügbarkeitsgruppen für hohe Verfügbarkeit und Notfallwiederherstellung verwenden möchten, beachten Sie, dass dies für Datenbanken des Servers für beständigen Chat nicht unterstützt wird. 
  
Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank collocate, können Sie entweder eine einzelne Instanz von SQL Server für eine oder alle Datenbanken verwenden, oder Sie können für jede Datenbank eine separate Instanz von SQL Server verwenden.
  
> [!IMPORTANT]
> Der Server, auf dem die persistente Chat-Datenbank gehostet wird, kann andere Datenbanken hosten. Wenn Sie jedoch die persistente Chat-Datenbank mit anderen Datenbanken abstimmen, sollten Sie beachten, dass der von der persistenten Chat Datenbank benötigte Speicherplatz sehr groß werden kann, wenn Sie die Nachrichten von mehr als wenigen Benutzern speichern. Aus diesem Grund empfehlen wir, die Datenbank für persistente Chats nicht mit der Back-End-Datenbank abstimmen. 
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie für einen einzelnen beständigen Chat Server mit aktivierter Kompatibilität (optional).
  
**Topologie mit einem einzelnen Server**

![Server für beständigen Chat - Topologie mit einem einzelnen Server](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition-Server mit mehreren Servern für beständigen Chat

Mit Enterprise Edition können Sie eine Topologie mit mehreren Servern bereitstellen, um mehr Kapazität und Zuverlässigkeit zu erreichen. Eine Topologie mit mehreren Servern entspricht der Topologie mit einem Server, mit der Ausnahme, dass mehrere Server den persistenten Chat Server hosten und höher skalieren können. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer umfassen, auf denen der beständige Chat Server ausgeführt wird (für hoch Verfügbarkeits-und Disaster Recovery-Konfigurationen sind bis zu acht möglich, aber nur vier können aktiv sein und die restlichen vier im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem beständigen Chat Serverpool mit 4 Servern verbunden sind. Mehrere Computer, auf denen der beständige Chat Server ausgeführt wird, sollten sich in derselben Active Directory-Domänendienst Domäne wie Skype for Business Server und dem Kompatibilitätsdienst befinden.
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der beständige Chat Server, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt werden.
  
**Topologie mit mehreren Servern**

![Server für beständigen Chat – Topologie mit mehreren Servern](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool kommunizieren die beständigen Chat Dienste und geben Daten frei. So kann beispielsweise der Chatverlauf, der ursprünglich in einem beständigen Chatdienst gepostet wurde, von jedem beständigen Chatdienst im System zur Verfügung gestellt werden. Auf eine Datei, die über einen beständigen Chatdienst hochgeladen wird, kann von jedem beständigen Chatdienst zugegriffen werden. Benutzer können mit unterschiedlichen Front-End-Servern für beständigen Chat Server verbunden werden und können miteinander kommunizieren. Der Standardport von TCP 8011 verbindet einen Server mit einem Serverpool und wird von den beständigen Chat Diensten für die Kommunikation zwischen sich selbst oder für administrative Zwecke verwendet.
  
In einer persistent Chat Server-Bereitstellung mit vier Servern, bei der 80.000-Benutzer gleichzeitig beim beständigen Chat angemeldet werden können, wird die Auslastung gleichmäßig bei 20.000-Benutzern pro Server verteilt. Wenn ein Server nicht mehr zur Verfügung steht, verlieren die Benutzer, die mit diesem Server verbunden sind, den Zugriff auf den beständigen Chat Server. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server wieder verfügbar ist. 
  

