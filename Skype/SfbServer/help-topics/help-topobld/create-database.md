---
title: Erstellen der Datenbank
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server Speicher. Wenn Sie Datenbanken mithilfe des Topologie-Generators installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server Computer oder SQL Server Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine verbundenen Datenbank installieren müssen, müssen Sie stattdessen Windows PowerShell Befehlszeilenschnittstelle und das cmdlet Install-CsDatabase verwenden.
ms.openlocfilehash: b8c4cc75104093b868d40be18a540eea4019a0b7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619891"
---
# <a name="create-database"></a>Erstellen einer Datenbank
 
Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server Speicher. Wenn Sie Datenbanken mithilfe des Topologie-Generators installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server Computer oder SQL Server Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine verbundenen Datenbank installieren müssen, müssen Sie stattdessen Windows PowerShell Befehlszeilenschnittstelle und das Cmdlet ["Install-CsDatabase"](/powershell/module/skype/install-csdatabase?view=skype-ps) verwenden.
  
### <a name="creating-a-database"></a>Erstellen einer Datenbank

1. Klicken Sie auf den Knoten Skype for Business Server 2015, und klicken Sie dann auf **"Datenbank installieren".**
    
2. Wählen Sie im Dialogfeld **"Datenbanken installieren"** auf der Seite **"Datenbank erstellen"** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des SQL Server Speichers aus, in dem die neuen Datenbanken erstellt werden sollen.
    
3. Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:
    
   - **Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.
    
   - **Standardpfade der SQL Server-Instanz verwenden**. Wenn Sie diese Option auswählen, wird der integrierte Algorithmus nicht verwendet, um die Speicherorte für die Datenbankprotokolle und Datendateien auszuwählen. Stattdessen werden Protokolldateien und Datendateien an den Speicherorten gespeichert, die vom SQL Server Standardpfad angegeben werden (diese Pfade müssen von einem SQL Server Administrator erweitert konfiguriert werden). Datendateien werden im Standardmäßigen SQL Server Speicherort der Datendatei gespeichert, während Protokolldateien im Standardspeicherort SQL Server Protokolldatei gespeichert werden.
    
4. Klicken Sie auf **OK**.
    
5. Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.
    
6. Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.
