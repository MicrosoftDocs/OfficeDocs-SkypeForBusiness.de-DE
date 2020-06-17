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
# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das **Get-CsManagementStoreReplicationStatus-** Cmdlet Skype for Business Server 2019 auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer mit Domänenbeitritt, auf dem Skype for Business Server 2019-Kernkomponenten (OcsCore.msi) installiert ist. 
  
Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an. Wenn dies der Fall ist, führen Sie das **Invoke-CsManagementStoreReplication-** Cmdlet aus, und lassen Sie die Replikation vor dem erneuten Ausführen des **Get-CsManagementStoreReplicationStatus** Zeit in Anspruch nehmen. 
  

