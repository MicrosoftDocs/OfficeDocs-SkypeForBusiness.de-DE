---
title: Zurücksetzen der Anrufsteuerung
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
description: Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812803"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.
  
### <a name="to-reset-cac"></a>So setzen Sie CAC zurück

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie mit der rechten Maustaste auf den Websiteknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Vergewissern Sie sich, dass unter Einstellungen für die **Anrufsteuerung**die Option **Anrufsteuerung aktivieren** aktiviert ist. 
    
4. Wählen Sie unter **Front-End-Pool zum Ausführen der Anrufannahme Steuerung (CAC)** den Skype for Business Server 2019-Pool aus, der CAC hosten soll, und klicken Sie dann auf **OK**.
    
5. Veröffentlichen Sie die Topologie.
    

