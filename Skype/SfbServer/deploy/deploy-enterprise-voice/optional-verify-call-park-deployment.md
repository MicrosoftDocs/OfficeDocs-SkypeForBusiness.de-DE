---
title: Optional Überprüfen der Bereitstellung des Anruf Parks in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Überprüfen Ihrer Bereitstellung des Anruf Parks in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292843"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="85407-103">Optional Überprüfen der Bereitstellung des Anruf Parks in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="85407-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="85407-104">Überprüfen Ihrer Bereitstellung des Anruf Parks in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="85407-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="85407-105">Nachdem Sie den Parken von Anrufen installiert und konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Abrufen von anrufen wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="85407-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="85407-106">Überprüfen Sie mindestens Folgendes:</span><span class="sxs-lookup"><span data-stu-id="85407-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="85407-107">Rufen Sie einen Benutzer an, der den Anruf Park aktiviert hat, und lassen Sie den Anruf vom Nutzer Parken.</span><span class="sxs-lookup"><span data-stu-id="85407-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85407-108">Wenn Sie den Anruf Park in der VoIP-Richtlinie unmittelbar vor der Durchführung dieses Tests aktiviert haben, muss sich der Benutzer, der den Anruf parkt, von Skype for Business abmelden und dann wieder anmelden, um die Option Parken in der Anrufliste zu sehen.</span><span class="sxs-lookup"><span data-stu-id="85407-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="85407-109">Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="85407-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="85407-p102">Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="85407-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

