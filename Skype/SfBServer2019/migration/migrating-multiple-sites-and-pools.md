---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype für Business Server 2019 unterstützt mehrere Standorte und mit mehreren Pool-Bereitstellungen. Bei der Migration mehrerer Pools zu Skype für Business Server 2019 ist Folgendes erforderlich:'
ms.openlocfilehash: 5e369adb51bf95f4e3c3d12688d1e39611aa5692
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888661"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

Skype für Business Server 2019 unterstützt mehrere Standorte und mit mehreren Pool-Bereitstellungen. Bei der Migration mehrerer Pools zu Skype für Business Server 2019 ist Folgendes erforderlich: 
  
1. Nach der Bereitstellung einen Skype für Business Server 2019 pilotpool müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in der Skype für Business Server 2019-Pool und eine Methodik zum Überprüfen der Funktionalität der Benutzer verschoben werden sollen. Beispielsweise nach dem Verschieben eines Benutzers in den pilotpool, stellen Sie sicher, dass die Benutzerrichtlinie Konferenz in Skype für Business Server 2019 verschoben wurde. 
    
2. Nach der Bereitstellung eines Edgeservers im pilotpool müssen Sie überprüfen, ob externe Benutzer mit der Skype für Business Server 2019-Pool kommunizieren können.

3. Persistent Chat, SQL-Spiegelung und XMPP-Funktionalität in Skype für Business Server 2019 veraltete und nicht mehr als Skype für Business Server 2019 Features verfügbar sind, aber kann in einer koexistenzumgebung fortgesetzt werden, wenn sie zuvor in bereitgestellt wurden eine Legacy-Umgebung. Wenn Sie weiterhin diese Features verwenden möchten, sollten Sie planen, um einer koexistenzumgebung fortzusetzen, wo bestimmte Benutzer in alten Pools verbleibt.
    
4. Nach dem Übergang der Sammelsuche Routen Edge-Servern die pilot Skype für Business Server 2019 Edge-Server, müssen Sie überprüfen, ob die Partnerbenutzer mit dem Skype für Business Server 2019-Pool kommunizieren können.
    
5. Nach dem Verschieben von allen Benutzern und Kontaktobjekten nicht vom Benutzer, müssen Sie überprüfen, ob der Pool der Vorgängerversion leer ist.
    
6. Nachdem Sie sichergestellt haben, dass der Pool der Vorgängerversion leer ist, können Sie den Pool deaktivieren. 
    
    Informationen dazu, wie Sie die Vorversion Pools und-Servern aus der vorversionsumgebung finden Sie unter [Phase 8: Außerbetriebsetzen des vorversionspools](phase-8-decommission-legacy-pools.md).
    

