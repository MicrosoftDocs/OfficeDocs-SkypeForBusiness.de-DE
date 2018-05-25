---
title: Hinzufügen von Monitoring Server SQL Server-Speichers
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Monitoring Server erfordert eine unterstützte 64-Bit-Edition von SQL Server-Datenbanksoftware, um die Überwachungsdaten zu speichern. Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Überwachung verwendet werden, oder definieren eine neue SQL Server-Datenbank durch angeben einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank werden sollen, zusätzlich zu der Instanz von SQL gespeichert Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: f52f44acd9ca57112da75fcc368d8ebaae99b081
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-monitoring-server-sql-server-store"></a>Hinzufügen von Monitoring Server SQL Server-Speichers
 
Monitoring Server erfordert eine unterstützte 64-Bit-Edition von SQL Server-Datenbanksoftware, um die Überwachungsdaten zu speichern. Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Überwachung verwendet werden, oder definieren eine neue SQL Server-Datenbank durch angeben einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank werden sollen, zusätzlich zu der Instanz von SQL gespeichert Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben).
  
Ausführliche Informationen zu SQL Server unterstützen Sie, finden Sie in der Unterstützungsdokumentation unter [-Datenbanksoftware und Clustering unterstützt](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) . Ausführliche Informationen zu der Überwachungsdatenbank, einschließlich Kollokation der Überwachungsdatenbank finden Sie unter [Serverspeicherort unterstützt](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation[Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in der Planungsdokumentation und [SQL Server-Daten und Platzieren der Protokolldatei](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.
  
> [!NOTE]
> Wenn das Konto verwendet, um die Topologie zu veröffentlichen der ausreichenden Benutzerrechte und-Berechtigungen verfügt, können Sie die Überwachungsdatenbank erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können auch die Datenbank später im Rahmen des Installationsverfahrens einschließlich erstellen. > Zum Installieren und die Datenbanken auf dem SQL Server-basierten Server für die Überwachung bereitzustellen, müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie nicht Mitglied der Gruppe der SQL Server-Sysadmin sind, müssen Sie anfordern, der Gruppe hinzugefügt werden soll, bis die Datenbankdateien bereitgestellt werden. Wenn Sie ein Mitglied der Gruppe Sysadmins hergestellt werden können, sollten Sie sich an den Datenbankadministrator SQL Server bereitstellen, mit dem Skript konfigurieren und Bereitstellen der Datenbanken. Ausführliche Informationen über die Rechte und Berechtigungen, die Sie zum Ausführen dieser Verfahren müssen, finden Sie unter [Berechtigungen für SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.
  

