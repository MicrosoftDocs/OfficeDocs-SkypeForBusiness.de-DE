---
title: Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Zusammenfassung: in diesem Thema erfahren Sie mehr über die Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213231"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat kann mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition installiert werden. Die Anforderungen hängen von der installierten Skype for Business Server 2015 Edition und den Leistungsanforderungen Ihres Unternehmens ab. Enterprise Edition kann bis zu 80.000 gleichzeitige Benutzer unterstützen. Standard Edition kann bis zu 20.000 gleichzeitige Benutzer unterstützen. Der beständige Chat besteht aus einer Front-End-Komponente und einer Back-End-SQL-Datenbankkomponente.
  
Bevor Sie den Server für beständigen Chat bereitstellen, müssen Sie sicherstellen, dass die folgenden Hardware-und Softwareanforderungen erfüllt sind:
  
- Hardware, die Mindestanforderungen zur Unterstützung von Skype for Business Server 2015, beständigen Chat Server, Datenbankservern und Dateiservern erfüllt. Weitere Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Unterstützte Betriebssystem-und Datenbanksoftware.
    
    Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware sowie Windows Update-Anforderungen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype for Business Server 2015 Front-End-Server. Das Front-End-Server ist die Grundlage für das SIP-Routing (Session Initiation Protocol), das die Kommunikation zwischen Computern mit persistent Chat Server und der Funktion für beständigen Chat ermöglicht. 
    
- Message Queuing-Software. Wird vom beständigen Chat Server und dem Kompatibilitätsdienst für beständigen Chat verwendet, sofern bereitgestellt.
    
In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die Daten für beständigen Chat gespeichert sind.

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird in Skype for Business Server 2019 jedoch nicht mehr unterstützt. Die gleiche Funktionalität ist in Microsoft Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiter verwenden. 
  
## <a name="front-end-server-requirements"></a>Front-End-Server Anforderungen

Front-End-Server Anforderungen hängen davon ab, ob Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition bereitstellen.
  
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition bereitstellen, können Sie den Server für beständigen Chat Front-End-Server auf einem oder mehreren eigenständigen Computern im Enterprise Edition-Pool bereitstellen. Sie können die Front-End-Server für beständigen Chat im Skype for Business Server 2015 Front-End-Server nicht collocate. 
    
    Eine einzelne Server Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen. Sie können einen Server Pool für beständigen Chat mit bis zu 4 aktiven Front-Ends unterstützen, wodurch insgesamt 80.000 gleichzeitige Benutzer unterstützt werden. 
    
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Standard Edition bereitstellen, können Sie den beständigen Chat mit dem Front-End-Server collocate. Diese Bereitstellung mit einem Server kann bis zu 20.000 Benutzer unterstützen. 
    
## <a name="persistent-chat-server-database-requirements"></a>Datenbankanforderungen für beständigen Chat Server

Der Server für beständigen Chat erfordert SQL Server Datenbanksoftware zum Speichern des Chatroom-Verlaufs und des Inhalts, der Konfigurationsdaten, der Benutzerdaten und anderer relevanter Metadaten. Optional wird die Compliance-Datenbank für beständigen Chat zum Speichern von Kompatibilitätsdaten verwendet. Datenbanken für beständigen Chat können sich auf demselben SQL Server oder sogar auf der gleichen SQL-Instanz wie die Back-End-Datenbanken befinden. 
  
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition installieren, wird empfohlen, den Dateispeicher für beständigen Chat zu installieren, um eine optimale Leistung sicherzustellen.
    
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Standard Edition installieren, können Sie den Back-End-Server für beständigen Chat auf der lokalen SQL Server Express-Instanz bereitstellen.
    
- Die Datenbank für beständigen Chat (MGC) und die Kompatibilitätsdatenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf verschiedenen SQL-Servern befinden.
    
Um eine Datenbankserverplattform vorzubereiten, stellen Sie sicher, dass jeder Computer die Hardwareanforderungen erfüllt, und installieren Sie dann die erforderliche Software. Die Server Plattform für die Datenbankserver für beständigen Chat erfordert die gleiche Hardware wie der Skype for Business Server 2015 Back-End-Datenbankserver. Ausführliche Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Stellen Sie sicher, dass eine der folgenden Softwareanwendungen auf dem Datenbankserver installiert ist:

- Microsoft SQL Server 2017 mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 mit Service Pack 1, und Sie müssen mit Skype for Business Server kumulativen Update Version 7 oder höher ausgeführt werden. Es wurde empfohlen, SQL Server 2016 mit dem neuesten Service Pack auszuführen. Ausführliche Informationen zur Installation von Microsoft SQL Server 2016 finden Sie unter [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014, und Sie müssen mit Skype for Business Server kumulativen Update 6 oder höher ausgeführt werden. Es wurde empfohlen, SQL Server 2014 mit dem neuesten Service Pack auszuführen. Ausführliche Informationen zur Installation von Microsoft SQL Server 2014 finden Sie unter [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-Bit-Edition), und es wurde empfohlen, das neueste Service Pack auszuführen. Ausführliche Informationen zur Installation von Microsoft SQL Server 2012 finden Sie unter [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für den Server für beständigen Chat

Ausführliche Informationen zum Erwerb von Zertifikaten, zum Erstellen der SQL Server Datenbank und zum Erstellen von Datei speichern finden Sie unter [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu Hardware-und Softwareanforderungen finden Sie in den folgenden Themen:
  
- [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Umgebungsanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

