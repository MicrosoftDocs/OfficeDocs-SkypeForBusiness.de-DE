---
title: Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015 zu erfahren.'
ms.openlocfilehash: a8ee506d9bee1e99727dab2da18f70f3c6278664
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630429"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat kann mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition installiert werden. Die Anforderungen hängen davon ab, welche Edition von Skype for Business Server 2015 Sie installiert haben, und von den Leistungsanforderungen Ihres Unternehmens. Enterprise Edition können bis zu 80.000 gleichzeitige Benutzer unterstützen. Standard Edition können bis zu 20.000 gleichzeitige Benutzer unterstützen. Der beständige Chat besteht aus einer Front-End-Komponente sowie einer Back-End-SQL-Datenbankkomponente.
  
Bevor Sie den Server für beständigen Chat bereitstellen, müssen Sie sicherstellen, dass die folgenden Hardware- und Softwareanforderungen erfüllt sind:
  
- Hardware, die die Mindestanforderungen zur Unterstützung von Skype for Business Server 2015, dem Server für beständigen Chat, Datenbankservern und Dateiservern erfüllt. Weitere Informationen finden Sie unter [Serveranforderungen für Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Unterstützte Betriebssystem- und Datenbanksoftware.
    
    Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware sowie Windows Updateanforderungen finden Sie unter [Serveranforderungen für Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Skype for Business Server 2015 Front-End-Server. Der Front-End-Server ist die Grundlage für sip-Routing (Session Initiation Protocol), wodurch die Kommunikation zwischen Computern, auf denen der Server für beständigen Chat ausgeführt wird, und der Funktion für beständigen Chat ermöglicht wird. 
    
- Message Queuing-Software. Wird vom Server für beständigen Chat und vom Konformitätsdienst für beständigen Chat verwendet, falls bereitgestellt.
    
In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die Daten des beständigen Chats gespeichert werden.

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="front-end-server-requirements"></a>Anforderungen an den Front-End-Server

Die Anforderungen an den Front-End-Server hängen davon ab, ob Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition bereitstellen.
  
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition bereitstellen, können Sie den Front-End-Server für den Server für beständigen Chat auf einem oder mehreren eigenständigen Computern im pool Enterprise Edition bereitstellen. Sie können die Front-End-Server für beständigen Chat nicht auf dem Front-End-Server Skype for Business Server 2015 verbinden. 
    
    Ein einzelner Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen. Sie können über einen Serverpool für beständigen Chat mit bis zu 4 aktiven Front-Ends verfügen, wodurch insgesamt 80.000 gleichzeitige Benutzer unterstützt werden. 
    
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Standard Edition bereitstellen, können Sie den beständigen Chat mit dem Front-End-Server verbinden. Diese Bereitstellung mit einem einzelnen Server kann bis zu 20.000 Benutzer unterstützen. 
    
## <a name="persistent-chat-server-database-requirements"></a>Datenbankanforderungen für den Server für beständigen Chat

Für den Server für beständigen Chat ist SQL Server Datenbanksoftware zum Speichern des Chatroomverlaufs und von Inhalten, Konfigurationsdaten, Benutzerbereitstellungsdaten und anderen relevanten Metadaten erforderlich. Optional wird die Konformitätsdatenbank für beständigen Chat zum Speichern von Compliancedaten verwendet. Datenbanken für beständigen Chat können mit demselben SQL Server oder sogar derselben SQL Instanz wie die Back-End-Datenbanken verbunden werden. 
  
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition installieren, wird empfohlen, den Dateispeicher für beständigen Chat zu installieren, um eine optimale Leistung sicherzustellen.
    
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Standard Edition installieren, können Sie den Server für beständigen Chat Store Back-End-Server auf der lokalen SQL Server Express Instanz bereitstellen.
    
- Die Datenbank für beständigen Chat (mgc) und die Konformitätsdatenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf verschiedenen SQL Servern befinden.
    
Um eine Datenbankserverplattform vorzubereiten, stellen Sie sicher, dass jeder Computer die Hardwareanforderungen erfüllt, und installieren Sie dann die erforderliche Software. Die Serverplattform für die Datenbankserver für beständigen Chat erfordert die gleiche Hardware wie der Back-End-Datenbankserver Skype for Business Server 2015. Ausführliche Informationen finden Sie unter [Serveranforderungen für Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
Stellen Sie sicher, dass auf dem Datenbankserver eine der folgenden Softwareanwendungen installiert ist:

- Microsoft SQL Server 2017 mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 mit Service Pack 1, und Sie müssen mit Skype for Business Server kumulativen Update 7 oder höher ausführen. Es wird empfohlen, SQL Server 2016 mit dem neuesten Service Pack auszuführen. Ausführliche Informationen zur Installation von Microsoft SQL Server 2016 finden Sie unter [Install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014, und Sie müssen mit Skype for Business Server kumulativen Update 6 oder höher ausführen. Es wird empfohlen, SQL Server 2014 mit dem neuesten Service Pack auszuführen. Ausführliche Informationen zur Installation von Microsoft SQL Server 2014 finden Sie unter [Install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack. Ausführliche Informationen zur Installation von Microsoft SQL Server 2012 finden Sie unter [Install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110)).

## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für den Server für beständigen Chat

Ausführliche Informationen zum Abrufen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Dateispeichern finden Sie unter [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie in den folgenden Themen:
  
- [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
