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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Erfahren Sie, wie Sie mit DFS eine hohe Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server sicherstellen.
ms.openlocfilehash: 6abdf9656ddca5148c9b04c6dbe11cdc5da7e840
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603814"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server
 
Erfahren Sie, wie Sie mit DFS eine hohe Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server sicherstellen.
  
Um eine hohe Verfügbarkeit für die Dateifreigabe in Ihrer Skype for Business Server Bereitstellung sicherzustellen, können Sie das verteilte Dateisystem (DFS) verwenden. DFS unterstützt Failover von einem Dateiserver auf einen anderen Dateiserver innerhalb des gleichen Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden. Weitere Informationen zu DFS in Windows Server 2012 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) . Informationen zu DFS auf Windows Server 2008 finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .
  
Abhängig von der Größe Ihres Netzwerks und der gewünschten Ausfallsicherheit können Sie ein Serverpaar zum Hosten von sämtlichen Dateifreigaben eines Standorts oder ein Paar je Front-End-Pool verwenden.
  
DFS ist ein "Best Effort"-Mechanismus für die Dateireplikation ohne veröffentlichte Zusagen für Wiederherstellungszeit (Recovery Time Objective - RTO) oder Wiederherstellungspunkt (Recovery Point Objective - RPO). Ein Failover zwischen DFS-Servern sollte schnell abgeschlossen werden, aber die Verzögerung der Datenreplikation kann benutzer daran hindern, die laufenden Arbeiten fortzusetzen, wenn das Failover erfolgt.
  
Wenn Sie DFS verwenden und der Datenspeicher für die Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben häufig sichern, z. B. alle 4 bis 8 Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt auf dem ausgefallenen Server auf den anderen Server wiederherzustellen, der mit dem Server kombiniert ist, welcher jetzt nicht verfügbar ist.
