---
title: Höhere Verfügbarkeit von Dateien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informieren Sie sich über die Gewährleistung einer höheren Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server mithilfe von DFS.
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815933"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Höhere Verfügbarkeit von Dateien in Skype for Business Server
 
Informieren Sie sich über die Gewährleistung einer höheren Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server mithilfe von DFS.
  
Wenn Sie eine höhere Verfügbarkeit für die Dateifreigabe in Ihrer Skype for Business Server-Bereitstellung gewährleisten möchten, können Sie das verteilte Datei System (Distributed File System, DFS) verwenden. DFS unterstützt Failover von einem Dateiserver auf einen anderen innerhalb desselben Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden. Weitere Informationen zu DFS in Windows Server 2012 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Informationen zu DFS unter Windows Server 2008 finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
Je nach Größe Ihres Netzwerks und dem gewünschten Maß an Flexibilität können Sie mit einem Serverpaar alle Dateifreigaben auf einer Website hosten oder ein paar pro Front-End-Pool verwenden.
  
Bei DFS handelt es sich um einen Best Effort-Datei Replikationsmechanismus, bei dem keine RTO-oder Recovery Point Objective (RPO)-Zusicherungen veröffentlicht werden. Ein Failover zwischen DFS-Servern sollte schnell abgeschlossen werden, die Daten Replikationsverzögerung kann jedoch verhindern, dass Benutzer in der Lage sind, die laufende Arbeit fortzusetzen, wenn das Failover eintritt.
  
Wenn Sie DFS verwenden und der Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfter speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt des ausgefallenen Servers auf dem anderen Server wiederherzustellen, der mit dem jetzt nicht mehr verfügbaren Server kombiniert ist.
  

