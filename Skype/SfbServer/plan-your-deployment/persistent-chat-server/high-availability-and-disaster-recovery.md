---
title: Planen der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
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
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 planen.'
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832355"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planen der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 planen.
  
Hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat erfordern zusätzliche Ressourcen, die über die normalerweise für den Vollbetrieb erforderlichen Ressourcen hinausgehen. 
  
> [!NOTE]
> Die SQL von AlwaysOn-Verfügbarkeitsgruppen wird für Datenbanken des Servers für beständigen Chat nicht unterstützt. 

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="resource-requirements"></a>Ressourcenanforderungen

Stellen Sie vor dem Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung sicher, dass Sie über die folgenden zusätzlichen Ressourcen verfügen. 
  
- Eine dedizierte Datenbankinstanz im selben physischen Rechenzentrum, in dem sich das Home-Front-End des Servers für beständigen Chat befindet. Diese Datenbank dient als SQL Server für die primäre Datenbank für beständigen Chat. Legen Sie optional einen zusätzlichen SQL Server als Spiegelungszeugen bereit, wenn Sie ein automatisches Failover zur Spiegeldatenbank wünschen.
    
- Eine dedizierte Datenbankinstanz im anderen physischen Rechenzentrum. Diese Datenbank dient als sekundäre SQL Server Protokollversanddatenbank für die Datenbank im primären Rechenzentrum.
    
- Eine dedizierte Datenbankinstanz, die als SQL Server für die sekundäre Datenbank dient. Legen Sie optional eine zusätzliche SQL Server server als Spiegelungszeugen. Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.
    
- Wenn die Kompatibilität des Servers für beständigen Chat aktiviert ist, sind drei zusätzliche dedizierte Datenbankinstanzen erforderlich. Ihre Verteilung ist identisch mit denen, die zuvor für die Datenbank für beständigen Chat beschrieben wurden. Es ist zwar möglich, dass die Kompatibilitätsdatenbank dieselbe SQL Server wie die Datenbank für den beständigen Chat verwendet, eigenständige Instanzen für hohe Verfügbarkeit und Notfallwiederherstellung werden jedoch empfohlen.
    
- Eine Dateifreigabe muss erstellt und für die Transaktionsprotokolle SQL Server Protokollversand festgelegt werden. Alle SQL server in beiden Rechenzentren, in denen Datenbanken für den beständigen Chat ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen. Diese Freigabe ist nicht als Teil einer Dateispeicherrolle definiert.
    
- Eine Dateifreigabe auf dem sekundären Datenbankserver als Zielordner für die SQL Server Transaktionsprotokolle, die aus der primären Serverdateifreigabe kopiert werden.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Notfallwiederherstellungs- und Hochverfügbarkeitslösungen

Skype for Business Server unterstützt mehrere Modi der hohen Verfügbarkeit für Ihre Back-End-Server, einschließlich Datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
Die in diesem Thema beschriebene Notfallwiederherstellungslösung für den Server für beständigen Chat baut auf einem gestreckten Serverpool für beständigen Chat auf. Ein gestrecktes virtuelles lokales Netzwerk (VIRTUAL Local Area Network, VLAN) ist nicht erforderlich. Durch das Dehnen eines Pools für den Server für beständigen Chat konfigurieren Sie einen Pool in der Topologie logisch, platzieren die Server jedoch physisch in zwei verschiedenen Rechenzentren. Sie konfigurieren SQL Server die Spiegelung für die Datenbank auf die gleiche Weise und stellen die Datenbank und die Spiegelung im selben Rechenzentrum. Sie müssen im sekundären Rechenzentrum eine Sicherungsdatenbank konfigurieren (mit einem optionalen Spiegel, um eine hohe Verfügbarkeit im Fall einer Notfallwiederherstellung zu gewährleisten). Dies ist die Sicherungsdatenbank, die bei der Notfallwiederherstellung für das Failover verwendet wird. 
  
Weitere Informationen zum Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat finden Sie unter "Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen [Chat in Skype for Business Server 2015".](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 
  
Die folgenden Abbildungen zeigen, wie der Serverpool für beständigen Chat in zwei verschiedenen Topologien für gestreckte Pools konfiguriert werden kann:
  
- Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.
    
- Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.
    
Abbildung 1 zeigt eine gestreckte Pooltopologie für den Server für beständigen Chat, in der sich Rechenzentren mit hoher Bandbreite/geringer Latenz befinden. Gehen Sie für die logischen und physischen Topologien wie folgt vor:
  
- Die logische Topologie besteht aus folgenden:
    
  - Ein Pool für beständigen Chat über die Standorte 1 und 2 hinweg, der die Server 1 bis 8 enthält.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt), die sich physisch an Standort 1 befindet. 
    
  - Ein zweiter Front-End-Serverpool und eine Sicherungsdatenbank, die sich physisch an Standort 2 befindet.
    
- Die physische Topologie besteht wie folgt aus den Standorten 1 und 2:
    
  - Ein Pool für beständigen Chat mit den Servern 1 bis 4, zwei aktiv, zwei im Leerlauf an Standort 1.
    
  - Ein Pool für beständigen Chat mit den Servern 5 bis 8, zwei aktiv, zwei im Leerlauf an Standort 2.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt) an Standort 1.
    
  - Ein Front-End-Serverpool und eine Sicherungsdatenbank, die SQL Protokollversandziel ist, an Standort 2.
    
**Gestreckter Serverpool für beständigen Chat, wenn sich Rechenzentren mit hoher Bandbreite/geringer Latenz im geografischen Raum befinden**

![Gestreckter Pool für beständigen Chat mit hoher Bandbreite/geringer Latenz](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Abbildung 2 zeigt eine gestreckte Pooltopologie für den Server für beständigen Chat, in der sich Die Rechenzentren mit geringer Bandbreite/hoher Latenz im geografischen Raum befinden.
  
- Die logische Topologie besteht aus folgenden:
    
  - Ein Pool für beständigen Chat über die Standorte 1 und 2 hinweg, der die Server 1 bis 8 enthält.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt), die sich physisch an Standort 1 befindet. 
    
  - Ein zweiter Front-End-Serverpool und eine Sicherungsdatenbank, die sich physisch an Standort 2 befindet.
    
- Die physische Topologie besteht wie folgt aus den Standorten 1 und 2:
    
  - Ein Pool für beständigen Chat mit den Servern 1 bis 4, alle aktiv, an Standort 1.
    
  - Ein Pool für beständigen Chat, der die Server 5 bis 8 an Standort 2 im Leerlauf enthält.
    
  - Ein Front-End-Serverpool, eine Datenbank für beständigen Chat, eine gespiegelte Datenbank und optional eine Zeugendatenbank (nicht im Diagramm dargestellt) an Standort 1.
    
  - Ein Front-End-Serverpool und eine Sicherungsdatenbank, die SQL Protokollversandziel ist, an Standort 2.
    
**Gestreckter Serverpool für beständigen Chat, wenn sich Rechenzentren mit geringer Bandbreite/hoher Latenz im geografischen Raum befinden**

![Gestreckter Pool für beständigen Chat mit geringer Bandbreite/hoher Latenz](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

