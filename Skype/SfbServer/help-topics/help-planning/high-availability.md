---
title: Hohe Verfügbarkeit (Planungstool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server 2015 basiert auf serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.
ms.openlocfilehash: a866784f94dd2e2c861aa93c482b40946da7ac7d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829005"
---
# <a name="high-availability-planning-tool"></a>Hohe Verfügbarkeit (Planungstool)
 
Das Hauptschema für hohe Verfügbarkeit für die meisten Serverrollen in Skype for Business Server 2015 basiert auf serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.
  
Skype for Business Server 2015 erfordert mindestens zwei Front-End-Server, um hohe Verfügbarkeit zu ermöglichen. Das Planungstool ermittelt anhand der folgenden Kriterien, ob zusätzliche Server hinzugefügt werden, um hohe Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung zwei oder mehr Front-End-Server enthält, fügt das Planungstool keinen zusätzlichen Server hinzu.
    
- Wenn die Bereitstellung Edgeserver enthält, wird ein zusätzlicher Server hinzugefügt. 
    
- Wenn die Bereitstellung den beständigen Chat enthält, fügt das Planungstool einen zusätzlichen Server hinzu, erhöht jedoch nicht die Poolnummer. Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungstool das Hinzufügen eines zusätzlichen Servers (für insgesamt fünf Server) vor, es wird jedoch ein einzelner Pool beibehalten. 
    
Das Planungstool fügt außerdem eine Spiegeldatenbank SQL Datenbanken hinzu. Wenn z. B. eine Front-End-SQL Server-Datenbank vorhanden ist, fügt das Planungstool die andere Datenbank als Spiegeldatenbank für diese hinzu und benennen sie als "Front-End-SQL Datenbank.
  
Weitere Informationen zum Vorbereiten Ihrer Umgebung auf hohe Verfügbarkeit finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

