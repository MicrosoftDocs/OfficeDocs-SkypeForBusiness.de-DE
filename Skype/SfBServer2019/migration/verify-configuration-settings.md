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
description: Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Domänencomputer, auf dem Skype for Business Server 2019 Core Components (OcsCore.msi) installiert ist.
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335745"
---
# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer, auf dem Skype for Business Server 2019 Core Components (OcsCore.msi) installiert ist. 
  
Anfänglich wird anstelle des Status "True" möglicherweise der Status "False" für die Replikation angezeigt. Führen Sie in diesem Fall das Cmdlet **Invoke-CsManagementStoreReplication** aus, und warten Sie den Abschluss der Replikation ab. Führen Sie anschließend erneut das Cmdlet **Get-CsManagementStoreReplicationStatus** aus. 
  

