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
description: 'Skype for Business Server 2019 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Prozess der Migration mehrerer Pools zu Skype for Business Server 2019 erfordert die folgenden Überlegungen:'
ms.openlocfilehash: 445c519fd9a470002258ff50c14ebac7328979acc667c60a77b15a503ec3f3fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303439"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

Skype for Business Server 2019 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Prozess der Migration mehrerer Pools zu Skype for Business Server 2019 erfordert die folgenden Überlegungen: 
  
1. Nach der Bereitstellung eines Skype for Business Server 2019-Pilotpools müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den Skype for Business Server 2019-Pool verschoben werden, und eine Methodik für die Überprüfung der Funktionalität der Benutzer. Stellen Sie beispielsweise nach dem Verschieben eines Benutzers in den Pilotpool sicher, dass die Konferenzrichtlinie des Benutzers auf Skype for Business Server 2019 verschoben wurde. 
    
2. Nach der Bereitstellung eines Edgeservers im Pilotpool müssen Sie überprüfen, ob externe Benutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.

3. Die Funktionen für beständigen Chat, SQL Spiegelung und XMPP sind in Skype for Business Server 2019 veraltet und nicht mehr als Skype for Business Server 2019-Features verfügbar, können aber in einer Koexistenzumgebung fortgesetzt werden, wenn sie zuvor in einer Legacyumgebung bereitgestellt wurden. Wenn Sie diese Features weiterhin verwenden möchten, sollten Sie planen, mit einer Koexistenzumgebung fortzufahren, in der bestimmte Benutzer in älteren Pools verbleiben.
    
4. Nach dem Übergang der Edgeserver der Partnerrouten zu den Pilotservern Skype for Business Server 2019 Edgeserver müssen Sie überprüfen, ob Verbundbenutzer mit dem pool Skype for Business Server 2019 kommunizieren können.
    
5. Nachdem Sie alle Benutzer und Nicht-Benutzerkontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Legacypool leer ist.
    
6. Nachdem Sie überprüft haben, ob der Legacypool leer ist, können Sie den Pool deaktivieren. 
    
    Ausführliche Informationen zum Deaktivieren des Legacypools und der Server finden Sie in [Phase 8: Außerbetriebnahme von Legacypools.](phase-8-decommission-legacy-pools.md)
    

