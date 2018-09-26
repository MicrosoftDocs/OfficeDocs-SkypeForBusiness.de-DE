---
title: Überprüfen von Konfigurationseinstellungen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können die Replikation der Konfigurationsinformationen auf dem Edge-Server durch Ausführen der Skype für Business Server 2019 Get-CsManagementStoreReplicationStatus-Cmdlet auf dem internen Computer, auf dem sich der zentrale Verwaltungsspeicher befindet oder auf eine überprüfen in die Domäne eingebundener Computer, auf dem Skype für Business Server 2019-Hauptkomponenten (OcsCore.msi) installiert ist.
ms.openlocfilehash: 23a5b4c3af8ac02ebfd620d3bbc46ddcba5bea11
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027809"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="ce755-103">Überprüfen von Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ce755-103">Verify configuration settings</span></span>

<span data-ttu-id="ce755-104">Sie können auf Gültigkeit überprüfen die Replikation der Konfigurationsinformationen auf dem Edge-Server durch Ausführen der Skype für Business Server 2019 **Get-CsManagementStoreReplicationStatus** -Cmdlet auf dem internen Computer, auf dem sich der zentralen Verwaltungsspeicher befindet, oder Klicken Sie auf eine beliebige Domäne gehörenden Computer auf dem Skype für Business Server 2019-Hauptkomponenten (OcsCore.msi) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ce755-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="ce755-105">Anfängliche Ergebnisse können Sie den Status als "False" anstelle von "True" für die Replikation angeben.</span><span class="sxs-lookup"><span data-stu-id="ce755-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="ce755-106">Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** und Zeit für die Replikation abgeschlossen ist, das **Get-CsManagementStoreReplicationStatus** erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="ce755-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

