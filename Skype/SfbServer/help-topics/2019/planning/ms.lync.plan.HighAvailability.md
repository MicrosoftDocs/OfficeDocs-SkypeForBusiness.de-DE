---
title: Hohe Verfügbarkeit (Planungstool)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Das Hauptfenster Hochverfügbarkeits-Schema für die meisten Serverrollen in Skype für Business Server basiert auf Serverredundanz über pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 9948fbc4f1daff73afa020b83357a26c185d7785
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19977264"
---
# <a name="high-availability-planning-tool"></a>Hohe Verfügbarkeit (Planungstool)
 
Das Hauptfenster Hochverfügbarkeits-Schema für die meisten Serverrollen in Skype für Business Server basiert auf Serverredundanz über pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
  
Skype für Business Server erfordert mindestens zwei Front-End-Servern, um hohe Verfügbarkeit zu aktivieren. Das Planungstool verwendet die folgenden Kriterien, um festzustellen, ob sie zusätzliche Server hinzufügen, um hohe Verfügbarkeit zu unterstützen:
  
- Wenn die Bereitstellung mindestens zwei Front-End-Server enthält, werden das Planungstool keinen zusätzlichen Server hinzugefügt.
    
- Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt. 
    
- Wenn die Bereitstellung beständigen Chat enthält, das Planungstool für das Hinzufügen eines zusätzlichen Servers, aber nicht erhöhen der Anzahl Pool. Angenommen, wenn die Bereitstellung bereits vier Servern enthält, das Planungstool schlägt (für insgesamt fünf Servern) einen weiteren Server hinzufügen jedoch behält einen einzelnen Pool. 
    
Das Planungstool fügt auch eine Spiegeldatenbank SQL für alle Datenbanken. Beispielsweise wenn eine Front-End-SQL Server-Datenbank vorhanden ist, wird das Planungstool die anderen Datenbank als der Spiegeldatenbank für diese Vorlage hinzufügen und nennen Sie es als"Front-End Spiegel SQL-Datenbank.
  
Weitere Informationen zur Vorbereitung Ihrer Umgebung für hohe Verfügbarkeit finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

