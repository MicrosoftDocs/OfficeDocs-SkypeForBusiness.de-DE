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
ms.localizationpriority: medium
description: Der Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Er muss als Front-End-Pool definiert werden, auch wenn sich nur ein einzelner Computer im Pool befindet.
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594999"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Entfernen eines Front-End-Servers aus einem Pool

Der Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Er muss als Front-End-Pool definiert werden, auch wenn sich nur ein einzelner Computer im Pool befindet.
  
Dieses Thema führt Sie durch den Prozess des Entfernens eines einzelnen Front-End-Servers aus einem vorhandenen Front-End-Pool. Wenn der Front-End-Server der letzte Server im Pool ist oder Wenn Sie den Pool vollständig entfernen, lesen Sie ["Entfernen des Front-End-Pools oder Standard Edition Servers".](remove-front-end-pool-or-standard-edition-server.md) Es ist nicht erforderlich, die einzelnen Front-End-Server zu entfernen, bevor Sie den Front-End-Pool entfernen. Wenn Sie den Pool entfernen, entfernen Sie jeden Front-End-Server.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>So entfernen Sie einen Front-End-Server aus einem Pool

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 den Topologie-Generator.
    
2. Navigieren Sie zum Legacyinstallationsknoten.
    
3. Erweitern Sie **Enterprise Edition Front-End-Pools,** erweitern Sie den Front-End-Pool mit dem Front-End-Server, den Sie entfernen möchten, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **"Löschen".**
    

