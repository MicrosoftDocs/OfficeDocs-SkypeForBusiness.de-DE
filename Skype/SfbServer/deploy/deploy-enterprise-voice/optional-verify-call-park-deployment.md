---
title: (Optional) Überprüfen der Bereitstellung des Parkens von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen der Bereitstellung des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 279f55e058678bdd33616a71642555b134052018
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579949"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Optional) Überprüfen der Bereitstellung des Parkens von Anrufen in Skype for Business
 
Überprüfen der Bereitstellung des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP. 
  
Nachdem Sie das Parken von Anrufen installiert und konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Abrufen von Anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:
  
- Rufen Sie einen Benutzer auf, für den das Parken von Anrufen aktiviert ist und der Benutzer den Anruf parken lässt.
    
    > [!NOTE]
    > Wenn Sie das Parken von Anrufen in der VoIP-Richtlinie direkt vor dem Ausführen dieses Tests aktiviert haben, muss sich der Benutzer, der den Anruf parkt, von Skype for Business abmelden und sich dann wieder anmelden, um die Option zum Parken von Anrufen in der Anrufweiterleitungsliste anzeigen zu können. 
  
- Wählen Sie die Orbitnummer, um den Anruf abzurufen.
    
- Parken Sie einen weiteren Anruf, lassen Sie das Timeout für den geparkten Anruf aus, und nehmen Sie den Rückruf nicht an. Stellen Sie sicher, dass der Timedout-Anruf ordnungsgemäß an das Fallbackziel weitergeleitet wird, das für **OnTimeoutURI** angegeben ist.
    

