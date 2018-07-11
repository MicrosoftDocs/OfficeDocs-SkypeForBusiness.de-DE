---
title: Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015 erhalten.'
ms.openlocfilehash: 8db3bda71cb27ec059dcf4c73f8d4754ffcb8b2d
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246656"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zu Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015 erhalten.
  
Persistent Chat-Server kann mit Skype für Business Server 2015 Enterprise Edition oder Standard Edition installiert werden. Anforderungen hängen davon ab, welche Edition von Skype für Business Server 2015 Sie installiert haben, und die leistungsanforderungen Ihres Unternehmens. Die Enterprise Edition kann bis zu 80.000 gleichzeitige Benutzer und die Standard Edition bis zu 20.000 gleichzeitige Benutzer unterstützen. Beständiger Chat besteht aus einer Front-End-Komponente sowie einer Back-End-SQL-Datenbankkomponente.
  
Bevor Sie Persistent Chat Server bereitstellen, müssen Sie sicherstellen, dass die folgenden Hardware und Software-Anforderungen erfüllt sind:
  
- Hardware, die zur Unterstützung von Skype für Business Server 2015, Persistent Chat Server, Datenbankserver und Dateiserver Mindestanforderungen erfüllt. Weitere Informationen finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Unterstützte Betriebssystem- und Datenbanksoftware.
    
    Ausführliche Informationen zu unterstützten Betriebssysteme und Datenbank-Software und Windows aktualisieren Sie Anforderungen zu, finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype für Business Server 2015 Front-End-Server. Der Front-End-Server ist die Grundlage für Session Initiation Protocol (SIP) routing, die Kommunikation zwischen Computern mit Persistent Chat Server und die Funktionalität beständigen Chat ermöglicht. 
    
- Message Queuing-Software. Wird von den Persistent Chat Server und Kompatibilität für Persistent Chat-Dienst verwendet, wenn bereitgestellt.
    
Den folgenden Abschnitten werden die spezifischen Anforderungen für Persistent Chat Server und die Datenbank, die die beständigen Chat Daten gespeichert werden.
  
## <a name="front-end-server-requirements"></a>Anforderungen an den Front-End-Server

Anforderungen für Front-End-Server hängen davon ab, ob Sie Persistent Chat Server mit Skype für Business Server 2015 Enterprise Edition oder Standard Edition bereitstellen.
  
- Wenn Sie Persistent Chat Server mit Skype für Business Server 2015 Enterprise Edition bereitstellen, können Sie die Persistent Chat Server-Front-End-Server auf einem oder mehreren eigenständigen Computern in der Enterprise Edition-Pool bereitstellen. Sie können nicht den beständigen Chat Front-End-Servern auf die Skype für Business Server 2015 Front-End-Server verbinden. 
    
    Eine einzelne Persistent Chat Server-Front-End-Server kann 20.000 aktive Benutzer unterstützen. Sie können einen Persistent Chat Server Pool mit bis zu 4 aktiven Front-Ends dadurch insgesamt 80.000 gleichzeitige Benutzer unterstützen müssen. 
    
- Wenn Sie Persistent Chat Server mit Skype Business Server 2015 Standard Edition bereitstellen, können Sie die beständigen Chat mit dem Front-End-Server verbinden. Diese Bereitstellung mit einem einzelnen Server kann bis zu 20.000 Benutzer unterstützen. 
    
## <a name="persistent-chat-server-database-requirements"></a>Persistent Chat-Server-Anforderungen der Suchdatenbanken

Persistent Chat-Server erfordert SQL Server-Datenbanksoftware chatroomverlauf und Inhalte, Daten zur Konfiguration, benutzerbereitstellungsdaten und anderen relevanten Metadaten gespeichert. Optional, verwendet er die Persistent Chat Kompatibilitätsdatenbank die Kompatibilitätsdaten speichern. Datenbanken für beständigen Chat können mit demselben SQL-Server oder sogar derselben SQL-Instanz wie die Back-End-Datenbanken verbunden werden. 
  
- Wenn Sie Persistent Chat Server mit Skype für Business Server 2015 Enterprise Edition installieren, um eine optimale Leistung zu gewährleisten empfiehlt es, den Dateispeicher für beständigen Chat zu installieren.
    
- Wenn Sie Persistent Chat Server mit Skype für Business Server 2015 Standard Edition installieren, können Sie dem Persistent Chat Store Back End-Server auf der lokalen SQL Server Express-Instanz bereitstellen.
    
- Datenbank für beständigen Chat (Mgc) und die Kompatibilitätsdatenbank (Mgccomp) können in derselben Instanz von SQL Server oder auf unterschiedlichen SQL-Servern befinden.
    
Beim Vorbereiten einer Datenbankserverplattform müssen Sie sich vergewissern, dass jeder Computer die Hardwareanforderungen erfüllt, bevor Sie die erforderliche Software installieren. Die Serverplattform für den beständigen Chat Datenbankservern erfordert die gleiche Hardware wie der Skype für Business Server 2015 Back-End-Datenbankserver. Weitere Informationen hierzu finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Stellen Sie sicher, dass auf dem Datenbankserver eine der folgenden Softwareanwendungen installiert ist:

- Microsoft SQL Server 2016, und Sie müssen mit Skype für Business Server kumulative Update 7 oder höhere Versionen ausführen. Es wird empfohlen, SQL Server 2016 mit dem neuesten Servicepack ausgeführt. Ausführliche Informationen zum Installieren von Microsoft SQL Server 2016 finden Sie unter [Installieren von SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2012 (64-Bit-Edition), und wir empfohlen, mit dem neuesten Servicepack. Ausführliche Informationen zum Installieren von Microsoft SQL Server 2012 finden Sie unter [Installieren von SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

- Microsoft SQL Server 2008 R2 (64-Bit-Edition), und wir empfohlen, mit dem neuesten Servicepack. Ausführliche Informationen zur Installation von Microsoft SQL Server 2008 R2 finden Sie unter [SQL Server-Installation (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702). 
    
## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für persistent Chat Server

Weitere Informationen zum Erwerb von Zertifikaten SQL Server-Datenbank erstellen, und Erstellen von DateiSpeichern, finden Sie unter [Bereitstellen von Skype für Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie in den folgenden Themen:
  
- [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Anforderungen an die Umgebung für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

