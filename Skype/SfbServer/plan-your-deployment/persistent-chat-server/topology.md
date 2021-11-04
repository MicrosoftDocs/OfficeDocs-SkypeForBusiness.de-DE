---
title: Planen der Topologie des Servers für beständigen Chat
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über Komponenten und Topologien des Servers für beständigen Chat in Skype for Business Server 2015 zu erfahren.'
ms.openlocfilehash: f50059617ca777b283a62eb8a487b59c3742327a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749934"
---
# <a name="plan-persistent-chat-server-topology"></a>Planen der Topologie des Servers für beständigen Chat
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über Komponenten und Topologien des Servers für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat unterstützt Konfigurationen mit einem server und mehreren Servern. Sie können den Server für beständigen Chat entweder auf einem Skype for Business Server 2015-Enterprise Edition oder Standard Edition-Server installieren. 

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="persistent-chat-server-components"></a>Komponenten des Servers für beständigen Chat

Der Server für beständigen Chat besteht aus den folgenden Komponenten:
  
- Mindestens ein Computer, auf dem der Server für beständigen Chat ausgeführt wird und der die folgenden Dienste bereitstellt:
    
  - Dienst für beständigen Chat
    
  - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    
- Ein oder mehrere Server (mehrere, wenn die Spiegelung verwendet wird), auf denen die SQL Server Back-End-Datenbank zum Hosten der Inhaltsdatenbank für beständigen Chat ausgeführt wird, auf dem Chatroominhalte, Chatrooms und Kategorien gespeichert sind.
    
    > [!NOTE]
    > In der Back-End-Datenbank werden Chatverlaufsdaten gespeichert, einschließlich Informationen zu Kategorien und erstellten Chatrooms für beständige Chatrooms. 
  
- Wenn die Kompatibilität aktiviert ist, führt ein oder mehrere Server (mehrere, wenn spiegelung verwendet wird) die SQL Server Back-End-Datenbank zum Hosten der Konformitätsdatenbank für beständigen Chat aus, auf dem Complianceereignisse und Chatinhalte zum Zweck der Compliance gespeichert werden.
    
Ausführliche Informationen zu den Hardware- und Softwareanforderungen für den Server für beständigen Chat finden Sie unter [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.](hardware-and-software-requirements.md) 
  
## <a name="persistent-chat-server-topologies"></a>Topologien für den Server für beständigen Chat

Sie können den Server für beständigen Chat in Einem- oder Mehrere-Server-Pools und mit einer Topologie mit einem Pool oder mehreren Pools bereitstellen. Der Server für beständigen Chat unterstützt die folgenden Topologien:
  
-  Standard Edition Server mit Server für beständigen Chat, der auf dem Front-End-Server verbunden ist
    
-  Standard Edition Server mit Server für beständigen Chat auf einem separaten Server
    
-  Enterprise Edition Server mit einem einzelnen Server für beständigen Chat auf einem separaten Server
    
-  Enterprise Edition Server mit mehr als einem Server für beständigen Chat auf separaten Servern
    
Obwohl Sie den Server für beständigen Chat auf einem Standard Edition Server bereitstellen können, beachten Sie, dass Leistung und Skalierung beeinträchtigt werden und hohe Verfügbarkeit keine Option ist. Daher wird empfohlen, den beständigen Chat auf einem Standard Edition-Server in erster Linie zu Machbarkeitsstudien und Evaluierungszwecken bereitzustellen. 
  
Skype for Business Server 2015 unterstützt eine Vielzahl von Kollokationsszenarien und bietet Ihnen die Flexibilität, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie eine kleine Organisation haben) oder einzelne Komponenten auf verschiedenen Servern ausführen (wenn Sie über eine größere Organisation verfügen, die Skalierbarkeit und Leistung benötigt). Sie sollten Skalierbarkeitsfaktoren berücksichtigen, bevor Sie entscheiden, ob Komponenten gemeinsam verwendet werden sollen. Kollokationsszenarien unterscheiden sich für Skype for Business Server 2015-Enterprise Edition- und Standard Edition-Server. 
  
