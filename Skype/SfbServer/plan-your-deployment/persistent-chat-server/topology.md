---
title: Planen der Topologie für den Server für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Zusammenfassung: In diesem Thema erhalten Sie Informationen zu Komponenten und Topologien für den Server für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825505"
---
# <a name="plan-persistent-chat-server-topology"></a>Planen der Topologie für den Server für beständigen Chat
 
**Zusammenfassung:** In diesem Thema erhalten Sie Informationen zu Komponenten und Topologien für den Server für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat unterstützt sowohl Konfigurationen mit einem Server als auch mit mehreren Servern. Sie können den Server für beständigen Chat entweder auf einem Skype for Business Server 2015 Enterprise Edition- oder Standard Edition Server installieren. 

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="persistent-chat-server-components"></a>Komponenten des Servers für beständigen Chat

Der Server für beständigen Chat besteht aus den folgenden Komponenten:
  
- Mindestens ein Computer, auf dem der Server für beständigen Chat ausgeführt wird und der die folgenden Dienste zur Verfügung stellt:
    
  - Dienst für beständigen Chat
    
  - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    
- Mindestens ein Server (bei Verwendung der Spiegelung) mit der SQL Server-Back-End-Datenbank zum Hosten der Inhaltsdatenbank für beständigen Chat, in der Chatroominhalte, Chatrooms und Kategorien gespeichert werden.
    
    > [!NOTE]
    > In der Back-End-Datenbank werden Chatverlaufsdaten gespeichert, einschließlich Informationen zu Kategorien und erstellten Chatrooms für beständigen Chat. 
  
- Wenn die Kompatibilität aktiviert ist, wird auf einem oder mehreren Servern (bei Verwendung der Spiegelung) die SQL Server-Back-End-Datenbank zum Hosten der Konformitätsdatenbank für beständigen Chat ausgeführt, auf dem Kompatibilitätsereignisse und Chatinhalte zum Zweck der Kompatibilität gespeichert werden.
    
Einzelheiten zu den Hardware- und Softwareanforderungen für den Server für beständigen Chat finden Sie unter ["Serveranforderungen für Skype for Business Server 2015"](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und "Hardware- und Softwareanforderungen für den Server für beständigen [Chat" in Skype for Business Server 2015.](hardware-and-software-requirements.md) 
  
## <a name="persistent-chat-server-topologies"></a>Topologien für den Server für beständigen Chat

Sie können den Server für beständigen Chat in Pools mit einem oder mehreren Servern und mit einer Topologie mit einem pool oder mehreren Pools bereitstellen. Der Server für beständigen Chat unterstützt die folgenden Topologien:
  
-  Standard Edition Server mit Server für beständigen Chat, der auf dem Front-End-Server ausgeführt wird
    
-  Standard Edition Server mit Server für beständigen Chat auf einem separaten Server
    
-  Enterprise Edition Server mit einem einzelnen Server für beständigen Chat auf einem separaten Server
    
-  Enterprise Edition Server mit mehr als einem Server für beständigen Chat auf separaten Servern
    
Sie können den Server für beständigen Chat zwar auf einem Standard Edition-Server bereitstellen, beachten Sie jedoch, dass leistung und Skalierung beeinträchtigt werden und hohe Verfügbarkeit keine Option ist. Aus diesem Grund wird empfohlen, den beständigen Chat in erster Linie zu Konzept- und Evaluierungszwecken auf einem Standard Edition Server bereitstellen. 
  
Skype for Business Server 2015 unterstützt eine Vielzahl von Kollokationsszenarien und bietet Ihnen die Flexibilität, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie über eine kleine Organisation verfügen) oder einzelne Komponenten auf verschiedenen Servern ausführen (wenn Sie eine größere Organisation haben, die Skalierbarkeit und Leistung benötigt). Sie sollten Skalierbarkeitsfaktoren berücksichtigen, bevor Sie entscheiden, ob Sie Komponenten zusammen verwenden möchten. Kollokationsszenarien unterscheiden sich für Skype for Business Server 2015 Enterprise Edition- und Standard Edition-Server. 
  
