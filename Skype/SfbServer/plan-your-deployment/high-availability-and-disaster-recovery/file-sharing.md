---
title: Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informationen Sie zu sicherstellen hoher Verfügbarkeit für Ihre Dateifreigaben in Skype für Business Server unter Verwendung von DFS.
ms.openlocfilehash: f96e4aaca70c501425528b12207eeab01027c9a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="file-sharing-high-availability-in-skype-for-business-server-2015"></a>Hohe Verfügbarkeit der Dateifreigabe in Skype for Business Server 2015
 
Informationen Sie zu sicherstellen hoher Verfügbarkeit für Ihre Dateifreigaben in Skype für Business Server unter Verwendung von DFS.
  
Um hohe Verfügbarkeit für Dateifreigabe in Ihrer Skype für Business Server-Bereitstellung zu gewährleisten, können Sie das verteilten Dateisystem (DFS). DFS unterstützt Failover von einem Dateiserver auf einen anderen innerhalb desselben Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden. Weitere Informationen zu DFS in Windows Server 2012 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Informationen zu DFS unter Windows Server 2008 finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
Je nach Größe Ihres Netzwerks, und die Größe des gewünschten Resiliency, können Sie ein Paar von Servern zum Hosten von alle Dateifreigaben in einer Website verwenden oder ein Paar pro Front-End-Pool verwenden.
  
DFS ist ein best Effort Datei Replikationsmechanismus, ohne veröffentlichte Recovery Time Objective (RTO) und Recovery Point Objective (RPO) Engagement. Ein Failover zwischen DFS-Servern sollten schnell ausgeführt werden, aber Daten Replikation Verzögerung möglicherweise verhindern, dass Benutzer wird Arbeit fortsetzen, wenn das Failover erfolgt.
  
Wenn Sie DFS verwenden und der Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfter speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt des ausgefallenen Servers auf dem anderen Server wiederherzustellen, der mit dem jetzt nicht mehr verfügbaren Server kombiniert ist.
  

