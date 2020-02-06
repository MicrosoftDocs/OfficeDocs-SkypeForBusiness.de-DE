---
title: Migrieren von mehreren Standorten und Pools
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
description: 'Skype for Business Server 2019 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools. Der Vorgang zum Migrieren mehrerer Pools zu Skype for Business Server 2019 erfordert die folgenden Überlegungen:'
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813443"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

Skype for Business Server 2019 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools. Der Vorgang zum Migrieren mehrerer Pools zu Skype for Business Server 2019 erfordert die folgenden Überlegungen: 
  
1. Nachdem Sie einen Skype for Business Server 2019-Pilot Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den Skype for Business Server 2019-Pool verschoben werden, sowie eine Methodik zum Überprüfen der Funktionalität der Benutzer. Wenn Sie beispielsweise einen Benutzer in den Pilot Pool verschieben, stellen Sie sicher, dass die konferenzrichtlinie des Benutzers in Skype for Business Server 2019 verschoben wurde. 
    
2. Nachdem Sie einen Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.

3. Beständiger Chat, SQL-Spiegelung und XMPP-Funktionalität sind in Skype for Business Server 2019 veraltet und nicht mehr als Funktionen von Skype for Business Server 2019 verfügbar, können aber in einer Koexistenz-Umgebung fortgesetzt werden, wenn Sie zuvor in einer Legacyumgebung Wenn Sie diese Features weiterhin verwenden möchten, sollten Sie mit einer Koexistenz-Umgebung fortfahren, in der bestimmte Benutzer in Legacy Pools verbleiben.
    
4. Nachdem Sie die Edgeserver der Federated-Routes an die Pilot-Edgeserver von Skype for Business Server 2019 übertragen haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.
    
5. Nachdem Sie alle Benutzer und nicht Benutzer-Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Legacy Pool leer ist.
    
6. Nachdem Sie überprüft haben, dass der Legacy Pool leer ist, können Sie den Pool deaktivieren. 
    
    Weitere Informationen zum Deaktivieren des Legacy Pools und der Legacy Server finden Sie unter [Phase 8: Legacy Pools für decommission](phase-8-decommission-legacy-pools.md).
    

