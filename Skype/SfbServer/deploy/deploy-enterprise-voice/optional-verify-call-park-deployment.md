---
title: Optional Überprüfen der Bereitstellung des Anruf Parks in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen Ihrer Bereitstellung des Anruf Parks in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 7dfaf916e94db18c3b53fc7e9c9e3b136fa445b8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767338"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Optional Überprüfen der Bereitstellung des Anruf Parks in Skype for Business
 
Überprüfen Ihrer Bereitstellung des Anruf Parks in Skype for Business Server Enterprise-VoIP 
  
Nachdem Sie den Parken von Anrufen installiert und konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Abrufen von anrufen wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes:
  
- Rufen Sie einen Benutzer an, der den Anruf Park aktiviert hat, und lassen Sie den Anruf vom Nutzer Parken.
    
    > [!NOTE]
    > Wenn Sie den Anruf Park in der VoIP-Richtlinie unmittelbar vor der Durchführung dieses Tests aktiviert haben, muss sich der Benutzer, der den Anruf parkt, von Skype for Business abmelden und dann wieder anmelden, um die Option Parken in der Anrufliste zu sehen. 
  
- Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.
    
- Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.
    

