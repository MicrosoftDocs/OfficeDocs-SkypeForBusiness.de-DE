---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Wenn Sie die Eigenschaften einer SQL Server bearbeiten möchten, müssen Sie die SQL Server ändern. Sie können das Dialogfeld Eigenschaften bearbeiten nicht verwenden, um Aufgaben wie das Verschieben der Archivierungsserverdatenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das Dialogfeld Eigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server, die den zentralen Verwaltungsspeicher hostet, zu ändern.
ms.openlocfilehash: d6601349afcc458fc4ba8c3f4feb8810a9c71c42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818095"
---
# <a name="sql-store-settings-expander"></a>SQL-Speichereinstellungen – Erweiterung
 
Wenn Sie die Eigenschaften einer SQL Server bearbeiten möchten, müssen Sie die SQL Server ändern. Sie können das Dialogfeld **Eigenschaften** bearbeiten nicht verwenden, um Aufgaben wie das Verschieben der Archivierungsserverdatenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie  das Dialogfeld Eigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server, die den zentralen Verwaltungsspeicher hostet, zu ändern.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Bearbeiten der Eigenschaften einer SQL Server Datenbank

Führen Sie zum Ändern der Instanz SQL Server, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird, das folgende Verfahren im Topologie-Generator aus:
  
### <a name="to-modify-an-instance-of-sql-server"></a>So ändern Sie eine Instanz SQL Server

1. Wählen Sie unter dem Knoten **SQL-Speicher** die gewünschte Datenbank aus, und klicken Sie auf **Eigenschaften bearbeiten**.
    
2. Führen Sie im Dialogfeld **Eigenschaften bearbeiten** einen der folgenden Schritte aus:
    
   - Wenn Sie die Standardinstanz SQL Server, wählen Sie **"Standardinstanz" aus,** und klicken Sie dann auf **"OK".**
    
   - Wählen Sie zum Verwenden einer benannten Datenbankinstanz die Option **Benannte Instanz** aus, geben Sie den Instanznamen in das Textfeld ein, und klicken Sie auf **OK**. Sie sollten nur den Instanznamen (z. B. ArchivingInstance) und nicht den SQL Server eingeben.
    
Wenn Sie im  Dialogfeld Eigenschaften bearbeiten arbeiten, überprüft der Topologie-Generator nicht, ob es sich bei der eingegebenen Datenbankinstanz um eine gültige Instanz handelt. Wenn Sie beispielsweise versehentlich "ArchivingInstanec" als Instanznamen eingeben und dann auf **"OK"** klicken, akzeptiert der Topologie-Generator diese ungültige Instanz. Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler beheben: Wenn eine SQL Server nicht gefunden werden kann, erstellt der Topologie-Generator diese Instanz nicht für Sie.
  

