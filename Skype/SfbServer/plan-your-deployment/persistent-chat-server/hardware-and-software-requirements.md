---
title: Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu den Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015 zu erhalten.'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418445"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema finden Sie Informationen zu den Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat kann mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition installiert werden. Die Anforderungen hängen davon ab, welche Version von Skype for Business Server 2015 Sie installiert haben und welche Leistungsanforderungen Ihr Unternehmen hat. Die Enterprise Edition kann bis zu 80.000 gleichzeitige Benutzer und die Standard Edition bis zu 20.000 gleichzeitige Benutzer unterstützen. Beständiger Chat besteht aus einer Front-End-Komponente sowie einer Back-End-SQL-Datenbankkomponente.
  
Bevor Sie den Server für beständigen Chat bereitstellen, müssen Sie sicherstellen, dass die folgenden Hardware-und Softwareanforderungen erfüllt sind:
  
- Hardware, die Mindestanforderungen erfüllt, um Skype for Business Server 2015, beständigen Chat Server, Datenbankserver und Dateiserver zu unterstützen. Weitere Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Unterstützte Betriebssystem- und Datenbanksoftware.
    
    Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware sowie zu den Windows Update-Anforderungen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype for Business Server 2015-Front-End-Server. Der Front-End-Server ist die Grundlage für das SIP-Routing (Session Initiation Protocol), mit dem die Kommunikation zwischen Computern, auf denen der beständige Chat Server ausgeführt wird, und der Funktion für beständigen Chat ermöglicht wird. 
    
- Message Queuing-Software. Wird vom beständigen Chat Server und dem beständigen Chat-Kompatibilitätsdienst verwendet, falls bereitgestellt.
    
In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die persistenten Chat-Daten gespeichert sind.

> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
  
## <a name="front-end-server-requirements"></a>Anforderungen an den Front-End-Server

Die Anforderungen an den Front-End-Server hängen davon ab, ob Sie den beständigen Chat Server mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition bereitstellen.
  
- Wenn Sie einen beständigen Chat Server mit Skype for Business Server 2015 Enterprise Edition bereitstellen, können Sie den beständigen Chat Server-Front-End-Server auf einem oder mehreren eigenständigen Computern im Enterprise Edition-Pool bereitstellen. Sie können die collocate-Front-End-Server auf dem Skype for Business Server 2015-Front-End-Server nicht übernehmen. 
    
    Ein einzelner beständiger Chat Server-Front-End-Server kann 20.000-aktive Benutzer unterstützen. Sie können einen beständigen Chat-Server Pool mit bis zu vier aktiven Front-Ends haben, wodurch insgesamt 80.000 gleichzeitige Benutzer unterstützt werden. 
    
- Wenn Sie mit dem Server für beständigen Chats mit Skype for Business Server 2015 Standard Edition arbeiten, können Sie den beständigen Chat mit dem Front-End-Server collocate. Diese Bereitstellung mit einem einzelnen Server kann bis zu 20.000 Benutzer unterstützen. 
    
## <a name="persistent-chat-server-database-requirements"></a>Datenbankanforderungen für beständigen Chat Server

Der Server für beständigen Chat erfordert die SQL Server-Datenbanksoftware zum Speichern des Chatroom-Verlaufs und-Inhalts, der Konfigurationsdaten, der Benutzer Bereitstellungsdaten und anderer relevanter Metadaten. Optional wird die Compliance-Datenbank für beständigen Chat verwendet, um Kompatibilitätsdaten zu speichern. Datenbanken für beständigen Chat können mit demselben SQL-Server oder sogar derselben SQL-Instanz wie die Back-End-Datenbanken verbunden werden. 
  
- Wenn Sie den Server für beständigen Chats mit Skype for Business Server 2015 Enterprise Edition installieren, sollten Sie den Dateispeicher für beständigen Chat installieren, um eine optimale Leistung zu gewährleisten.
    
- Wenn Sie den Server für beständigen Chats mit Skype for Business Server 2015 Standard Edition installieren, können Sie den beständigen Chat-Speicher-Back-End-Server auf der lokalen SQL Server Express-Instanz bereitstellen.
    
- Die persistent Chat-Datenbank (MGC) und die Compliance-Datenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf verschiedenen SQL-Servern befinden.
    
Beim Vorbereiten einer Datenbankserverplattform müssen Sie sich vergewissern, dass jeder Computer die Hardwareanforderungen erfüllt, bevor Sie die erforderliche Software installieren. Die Server Plattform für die persistenten Chat-Datenbankserver erfordert dieselbe Hardware wie der Back-End-Datenbankserver von Skype for Business Server 2015. Weitere Einzelheiten finden Sie in [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Stellen Sie sicher, dass auf dem Datenbankserver eine der folgenden Softwareanwendungen installiert ist:

- Microsoft SQL Server 2017 mit dem neuesten Service Pack

- Microsoft SQL Server 2016 mit Service Pack 1, und Sie müssen mit dem kumulativen Update 7 oder höheren Versionen von Skype for Business Server ausgeführt werden. Wir empfehlen, SQL Server 2016 mit dem neuesten Service Pack zu führen. Informationen zum Installieren von Microsoft SQL Server 2016 finden Sie unter [Installieren von SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014, und Sie müssen das kumulative Update 6 oder höhere Versionen von Skype for Business Server ausführen. Wir empfehlen, SQL Server 2014 mit dem neuesten Service Pack zu führen. Informationen zum Installieren von Microsoft SQL Server 2014 finden Sie unter [Installieren von SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten. Informationen zum Installieren von Microsoft SQL Server 2012 finden Sie unter [Installieren von SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für beständigen Chat Server

Details zum Erwerb von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Datei speichern finden Sie unter [Bereitstellen von Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie in den folgenden Themen:
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

