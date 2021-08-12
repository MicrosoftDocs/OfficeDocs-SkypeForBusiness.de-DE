---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
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
description: Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den nächsten Hoppool als Skype for Business Server 2019-Pool festlegen. In einer gemischten Umgebung werden sowohl der Legacypool als auch der pool Skype for Business Server 2019 in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.
ms.openlocfilehash: 6db3aaadfe028e6d1975521ecacb52ad26754b7bcf8766af345d4786bc825f31
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296092"
---
# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den nächsten Hoppool als Skype for Business Server 2019-Pool festlegen. In einer gemischten Umgebung werden sowohl der Legacypool als auch der pool Skype for Business Server 2019 in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.
  
> [!IMPORTANT]
> Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die version von UCMA aktualisieren, die Sie verwenden. Wenn Sie einen neuen vertrauenswürdigen Anwendungspool für Skype for Business Server 2019 erstellen, sollten Sie UCMA auf die Version aktualisieren, die in Skype for Business Server 2019 oder der neuesten verfügbaren Version enthalten ist. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Wählen Sie beim Erstellen eines vertrauenswürdigen Anwendungsservers Skype for Business Server 2019 als nächsten Hop aus.

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste auf **"Vertrauenswürdige Anwendungsserver",** und klicken Sie auf **"Neuer vertrauenswürdiger Anwendungspool".**
    
3. Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um einen einzelnen Server oder mehrere Server handelt. 
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie auf der Seite **"Nächsten Hop auswählen"** in der Liste den Front-End-Pool Skype for Business Server 2019 aus. 
    
6. Klicken Sie auf **Fertig stellen**.
    
7. Wählen Sie den oberen Knoten **Skype for Business Server** aus, und wählen Sie im Menü **"Aktion"** die Option **"Veröffentlichen"** aus.
    
    Stellen Sie sicher, dass der **Pool der vertrauenswürdigen Anwendung** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist. 
    

