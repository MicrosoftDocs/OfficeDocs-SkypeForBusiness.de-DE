---
title: Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Aktivieren Sie Benutzer für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.
ms.openlocfilehash: bebddb5f71612cf23d442366c774d0e8d4b9f500
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767268"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="c0d52-103">Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c0d52-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="c0d52-104">Aktivieren Sie Benutzer für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.</span><span class="sxs-lookup"><span data-stu-id="c0d52-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="c0d52-105">Nach dem Hinzufügen von Gruppennummern für die Anruf Abholung zur Umlaufbahn Tabelle des Anruf Parks verwenden Sie das SEFAUtil-Tool, um die Gruppennummern Benutzern zuzuweisen und die Gruppenanruf Abholung für Sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c0d52-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="c0d52-106">Weisen Sie in einer hybridbereitstellung Benutzern, die Online sind, keine Gruppenanruf-Abhol Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="c0d52-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="c0d52-107">Benutzer, die Online sind, können nicht an der Gruppenanruf Abholung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c0d52-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="c0d52-108">Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="c0d52-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="c0d52-109">So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanruf Abholung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="c0d52-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="c0d52-110">Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c0d52-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="c0d52-111">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c0d52-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="c0d52-112">Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:</span><span class="sxs-lookup"><span data-stu-id="c0d52-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="c0d52-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0d52-113">See also</span></span>

[<span data-ttu-id="c0d52-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="c0d52-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

