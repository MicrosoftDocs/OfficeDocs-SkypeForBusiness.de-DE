---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie die Eigenschaften einer SQL Server-Datenbank bearbeiten möchten, müssen Sie die SQL Server-Datenbankinstanz ändern. Sie können das DialogfeldEigenschaften bearbeiten nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungs Server-Datenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das DialogfeldEigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
ms.openlocfilehash: 10dd68bc7cfbeb58461afdb5d6c3427c4bc80056
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798282"
---
# <a name="sql-store-settings-expander"></a>SQL-Speichereinstellungen – Erweiterung
 
Wenn Sie die Eigenschaften einer SQL Server-Datenbank bearbeiten möchten, müssen Sie die SQL Server-Datenbankinstanz ändern. Sie können das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungs Server-Datenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Bearbeiten der Eigenschaften einer SQL Server-Datenbank

Wenn Sie die Instanz von SQL Server ändern möchten, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird, führen Sie das folgende Verfahren im Topologie-Generator aus:
  
### <a name="to-modify-an-instance-of-sql-server"></a>So ändern Sie eine Instanz von SQL Server

1. Wählen Sie die entsprechende Datenbank unter dem Knoten **SQL Stores** aus, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Führen Sie im Dialogfeld **Eigenschaften bearbeiten** eine der folgenden Aktionen aus:
    
   - Wenn Sie die standardmäßige SQL Server-Instanz verwenden möchten, wählen Sie **Standardinstanz** aus, und klicken Sie dann auf **OK**.
    
   - Wenn Sie eine benannte Datenbankinstanz verwenden möchten, wählen Sie **benannte Instanz**aus, geben Sie den Namen der Instanz in das Textfeld ein, und klicken Sie dann auf **OK**. Geben Sie nur den Namen der Instanz (beispielsweise ArchivingInstance) und nicht den gesamten SQL Server-Pfad ein.
    
Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, überprüft der Topologie-Generator nicht, ob es sich bei der von Ihnen eingegebenen Datenbankinstanz um eine gültige Instanz handelt. Wenn Sie beispielsweise versehentlich als typeArchivingInstanec und dann auf **OK**klicken, akzeptiert der Topologie-Generator diese ungültige Instanz. Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler korrigieren: Wenn eine SQL Server-Instanz nicht gefunden werden kann, wird diese Instanz von Topology Builder nicht für Sie erstellt.
  

