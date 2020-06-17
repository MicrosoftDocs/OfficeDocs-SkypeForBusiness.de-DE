---
title: Migrieren von mehreren Standorten und Pools
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
description: 'Skype for Business Server 2019 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Vorgang der Migration mehrerer Pools zu Skype for Business Server 2019 erfordert folgende Überlegungen:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752657"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

Skype for Business Server 2019 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Vorgang der Migration mehrerer Pools zu Skype for Business Server 2019 erfordert folgende Überlegungen: 
  
1. Nachdem Sie einen Skype for Business Server 2019-Pilot Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den Skype for Business Server 2019-Pool verschoben werden, und eine Methode zur Überprüfung der Funktionalität der Benutzer. Nachdem Sie beispielsweise einen Benutzer in den Pilot Pool verschoben haben, stellen Sie sicher, dass die konferenzrichtlinie des Benutzers zu Skype for Business Server 2019 verschoben wurde. 
    
2. Nachdem Sie eine Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.

3. Beständiger Chat, SQL-Spiegelung und XMPP-Funktionalität sind in Skype for Business Server 2019 veraltet und nicht mehr als Skype for Business Server 2019-Features verfügbar, aber Sie können in einer Umgebung mit Koexistenz fortgesetzt werden, wenn Sie zuvor in einer Legacyumgebung bereitgestellt wurden. Wenn Sie diese Funktionen weiterhin verwenden möchten, sollten Sie mit einer Koexistenz-Umgebung fortfahren, in der bestimmte Benutzer in älteren Pools verbleiben sollen.
    
4. Nach dem Übergang der Edgeserver der Verbund Routen zu den Pilot Skype for Business Server 2019-Edgeserver müssen Sie überprüfen, ob Verbundbenutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.
    
5. Nachdem Sie alle Benutzer und nicht-Benutzer Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Legacy Pool leer ist.
    
6. Nachdem Sie überprüft haben, dass der Legacy Pool leer ist, können Sie den Pool deaktivieren. 
    
    Ausführliche Informationen zum Deaktivieren des Legacy Pools und der Server finden Sie unter [Phase 8: decommission Legacy Pools](phase-8-decommission-legacy-pools.md).
    

