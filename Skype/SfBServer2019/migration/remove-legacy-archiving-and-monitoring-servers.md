---
title: Entfernen von Archivierungsservern und Monitoring Servern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Ihre Legacy Bereitstellung einen Archivierungsserver oder einen Überwachungsserver enthielt, können nach der Migration zu Skype for Business Server 2019 diese Server aus der Legacyumgebung entfernt werden, vorausgesetzt, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden. Sie können den Archivierungsserver oder den Monitoring Server in beliebiger Reihenfolge entfernen. Die wichtigste Anforderung ist, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden.
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301125"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="60fbf-105">Entfernen von Archivierungsservern und Monitoring Servern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="60fbf-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="60fbf-106">Wenn Ihre Legacy Bereitstellung einen Archivierungsserver oder einen Überwachungsserver enthielt, können nach dem Migrieren zu Skype for Business Server 2019 diese Server aus der Legacyumgebung entfernt werden, vorausgesetzt, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="60fbf-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="60fbf-107">Sie können den Archivierungsserver oder den Monitoring Server in beliebiger Reihenfolge entfernen.</span><span class="sxs-lookup"><span data-stu-id="60fbf-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="60fbf-108">Die wichtigste Anforderung ist, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="60fbf-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="60fbf-109">Sie können Benutzer zu Skype for Business Server 2019 verschieben, indem Sie die in Phase 4 beschriebenen Verfahren ausführen [: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="60fbf-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="60fbf-110">Nachdem Sie bestätigt haben, dass alle Benutzer aus allen verbleibenden Pools entfernt wurden, decommision Sie den Server aus, und entfernen Sie Rollen.</span><span class="sxs-lookup"><span data-stu-id="60fbf-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="60fbf-111">Ein datiertes, aber relevantes Beispiel ist "Deinstallieren von Microsoft lync Server und Entfernen von Serverrollen", das unter [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="60fbf-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