In den folgenden Abschnitten werden die Topologien ausführlicher beschrieben, einschließlich Kollokationsszenarien und Optionen für die Back-End-Datenbankserver. Weitere Informationen zum Verbinden aller Serverrollen und Datenbanken finden Sie unter [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server mit Server für beständigen Chat, der auf dem Front-End-Server ausgeführt wird

Mit Standard Edition können Sie den beständigen Chat auf dem Front-End-Server verbinden. Dies ist die einfachste und grundlegendste Konfiguration. Sie müssen sicherstellen, dass der vorhandene Front-End-Server hinsichtlich der physischen Ressourcen über ausreichend Kapazität verfügt: CPU, Arbeitsspeicher, Speicherplatz und so weiter.
  
Darüber hinaus können Sie den Back-End-Server für den Server für beständigen Chat und die Konformitätsdatenbank für beständigen Chat (sofern aktiviert) auf dem lokalen SQL Server Express-Back-End-Server verbinden. Sie können auch eine separate SQL Server mit einer dedizierten Instanz verwenden. 
  
> [!IMPORTANT]
> Sie können keine weiteren Server zu einem Pool für den Server für beständigen Chat hinzufügen, wenn der erste Server für beständigen Chat mit einem Front-End-Server der Standard Edition ausgeführt wird. Es wird empfohlen, den ersten Server als eigenständige Instanz zu installieren, damit Sie später bei Bedarf weitere Server hinzufügen können. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition Server mit auf einem separaten Server installiertem Server für beständigen Chat

Mit Standard Edition können Sie den Server für beständigen Chat als eigenständige Instanz installieren und später bei Bedarf weitere Server hinzufügen. 
  
Sie können den Back-End-Server für den Server für beständigen Chat und die Konformitätsdatenbank für beständigen Chat (sofern aktiviert) auf dem lokalen SQL Server Express-Back-End-Server verbinden. Sie können auch eine separate SQL Server mit einer dedizierten Instanz verwenden. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server mit einem einzigen Server für beständigen Chat

Bei Enterprise Edition müssen Sie den Server für beständigen Chat auf einem separaten Computer installieren. Das heißt, Sie können den Server für beständigen Chat nicht auf dem Front-End-Server der Enterprise Edition verbinden. Für diese Bereitstellung ist ein separater Server erforderlich, auf dem der Server für beständigen Chat und der Kompatibilitätsdienst ausgeführt werden (sofern aktiviert).
  
Sie können jedoch die SQL Server für den Server für beständigen Chat in der Back-End-Datenbank eines Front-End-Pools der Enterprise Edition verbinden.
  
> [!NOTE]
> Wenn Sie die Verwendung SQL AlwaysOn-Verfügbarkeitsgruppen für HA DR planen, beachten Sie, dass dies für Datenbanken des Servers für beständigen Chat nicht unterstützt wird. 
  
Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank in Verbindung setzen, können Sie entweder eine einzelne Instanz von SQL Server für eine oder alle Datenbanken oder eine separate Instanz von SQL Server für jede Datenbank verwenden.
  
> [!IMPORTANT]
> Der Server, der die Datenbank für den beständigen Chat hosten kann, kann andere Datenbanken hosten. Wenn Sie jedoch erwägen, die Datenbank für den beständigen Chat mit anderen Datenbanken zu arbeiten, beachten Sie, dass beim Speichern der Nachrichten von mehr als einigen wenigen Benutzern der von der Datenbank für den beständigen Chat benötigte Speicherplatz sehr groß werden kann. Aus diesem Grund wird nicht empfohlen, die Datenbank für beständigen Chat mit der Back-End-Datenbank zu verwenden. 
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie für einen einzelnen Server für beständigen Chat mit aktivierter Kompatibilität (optional).
  
**Topologie mit einzelnem Server**

![Server für beständigen Chat – Topologie mit einem Server](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition Server mit mehreren Servern für beständigen Chat

Mit Enterprise Edition können Sie eine Topologie mit mehreren Servern bereitstellen, um die Kapazität und Zuverlässigkeit zu erhöhen. Eine Topologie mit mehreren Servern ist identisch mit der Topologie mit einem Server, mit der Ausnahme, dass mehrere Server den Server für beständigen Chat hosten und höher skaliert werden können. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer umfassen, auf denen der Server für beständigen Chat ausgeführt wird (Hochverfügbarkeits- und Notfallwiederherstellungskonfigurationen ermöglichen bis zu acht, aber nur vier können aktiv sein, und die übrigen vier sind im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem Pool für den Server für beständigen Chat mit vier Servern verbunden sind. Mehrere Computer, auf denen der Server für beständigen Chat ausgeführt wird, sollten sich in derselben Active Directory Domain Services-Domäne wie Skype for Business Server und der Kompatibilitätsdienst befinden.
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der Server für beständigen Chat ausgeführt wird, den optionalen Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank.
  
**Topologie mit mehreren Servern**

![Server für beständigen Chat – Topologie mit mehreren Servern](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool kommunizieren die Dienste für beständigen Chat und geben Daten frei. Beispielsweise ist der Chatverlauf, der ursprünglich in einem Dienst für beständigen Chat veröffentlicht wurde, in jedem Dienst für beständigen Chat im System verfügbar. Auf eine Datei, die über einen Dienst für beständigen Chat hochgeladen wird, kann jeder Dienst für beständigen Chat zugreifen. Benutzer können mit unterschiedlichen Front-End-Servern für den Server für beständigen Chat verbunden sein und miteinander kommunizieren. Der Standardport von TCP 8011 verbindet einen Server mit einem Serverpool und wird von den Diensten für beständigen Chat für die Kommunikation zwischen sich selbst oder zu Verwaltungszwecken verwendet.
  
In einer Bereitstellung des Servers für beständigen Chat mit vier Servern, bei der 80.000 Benutzer gleichzeitig beim beständigen Chat angemeldet werden können, wird die Last gleichmäßig auf 20.000 Benutzer pro Server verteilt. Wenn ein Server nicht mehr verfügbar ist, verlieren die Benutzer, die mit diesem Server verbunden sind, ihren Zugriff auf den Server für beständigen Chat. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server erneut verfügbar ist. 
  