In den folgenden Abschnitten werden die Topologien ausführlicher beschrieben, einschließlich Kollokationsszenarien und Optionen für die Back-End-Datenbankserver. Ausführliche Informationen zur Kollokation aller Serverrollen und Datenbanken finden Sie unter [Topologiegrundlagen für Skype for Business Server 2015.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server mit Server für beständigen Chat, der auf dem Front-End-Server verbunden ist

Mit Standard Edition können Sie den beständigen Chat auf dem Front-End-Server verbinden. Dies ist die einfachste und einfachste Konfiguration. Sie müssen sicherstellen, dass der vorhandene Front-End-Server über genügend Kapazität hinsichtlich physischer Ressourcen verfügt: CPU, Arbeitsspeicher, Speicherplatz usw.
  
Darüber hinaus können Sie den Back-End-Server für den Server für beständigen Chat und die Konformitätsdatenbank für beständigen Chat (falls aktiviert) auf dem lokalen SQL Server Express Back-End-Server verbinden. Sie können auch eine separate SQL Server mit einer dedizierten Instanz verwenden. 
  
> [!IMPORTANT]
> Sie können einem Serverpool für beständigen Chat keine zusätzlichen Server hinzufügen, wenn der erste Server für beständigen Chat mit einem Standard Edition Front-End-Server verbunden ist. Es wird empfohlen, den ersten Server als eigenständige Instanz zu installieren, damit Sie später bei Bedarf weitere Server hinzufügen können. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition Server mit Server für beständigen Chat, der auf einem separaten Server installiert ist

Mit Standard Edition können Sie den Server für beständigen Chat als eigenständige Instanz installieren und später bei Bedarf weitere Server hinzufügen. 
  
Sie können den Back-End-Server für den Server für beständigen Chat und die Konformitätsdatenbank für beständigen Chat (sofern aktiviert) auf dem lokalen SQL Server Express Back-End-Server verbinden. Sie können auch eine separate SQL Server mit einer dedizierten Instanz verwenden. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server mit einem einzelnen Server für beständigen Chat

Mit Enterprise Edition müssen Sie den Server für beständigen Chat auf einem separaten Computer installieren. Das heißt, Sie können den Server für beständigen Chat nicht auf dem Enterprise Edition Front-End-Server verbinden. Für diese Bereitstellung ist ein separater Server erforderlich, auf dem der Server für beständigen Chat und der Konformitätsdienst ausgeführt werden (sofern aktiviert).
  
Sie können jedoch die SQL Server-Datenbank für den Server für beständigen Chat in der Back-End-Datenbank eines Enterprise Edition Front-End-Pools verbinden.
  
> [!NOTE]
> Wenn Sie beabsichtigen, SQL AlwaysOn-Verfügbarkeitsgruppen für HA DR zu verwenden, beachten Sie, dass sie für Datenbanken des Servers für beständigen Chat nicht unterstützt wird. 
  
Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank verbinden, können Sie entweder eine einzelne Instanz von SQL Server für eine oder alle Datenbanken oder eine separate Instanz von SQL Server für jede Datenbank verwenden.
  
> [!IMPORTANT]
> Der Server, auf dem die Datenbank für beständigen Chat gehostet wird, kann andere Datenbanken hosten. Wenn Sie jedoch in Betracht ziehen, die Datenbank für beständigen Chat mit anderen Datenbanken zu verbinden, beachten Sie, dass beim Speichern der Nachrichten mehrerer Benutzer der Speicherplatz, der von der Datenbank für beständigen Chat benötigt wird, sehr groß werden kann. Aus diesem Grund wird nicht empfohlen, die Datenbank für beständigen Chat mit der Back-End-Datenbank zu verbinden. 
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie für einen einzelnen Server für beständigen Chat mit aktivierter Kompatibilität (optional).
  
**Topologie mit einzelnem Server**

![Server für beständigen Chat – Topologie mit einem Server.](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition Server mit mehreren Servern für beständigen Chat

Mit Enterprise Edition können Sie eine Topologie mit mehreren Servern bereitstellen, um mehr Kapazität und Zuverlässigkeit zu gewährleisten. Eine Topologie mit mehreren Servern ist identisch mit der Topologie mit einem Server, mit der Ausnahme, dass mehrere Server den Server für beständigen Chat hosten und höher skaliert werden können. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer enthalten, auf denen der Server für beständigen Chat ausgeführt wird (Konfigurationen für hohe Verfügbarkeit und Notfallwiederherstellung ermöglichen bis zu acht, aber nur vier können aktiv sein und die restlichen vier im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, insgesamt 80.000 gleichzeitige Benutzer, die mit einem Serverpool für beständigen Chat mit 4 Servern verbunden sind. Mehrere Computer, auf denen der Server für beständigen Chat ausgeführt wird, sollten sich in derselben Active Directory Domain Services-Domäne befinden wie Skype for Business Server und der Konformitätsdienst.
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der Server für beständigen Chat ausgeführt wird, den optionalen Kompatibilitätsdienst und eine separate Konformitätsdatenbank.
  
**Topologie mit mehreren Servern**

![Server für beständigen Chat – Topologie mit mehreren Servern.](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool kommunizieren die Dienste für beständigen Chat und geben Daten frei. Beispielsweise ist der Chatverlauf, der ursprünglich in einem Dienst für beständigen Chat veröffentlicht wurde, über jeden Dienst für beständigen Chat im System verfügbar. Auf eine Datei, die über einen Dienst für beständigen Chat hochgeladen wird, kann von jedem Dienst für beständigen Chat zugegriffen werden. Benutzer können mit unterschiedlichen Front-End-Servern für den Server für beständigen Chat verbunden sein und miteinander kommunizieren. Der Standardport von TCP 8011 verbindet einen Server mit einem Serverpool und wird von den Diensten für beständigen Chat für die Kommunikation zwischen sich selbst oder zu Administrativen Zwecken verwendet.
  
Bei einer Bereitstellung mit vier Servern für beständigen Chat, bei der 80.000 Benutzer gleichzeitig beim beständigen Chat angemeldet sein können, wird die Last gleichmäßig auf 20.000 Benutzer pro Server verteilt. Wenn ein Server nicht mehr verfügbar ist, verlieren die Benutzer, die mit diesem Server verbunden sind, ihren Zugriff auf den Server für beständigen Chat. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server erneut verfügbar ist. 
  

