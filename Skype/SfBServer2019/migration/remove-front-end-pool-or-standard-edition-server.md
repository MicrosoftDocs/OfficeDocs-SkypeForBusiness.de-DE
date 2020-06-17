---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema werden Sie durch den Vorgang zum Entfernen einer Front-End-Pool oder einer Standard Edition Front-End-Server geführt. Wenn Sie ein Front-End-Pool entfernen, entfernen Sie alle Front-End-Server, die zum Pool gehören, als Teil des Prozesses zur Pool Entfernung. Wenn Sie eine Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-speicherdefinition aus dem Topologie-Generator entfernen.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752277"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Entfernen eines Front-End-Pools oder Standard Edition-Servers

Dieser Artikel führt Sie durch den Vorgang des Entfernens einer Front-End-Pool oder einer Standard Edition Front-End-Server. Wenn Sie ein Front-End-Pool entfernen, entfernen Sie alle Front-End-Server, die zum Pool gehören, als Teil des Prozesses zur Pool Entfernung. Wenn Sie eine Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-speicherdefinition aus dem Topologie-Generator entfernen.
  
## <a name="to-remove-a-front-end-server-pool"></a>So entfernen Sie einen Front-End-Server-Pool

1. Öffnen Sie den Topologie-Generator.
    
2. Navigieren Sie zum Knoten Legacy.
    
3. Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie die Front-End-Pool, klicken Sie mit der rechten Maustaste auf das Front-End-Pool, das Sie entfernen möchten, und klicken Sie dann auf **Löschen**.
    
4. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die Legacy Bereitstellung bei Bedarf aus. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>So entfernen Sie einen Standard Edition-Front-End-Server

1. Öffnen Sie den Topologie-Generator.
    
2. Navigieren Sie zum Knoten Legacy Installationen.
    
3. Erweitern Sie **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.
    
4. Erweitern Sie **SQL-Speicher**, klicken Sie mit der rechten Maustaste auf die SQL Server Datenbank, die der Standard Edition Front-End-Server zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
    > [!IMPORTANT]
    > Sie müssen die Definition der verbundenen SQL Server Datenbanken aus der Standard Edition Front-End-Server entfernen. 
  
5. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Bereitstellungs-Assistenten nach Bedarf aus. 
    

