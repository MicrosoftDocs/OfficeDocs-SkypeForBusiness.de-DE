---
title: Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Business Server.'
ms.openlocfilehash: feb240600c02da2cdb5cabf9db8ca55605240901
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891280"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="98642-103">Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="98642-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="98642-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="98642-p101">VoIP-Richtlinien, PSTN-Verwendungsdatensätze und VoIP-Routen stehen in enger Beziehung zueinander. Zur Konfiguration von VoIP-Richtlinien wird eine Reihe von Anruffunktionen ausgewählt. Anschließend wird die Richtlinie einem Satz von PSTN-Verwendungsdatensätzen zugewiesen, in denen die Rechte für die Benutzer oder Gruppen festgelegt sind, denen die VoIP-Richtlinie zugewiesen wird. Auch VoIP-Routen werden PSTN-Verwendungsdatensätze zugewiesen, um Routen und die für ihre Verwendung autorisierten Benutzer einander zuzuordnen. Benutzer können also nur Anrufe über Routen tätigen, für die sie passende PSTN-Verwendungsdatensätze besitzen.</span><span class="sxs-lookup"><span data-stu-id="98642-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="98642-109">Der empfohlene Workflow für eine neue Enterprise-VoIP-Bereitstellung besteht darin, zunächst eine VoIP-Richtlinie mit den geeigneten PSTN-Verwendungsdatensätzen zu konfigurieren und anschließend den einzelnen PSTN-Verwendungsdatensätzen die entsprechenden Routen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="98642-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="98642-110">Sie können auch VoIP-Richtlinien *Benutzerebene* erstellen und diese für einzelne Benutzer oder Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="98642-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="98642-111">Die einzelnen Schritte zur Durchführung dieser Aufgaben finden Sie in den Verfahren in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="98642-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="98642-112">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="98642-112">In this section</span></span>

- [<span data-ttu-id="98642-113">Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="98642-114">Konfigurieren des Wechsels der Voicemail in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="98642-115">Anzeigen von PSTN-Verwendungseinträge in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="98642-116">Erstellen oder Ändern einer VoIP-Route in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="98642-117">Exportieren oder Importieren einer VoIP-routenkonfigurationsdatei in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="98642-118">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98642-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

