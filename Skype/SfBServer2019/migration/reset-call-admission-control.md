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
ms.localizationpriority: medium
description: Wenn ein Legacy-Front-End-Pool Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das Anrufsteuerungshosting in einen pool Skype for Business Server 2019 verschieben, bevor Sie den älteren Front-End-Pool entfernen können.
ms.openlocfilehash: f660f14adfcdee64d9fa4c79e08393d4f0a0af2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583449"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

Wenn ein Legacy-Front-End-Pool Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das Anrufsteuerungshosting in einen pool Skype for Business Server 2019 verschieben, bevor Sie den älteren Front-End-Pool entfernen können.
  
### <a name="to-reset-cac"></a>So setzen Sie die Anrufsteuerung zurück

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie mit der rechten Maustaste auf den Standortknoten, und klicken Sie auf **Eigenschaften bearbeiten**.
    
3. Vergewissern Sie sich, dass in der **Einstellung für Anrufsteuerung** die Option **Anrufsteuerung aktivieren** ausgewählt wurde. 
    
4. Wählen Sie im **Front-End-Pool zum Ausführen der Anrufsteuerung (Call Admission Control, CAC)** den Pool Skype for Business Server 2019 aus, der die Anrufsteuerung hosten soll, und klicken Sie dann auf **"OK".**
    
5. Veröffentlichen Sie die Topologie.
    

