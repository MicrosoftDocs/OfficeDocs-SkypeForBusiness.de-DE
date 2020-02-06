---
title: Entfernen von Archivierungsservern und Monitoring Servern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn Ihre Legacy Bereitstellung einen Archivierungsserver oder einen Überwachungsserver enthielt, können nach der Migration zu Skype for Business Server 2019 diese Server aus der Legacyumgebung entfernt werden, vorausgesetzt, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden. Sie können den Archivierungsserver oder den Monitoring Server in beliebiger Reihenfolge entfernen. Die wichtigste Anforderung ist, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden.
ms.openlocfilehash: 034d2ad284c0247b19e56e4cd8d751a0cf32ee69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812993"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="1eb43-105">Entfernen von Archivierungsservern und Monitoring Servern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="1eb43-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="1eb43-106">Wenn Ihre Legacy Bereitstellung einen Archivierungsserver oder einen Überwachungsserver enthielt, können nach dem Migrieren zu Skype for Business Server 2019 diese Server aus der Legacyumgebung entfernt werden, vorausgesetzt, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="1eb43-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="1eb43-107">Sie können den Archivierungsserver oder den Monitoring Server in beliebiger Reihenfolge entfernen.</span><span class="sxs-lookup"><span data-stu-id="1eb43-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="1eb43-108">Die wichtigste Anforderung ist, dass alle Benutzer aus allen verbleibenden Legacy Pools entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="1eb43-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="1eb43-109">Sie können Benutzer zu Skype for Business Server 2019 verschieben, indem Sie die in Phase 4 beschriebenen Verfahren ausführen [: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="1eb43-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="1eb43-110">Nachdem Sie bestätigt haben, dass alle Benutzer aus allen verbleibenden Pools entfernt wurden, decommision Sie den Server aus, und entfernen Sie Rollen.</span><span class="sxs-lookup"><span data-stu-id="1eb43-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="1eb43-111">Ein datiertes, aber relevantes Beispiel ist "Deinstallieren von Microsoft lync Server und Entfernen von Serverrollen", das unter [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1eb43-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

