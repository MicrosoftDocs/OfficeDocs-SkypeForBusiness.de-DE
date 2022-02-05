---
title: Planen der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 planen.'
---

# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planen der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 planen.
  
Hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat erfordern zusätzliche Ressourcen, die über die für den Vollbetrieb normalerweise erforderlichen Ressourcen hinausgehen. 
  
> [!NOTE]
> Die Verwendung von SQL AlwaysOn-Verfügbarkeitsgruppen wird für Datenbanken des Servers für beständigen Chat nicht unterstützt. 

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams Upgrade](/microsoftteams/upgrade-start-here)". Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="resource-requirements"></a>Ressourcenanforderungen

Bevor Sie den Server für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung konfigurieren, stellen Sie sicher, dass Sie über die folgenden zusätzlichen Ressourcen verfügen. 
  
- Eine dedizierte Datenbankinstanz, die sich im selben physischen Rechenzentrum befindet, in dem sich das Start-Front-End des Servers für beständigen Chat befindet. Diese Datenbank dient als SQL Server Spiegelung für die primäre Datenbank für beständigen Chat. Legen Sie optional eine zusätzliche SQL Server fest, die als Spiegelungszeugen dienen soll, wenn Sie ein automatisches Failover auf die Spiegeldatenbank wünschen.
    
- Eine dedizierte Datenbankinstanz im anderen physischen Rechenzentrum. Diese Datenbank dient als SQL Server sekundäre Datenbank für den Protokollversand für die Datenbank im primären Rechenzentrum.
    
- Eine dedizierte Datenbankinstanz, die als SQL Server Spiegelung für die sekundäre Datenbank dient. Legen Sie optional eine zusätzliche SQL Server für den Server als Spiegelungszeugen fest. Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.
    
- Wenn die Kompatibilität des Servers für beständigen Chat aktiviert ist, sind drei zusätzliche dedizierte Datenbankinstanzen erforderlich. Ihre Verteilung ist identisch mit denen, die zuvor für die Datenbank für beständigen Chat beschrieben wurden. Es ist zwar möglich, dass die Compliancedatenbank dieselbe SQL Server Instanz wie die Datenbank für beständigen Chat gemeinsam verwendet, es werden jedoch eigenständige Instanzen für hohe Verfügbarkeit und Notfallwiederherstellung empfohlen.
    
- Eine Dateifreigabe muss erstellt und für die SQL Server Protokollversand-Transaktionsprotokolle festgelegt werden. Alle SQL Server in beiden Rechenzentren, auf denen Datenbanken für beständigen Chat ausgeführt werden, müssen Über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen. Diese Freigabe ist nicht als Teil einer FileStore-Rolle definiert.
    
- Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server Transaktionsprotokollen dient, die aus der primären Serverdateifreigabe kopiert werden.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Notfallwiederherstellungs- und Hochverfügbarkeitslösungen

Skype for Business Server unterstützt mehrere Modi mit hoher Verfügbarkeit für Ihre Back-End-Server, einschließlich Datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
Die in diesem Thema beschriebene Notfallwiederherstellungslösung für den Server für beständigen Chat basiert auf einem gestreckten Serverpool für beständigen Chat. Es ist kein erweitertes virtuelles lokales Netzwerk (VIRTUAL Local Area Network, VLAN) erforderlich. Durch stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data center. Sie konfigurieren SQL Server Spiegelung für die Datenbank auf die gleiche Weise und stellen die Datenbank und die Spiegelung im selben Rechenzentrum bereit. Sie müssen im sekundären Rechenzentrum eine Sicherungsdatenbank konfigurieren (mit einem optionalen Spiegel, um eine hohe Verfügbarkeit im Fall einer Notfallwiederherstellung zu gewährleisten). Dies ist die Sicherungsdatenbank, die bei der Notfallwiederherstellung für das Failover verwendet wird. 
  
Ausführliche Informationen zum Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat finden Sie unter [Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Die folgenden Abbildungen zeigen, wie der Serverpool für beständigen Chat in zwei verschiedenen Topologien für gestreckte Pools konfiguriert werden kann:
  
- Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.
    
- Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.
    
Abbildung 1 zeigt eine gestreckte Pooltopologie des Servers für beständigen Chat, in der sich Rechenzentren geografisch mit hoher Bandbreite/geringer Latenz befinden. Gehen Sie für die logischen und physischen Topologien von Folgendem aus:
  
- Die logische Topologie besteht aus folgenden Komponenten:
    
  - Ein Pool für beständigen Chat an den Standorten 1 und 2 mit den Servern 1 bis 8.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt), die sich physisch auf Standort 1 befindet. 
    
  - Ein zweiter Front-End-Serverpool und eine Sicherungsdatenbank, die sich physisch an Standort 2 befinden.
    
- Die physische Topologie besteht aus den Standorten 1 und 2 wie folgt:
    
  - Ein Pool für beständigen Chat mit den Servern 1 bis 4, zwei aktiv, zwei im Leerlauf an Standort 1.
    
  - Ein Pool für beständigen Chat mit den Servern 5 bis 8, zwei aktiv, zwei im Leerlauf an Standort 2.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt) an Standort 1.
    
  - Ein Front-End-Serverpool und eine Sicherungsdatenbank, die das SQL Protokollversandziel ist, an Standort 2.
    
**Gestreckter Serverpool für beständigen Chat, wenn sich Rechenzentren mit hoher Bandbreite/geringer Latenz befinden**

![Gestreckter Pool für beständigen Chat mit hoher Bandbreite/geringer Latenz.](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Abbildung 2 zeigt eine gestreckte Pooltopologie des Servers für beständigen Chat, in der sich Rechenzentren mit geringer Bandbreite/hoher Latenz geografisch befinden.
  
- Die logische Topologie besteht aus folgenden Komponenten:
    
  - Ein Pool für beständigen Chat an den Standorten 1 und 2 mit den Servern 1 bis 8.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt), die sich physisch auf Standort 1 befindet. 
    
  - Ein zweiter Front-End-Serverpool und eine Sicherungsdatenbank, die sich physisch an Standort 2 befinden.
    
- Die physische Topologie besteht aus den Standorten 1 und 2 wie folgt:
    
  - Ein Pool für beständigen Chat, der die Server 1 bis 4 (alle aktiv) an Standort 1 enthält.
    
  - Ein Pool für beständigen Chat, der die Server 5 bis 8 im Leerlauf an Standort 2 enthält.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt) an Standort 1.
    
  - Ein Front-End-Serverpool und eine Sicherungsdatenbank, die das SQL Protokollversandziel ist, an Standort 2.
    
**Gestreckter Serverpool für beständigen Chat, wenn sich Rechenzentren geografisch mit geringer Bandbreite/hoher Latenz befinden**

![Gestreckter Pool für beständigen Chat mit geringer Bandbreite/hoher Latenz.](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

