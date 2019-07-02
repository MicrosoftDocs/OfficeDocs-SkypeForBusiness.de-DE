---
title: Planen von Höchstverfügbarkeit und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server planen.'
ms.openlocfilehash: 0cdd1d17680f0546a0081bb769e2c6f45a370d0c
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418266"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planen von Höchstverfügbarkeit und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server planen.
  
Hochverfügbarkeit und Disaster Recovery für beständigen Chat Server erfordern zusätzliche Ressourcen, die über die normalerweise für den vollständigen Betrieb erforderlichen Ressourcen hinausgehen. 
  
> [!NOTE]
> Die Verwendung von SQL AlwaysOn-Verfügbarkeitsgruppen wird für Datenbanken des Servers für beständigen Chat nicht unterstützt. 

> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
  
## <a name="resource-requirements"></a>Ressourcenanforderungen

Bevor Sie den beständigen Chat Server für die Hochverfügbarkeits-und Disaster Recovery konfigurieren, stellen Sie sicher, dass Sie über die folgenden zusätzlichen Ressourcen verfügen. 
  
- Eine dedizierte Datenbankinstanz, die sich im gleichen physikalischen Rechenzentrum befindet, in dem sich das Home-Front-End des Server Diensts für beständigen Chat befindet. Diese Datenbank dient als SQL Server-Spiegelung für die primäre Datenbank für beständigen Chat. Optional können Sie einen zusätzlichen SQL-Server als Spiegelungs Zeuge festlegen, wenn Sie ein automatisches Failover zur Spiegeldatenbank durch stellen möchten.
    
- Eine dedizierte Datenbankinstanz in dem anderen physischen Rechenzentrum. Diese Datenbank dient als SQL Server-Protokollversand-sekundäre Datenbank für die Datenbank im primären Rechenzentrum.
    
- Eine dedizierte Datenbankinstanz, die als SQL Server-Spiegelung für die sekundäre Datenbank fungieren soll. Optional können Sie einen zusätzlichen SQL Server als Spiegelungs Zeuge auf dem Server angeben. Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.
    
- Wenn die Kompatibilität des beständigen Chat Servers aktiviert ist, sind zusätzliche drei dedizierte Datenbankinstanzen erforderlich. Ihre Verteilung ist mit denen identisch, die zuvor für die persistente Chat-Datenbank beschrieben wurden. Es ist zwar möglich, dass die Compliance-Datenbank dieselbe SQL Server-Instanz wie die persistent Chat-Datenbank hat, aber es werden eigenständige Instanzen für eine höhere Verfügbarkeit und Disaster Recovery empfohlen.
    
- Es muss eine Dateifreigabe erstellt und für die Transaktionsprotokolle des SQL Server-Protokollversands festgelegt werden. Alle SQL-Server in beiden Rechenzentren, in denen persistente Chat Datenbanken ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen. Diese Freigabe wird nicht als Teil einer FileStore-Rolle definiert.
    
- Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server-Transaktionsprotokolle fungieren soll, die aus der Dateifreigabe des primären Servers kopiert werden.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Lösungen für Notfallwiederherstellung und hohe Verfügbarkeit

Skype for Business Server unterstützt mehrere Modi mit höherer Verfügbarkeit für Ihre Back-End-Server, einschließlich der Datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
Die in diesem Thema beschriebene Disaster Recovery-Lösung für beständigen Chat Server basiert auf einem gedehnten beständigen Chat Serverpool. Für ein gedehntes virtuelles lokales Netzwerk (VLAN) gibt es keine Voraussetzungen. Wenn Sie einen Server Pool für beständigen Chat Strecken, konfigurieren Sie einen Pool in der Topologie logisch, aber Sie platzieren die Server physisch in einem Pool in zwei unterschiedlichen Rechenzentren. Sie können die SQL Server-Spiegelung für die Datenbank auf die gleiche Weise konfigurieren und die Datenbank und die Spiegelung im gleichen Rechenzentrum bereitstellen. Sie müssen eine Sicherungsdatenbank im sekundären Rechenzentrum konfigurieren (mit einem optionalen Mirror, um eine höhere Verfügbarkeit während der Disaster Recovery zu gewährleisten). Hierbei handelt es sich um die Backup-Datenbank, die für ein Failover während der Disaster Recovery verwendet wird. 
  
