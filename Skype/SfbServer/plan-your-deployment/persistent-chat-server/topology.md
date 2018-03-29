---
title: Topologieplanung für den Server für beständigen Chat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Zusammenfassung: Lesen Sie dieses Thema, um über Persistent Chat-Server-Komponenten und Topologien in Skype für Business Server 2015 zu erfahren.'
ms.openlocfilehash: 11d12283c3ee302c8133b0a56bbea53315508aec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-persistent-chat-server-topology"></a>Topologieplanung für den Server für beständigen Chat
 
**Zusammenfassung:** Lesen Sie dieses Thema Weitere Informationen zu Persistent Chat-Server-Komponenten und Topologien in Skype für Business Server 2015.
  
Persistent Chat Server unterstützt Konfigurationen mit einem einzelnen Server oder mehreren Servern. Sie können Persistent Chat Server auf entweder einen Skype für Business Server 2015 Enterprise Edition oder Standard Edition-Server installieren. 
  
## <a name="persistent-chat-server-components"></a>Persistent Chat-Server-Komponenten

Der permanente Chatserver besteht aus folgenden Komponenten:
  
- Mindestens ein Computer Persistent Chat Server ausgeführt wird und die folgenden Dienste bereitstellt:
    
  - Persistent Chat-Dienst
    
  - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    
- Einem oder mehreren Servern (mehr als eine wenn Spiegelung verwendet wird) mit SQL Server-Back-End-Datenbank zum Hosten der Inhaltsdatenbank für beständigen Chat, in dem chatroominhalte, Räume und Kategorien gespeichert.
    
    > [!NOTE]
    > Back-End-Datenbank werden chatverlaufsdaten, einschließlich Informationen zu Kategorien und beständigen Chatrooms, die erstellt werden gespeichert. 
  
- Wenn Kompatibilität aktiviert ist, werden einem oder mehreren Servern (mehr als eine wenn Spiegelung verwendet wird) mit SQL Server-Back-End-Datenbank zum Hosten der Persistent Chat Kompatibilitätsdatenbank Konformitätsereignisse und Chat, in dem für die Einhaltung von Bestimmungen des Inhalts gespeichert.
    
