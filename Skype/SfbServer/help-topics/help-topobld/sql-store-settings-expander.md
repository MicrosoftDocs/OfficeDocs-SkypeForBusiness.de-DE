---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Zum Bearbeiten der Eigenschaften einer SQL Server Datenbank müssen Sie die SQL Server Datenbankinstanz ändern. Sie können das DialogfeldEigenschaften bearbeiten nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungsserver Datenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das DialogfeldEigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219610"
---
# <a name="sql-store-settings-expander"></a>SQL-Speichereinstellungen – Erweiterung
 
Zum Bearbeiten der Eigenschaften einer SQL Server Datenbank müssen Sie die SQL Server Datenbankinstanz ändern. Sie können das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungsserver Datenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Bearbeiten der Eigenschaften einer SQL Server Datenbank

Zum Ändern der Instanz von SQL Server, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird, führen Sie das folgende Verfahren im Topologie-Generator aus:
  
### <a name="to-modify-an-instance-of-sql-server"></a>So ändern Sie eine Instanz von SQL Server

1. Wählen Sie unter dem Knoten **SQL-Speicher** die gewünschte Datenbank aus, und klicken Sie auf **Eigenschaften bearbeiten**.
    
2. Führen Sie im Dialogfeld **Eigenschaften bearbeiten** einen der folgenden Schritte aus:
    
   - Wenn Sie die Standard SQL Server Instanz verwenden möchten, wählen Sie **Standardinstanz** aus, und klicken Sie dann auf **OK**.
    
   - Wählen Sie zum Verwenden einer benannten Datenbankinstanz die Option **Benannte Instanz** aus, geben Sie den Instanznamen in das Textfeld ein, und klicken Sie auf **OK**. Geben Sie nur den Namen der Instanz ein (beispielsweise ArchivingInstance), und nicht den gesamten SQL Server Pfad.
    
Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, überprüft der Topologie-Generator nicht, ob es sich bei der Datenbankinstanz, die Sie eingegeben haben, um eine gültige Instanz handelt. Wenn Sie beispielsweise versehentlich typeArchivingInstanec als Instanzname und dann auf **OK**klicken, akzeptiert Topologie-Generator diese ungültige Instanz. Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler korrigieren: Wenn eine SQL Server Instanz nicht gefunden werden kann, erstellt der Topologie-Generator diese Instanz nicht für Sie.
  

