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
description: Wenn ein Legacy-Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das Anrufsteuerungshosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den älteren Front-End-Pool entfernen können.
ms.openlocfilehash: c3ebb748d877e88060b699b1599c39038124565df361c5032533260e4c5643e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334567"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

Wenn ein Legacy-Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das Anrufsteuerungshosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den älteren Front-End-Pool entfernen können.
  
### <a name="to-reset-cac"></a>So setzen Sie die Anrufsteuerung zurück

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie mit der rechten Maustaste auf den Standortknoten, und klicken Sie auf **Eigenschaften bearbeiten**.
    
3. Vergewissern Sie sich, dass in der **Einstellung für Anrufsteuerung** die Option **Anrufsteuerung aktivieren** ausgewählt wurde. 
    
4. Wählen Sie im **Front-End-Pool zum Ausführen der Anrufsteuerung (Call Admission Control, CAC)** den Pool Skype for Business Server 2019 aus, der die Anrufsteuerung hosten soll, und klicken Sie dann auf **OK.**
    
5. Veröffentlichen Sie die Topologie.
    

