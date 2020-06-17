---
title: Zurücksetzen der Anrufsteuerung
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
description: Wenn ein Legacy Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool versetzen, bevor Sie die Legacy Front-End-Pool entfernen können.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753297"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

Wenn ein Legacy Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool versetzen, bevor Sie die Legacy Front-End-Pool entfernen können.
  
### <a name="to-reset-cac"></a>So setzen Sie die Anrufsteuerung zurück

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie mit der rechten Maustaste auf den Standortknoten, und klicken Sie auf **Eigenschaften bearbeiten**.
    
3. Vergewissern Sie sich, dass in der **Einstellung für Anrufsteuerung** die Option **Anrufsteuerung aktivieren** ausgewählt wurde. 
    
4. Wählen Sie unter **Front-End-Pool, um die Anrufsteuerung (Call Admission Control, CAC) auszuführen**, den Skype for Business Server 2019-Pool aus, der als Host für CAC dient, und klicken Sie dann auf **OK**.
    
5. Veröffentlichen Sie die Topologie.
    