Ausführliche Informationen zu Hardware und Software für Persistent Chat Server finden Sie unter [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Persistent Chat-Server-Topologien

Sie können die Persistent Chat Server in einem einzelnen Server oder mehreren Servern Pools und mit Single- oder Pool mit mehreren Topologie bereitstellen. Persistent Chat-Server unterstützt die folgenden Topologien:
  
-  Standard Edition-Server mit auf dem Front-End-Server bereitgestelltem Server für beständigen Chat
    
-  Standard Edition-Server mit Persistent Chat Server auf einem separaten server
    
-  Enterprise Edition-Server mit einem einzigen Persistent Chat Server auf einem separaten server
    
-  Enterprise Edition-Server mit mehr als eine Persistent Chat Server auf separaten Servern
    
Obwohl Sie Persistent Chat Server auf einem Standard Edition-Server bereitstellen können, beachten Sie, dass die Leistung und Skalierung betroffen sind, und hoher Verfügbarkeit ist keine Option. Aus diesem Grund wird empfohlen, dass Sie auf einem Standard Edition-Server in erster Linie zum Nachweis des Konzept und Evaluierungszwecke beständigen Chat bereitstellen. 
  
Skype für Business Server 2015 unterstützt eine Vielzahl von zusammenstellungsszenarien, bietet Ihnen die Flexibilität, die zum Speichern der Hardwarekosten durch Ausführen von mehreren Komponenten auf einem Server (Wenn Sie eine kleine Organisation verwenden), oder einzelne Komponenten auf verschiedenen Servern (auszuführen Wenn Sie eine größere Organisation haben benötigt, Skalierbarkeit und Leistung). Die skalierbarkeitsfaktoren sollten Sie berücksichtigen, bevor Sie sich entscheiden, ob Komponenten zu verbinden. Zusammenstellungsszenarien unterscheiden sich für Skype für Business Server 2015 Enterprise Edition und Standard Edition-Server. 
  
In den folgenden Abschnitten werden die Topologien im Detail beschrieben und Kollokationsszenarien sowie Optionen für die Back-End-Datenbankserver erläutert. Ausführliche Informationen zum Verbinden aller Serverrollen und Datenbanken finden Sie unter [Grundlagen der Topologie Skype für Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition-Server mit auf dem Front-End-Server bereitgestelltem Server für beständigen Chat

Mit Standard Edition können Sie den beständigen Chat auf dem Front-End-Server verbinden. Dies ist die einfachste und grundlegenden Konfiguration. Sie müssen sicherstellen, dass die vorhandenen Front-End-Server ausreichende Kapazität im Hinblick auf die physischen Ressourcen verfügt: CPU, Arbeitsspeicher, Speicherplatz und So weiter.
  
Darüber hinaus können Sie die Persistent Chat Server-Back-End-Server und die Persistent Chat Kompatibilitätsdatenbank verbinden (sofern aktiviert) auf dem lokalen SQL Server Express-Back-End-Server. Sie können auch einen separaten Server mit SQL Server mit einer dedizierten Instanz verwenden. 
  
> [!IMPORTANT]
> Wenn Sie keine weitere Servern in einer Persistent Chat Server Pool Hinzufügen der ersten Persistent Chat Server mit einem Standard Edition-Front-End-Server verbunden ist. Es wird empfohlen, dass Sie den ersten Server als eigenständige Instanz installieren, damit Sie später weitere Server hinzufügen können bei Bedarf. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition-Server mit auf einem separaten Server installiertem Server für beständigen Chat

Bei der Standard Edition können Sie Server für beständigen Chat als eine eigenständige Instanz installieren und später bei Bedarf weitere Server hinzufügen.   
  
Sie können die Persistent Chat Server-Back-End-Server und die Persistent Chat Kompatibilitätsdatenbank verbinden (sofern aktiviert) auf dem lokalen SQL Server Express-Back-End-Server. Sie können auch einen separaten Server mit SQL Server mit einer dedizierten Instanz verwenden. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition-Server mit einem einzelnen Server für beständigen Chat

Mit Enterprise Edition müssen Sie den Server für beständigen Chat auf einem separaten Computer installieren. Das heißt, Sie können den Server für beständigen Chat nicht auf dem Enterprise Edition-Front-End-Server ausführen. Diese Bereitstellung erfordert einen separaten Server, der Persistent Chat Server und die Einhaltung von Bestimmungen (sofern aktiviert) ausgeführt werden.
  
Sie können, jedoch SQL Server-Datenbank für Persistent Chat Server in der Back-End-Datenbank von einem Enterprise Edition-Front-End-Pool verbinden.
  
> [!NOTE]
> Wenn Sie SQL AlwaysOn-Verfügbarkeitsgruppen für hohe Verfügbarkeit und Notfallwiederherstellung verwenden möchten, beachten Sie, dass dies für Datenbanken des Servers für beständigen Chat nicht unterstützt wird. 
  
Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank zusammenstellen, Sie können entweder eine einzelne Instanz von SQL Server für einige oder alle Datenbanken verwenden, oder Sie können für jede Datenbank eine separate Instanz von SQL Server verwenden.
  
> [!IMPORTANT]
> Der Hostserver für die Datenbank für beständigen Chat kann andere Datenbanken hosten. Jedoch, wenn Sie die Verbindung mit anderen Datenbanken Datenbank für beständigen Chat berücksichtigen, beachten Sie, dass, wenn Sie die Nachrichten von mehr als ein paar Benutzern speichern, der Speicherplatz von Datenbank für beständigen Chat sehr groß können benötigt. Aus diesem Grund empfohlen nicht Verbindung Datenbank für beständigen Chat mit der Back-End-Datenbank. 
  
Die folgende Abbildung zeigt alle Komponenten einer Topologie für einen einzelnen Persistent Chat Server mit aktiviertem kompatibilitätsdienst (optional).
  
**Einzelserver-Topologie**

![Server für beständigen Chat - Topologie mit einem einzelnen Server](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition-Server mit mehreren Servern für beständigen Chat

Mit Enterprise Edition können Sie eine Topologie mit mehreren Servern für höhere Kapazität und Zuverlässigkeit bereitstellen. Eine Topologie mit mehreren Servern ist eine Einzelservertopologie identisch, außer dass mehrere Server Persistent Chat Server gehostet, und höher skalieren können. Die Topologie mit mehreren Servern kann bis zu vier aktive Computern Persistent Chat Server enthalten (hohe Verfügbarkeit und Disaster Recovery-Konfigurationen können bis zu acht, nämlich, aber nur vier sind aktiv sind und die übrigen vier Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer, für insgesamt 80.000 gleichzeitige Benutzer mit einer Persistent Chat Server Pool mit 4 Server verbunden unterstützen. Mehrere Computer mit Persistent Chat Server sollte in derselben Active Directory-Domänendienste Domäne als Skype für Business Server und die Einhaltung von Bestimmungen befinden.
  
Die folgende Abbildung zeigt alle Komponenten einer MultiServer-Topologie mit mehreren Computern Persistent Chat-Server, der optionale kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt.
  
**Topologie mit mehreren Servern**

![Server für beständigen Chat – Topologie mit mehreren Servern](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool der Persistent Chat-Dienste kommunizieren und Daten austauschen. Beispielsweise steht der Chatverlauf, die ursprünglich in einem Persistent Chat-Dienst veröffentlicht wurde keinen Persistent Chat-Dienst im System. Eine Datei, die über einen beständigen Chat Dienst hochgeladen wird, kann von jedem Persistent Chat-Dienst zugegriffen werden. Benutzer verschiedene Persistent Chat Server-Front-End-Server hergestellt werden können und miteinander kommunizieren können. Die standardmäßigen Port von TCP 8011 verbindet einen Server mit einem Serverpool und wird von den Diensten beständigen Chat Kommunikation untereinander oder administrativen Zwecken verwendet.
  
Beispielsweise in einem vier Servern Persistent Chat Server Bereitstellung, wobei 80.000 Benutzern können gleichzeitig bei angemeldet sein, und mit beständigen Chat, die Last gleichmäßig auf 20.000 Benutzer pro Server. Wenn ein Server ausfällt, verlieren die Benutzer, die mit dem Server verbunden sind deren Zugriff auf Persistent Chat Server. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server wieder verfügbar ist. 
  

