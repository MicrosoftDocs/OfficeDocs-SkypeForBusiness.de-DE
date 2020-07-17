---
title: Entfernen von Archivierungsservern und Monitoring Servern der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn die Legacy Bereitstellung eine Archivierungsserver oder ein Monitoring Server enthielt, können diese Server nach der Migration zu Skype for Business Server 2019 aus der vorversions Umgebung entfernt werden, vorausgesetzt, dass alle Benutzer aus den verbleibenden Legacy Pools entfernt wurden. Die Archivierungsserver oder Monitoring Server können in beliebiger Reihenfolge entfernt werden. Wesentliche Voraussetzung ist, dass alle Benutzer aus den verbleibenden Vorversionspools entfernt worden sind.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752167"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="c1211-105">Entfernen von Archivierungsservern und Monitoring Servern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="c1211-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="c1211-106">Wenn die Legacy Bereitstellung eine Archivierungsserver oder ein Monitoring Server enthielt, können diese Server nach der Migration zu Skype for Business Server 2019 aus der vorversions Umgebung entfernt werden, vorausgesetzt, alle Benutzer wurden aus den verbleibenden Legacy Pools entfernt.</span><span class="sxs-lookup"><span data-stu-id="c1211-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="c1211-107">Die Archivierungsserver oder Monitoring Server können in beliebiger Reihenfolge entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c1211-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="c1211-108">Wesentliche Voraussetzung ist, dass alle Benutzer aus den verbleibenden Vorversionspools entfernt worden sind.</span><span class="sxs-lookup"><span data-stu-id="c1211-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="c1211-109">Sie können Benutzer auf Skype for Business Server 2019 umstellen, indem Sie die in [Phase 4: verlagern von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)beschriebenen Verfahren ausführen.</span><span class="sxs-lookup"><span data-stu-id="c1211-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="c1211-110">Nachdem Sie bestätigt haben, dass alle Benutzer aus den verbleibenden Pools entfernt wurden, decommision Sie den Server und Rollen entfernen.</span><span class="sxs-lookup"><span data-stu-id="c1211-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="c1211-111">Ein datiertes, aber relevantes Beispiel ist "deinstallieren Microsoft lync Server und Entfernen von Server Rollen", die unter heruntergeladen werden können [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="c1211-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

