---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dieses Thema führt Sie durch den Vorgang zum Entfernen eines Front-End-Pools oder eines Front-End-Servers der Standard Edition. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Prozesses zum Entfernen des Pools. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL Store-Definition aus dem Topology Builder entfernen.
ms.openlocfilehash: d3397b47f94a96cde3326b2479a9e5c6ffd365e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813003"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Entfernen eines Front-End-Pools oder Standard Edition-Servers

Dieser Artikel führt Sie durch den Vorgang zum Entfernen eines Front-End-Pools oder eines Standard Edition-Front-End-Servers. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Prozesses zum Entfernen des Pools. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL Store-Definition aus dem Topology Builder entfernen.
  
## <a name="to-remove-a-front-end-server-pool"></a>So entfernen Sie einen Front-End-Server Pool

1. Öffnen Sie den Topologie-Generator.
    
2. Navigieren Sie zum Legacy Knoten.
    
3. Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool, klicken Sie mit der rechten Maustaste auf den zu entfernenden Frontend-Pool, und klicken Sie dann auf **Löschen**.
    
4. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Legacy Bereitstellungs-Assistenten nach Bedarf aus. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>So entfernen Sie einen Front-End-Server der Standard Edition

1. Öffnen Sie den Topologie-Generator.
    
2. Navigieren Sie zum Knoten Legacy Installationen.
    
3. Erweitern Sie die **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.
    
4. Erweitern Sie **SQL Stores**, klicken Sie mit der rechten Maustaste auf die SQL Server-Datenbank, die dem Front-End-Server der Standard Edition zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
    > [!IMPORTANT]
    > Sie müssen die Definition der SQL Server-Datenbanken vom Standard Edition-Front-End-Server entfernen. 
  
5. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Bereitstellungs-Assistenten nach Bedarf aus. 
    

