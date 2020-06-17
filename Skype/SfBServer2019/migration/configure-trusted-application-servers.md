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
description: Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool festlegen. In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Pool Skype for Business Server 2019 in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753945"
---
# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool festlegen. In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Pool Skype for Business Server 2019 in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.
  
> [!IMPORTANT]
> Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die Version von UCMA aktualisieren, die Sie verwenden. Wenn Sie einen neuen vertrauenswürdigen Anwendungs Pool für Skype for Business Server 2019 erstellen, sollten Sie UCMA auf die Version aktualisieren, die in Skype for Business Server 2019 enthalten ist, oder die neueste Version verfügbar ist. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Auswählen Skype for Business Server 2019 als nächsten Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.
    
3. Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um einen Einzelserver oder mehrere Server handelt. 
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die Skype for Business Server 2019 Front-End-Pool aus. 
    
6. Klicken Sie auf **Fertig stellen**.
    
7. Wählen Sie den obersten Knoten **Skype for Business Server**aus, und wählen Sie im Menü **Aktion** die Option **veröffentlichen**aus.
    
    Stellen Sie sicher, dass der **Vertrauenswürdige Anwendungs Pool** erfolgreich erstellt wurde und dem korrekten Front-End-Pool zugeordnet ist. 
    

