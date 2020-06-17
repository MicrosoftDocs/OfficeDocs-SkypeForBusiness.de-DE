---
title: Entfernen eines Front-End-Servers aus einem Pool
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
description: Das Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Er muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752317"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Entfernen eines Front-End-Servers aus einem Pool

Das Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Er muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.
  
In diesem Thema wird erläutert, wie Sie eine einzelne Front-End-Server aus einer vorhandenen Front-End-Pool entfernen. Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen, finden Sie weitere Informationen unter [Entfernen von Front-End-Pool oder Standard Edition-Server](remove-front-end-pool-or-standard-edition-server.md). Es ist nicht erforderlich, die einzelnen Front-End-Server zu entfernen, bevor Sie die Front-End-Pool entfernen. Wenn Sie den Pool entfernen, entfernen Sie die einzelnen Front-End-Server.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>So entfernen Sie einen Front-End-Server aus einem Pool

1. Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie zum Knoten Legacy Installation.
    
3. Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie die Front-End-Pool mit der Front-End-Server, die Sie entfernen möchten, klicken Sie mit der rechten Maustaste auf das Front-End-Server, das Sie entfernen möchten, und klicken Sie dann auf **Löschen**.
    

