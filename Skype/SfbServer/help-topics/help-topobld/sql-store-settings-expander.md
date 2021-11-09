---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Um die Eigenschaften einer SQL Server Datenbank zu bearbeiten, müssen Sie die SQL Server Datenbankinstanz ändern. Sie können das Dialogfeld Eigenschaften bearbeiten nicht verwenden, um Aufgaben auszuführen, z. B. das Verschieben der Archivierungsserverdatenbank von einem Computer auf einen anderen. Darüber hinaus können Sie das Dialogfeld Eigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
ms.openlocfilehash: 0c5af1546b601933705daf4b4e1a6817fe4b04ee
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861372"
---
# <a name="sql-store-settings-expander"></a>SQL-Speichereinstellungen – Erweiterung
 
Um die Eigenschaften einer SQL Server Datenbank zu bearbeiten, müssen Sie die SQL Server Datenbankinstanz ändern. Sie können das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um Aufgaben auszuführen, z. B. das Verschieben der Archivierungsserverdatenbank von einem Computer auf einen anderen. Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Bearbeiten der Eigenschaften einer SQL Server-Datenbank

Führen Sie das folgende Verfahren im Topologie-Generator aus, um die Instanz von SQL Server zu ändern, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird:
  
### <a name="to-modify-an-instance-of-sql-server"></a>So ändern Sie eine Instanz von SQL Server

1. Wählen Sie unter dem Knoten **SQL-Speicher** die gewünschte Datenbank aus, und klicken Sie auf **Eigenschaften bearbeiten**.
    
2. Führen Sie im Dialogfeld **Eigenschaften bearbeiten** einen der folgenden Schritte aus:
    
   - Wenn Sie die Standardinstanz SQL Server verwenden möchten, wählen Sie **"Standardinstanz" aus,** und klicken Sie dann auf **"OK".**
    
   - Wählen Sie zum Verwenden einer benannten Datenbankinstanz die Option **Benannte Instanz** aus, geben Sie den Instanznamen in das Textfeld ein, und klicken Sie auf **OK**. Sie sollten nur den Instanznamen (z. B. ArchivingInstance) und nicht den gesamten SQL Server Pfad eingeben.
    
Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, überprüft der Topologie-Generator nicht, ob es sich bei der eingegebenen Datenbankinstanz um eine gültige Instanz handelt. Wenn Sie z. B. versehentlich "ArchivingInstanec" als Instanznamen eingeben und dann auf **"OK"** klicken, akzeptiert der Topologie-Generator diese ungültige Instanz. Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler beheben: Wenn eine SQL Server Instanz nicht gefunden werden kann, erstellt der Topologie-Generator diese Instanz nicht für Sie.
  

