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
localization_priority: Normal
description: Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die ausgeführten Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server für die Verwendung einer anderen Datenbank neu konfiguriert haben. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie das aktuelle SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht mehr verfügbar sind.
ms.openlocfilehash: f9e942f1f5516c0bf3437dd3fc9e2dc25b4cc4236e3cffabbf07ff08dde1e404
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306208"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server

Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die ausgeführten Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server für die Verwendung einer anderen Datenbank neu konfiguriert haben. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie das aktuelle SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht mehr verfügbar sind.
  
Um die Datenbanken oder Instanzen für den Archivierungsserver oder Den Monitoring Server zu entfernen, müssen Sie zuerst die Serverrolle entfernen. Entsprechend müssen Sie zum Entfernen der Instanzen oder Datenbanken für den Front-End-Pool zuerst die abhängige Serverrolle entfernen oder neu konfigurieren. Bei diesen Verfahren wird nicht zwischen oder verbundenen Datenbanken oder getrennten Instanzen für Server unterschieden. Die Kollokation von Datenbanken wirkt sich nicht auf die Verfahren aus.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Entfernen der SQL Server-Datenbank für einen Monitoring Server](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Entfernen der SQL Server-Datenbank für einen Archivierungsserver](remove-the-sql-server-database-for-an-archiving-server.md)
    