Ausführliche Informationen zum Konfigurieren von Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server finden Sie unter Konfigurieren von Hochverfügbarkeits [-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Die folgenden Abbildungen zeigen, wie der Server Pool für beständigen Chat in zwei unterschiedlichen gedehnten Pool Topologien konfiguriert werden kann:
  
- Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.
    
- Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit niedriger Bandbreite/hoher Latenz geografischer Standort sind.
    
Abbildung 1 zeigt eine gedehnte Server Pooltopologie mit beständigem Chat, in der Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind. Gehen Sie für die logischen und physikalischen Topologien wie folgt vor:
  
- Die logische Topologie beinhaltet die folgenden Komponenten:
    
  - Einen Pool für beständigen Chat über die Standorte 1 und 2 hinweg mit den Servern 1 bis einschließlich 8.
    
  - Ein Front-End-Server Pool, eine persistente Chat Datenbank, eine gespiegelte Datenbank und optional eine Zeugen Datenbank (nicht in Diagramm dargestellt), die sich physisch auf Website 1 befindet. 
    
  - Einen zweiten Front-End-Server-Pool und eine Sicherungsdatenbank, die physisch auf Standort 2 liegen.
    
- Die physikalische Topologie besteht aus den Websites 1 und 2 wie folgt:
    
  - Einen Pool für beständigen Chat mit den Servern 1 bis einschließlich 4, zwei aktiv und zwei im Leerlauf, an Standort 1.
    
  - Einen Pool für beständigen Chat mit den Servern 5 bis einschließlich 8, zwei aktiv und zwei im Leerlauf, an Standort 2.
    
  - Ein Front-End-Server Pool, eine persistente Chat Datenbank, eine gespiegelte Datenbank und optional eine Zeugen Datenbank (nicht in Diagramm dargestellt) auf Website 1.
    
  - Einen Front-End-Server-Pool und eine Sicherungsdatenbank, die das SQL-Protokollversandziel ist, auf Standort 2.
    
**Gestreckter Serverpool für beständigen Chat bei Rechenzentren an einem geografischen Standort mit hoher Bandbreite und niedriger Latenz**

![Erweiterter Pool für beständigen Chat mit hoher Bandbreite/niedriger Latenz](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Abbildung 2 zeigt eine gedehnte Server Pooltopologie mit beständigem Chat, in der Rechenzentren mit niedriger Bandbreite/hoher Latenz geografisch lokalisiert sind.
  
- Die logische Topologie beinhaltet die folgenden Komponenten:
    
  - Einen Pool für beständigen Chat über die Standorte 1 und 2 hinweg mit den Servern 1 bis einschließlich 8.
    
  - Ein Front-End-Server Pool, eine persistente Chat Datenbank, eine gespiegelte Datenbank und optional eine Zeugen Datenbank (nicht in Diagramm dargestellt), die sich physisch auf Website 1 befindet. 
    
  - Einen zweiten Front-End-Server-Pool und eine Sicherungsdatenbank, die physisch auf Standort 2 liegen.
    
- Die physikalische Topologie besteht aus den Websites 1 und 2 wie folgt:
    
  - Einen Pool für beständigen Chat mit den Servern 1 bis einschließlich 4, alle aktiv, an Standort 1.
    
  - Einen Pool für beständigen Chat mit den Servern 5 bis einschließlich 8, alle im Leerlauf, an Standort 2.
    
  - Ein Front-End-Server Pool, eine persistente Chat Datenbank, eine gespiegelte Datenbank und optional eine Zeugen Datenbank (nicht in Diagramm dargestellt) auf Website 1.
    
  - Einen Front-End-Server-Pool und eine Sicherungsdatenbank, das SQL-Protokollversandziel ist, an Standort 2.
    
**Gestreckter Pool mit Servern für beständigen Chat, bei dem sich die Rechenzentren an einem geografischen Standort mit niedriger Bandbreite und hoher Latenz befinden**

![Erweiterter Pool für beständigen Chat mit niedriger Bandbreite/hoher Latenz](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

