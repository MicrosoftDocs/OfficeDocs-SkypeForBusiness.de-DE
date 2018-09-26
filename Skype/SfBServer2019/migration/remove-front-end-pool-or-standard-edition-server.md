---
title: Entfernen von Front-End-Pool oder Standard Edition-server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Thema führt Sie durch den Vorgang des Entfernens von einem Front-End-Pool oder Standard Edition-Front-End-Servers. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jedem Front-End-Server, die als Teil des Löschvorgangs Pool auf den Pool gehört. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-Speicher-Definition Topologie-Generator entfernen.
ms.openlocfilehash: 7e56f2e9ff57536d1f065452f299a9af33a46aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028887"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Entfernen von Front-End-Pool oder Standard Edition-server

Dieser Artikel führt Sie durch den Vorgang des Entfernens von einem Front-End-Pool oder Standard Edition-Front-End-Servers. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jedem Front-End-Server, die als Teil des Löschvorgangs Pool auf den Pool gehört. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-Speicher-Definition Topologie-Generator entfernen.
  
## <a name="to-remove-a-front-end-server-pool"></a>So entfernen einen Front-End-Server-pool

1. Topologie-Generator zu öffnen.
    
2. Navigieren Sie zum Knoten Vorversion.
    
3. Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool, mit der rechten Maustaste in des Front-End-Pools, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.
    
4. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann bei Bedarf legacy Bereitstellungs-Assistenten aus. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Entfernen eines Standard Edition-Front-End-Servers

1. Topologie-Generator zu öffnen.
    
2. Navigieren Sie zum Knoten Vorversion installiert.
    
3. Erweitern Sie **Standard Edition-Front-End-Server**rechten Maustaste auf den Front-End-Server, die Sie entfernen möchten, und klicken Sie dann auf **Löschen**.
    
4. Erweitern Sie **SQL-Speicher**, mit der rechten Maustaste in der SQL Server-Datenbank, die mit dem Standard Edition-Front-End-Server verbunden ist, und klicken Sie dann auf **Löschen**.
    
    > [!IMPORTANT]
    > Sie müssen die Definition der verbundenen SQL Server-Datenbanken aus dem Standard Edition-Front-End-Server entfernen. 
  
5. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann je nach Bedarf den Bereitstellungs-Assistenten aus. 
    

