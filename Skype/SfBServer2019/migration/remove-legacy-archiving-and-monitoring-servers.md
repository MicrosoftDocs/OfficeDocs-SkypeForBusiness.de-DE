---
title: Entfernen von Archivierungsservern und Monitoring Servern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Falls Ihre Bereitstellung der Vorversion einen Archivierungsserver oder einen Monitoring Server nach der Migration zu Skype für Business Server 2019 enthalten, können dieser Server aus der vorgängerumgebung entfernt werden, sofern alle Benutzer aus den verbleibenden Pools Vorversion entfernt wurden. Sie können in eine beliebige Abfolge der Archivierungsserver oder Monitoring Server entfernen. Die wichtigste Anforderung ist, dass alle Benutzer aus den verbleibenden Pools Vorversion entfernt wurden.
ms.openlocfilehash: 5a3a691c8f2e8a4ad3610ccf1ea947ce23b74111
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878339"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="10db0-105">Entfernen von Archivierungsservern und Monitoring Servern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="10db0-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="10db0-106">Falls Ihre Bereitstellung der Vorversion einen Archivierungsserver oder einen Monitoring Server nach der Migration zu Skype für Business Server 2019 enthalten, kann dieser Server aus der vorgängerumgebung entfernt, vorausgesetzt, dass alle Benutzer aus den verbleibenden Pools Vorversion entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="10db0-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="10db0-107">Sie können in eine beliebige Abfolge der Archivierungsserver oder Monitoring Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="10db0-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="10db0-108">Die wichtigste Anforderung ist, dass alle Benutzer aus den verbleibenden Pools Vorversion entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="10db0-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="10db0-109">Können Sie Benutzer zu wechseln Skype für Business Server 2019 gemäß die Verfahren in [Phase 4: Verschieben von Testbenutzern in den pilotpool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="10db0-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="10db0-110">Nachdem Sie sichergestellt haben, dass alle Benutzer aus den verbleibenden Pools, Decommision der Server entfernt wurden und Rollen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="10db0-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="10db0-111">Ein Benutzer, aber relevant, Beispiel ist "Deinstallieren von Microsoft Lync Server und Entfernen von Serverrollen," die unter heruntergeladen werden kann [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="10db0-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

