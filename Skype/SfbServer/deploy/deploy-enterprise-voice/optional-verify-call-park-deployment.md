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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen Ihrer Bereitstellung des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830895"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Optional) Überprüfen der Bereitstellung des Parkens von Anrufen in Skype for Business
 
Überprüfen Ihrer Bereitstellung des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP. 
  
Nachdem Sie das Parken von Anrufen installiert und konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Abrufen von Anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:
  
- Rufen Sie einen Benutzer an, für den das Parken von Anrufen aktiviert ist, und fordern Sie den Benutzer auf, den Anruf zu parken.
    
    > [!NOTE]
    > Wenn Sie das Parken von Anrufen in der Sprachrichtlinie direkt vor diesem Test aktiviert haben, muss sich der Benutzer, der den Anruf parkt, von Skype for Business abmelden und dann wieder anmelden, um die Option zum Parken von Anrufen in der Anrufliste sehen zu können. 
  
- Wählen Sie die Orbitnummer, um den Anruf abzurufen.
    
- Parken Sie einen weiteren Anruf, lassen Sie für den geparkten Anruf ein Zeit out, und nehmen Sie den Rückruf nicht wieder auf. Stellen Sie sicher, dass der Zeittimeoutanruf ordnungsgemäß an das Fallbackziel geroutet wurde, das für **OnTimeoutURI angegeben ist.**
    

