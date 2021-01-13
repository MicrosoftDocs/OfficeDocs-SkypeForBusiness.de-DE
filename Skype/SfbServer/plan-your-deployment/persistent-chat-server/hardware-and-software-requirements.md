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
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über die Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 32ba0d94679e6f326fa1821cbe3401d031854037
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834535"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat kann mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition installiert werden. Die Anforderungen hängen von der installierten Edition von Skype for Business Server 2015 und den Leistungsanforderungen Ihres Unternehmens ab. Enterprise Edition kann bis zu 80.000 gleichzeitige Benutzer unterstützen. Standard Edition kann bis zu 20.000 gleichzeitige Benutzer unterstützen. Der beständigen Chat besteht aus einer Front-End-Komponente sowie einer Back-End-SQL Datenbankkomponente.
  
Bevor Sie den Server für beständigen Chat bereitstellen, müssen Sie sicherstellen, dass die folgenden Hardware- und Softwareanforderungen erfüllt sind:
  
- Hardware, die die Mindestanforderungen für die Unterstützung von Skype for Business Server 2015, Persistent Chat Server, Datenbankservern und Dateiservern erfüllt. Weitere Informationen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015".](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Unterstützte Betriebssystem- und Datenbanksoftware.
    
    Weitere Informationen zu unterstützten Betriebssystemen und Datenbanksoftware sowie Zusicherungen an Windows Update finden Sie unter [den Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype for Business Server 2015 Front-End-Server. Der Front-End-Server ist die Grundlage für sip-Routing (Session Initiation Protocol), wodurch die Kommunikation zwischen Computern, auf denen der Server für beständigen Chat ausgeführt wird, und der Funktion für beständigen Chat möglich ist. 
    
- Message Queuing-Software. Wird vom Server für beständigen Chat und dem Kompatibilitätsdienst für beständigen Chat verwendet, sofern bereitgestellt.
    
In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die Daten des beständigen Chats gespeichert werden.

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="front-end-server-requirements"></a>Anforderungen an den Front-End-Server

Die Anforderungen an den Front-End-Server hängen davon ab, ob Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition oder Standard Edition bereitstellen.
  
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition bereitstellen, können Sie den Front-End-Server für beständigen Chat auf einem oder mehreren eigenständigen Computern im Enterprise Edition-Pool bereitstellen. Sie können die Front-End-Server für beständigen Chat nicht auf dem Skype for Business Server 2015-Front-End-Server verbinden. 
    
    Ein einzelner Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen. Sie können über einen Pool für den Server für beständigen Chat mit bis zu vier aktiven Front-Ends verfügen, wodurch insgesamt 80.000 gleichzeitige Benutzer unterstützt werden. 
    
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Standard Edition bereitstellen, können Sie den beständigen Chat mit dem Front-End-Server verbinden. Diese Einzelserverbereitstellung kann bis zu 20.000 Benutzer unterstützen. 
    
## <a name="persistent-chat-server-database-requirements"></a>Datenbankanforderungen für den Server für beständigen Chat

Der Server für beständigen Chat erfordert SQL Server Datenbanksoftware zum Speichern von Chatroomverlauf und -inhalten, Konfigurationsdaten, Benutzerbereitstellungsdaten und anderen relevanten Metadaten. Optional wird die Konformitätsdatenbank für beständigen Chat zum Speichern von Kompatibilitätsdaten verwendet. Datenbanken für beständigen Chat können auf derselben SQL Server oder sogar auf derselben SQL instanz wie die Back-End-Datenbanken. 
  
- Wenn Sie den Server für beständigen Chat mit Skype for Business Server 2015 Enterprise Edition installieren, wird empfohlen, den Dateispeicher für beständigen Chat zu installieren, um eine optimale Leistung sicherzustellen.
    
- Wenn Sie den Server für beständigen Chat mit der Skype for Business Server 2015 Standard Edition installieren, können Sie den Back-End-Server für den Speicher für beständigen Chat auf der lokalen SQL Server Express-Instanz bereitstellen.
    
- Die Datenbank für beständigen Chat (mgc) und die Kompatibilitätsdatenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf unterschiedlichen SQL befinden.
    
Stellen Sie zum Vorbereiten einer Datenbankserverplattform sicher, dass jeder Computer die Hardwareanforderungen erfüllt, und installieren Sie dann die erforderliche Software. Die Serverplattform für die Datenbankserver für beständigen Chat erfordert die gleiche Hardware wie der Skype for Business Server 2015-Back-End-Datenbankserver. Weitere Informationen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015".](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
Stellen Sie auf dem Datenbankserver sicher, dass eine der folgenden Softwareanwendungen installiert ist:

- Microsoft SQL Server 2017 mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 mit Service Pack 1, und Sie müssen mit dem kumulativen Update 7 oder höher von Skype for Business Server ausgeführt werden. Es wird empfohlen, SQL Server 2016 mit dem neuesten Service Pack zu verwenden. Weitere Informationen zum Installieren von Microsoft SQL Server 2016 finden Sie unter [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014, und Sie müssen mit dem kumulativen Update 6 oder höher von Skype for Business Server ausgeführt werden. Es wird empfohlen, SQL Server 2014 mit dem neuesten Service Pack zu verwenden. Weitere Informationen zum Installieren von Microsoft SQL Server 2014 finden Sie unter [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. Weitere Informationen zum Installieren von Microsoft SQL Server 2012 finden Sie unter [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für den Server für beständigen Chat

Weitere Informationen zum Erwerb von Zertifikaten, zum Erstellen SQL Server datenbank und zum Erstellen von Dateispeichern finden Sie unter [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie in den folgenden Themen:
  
- [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Umgebungsanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

