---
title: Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Business Server 2015.'
ms.openlocfilehash: b0d5d9edaf94cb0c8041ef5ef679ad81b9c54edd
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business-2015"></a><span data-ttu-id="75c76-103">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>
 
<span data-ttu-id="75c76-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="75c76-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="75c76-p101">VoIP-Richtlinien, PSTN-Verwendungsdatensätze und VoIP-Routen stehen in enger Beziehung zueinander. Zur Konfiguration von VoIP-Richtlinien wird eine Reihe von Anruffunktionen ausgewählt. Anschließend wird die Richtlinie einem Satz von PSTN-Verwendungsdatensätzen zugewiesen, in denen die Rechte für die Benutzer oder Gruppen festgelegt sind, denen die VoIP-Richtlinie zugewiesen wird. Auch VoIP-Routen werden PSTN-Verwendungsdatensätze zugewiesen, um Routen und die für ihre Verwendung autorisierten Benutzer einander zuzuordnen. Benutzer können also nur Anrufe über Routen tätigen, für die sie passende PSTN-Verwendungsdatensätze besitzen.</span><span class="sxs-lookup"><span data-stu-id="75c76-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="75c76-109">Der empfohlene Workflow für eine neue Enterprise-VoIP-Bereitstellung besteht darin, zunächst eine VoIP-Richtlinie mit den geeigneten PSTN-Verwendungsdatensätzen zu konfigurieren und anschließend den einzelnen PSTN-Verwendungsdatensätzen die entsprechenden Routen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="75c76-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75c76-110">Sie können auch VoIP-Richtlinien *Benutzerebene* erstellen und diese für einzelne Benutzer oder Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="75c76-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="75c76-111">Die einzelnen Schritte zur Durchführung dieser Aufgaben finden Sie in den Verfahren in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="75c76-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="75c76-112">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="75c76-112">In this section</span></span>

- [<span data-ttu-id="75c76-113">Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="75c76-114">Konfigurieren des Wechsels der Voicemail in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-114">Configure voice mail escape in Skype for Business 2015</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="75c76-115">Anzeigen von PSTN-Verwendungseinträge in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-115">View PSTN usage records in Skype for Business 2015</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="75c76-116">Erstellen oder Ändern einer VoIP-Route in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-116">Create or modify a voice route in Skype for Business 2015</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="75c76-117">Exportieren oder Importieren einer VoIP-routenkonfigurationsdatei in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-117">Export or import a voice route configuration file in Skype for Business 2015</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="75c76-118">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="75c76-118">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
    

