---
title: (Optional) Überprüfen der Bereitstellung in Skype für Unternehmen zum Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 514c82590d56a2de16ca31cc892032afe5e7a34c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895097"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="9fa02-103">(Optional) Überprüfen der Bereitstellung in Skype für Unternehmen zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="9fa02-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="9fa02-104">Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="9fa02-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="9fa02-105">Nachdem Sie installieren und des Parkens von Anrufen konfigurieren, müssen Sie überprüfen Sie die Konfiguration, um sicherzustellen, dass das Parken und Wiederaufnehmen von Anrufen wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9fa02-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="9fa02-106">Überprüfen Sie mindestens Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9fa02-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="9fa02-107">Rufen Sie einen Benutzer, der zum Parken von Anrufen aktiviert hat, und haben Sie die Benutzer den Anruf Parken.</span><span class="sxs-lookup"><span data-stu-id="9fa02-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9fa02-108">Wenn Sie zum Parken von Anrufen in VoIP-Richtlinie aktiviert, unmittelbar vor diesem Test ausführen, muss der Benutzer, der den Anruf zu parken ist Skype für Unternehmen abmelden und dann wieder anmelden, finden die Option zum Parken von Anrufen bei der Übertragung Liste aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="9fa02-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="9fa02-109">Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9fa02-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="9fa02-p102">Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="9fa02-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

