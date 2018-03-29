---
title: Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Zusammenfassung: Lesen Sie in diesem Thema, um Informationen zu Hardware- und softwareanforderungen für die Archivierung in Skype für Business Server 2015 zu informieren.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie in diesem Thema, um Informationen zu Hardware- und softwareanforderungen für die Archivierung in Skype für Business Server 2015 zu informieren.
  
Skype für die Archivierung Business Server 2015 ist nun Teil der Front-End-Rolle, daher Sie keinen separaten Server installieren müssen. Sie müssen jedoch die folgenden Anforderungen berücksichtigen:
  
- Infrastrukturanforderungen
    
- Erforderliche Softwareanforderungen
    
- Datenspeicherungsanforderungen
    
## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen

Skype für Business-Archivierung infrastrukturanforderungen sind die gleichen wie bei der Bereitstellung von Skype für Business Server. Weitere Informationen hierzu finden Sie unter [Anforderungen für Ihre Skype für Business-Umgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
## <a name="prerequisite-software-requirements"></a>Erforderliche Softwareanforderungen

Archivierung erforderlichen Komponenten für Skype für Business Server sind aufgrund der folgenden einfacher als in früheren Versionen von Lync Server: 
  
- Da eine Serverrolle Archivierung nicht mehr ist, müssen Sie nicht auf einen separaten Server für die Archivierung zu installieren. Stattdessen werden auf jedem Front-End-Pool der Enterprise Edition und auf jedem Server der Standard Edition automatisch einheitliche Datensammlungs-Agents installiert und aktiviert. Sie müssen Ihre Archivierungstopologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.
    
- Archivierung werden die Skype für Business Server-Dateispeicher für die temporäre Speicherung von Dateien, sodass keine separate dateispeicherung für die Archivierung eingerichtet werden mit Besprechungsinhalten verwendet.
    
- In Skype für Business Server ist das Microsoft Message Queuing nicht erforderlich.
    
## <a name="data-storage-requirements"></a>Datenspeicherungsanforderungen

Die Infrastruktur für Archivierungsspeicher muss eingerichtet werden. Dies umfasst eine oder beide der folgenden Optionen:
  
- **Microsoft Exchange-Speicher**. Dateien mit Besprechungsinhalten, z. B. PowerPoint-Präsentationen, werden als Anlagen archiviert. Wenn Sie Skype für Geschäftsdaten für Archivierung mit Exchange Kompatibilitätsdaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und stellen Sie sicher, dass die maximale Speichergröße Speicherung von der Besprechung Inhaltsdateien unterstützt. Sie müssen vor dem Bereitstellen und Aktivieren der Archivierung die Option Microsoft Exchange-Integration mit Exchange bereitstellen. 
    
    Wenn Sie Exchange-Speicher verwenden, müssen Sie nicht zum Bereitstellen von separater SQL Server-Datenbanken für die Archivierung, es sei denn, Sie Skype für Unternehmensbenutzer verfügen, die nicht auf Ihren Exchange-Servern verwaltet werden. Wenn Sie die Archivierung die Option Microsoft Exchange-Integration mit bereitstellen, wird Skype für Geschäftsdaten-Archivierung mit Exchange Kompatibilitätsdaten nur für die Benutzer gespeichert, die auf Ihren Exchange-Servern verwaltet werden. 
    
- **Skype als Archivierungsspeicher Business Server**. Zur Unterstützung von Benutzern, die nicht auf Exchange-Servern verwaltet werden, oder wenn Sie nicht die Option Microsoft Exchange-Integration verwenden möchten, müssen Sie Archivierungsspeicher mithilfe einer SQL Server-Datenbank bereitstellen. Skype für Business Server unterstützt die folgenden 64-Bit-Versionen von SQL Server:
    
  - Microsoft SQL Server 2008 R2 Enterprise
    
  - Microsoft SQL Server 2008 R2 Standard
    
  - Microsoft SQL Server 2012 Enterprise
    
  - Microsoft SQL Server 2012 Standard
    
  - Microsoft SQL Server 2014 Enterprise
    
  - Microsoft SQL Server 2014 Standard
    
    > [!NOTE]
    > Microsoft SQL Server Express-Versionen werden für die Archivierung nicht unterstützt. 32-Bit-Versionen von SQL Server werden nicht unterstützt. Zusätzliche Anforderungen für SQL Server und Einschränkungen finden Sie unter [Anforderungen für Ihre Skype für Business-Umgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
    Sie müssen die SQL Server-Plattformen vor der Bereitstellung und Aktivieren der Archivierung einrichten. Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen der Topologie erstellen. Sie können die Datenbank auch später erstellen, z. B. im Rahmen des Installationsverfahrens. Ausführliche Informationen zu SQL Server finden Sie im [SQL Server-TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
    Die Auslastung im Zuge der Archivierung kann erheblich steigen. Aus diesem Grund sollten Sie sicherstellen, dass Speicherplatz für Front-End-Servern geeignet ist, auf dem die Archivierung aktiviert ist.
    

