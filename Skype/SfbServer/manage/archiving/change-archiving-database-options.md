---
title: Ändern der Archivierungsdatenbankoptionen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Zusammenfassung: Informationen zum Ändern der Archivierungsdatenbankoptionen für Skype for Business Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817695"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Ändern der Archivierungsdatenbankoptionen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie archivierungsdatenbankoptionen für Skype for Business Server ändern.
  
Wenn Sie die Archivierung mithilfe SQL Server Archivierungsspeichers für einen Ihrer Benutzer bereitstellen, können Sie die folgenden Datenbankspeicheränderungen vornehmen:
  
- Verwenden Sie eine andere SQL Server für den Archivierungsspeicher. Dazu gehören die primäre Archivierungsdatenbank und alle Datenbanken, die Sie für die SQL Server verwenden.
    
- Wechseln Sie zur Microsoft Exchange-Integration, um Archivierungsdaten und Dateien auf den Exchange-Servern zu speichern. Wenn alle Ihre Benutzer auf Ihren Exchange-Servern gespeichert sind und Sie Microsoft Exchange-Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server Auslagerungsspeicherdatenbanken aus ihrer Topologie entfernen. 
    
Um eine dieser Änderungen vorzunehmen, müssen Sie den Topologie-Generator ausführen, die Änderungen vornehmen und die Topologie dann erneut veröffentlichen. Geben Sie keine **Archivierungsspeicher SQL Server speicher-** oder **SQL Server** Speicherspiegelungsinformationen an, es sei denn, Sie verfügen über Skype for Business-Benutzer, die nicht auf den Exchange-Servern gespeichert sind.
  
## <a name="change-archiving-database-options"></a>Ändern von Optionen für Archivierungsdatenbanken

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe (oder eines Kontos mit entsprechenden Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist, aber eine Topologie veröffentlichen. zum Hinzufügen einer Komponente zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe **"Domänen-Admins"** und der Gruppe **"RTCUniversalServerAdmins"** ist und über Vollzugriffsberechtigungen (d. h. Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den Skype for Business Server-Dateispeicher verwenden (d. h. damit der Topologie-Generator die erforderlichen discretionary Access Control Lists (DACLs) oder ein Konto mit entsprechenden Rechten konfigurieren kann.
  
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben, und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.
    
7. Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:
    
   - Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
   - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
    
     - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
     - Wenn Sie einen neuen SQL Server angeben möchten, klicken Sie auf "Neu", und gehen Sie dann im Dialogfeld "Neuen **SQL Server Speicher** definieren" wie folgt vor:
    
       - Geben **SQL Server FQDN** des Servers an, auf dem Sie den neuen SQL Server erstellen möchten.
    
       - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
       - Wenn sich die angegebene SQL Server in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen  **"This SQL instance is in mirroring relation",** und geben Sie dann in der Nummer des Spiegelports die Portnummer an.
    
   - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:
    
     - Um einen vorhandenen SQL Server speicher für die  Spiegelung zu verwenden, klicken Sie im Dropdownlistenfeld für den Archivierungsspeicher SQL Server auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
    
     - Um einen neuen SQL Server für die Spiegelung anzugeben, klicken Sie auf "Neu", **und** gehen Sie dann im Dialogfeld "Neuen SQL Server Speicher definieren" wie folgt vor:
    
       a. Geben **SQL Server FQDN** des SQL Server an, auf dem Sie den neuen SQL Server erstellen möchten.
    
       b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
       c. Wenn sich die angegebene SQL Server in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen  **"This SQL instance is in mirroring relation",** und geben Sie dann in der Nummer des Spiegelports die Portnummer an.
    
   - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungszeugen hinzufügen oder ändern möchten (eine dritte, separate SQL Server-Instanz, die die Integrität  des primären SQL Server-Servers und der Spiegelinstanzen erkennen kann), aktivieren Sie das Kontrollkästchen SQL Server-Spiegelungszeugen verwenden, um das automatische Failover zu aktivieren, und führen Sie dann einen der folgenden Schritte aus:
    
      a. Geben **SQL Server FQDN** des Servers, auf dem Sie den neuen Spiegelungszeugen erstellen möchten, SQL Server an.
    
      b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
      c. Wenn sich die angegebene SQL Server in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen  **"This SQL instance is in mirroring relation",** und geben Sie dann in der Nummer des Spiegelports die Portnummer an.
    
   - Löschen Sie alle Informationen für Archivierungsdatenbanken, um zur Microsoft Exchange-Integration zu wechseln, um Archivierungsdaten und Dateien auf den Exchange-Servern zu speichern (wenn alle Benutzer in Ihrer Bereitstellung auf ihren Exchange-Servern gespeichert sind).
    
     > [!IMPORTANT]
     > Wenn Sie Skype for Business-Benutzer haben, die nicht auf den Exchange-Servern gespeichert sind, löschen Sie die SQL Server Speicherinformationen. 
  
8. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
    > [!IMPORTANT]
    > Die Änderungen, die Sie im Topologie-Generator vornehmen, werden erst wirksam, wenn Sie die neue Topologie veröffentlichen. Weitere Informationen finden Sie unter [Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server.](../../deploy/deploy-archiving/add-archiving-databases.md) 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Ändern des Speicherorts der Archivierungsdatenbank mithilfe Windows PowerShell

In den meisten Fällen müssen Sie den Speicherort der Archivierungsdatenbank, der bei der Installation des Archivierungsservers angegeben wird, nicht ändern. Sollte jedoch ein Hardwarefehler oder ein anderes Problem auftreten, können Sie den Archivierungsserver mithilfe des Cmdlets **"Set-CsArchivingServer"** auf eine neue Datenbank verweisen.
  
Im folgenden Beispiel wird der Speicherort der Archivierungsdatenbank für den Archivierungsserver "ArchivingServer:atl-cs-001.contoso.com" geändert. In diesem Beispiel befindet sich die neue Datenbank unter "ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


