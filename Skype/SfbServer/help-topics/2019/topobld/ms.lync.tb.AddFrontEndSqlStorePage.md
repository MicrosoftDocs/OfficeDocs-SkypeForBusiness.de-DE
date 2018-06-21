---
title: Hinzufügen von Front-End-SQL Server-Speichers
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Eine Standard Edition-Server-Bereitstellung installiert automatisch die erforderlichen Microsoft SQL Server Express-Datenbanksoftware und SQL Server-Datenbank. Aus diesem Grund können alle Optionen sind vorausgefüllt, und Sie Änderungen auf die Standardkonfiguration.
ms.openlocfilehash: 2b7527207974310c30b559011a580fe8871164d1
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964491"
---
# <a name="add-front-end-sql-server-store"></a>Hinzufügen von Front-End-SQL Server-Speichers
 
Eine Standard Edition-Server-Bereitstellung installiert automatisch die erforderlichen Microsoft SQL Server Express-Datenbanksoftware und SQL Server-Datenbank. Aus diesem Grund können alle Optionen sind vorausgefüllt, und Sie Änderungen auf die Standardkonfiguration.
  
Der Front-End-Pool von einer Enterprise Edition-Server-Bereitstellung erfordert eine unterstützte 64-Bit-Edition von SQL Server-Datenbanksoftware für Back-End-Datenbank. Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Back-End-Datenbank verwendet werden soll, oder definieren eine neue SQL Server-Datenbank durch einen vollqualifizierten Domänennamen (FQDN) des Servers auf dem SQL Server-Datenbank gespeichert ist und die Instanz von SQL S angeben Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben). Sie können Sie die Spiegelung in SQL Server-Speichers aktivieren, und angeben ein spiegelungszeugen für automatisches Failover.
  
Ausführliche Informationen zu SQL Server unterstützen Sie, finden Sie in der Unterstützungsdokumentation unter [-Datenbanksoftware und Clustering unterstützt](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) . Ausführliche Informationen zum Einrichten von SQL Server für die Back-End-Datenbank finden Sie unter [Konfigurieren von SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in der Bereitstellungsdokumentation.
  
> [!NOTE]
> Wenn das Konto, mit dem Veröffentlichen der Topologie, der ausreichenden Benutzerrechte und-Berechtigungen verfügt, können Sie die Back-End-Datenbank (Real-Time Communications (RTC)) erstellen beim Veröffentlichen Ihrer Topologie. Sie können auch die Datenbank später im Rahmen des Installationsverfahrens einschließlich erstellen. 
  
> [!NOTE]
> Zum Installieren und die Datenbanken auf dem SQL Server-basierten Server für Enterprise Edition-Bereitstellung bereitzustellen, müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie ein Mitglied der SQL Server-Gruppe Sysadmins nicht sind, müssen Sie anfordern, der Gruppe hinzugefügt werden soll, bis die Datenbankdateien bereitgestellt werden. Wenn Sie ein Mitglied der Gruppe Sysadmins hergestellt werden können, sollten Sie sich an den Datenbankadministrator SQL Server bereitstellen, mit dem Skript konfigurieren und Bereitstellen der Datenbanken. Ausführliche Informationen über die Benutzerrechte und Berechtigungen, mit denen Sie die Verfahren durchführen müssen, finden Sie unter [Berechtigungen für SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx). 
  

