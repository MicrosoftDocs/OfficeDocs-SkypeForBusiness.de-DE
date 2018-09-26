---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie in einer gemischten Umgebung mit den nächsten hoppool einen Skype für Business Server 2019 Pool werden festlegen. In einer gemischten Umgebung werden sowohl Pool der Vorgängerversion der Skype für Business Server 2019 Pool in der Dropdownliste aus. Auswählen der Pool den Vorgängerversion wird nicht unterstützt.
ms.openlocfilehash: d1c79e044145a4739cf1b7bfb3992320be1e4ab3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027746"
---
# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

Wenn Sie einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie in einer gemischten Umgebung mit den nächsten hoppool einen Skype für Business Server 2019 Pool werden festlegen. In einer gemischten Umgebung werden sowohl Pool der Vorgängerversion der Skype für Business Server 2019 Pool in der Dropdown-Liste. Auswählen der Pool den Vorgängerversion wird nicht unterstützt.
  
> [!IMPORTANT]
> Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die Version von UCMA aktualisieren, den, die Sie verwenden. Wenn Sie einen neuen vertrauenswürdigen Anwendungspool für Skype für Business Server 2019 erstellen, sollten Sie UCMA aktualisieren, um die Version, die in Skype für Business Server 2019 enthalten ist oder die neueste Version verfügbar. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Wählen Sie Skype für Business Server 2019 als nächsten Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers

1. Topologie-Generator zu öffnen.
    
2. Klicken Sie im linken Bereich Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **Neuer Pool für vertrauenswürdige Anwendung**.
    
3. Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools, und wählen Sie aus, ob es Einzelserver oder mehreren Servern ist. 
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie auf der Seite **Wählen Sie den nächsten Hop** aus der Liste der Skype für Business Server 2019 Front-End-Pool ein. 
    
6. Klicken Sie auf **Fertig stellen**.
    
7. Wählen Sie den obersten Knoten **Skype für Business Server**aus, und wählen Sie im Menü **Aktion** **Veröffentlichen**.
    
    Stellen Sie sicher, dass der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist. 
    

