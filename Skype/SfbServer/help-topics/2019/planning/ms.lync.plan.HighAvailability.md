---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Das Hauptfenster Hochverfügbarkeits-Schema für die meisten Serverrollen in Skype für Business Server basiert auf Serverredundanz über pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 38887d576a6e15135d9ea35c1dd286ee8c052063
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889360"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Das Hauptfenster Hochverfügbarkeits-Schema für die meisten Serverrollen in Skype für Business Server basiert auf Serverredundanz über pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
  
Skype für Business Server erfordert mindestens zwei Front-End-Servern, um hohe Verfügbarkeit zu aktivieren. Das Planungstool verwendet die folgenden Kriterien, um festzustellen, ob sie zusätzliche Server hinzufügen, um hohe Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung mindestens zwei Front-End-Server enthält, werden das Planungstool keinen zusätzlichen Server hinzugefügt.
    
- Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt. 
    
- Wenn die Bereitstellung beständigen Chat enthält, das Planungstool für das Hinzufügen eines zusätzlichen Servers, aber nicht erhöhen der Anzahl Pool. Angenommen, wenn die Bereitstellung bereits vier Servern enthält, das Planungstool schlägt (für insgesamt fünf Servern) einen weiteren Server hinzufügen jedoch behält einen einzelnen Pool. 

    > [!NOTE] 
    > Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [upgrade Skype für Unternehmen, die Microsoft-Teams](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl migrieren Benutzer, die diese Funktionalität für Teams oder weiterhin Skype für Business Server 2015 verwenden. 

    
Das Planungstool fügt auch eine Spiegeldatenbank SQL für alle Datenbanken. Beispielsweise wenn eine Front-End-SQL Server-Datenbank vorhanden ist, wird das Planungstool die anderen Datenbank als der Spiegeldatenbank für diese Vorlage hinzufügen und nennen Sie es als"Front-End Spiegel SQL-Datenbank.
  
Weitere Informationen zur Vorbereitung Ihrer Umgebung für hohe Verfügbarkeit finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

