---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie entfernen die Microsoft SQL Server-Datenbanken und-Instanzen, nachdem Sie die Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server neu konfiguriert haben, um eine andere Datenbank zu verwenden. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht verfügbar sind.
ms.openlocfilehash: 2d0902293c675143609dd720cd33734edd538d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301118"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server

Sie entfernen die Microsoft SQL Server-Datenbanken und-Instanzen, nachdem Sie die Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server neu konfiguriert haben, um eine andere Datenbank zu verwenden. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht verfügbar sind.
  
Um die Datenbanken oder Instanzen für den Archivierungsserver oder den Überwachungsserver zu entfernen, müssen Sie zuerst die Serverrolle entfernen. Um die Instanzen oder Datenbanken für den Front-End-Pool zu entfernen, müssen Sie die abhängige Serverrolle zunächst entfernen oder neu konfigurieren. Bei diesen Verfahren wird nicht zwischen zusammengefassten Datenbanken oder separaten Instanzen für Server unterschieden. Die Verfahren sind von der Daten Bank Zusammenstellung nicht betroffen.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Entfernen der SQL Server-Datenbank für einen Monitoring Server](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Entfernen der SQL Server-Datenbank für einen Archivierungsserver](remove-the-sql-server-database-for-an-archiving-server.md)
    

