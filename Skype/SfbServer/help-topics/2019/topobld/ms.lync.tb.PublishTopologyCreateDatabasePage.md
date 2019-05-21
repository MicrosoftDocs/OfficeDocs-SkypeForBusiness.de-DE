---
title: Erstellen der Datenbank
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server-Speicher. Wenn Sie Datenbanken mit dem Topologie-Generator installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server-Computer oder SQL Server-Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine in der Datenbank enthaltene Datenbank installieren müssen, müssen Sie stattdessen die Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet "installieren-CsDatabase" verwenden.
ms.openlocfilehash: 5736e399771eef30808e62c8a11876d1b6f3d8ed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302144"
---
# <a name="create-database"></a>Erstellen der Datenbank
 
Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server-Speicher. Wenn Sie Datenbanken mit dem Topologie-Generator installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server-Computer oder SQL Server-Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine in der Datenbank enthaltene Datenbank installieren müssen, müssen Sie stattdessen die Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet " [Installieren-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) " verwenden.
  
### <a name="creating-a-database"></a>Erstellen einer Datenbank

1. Klicken Sie auf den Knoten Skype for Business Server, und klicken Sie dann auf **Datenbank installieren**.
    
2. Wählen Sie im Dialogfeld **Datenbanken installieren** auf der Seite **Datenbank erstellen** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des SQL Server-Speichers aus, in dem die neuen Datenbanken erstellt werden sollen.
    
3. Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:
    
   - **Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.
    
   - **Verwenden Sie die Standardeinstellungen für SQL Server-Instanzen**. Wenn Sie diese Option auswählen, wird der integrierte Algorithmus nicht verwendet, um die Speicherorte für die Datenbankprotokolle und Datendateien auszuwählen. Stattdessen werden Protokoll-und Datendateien an den Speicherorten gespeichert, die vom SQL Server-Standardpfad angegeben werden (diese Pfade müssen von einem SQL Server-Administrator in Advanced konfiguriert werden). Datendateien werden im Standardspeicherort der SQL Server-Datendatei gespeichert, während Protokolldateien im Standardspeicherort der SQL Server-Protokolldatei gespeichert werden.
    
4. Klicken Sie auf **OK**.
    
5. Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.
    
6. Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.
    

