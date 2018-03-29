---
title: Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Aktivieren von Benutzern für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a><span data-ttu-id="d3c3c-103">Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="d3c3c-103">Enable Group Call Pickup for users and assign a group number in Skype for Business 2015</span></span>
 
<span data-ttu-id="d3c3c-104">Aktivieren von Benutzern für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer.</span><span class="sxs-lookup"><span data-stu-id="d3c3c-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="d3c3c-105">Nachdem Sie die orbittabelle für das Parken von Anrufen Rufnummern pickup-Gruppe hinzufügen, verwenden Sie das SEFAUtil-Tool, um Benutzer die Gruppennummern zugewiesen, und aktivieren für diese Gruppe aufrufen Pickup-.</span><span class="sxs-lookup"><span data-stu-id="d3c3c-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3c3c-106">Weisen Sie in einer hybridbereitstellung einer Gruppe anrufen Pickup-Gruppe nicht für Benutzer, die online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c3c-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="d3c3c-107">Benutzer, die online verwaltet werden können nicht in der Gruppe anrufen Pickup-teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d3c3c-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="d3c3c-108">Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="d3c3c-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="d3c3c-109">Zuweisen einer Gruppennummer und Gruppe aufrufen Pickup-für einen Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="d3c3c-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="d3c3c-110">Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="d3c3c-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="d3c3c-111">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d3c3c-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="d3c3c-112">Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:</span><span class="sxs-lookup"><span data-stu-id="d3c3c-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="d3c3c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3c3c-113">See also</span></span>

#### 

[<span data-ttu-id="d3c3c-114">Disable-Gruppe Pickup-für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d3c3c-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

