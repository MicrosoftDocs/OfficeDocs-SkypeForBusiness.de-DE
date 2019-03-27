---
title: Zurücksetzen der Anrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn eine Deaktivierung von Front-End-Pools die anrufsteuerung (CAC) gehostet wird, müssen Sie verschieben, CAC hosting an einen Skype für Business Server 2019 Pool, bevor Sie den legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895775"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

Wenn eine Deaktivierung von Front-End-Pools die anrufsteuerung (CAC) gehostet wird, müssen Sie verschieben, CAC hosting an einen Skype für Business Server 2019 Pool, bevor Sie den legacy-Front-End-Pool entfernen können.
  
### <a name="to-reset-cac"></a>Zurücksetzen der Anrufsteuerung

1. Topologie-Generator zu öffnen.
    
2. Maustaste auf den Standortknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Klicken Sie unter **Call Admission Control Einstellung**sicherstellen Sie, dass **Die Anrufsteuerung aktivieren** ausgewählt ist. 
    
4. Wählen Sie unter **Front-End-Pool, führen Sie die anrufsteuerung (CAC)** die Skype für Business Server 2019 Pool CAC gehostet ist, und klicken Sie dann auf **OK**.
    
5. Veröffentlichen Sie die Topologie.
    

