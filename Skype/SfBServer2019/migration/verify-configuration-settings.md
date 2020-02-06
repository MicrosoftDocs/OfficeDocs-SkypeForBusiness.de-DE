---
title: Überprüfen der Konfigurationseinstellungen
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
description: Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet "Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus" auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen der Computer, auf dem die Skype for Business Server 2019-Core-Komponenten (OcsCore. msi) installiert sind.
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812753"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="bd772-103">Überprüfen der Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="bd772-103">Verify configuration settings</span></span>

<span data-ttu-id="bd772-104">Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet "Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** " auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer, auf dem die Skype for Business Server 2019 Core Components (OcsCore. msi) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bd772-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="bd772-105">Anfängliche Ergebnisse können den Status "falsch" anstelle von "true" für die Replikation angeben.</span><span class="sxs-lookup"><span data-stu-id="bd772-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="bd772-106">Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** aus, und lassen Sie die Replikation Zeit, bevor **Sie die Get-CsManagementStoreReplicationStatus** erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="bd772-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

