---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Bearbeiten der Eigenschaften einer SQL Server-Datenbank müssen Sie die Instanz des SQL Server-Datenbank ändern. Klicken Sie im Dialogfeld Eigenschaften bearbeiten können Aufgaben wie die Archivierungsserver-Datenbank von einem Computer an eine andere verschieben. Darüber hinaus können Sie das Dialogfeld Eigenschaften bearbeiten zum Verwenden der Instanz von SQL Server, der als Host Ändern des zentralen Verwaltungsspeichers.
ms.openlocfilehash: d1b5287344095c062421a6afc56d620c81584fd3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894259"
---
# <a name="sql-store-settings-expander"></a>SQL-Speichereinstellungen – Erweiterung
 
Zum Bearbeiten der Eigenschaften einer SQL Server-Datenbank müssen Sie die Instanz des SQL Server-Datenbank ändern. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** können Aufgaben wie die Archivierungsserver-Datenbank von einem Computer an eine andere verschieben. Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** zum Verwenden der Instanz von SQL Server, der als Host Ändern des zentralen Verwaltungsspeichers.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Bearbeiten der Eigenschaften einer SQL Server-Datenbank

Führen Sie im Topologie-Generator die folgenden Schritte aus, um die Instanz von SQL Server zu ändern, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird:
  
### <a name="to-modify-an-instance-of-sql-server"></a>So ändern Sie eine Instanz von SQL Server

1. Wählen Sie unter dem Knoten **SQL-Speicher** die gewünschte Datenbank aus, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** führen Sie eine der folgenden Aktionen aus:
    
   - Um die Standardinstanz von SQL Server verwenden, wählen Sie **Standardinstanz** aus, und klicken Sie dann auf **OK**.
    
   - Um eine benannte Datenbankinstanz verwenden, wählen Sie **Benannte Instanz**, geben Sie den Namen der Instanz in das Textfeld ein, und klicken Sie dann auf **OK**. Sie sollten nur der Name der Instanz (beispielsweise ArchivingInstance) und nicht den gesamten SQL Server-Pfad eingeben.
    
Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, wird Topologie-Generator nicht stellen Sie sicher, dass die Datenbankinstanz, die Sie eingegeben haben, um eine gültige Instanz ist. Angenommen, wenn Sie versehentlich TypeArchivingInstanec als den Namen der Instanz, und klicken Sie dann auf **OK**, Topologie-Generator akzeptiert, dass ungültige Instanz. Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler beheben: Wenn eine SQL Server-Instanz kann nicht gefunden werden, erstellt der Topologie-Generator diese Instanz nicht für Sie.
  

