---
title: (Optional) Überprüfen der Bereitstellung der Funktion zum Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a>(Optional) Überprüfen der Bereitstellung der Funktion zum Parken von Anrufen in Skype for Business 2015
 
Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP. 
  
Nachdem Sie installieren und des Parkens von Anrufen konfigurieren, müssen Sie überprüfen Sie die Konfiguration, um sicherzustellen, dass das Parken und Wiederaufnehmen von Anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:
  
- Rufen Sie einen Benutzer, der zum Parken von Anrufen aktiviert hat, und haben Sie die Benutzer den Anruf Parken.
    
    > [!NOTE]
    > Wenn Sie zum Parken von Anrufen in VoIP-Richtlinie aktiviert, unmittelbar vor diesem Test ausführen, muss der Benutzer, der den Anruf zu parken ist Skype für Unternehmen abmelden und dann wieder anmelden, finden die Option zum Parken von Anrufen bei der Übertragung Liste aufrufen können. 
  
- Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.
    
- Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.
    

