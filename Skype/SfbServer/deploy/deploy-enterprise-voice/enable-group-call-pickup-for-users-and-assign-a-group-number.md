---
title: Aktivieren Sie Gruppe aufrufen Pickup-für Benutzer, und weisen Sie eine Gruppe Zahl in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Aktivieren von Benutzern für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer.
ms.openlocfilehash: e182919023aab7757f975cbdccc509a0b62a77b9
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260006"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="1e23d-103">Aktivieren Sie Gruppe aufrufen Pickup-für Benutzer, und weisen Sie eine Gruppe Zahl in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="1e23d-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="1e23d-104">Aktivieren von Benutzern für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer.</span><span class="sxs-lookup"><span data-stu-id="1e23d-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="1e23d-105">Nachdem Sie die orbittabelle für das Parken von Anrufen Rufnummern pickup-Gruppe hinzufügen, verwenden Sie das SEFAUtil-Tool, um Benutzer die Gruppennummern zugewiesen, und aktivieren für diese Gruppe aufrufen Pickup-.</span><span class="sxs-lookup"><span data-stu-id="1e23d-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="1e23d-106">Weisen Sie in einer hybridbereitstellung einer Gruppe anrufen Pickup-Gruppe nicht für Benutzer, die online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1e23d-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="1e23d-107">Benutzer, die online verwaltet werden können nicht in der Gruppe anrufen Pickup-teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="1e23d-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="1e23d-108">Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="1e23d-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="1e23d-109">Zuweisen einer Gruppennummer und Gruppe aufrufen Pickup-für einen Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="1e23d-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="1e23d-110">Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="1e23d-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="1e23d-111">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1e23d-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="1e23d-112">Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:</span><span class="sxs-lookup"><span data-stu-id="1e23d-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="1e23d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e23d-113">See also</span></span>

[<span data-ttu-id="1e23d-114">Disable-Gruppe Pickup-für Benutzer</span><span class="sxs-lookup"><span data-stu-id="1e23d-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

