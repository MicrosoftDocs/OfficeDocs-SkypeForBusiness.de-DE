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
description: Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server neu konfiguriert haben, um eine andere Datenbank zu verwenden. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass er die Datenbanken veraltet oder nicht verfügbar macht.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752157"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server

Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server neu konfiguriert haben, um eine andere Datenbank zu verwenden. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass er die Datenbanken veraltet oder nicht verfügbar macht.
  
Um die Datenbanken oder Instanzen für die Archivierungsserver oder Monitoring Server zu entfernen, müssen Sie zuerst die Server Rolle entfernen. Ebenso müssen Sie zum Entfernen der Instanzen oder Datenbanken für Front-End-Pool zunächst die abhängige Serverrolle entfernen oder neu konfigurieren. Bei diesen Verfahren wird nicht zwischen oder verbundenen Datenbanken oder getrennten Instanzen für Server unterschieden. Die Kollokation von Datenbanken wirkt sich nicht auf die Verfahren aus.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Entfernen der SQL Server-Datenbank für einen Monitoring Server](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Entfernen der SQL Server-Datenbank für einen Archivierungsserver](remove-the-sql-server-database-for-an-archiving-server.md)
    

