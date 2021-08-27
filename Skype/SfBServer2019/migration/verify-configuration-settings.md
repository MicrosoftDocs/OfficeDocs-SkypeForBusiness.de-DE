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
ms.localizationpriority: medium
description: Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Domänencomputer, auf dem Skype for Business Server 2019 Core Components (OcsCore.msi) installiert ist.
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594263"
---
# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer, auf dem Skype for Business Server 2019 Core Components (OcsCore.msi) installiert ist. 
  
Anfänglich wird anstelle des Status "True" möglicherweise der Status "False" für die Replikation angezeigt. Führen Sie in diesem Fall das Cmdlet **Invoke-CsManagementStoreReplication** aus, und warten Sie den Abschluss der Replikation ab. Führen Sie anschließend erneut das Cmdlet **Get-CsManagementStoreReplicationStatus** aus. 
  

