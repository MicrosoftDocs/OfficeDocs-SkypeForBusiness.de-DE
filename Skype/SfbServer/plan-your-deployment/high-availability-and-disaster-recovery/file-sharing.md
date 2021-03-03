---
title: Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Erfahren Sie mehr über die Sicherstellung der hohen Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server mithilfe von DFS.
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802895"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server
 
Erfahren Sie mehr über die Sicherstellung der hohen Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server mithilfe von DFS.
  
Um eine hohe Verfügbarkeit für die Dateifreigabe in Ihrer Skype for Business Server-Bereitstellung sicherzustellen, können Sie das verteilte Dateisystem (Distributed File System, DFS) verwenden. DFS unterstützt Failover von einem Dateiserver auf einen anderen Dateiserver innerhalb des gleichen Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden. Weitere Informationen zu DFS in Windows Server 2012 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) . Informationen zu DFS unter Windows Server 2008 finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) .
  
Abhängig von der Größe Ihres Netzwerks und der gewünschten Ausfallsicherheit können Sie ein Serverpaar zum Hosten von sämtlichen Dateifreigaben eines Standorts oder ein Paar je Front-End-Pool verwenden.
  
DFS ist ein "Best Effort"-Mechanismus für die Dateireplikation ohne veröffentlichte Zusagen für Wiederherstellungszeit (Recovery Time Objective - RTO) oder Wiederherstellungspunkt (Recovery Point Objective - RPO). Ein Failover zwischen den DFS-Servern sollte schnell abgeschlossen werden, aber die Verzögerung bei der Datenreplikation verhindert möglicherweise, dass Benutzer ihre Arbeit fortsetzen können, wenn das Failover eintritt.
  
Wenn Sie DFS verwenden und der Datenspeicher für die Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben häufig sichern, z. B. alle 4 bis 8 Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt auf dem ausgefallenen Server auf den anderen Server wiederherzustellen, der mit dem Server kombiniert ist, welcher jetzt nicht verfügbar ist.
  

