---
title: Überprüfen der Konfigurationseinstellungen
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
description: Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das Cmdlet Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer in der Domäne, auf dem Skype for Business Server 2019-Kernkomponenten (OcsCore.msi) installiert ist.
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752147"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="49ef5-103">Überprüfen der Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="49ef5-103">Verify configuration settings</span></span>

<span data-ttu-id="49ef5-104">Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das **Get-CsManagementStoreReplicationStatus-** Cmdlet Skype for Business Server 2019 auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer mit Domänenbeitritt, auf dem Skype for Business Server 2019-Kernkomponenten (OcsCore.msi) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="49ef5-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="49ef5-105">Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an.</span><span class="sxs-lookup"><span data-stu-id="49ef5-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="49ef5-106">Wenn dies der Fall ist, führen Sie das **Invoke-CsManagementStoreReplication-** Cmdlet aus, und lassen Sie die Replikation vor dem erneuten Ausführen des **Get-CsManagementStoreReplicationStatus** Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="49ef5-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

