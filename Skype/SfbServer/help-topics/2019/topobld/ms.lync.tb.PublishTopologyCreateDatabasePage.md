---
title: Erstellen der Datenbank
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Topologie-Generator bietet die Möglichkeit, Datenbanken auf SQL Server-Speicher zu installieren. Wenn Sie die Datenbanken mithilfe des Topologie-Generator installieren, wird die Anwendung liest Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen Computer mit SQL Server oder SQL Server-Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine verbundene Datenbank installieren müssen, müssen Sie Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet "Install-CsDatabase" stattdessen verwenden.
ms.openlocfilehash: f9d351d4b6b7cb37d2daeb889caabb1f4090e74e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979799"
---
# <a name="create-database"></a>Erstellen der Datenbank
 
Topologie-Generator bietet die Möglichkeit, Datenbanken auf SQL Server-Speicher zu installieren. Wenn Sie die Datenbanken mithilfe des Topologie-Generator installieren, wird die Anwendung liest Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen Computer mit SQL Server oder SQL Server-Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine verbundene Datenbank installieren müssen, müssen Sie Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet " [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) " stattdessen verwenden.
  
### <a name="creating-a-database"></a>Erstellen einer Datenbank

1. Klicken Sie auf die Skype für Business Server-Knoten, und klicken Sie dann auf **Datenbank installieren**.
    
2. Wählen Sie im Dialogfeld **Datenbanken installieren** auf der Seite **Datenbank erstellen** den vollqualifizierten Domänennamen (FQDN) des SQL Server-Speichers, in dem die neuen Datenbanken erstellt werden soll.
    
3. Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:
    
  - **Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.
    
  - **Mithilfe von SQL Server-Instanz Standardwerte**. Wenn Sie diese Option auswählen, wird der integrierte Algorithmus, wählen Sie die Speicherorte für die Datenbankprotokolle und Datendateien nicht verwendet. Protokoll- und Datendateien werden stattdessen in den durch den SQL Server-Standardeinstellungen Pfad (diese Pfade müssen in konfiguriert werden von SQL Server-Administrator erweiterte) angegebenen Speicherorten gespeichert. Datendateien werden in der SQL Server-Daten Datei Standardspeicherort gespeichert werden, während der Protokolldateien in der standardmäßigen SQL Server-Protokolldatei gespeichert werden.
    
4. Klicken Sie auf **OK**.
    
5. Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.
    
6. Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.
    

