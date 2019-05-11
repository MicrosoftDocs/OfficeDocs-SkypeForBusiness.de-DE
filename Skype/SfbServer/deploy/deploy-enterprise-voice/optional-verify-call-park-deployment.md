---
title: (Optional) Überprüfen der Bereitstellung in Skype für Unternehmen zum Parken von Anrufen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: da53d351acef3eb2fc7fcc1b59e24a83d0cb2495
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894668"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Optional) Überprüfen der Bereitstellung in Skype für Unternehmen zum Parken von Anrufen
 
Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP. 
  
Nachdem Sie installieren und des Parkens von Anrufen konfigurieren, müssen Sie überprüfen Sie die Konfiguration, um sicherzustellen, dass das Parken und Wiederaufnehmen von Anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:
  
- Rufen Sie einen Benutzer, der zum Parken von Anrufen aktiviert hat, und haben Sie die Benutzer den Anruf Parken.
    
    > [!NOTE]
    > Wenn Sie zum Parken von Anrufen in VoIP-Richtlinie aktiviert, unmittelbar vor diesem Test ausführen, muss der Benutzer, der den Anruf zu parken ist Skype für Unternehmen abmelden und dann wieder anmelden, finden die Option zum Parken von Anrufen bei der Übertragung Liste aufrufen können. 
  
- Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.
    
- Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.
    

