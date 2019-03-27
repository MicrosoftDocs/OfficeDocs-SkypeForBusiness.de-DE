---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können die Replikation der Konfigurationsinformationen auf dem Edge-Server durch Ausführen der Skype für Business Server 2019 Get-CsManagementStoreReplicationStatus-Cmdlet auf dem internen Computer, auf dem sich der zentrale Verwaltungsspeicher befindet oder auf eine überprüfen in die Domäne eingebundener Computer, auf dem Skype für Business Server 2019-Hauptkomponenten (OcsCore.msi) installiert ist.
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889676"
---
# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

Sie können auf Gültigkeit überprüfen die Replikation der Konfigurationsinformationen auf dem Edge-Server durch Ausführen der Skype für Business Server 2019 **Get-CsManagementStoreReplicationStatus** -Cmdlet auf dem internen Computer, auf dem sich der zentralen Verwaltungsspeicher befindet, oder Klicken Sie auf eine beliebige Domäne gehörenden Computer auf dem Skype für Business Server 2019-Hauptkomponenten (OcsCore.msi) installiert ist. 
  
Anfängliche Ergebnisse können Sie den Status als "False" anstelle von "True" für die Replikation angeben. Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** und Zeit für die Replikation abgeschlossen ist, das **Get-CsManagementStoreReplicationStatus** erneut ausführen. 
  

