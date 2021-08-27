---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
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
description: Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die ausgeführten Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server für die Verwendung einer anderen Datenbank neu konfiguriert haben. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie die aktuelle SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht mehr verfügbar sind.
ms.openlocfilehash: dafd1589bc4d1624a71998813fe785841cbfb713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582029"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server

Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die ausgeführten Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server für die Verwendung einer anderen Datenbank neu konfiguriert haben. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie die aktuelle SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht mehr verfügbar sind.
  
Um die Datenbanken oder Instanzen für den Archivierungsserver oder Den Monitoring Server zu entfernen, müssen Sie zuerst die Serverrolle entfernen. Entsprechend müssen Sie zum Entfernen der Instanzen oder Datenbanken für den Front-End-Pool zuerst die abhängige Serverrolle entfernen oder neu konfigurieren. Bei diesen Verfahren wird nicht zwischen oder verbundenen Datenbanken oder getrennten Instanzen für Server unterschieden. Die Kollokation von Datenbanken wirkt sich nicht auf die Verfahren aus.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Entfernen der SQL Server-Datenbank für einen Monitoring Server](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Entfernen der SQL Server-Datenbank für einen Archivierungsserver](remove-the-sql-server-database-for-an-archiving-server.md)
    

