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
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server Speicher. Wenn Sie Datenbanken mithilfe des Topologie-Generators installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server oder SQL Server Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine angeschlossene Datenbank installieren müssen, müssen Sie stattdessen die Befehlszeilenschnittstelle Windows PowerShell und das cmdlet Install-CsDatabase verwenden.
ms.openlocfilehash: 0ba463ed2995aae2a31890633b7a959cf889837c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833085"
---
# <a name="create-database"></a>Erstellen einer Datenbank
 
Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server Speicher. Wenn Sie Datenbanken mithilfe des Topologie-Generators installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server oder SQL Server Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine angeschlossene Datenbank installieren müssen, müssen Sie stattdessen die Befehlszeilenschnittstelle Windows PowerShell und das [Cmdlet "Install-CsDatabase"](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) verwenden.
  
### <a name="creating-a-database"></a>Erstellen einer Datenbank

1. Klicken Sie auf den Knoten Skype for Business Server 2015, und klicken Sie dann **auf Datenbank installieren.**
    
2. Wählen Sie **im** Dialogfeld "Datenbanken installieren" auf der Seite "Datenbank erstellen" den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des SQL Server-Speichers aus, in dem die neuen Datenbanken erstellt werden sollen. 
    
3. Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:
    
   - **Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.
    
   - **Standardpfade der SQL Server-Instanz verwenden**. Wenn Sie diese Option auswählen, wird der integrierte Algorithmus nicht verwendet, um die Speicherorte für die Datenbankprotokolle und Datendateien auszuwählen. Stattdessen werden Die Protokolldateien und Datendateien an den Speicherorten gespeichert, die im Standardpfad SQL Server angegeben sind (diese Pfade müssen von einem Administrator erweitert SQL Server werden). Datendateien werden im Standardspeicherort der SQL Server gespeichert, während Protokolldateien am Standardspeicherort der SQL Server gespeichert werden.
    
4. Klicken Sie auf **OK**.
    
5. Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.
    
6. Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.
    

