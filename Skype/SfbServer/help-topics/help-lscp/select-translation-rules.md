---
title: Auswählen von Übersetzungsregeln
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Enterprise-VoIP erfordert, dass alle Wählzeichenfolgen in das e. 164-Format für die inverssuche (RNL) normalisiert werden. Der Trunkpeer (also das zugeordnete Gateway, Nebenstellensystem oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie optional eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.
ms.openlocfilehash: 0dd2a50f68423a502fb25ba194ab82de76d356d7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220178"
---
# <a name="select-translation-rules"></a><span data-ttu-id="7ee1c-106">Auswählen von Übersetzungsregeln</span><span class="sxs-lookup"><span data-stu-id="7ee1c-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="7ee1c-107">Enterprise-VoIP erfordert, dass alle Wählzeichenfolgen in das e. 164-Format für die inverssuche (RNL) normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="7ee1c-108">Der Trunkpeer (also das zugeordnete Gateway, Nebenstellensystem oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="7ee1c-109">Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie optional eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="7ee1c-110">Sie können beispielsweise eine Übersetzungsregel erstellen, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7ee1c-111">Die Möglichkeit, einen Enterprise-VoIP-Routing testen eine oder mehrere Übersetzungsregeln zugeordnet ist als Alternative zum Konfigurieren von Übersetzungsregeln für den trunkpeer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="7ee1c-112">Ordnen Sie Übersetzungsregeln nicht mit einer Enterprise-VoIP-Routing testen, wenn Sie Übersetzungsregeln für den trunkpeer konfiguriert haben, da zwischen die zwei Regeln Konflikte auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="7ee1c-113">Klicken Sie auf eine Regel in der Liste und anschließend auf **OK**, um eine vorhandene Übersetzungsregel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ee1c-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="7ee1c-114">Ausführliche Informationen zu den verschiedenen Verfahren, die Sie mithilfe der Skype für Business Server-Systemsteuerung ausführen können, finden Sie unter [Verwalten von Skype für Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="7ee1c-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

