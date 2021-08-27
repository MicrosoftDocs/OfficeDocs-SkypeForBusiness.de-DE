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
ms.localizationpriority: medium
description: Dieses Thema führt Sie durch den Prozess des Entfernens eines Front-End-Pools oder eines Standard Edition Front-End-Servers. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Poolentfernungsprozesses. Wenn Sie einen Standard Edition Front-End-Server entfernen, müssen Sie die SQL Store Definition aus dem Topologie-Generator entfernen.
ms.openlocfilehash: 04ff2120fcbbe0c914a0a105669083eeb13a8347
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589249"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Entfernen eines Front-End-Pools oder Standard Edition-Servers

Dieser Artikel führt Sie durch den Prozess des Entfernens eines Front-End-Pools oder eines Standard Edition Front-End-Servers. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Poolentfernungsprozesses. Wenn Sie einen Standard Edition Front-End-Server entfernen, müssen Sie die SQL Store Definition aus dem Topologie-Generator entfernen.
  
## <a name="to-remove-a-front-end-server-pool"></a>So entfernen Sie einen Front-End-Server-Pool

1. Öffnen Sie den Topologie-Generator.
    
2. Navigieren Sie zum Legacyknoten.
    
3. Erweitern Sie **Enterprise Edition Front-End-Pools,** erweitern Sie den Front-End-Pool, klicken Sie mit der rechten Maustaste auf den Front-End-Pool, den Sie entfernen möchten, und klicken Sie dann auf **"Löschen".**
    
4. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Legacybereitstellungs-Assistenten nach Bedarf aus. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>So entfernen Sie einen Standard Edition-Front-End-Server

1. Öffnen Sie den Topologie-Generator.
    
2. Navigieren Sie zum Legacy-Installationsknoten.
    
3. Erweitern Sie **Standard Edition Front-End-Server,** klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **"Löschen".**
    
4. Erweitern Sie **SQL Speicher,** klicken Sie mit der rechten Maustaste auf die SQL Server Datenbank, die dem Standard Edition Front-End-Server zugeordnet ist, und klicken Sie dann auf **"Löschen".**
    
    > [!IMPORTANT]
    > Sie müssen die Definition der verbundenen SQL Server Datenbanken vom Standard Edition Front-End-Server entfernen. 
  
5. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Bereitstellungs-Assistenten nach Bedarf aus. 
    

