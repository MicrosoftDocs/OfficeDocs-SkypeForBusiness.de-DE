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
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="2eaec-103">(Optional) Überprüfen der Bereitstellung in Skype für Unternehmen zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="2eaec-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="2eaec-104">Überprüfen der bereitstellungs von zum Parken von Anrufen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="2eaec-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="2eaec-105">Nachdem Sie installieren und des Parkens von Anrufen konfigurieren, müssen Sie überprüfen Sie die Konfiguration, um sicherzustellen, dass das Parken und Wiederaufnehmen von Anrufen wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2eaec-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="2eaec-106">Überprüfen Sie mindestens Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2eaec-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="2eaec-107">Rufen Sie einen Benutzer, der zum Parken von Anrufen aktiviert hat, und haben Sie die Benutzer den Anruf Parken.</span><span class="sxs-lookup"><span data-stu-id="2eaec-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2eaec-108">Wenn Sie zum Parken von Anrufen in VoIP-Richtlinie aktiviert, unmittelbar vor diesem Test ausführen, muss der Benutzer, der den Anruf zu parken ist Skype für Unternehmen abmelden und dann wieder anmelden, finden die Option zum Parken von Anrufen bei der Übertragung Liste aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="2eaec-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="2eaec-109">Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="2eaec-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="2eaec-p102">Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="2eaec-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

