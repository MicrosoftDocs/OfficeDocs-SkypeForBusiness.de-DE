---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool einrichten. In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Skype for Business Server 2019-Pool in der Dropdownliste angezeigt. Das Auswählen des Legacy Pools wird nicht unterstützt.
ms.openlocfilehash: b715cd7f3f067c5e54dbc085350fcc7f96b5c4be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239298"
---
# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool einrichten. In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Skype for Business Server 2019-Pool in der Dropdownliste angezeigt. Das Auswählen des Legacy Pools wird nicht unterstützt.
  
> [!IMPORTANT]
> Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die von Ihnen verwendete Version von UCMA aktualisieren. Wenn Sie einen neuen vertrauenswürdigen Anwendungs Pool für Skype for Business Server 2019 erstellen, sollten Sie UCMA auf die Version aktualisieren, die im Lieferumfang von Skype for Business Server 2019 oder in der neuesten Version verfügbar ist. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Auswählen von Skype for Business Server 2019 als nächster Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.
    
3. Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um einen Einzelserver oder um mehrere Server handelt. 
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den Skype for Business Server 2019-Front-End-Pool aus. 
    
6. Klicken Sie auf **Fertig stellen**.
    
7. Wählen Sie den obersten Knoten **für Skype for Business Server**aus, und wählen Sie im Menü **Aktion** die Option **veröffentlichen**aus.
    
    Überprüfen Sie, ob der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist. 
    

