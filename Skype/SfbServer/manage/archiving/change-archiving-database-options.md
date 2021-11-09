---
title: Ändern von Archivierungsdatenbankoptionen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Archivierungsdatenbankoptionen für Skype for Business Server ändern.'
ms.openlocfilehash: e07c94530d71c9d31ef9f11eaef6332dbfa32d0e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847458"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Ändern von Archivierungsdatenbankoptionen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Archivierungsdatenbankoptionen für Skype for Business Server ändern.
  
Wenn Sie die Archivierung mit SQL Server Speicher für den Archivierungsspeicher für einen Ihrer Benutzer bereitstellen, können Sie die folgenden Änderungen am Datenbankspeicher vornehmen:
  
- Verwenden Sie eine andere SQL Server-Datenbank für den Archivierungsspeicher. Dazu gehören die primäre Archivierungsdatenbank und alle Datenbanken, die Sie für SQL Server Spiegelung verwenden.
    
- Wechseln Sie zur Integration von Microsoft Exchange, um Archivierungsdaten und Dateien auf Exchange Servern zu speichern. Wenn alle Ihre Benutzer auf Ihren Exchange Servern verwaltet werden und Sie Microsoft Exchange Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server-Speicherdatenbanken aus Ihrer Topologie entfernen. 
    
Um eine dieser Änderungen vorzunehmen, müssen Sie den Topologie-Generator ausführen, die Änderungen vornehmen und dann die Topologie erneut veröffentlichen. Geben Sie keine **Archivierungsinformationen SQL Server Speichers** an, oder aktivieren Sie **SQL Server Spiegelungsinformationen,** es sei denn, Sie haben Skype for Business Benutzer, die nicht auf Exchange Servern verwaltet werden.
  
## <a name="change-archiving-database-options"></a>Ändern von Optionen für Archivierungsdatenbanken

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mithilfe eines Kontos an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber um eine Topologie zu veröffentlichen, die zum Hinzufügen einer Komponente zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe **"Domänenadministratoren"** und der Gruppe **"RTCUniversalServerAdmins"** ist und über Vollzugriffsberechtigungen verfügt (d. h.  Lesen, Schreiben und Ändern) der Dateifreigabe, die Sie für den Skype for Business Server Dateispeicher verwenden (d. h., dass der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) oder ein Konto mit entsprechenden Rechten konfigurieren kann.
  
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
    
     - Klicken Sie zum Angeben eines neuen SQL Server Speichers auf **Neu,** und führen Sie dann im Dialogfeld **"Neuen SQL Server Store definieren"** die folgenden Schritte aus:
    
       - Geben Sie **in SQL Server FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server speicher erstellen möchten.
    
       - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
       - Wenn sich die angegebene SQL Server Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen "Diese SQL Instanz befindet sich **in der Spiegelungsbeziehung",** und geben Sie dann in der **Spiegelportnummer** die Portnummer an.
    
   - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:
    
     - Um einen vorhandenen SQL Server Speicher für die Spiegelung zu verwenden, klicken Sie im Dropdown-Listenfeld **"Archivierung SQL Server Speicherspiegel"** auf den Namen des SQL Server Speichers, den Sie für die Spiegelung verwenden möchten.
    
     - Um einen neuen SQL Server Speicher für die Spiegelung anzugeben, klicken Sie auf **Neu,** und führen Sie dann im Dialogfeld Neue **SQL Server Store** definieren eine der folgenden Aktionen aus:
    
       a. Geben Sie **in SQL Server FQDN** den FQDN des SQL Server an, in dem Sie den neuen SQL Server Speicher erstellen möchten.
    
       b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
       c. Wenn sich die angegebene SQL Server Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen "Diese SQL Instanz befindet sich **in der Spiegelungsbeziehung",** und geben Sie dann in der **Spiegelportnummer** die Portnummer an.
    
   - Wenn Sie SQL Server Spiegelung aktivieren und einen SQL Server Spiegelungszeugen hinzufügen oder ändern möchten (eine dritte, separate SQL Server Instanz, die die Integrität der primären SQL Server Server- und Spiegelinstanzen erkennen kann), aktivieren Sie das Kontrollkästchen **"Automatisches Failover" mithilfe SQL Server Spiegelungszeugen.**  führen Sie eine der folgenden Aktionen aus:
    
      a. Geben Sie in **SQL Server FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server Spiegelungszeugen erstellen möchten.
    
      b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
      c. Wenn sich die angegebene SQL Server Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen "Diese SQL Instanz befindet sich **in der Spiegelungsbeziehung",** und geben Sie dann in der **Spiegelportnummer** die Portnummer an.
    
   - Um zur Microsoft Exchange Integration zu wechseln, um Archivierungsdaten und Dateien auf Exchange Servern zu speichern (wenn alle Benutzer in Ihrer Bereitstellung auf Ihren Exchange Servern verwaltet werden), löschen Sie alle Informationen für Archivierungsdatenbanken.
    
     > [!IMPORTANT]
     > Wenn Sie über Skype for Business Benutzer verfügen, die nicht auf Exchange Servern verwaltet werden, löschen Sie nicht die SQL Server Speichern von Informationen. 
  
8. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
    > [!IMPORTANT]
    > Die Änderungen, die Sie im Topologie-Generator vornehmen, werden erst wirksam, wenn Sie die neue Topologie veröffentlichen. Ausführliche Informationen finden Sie unter [Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server.](../../deploy/deploy-archiving/add-archiving-databases.md) 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Ändern des Speicherorts der Archivierungsdatenbank mithilfe von Windows PowerShell

In den meisten Fällen müssen Sie den Speicherort der Archivierungsdatenbank nicht ändern, die bei der Installation des Archivierungsservers angegeben wird. Wenn jedoch ein Hardwarefehler oder ein anderes Problem auftreten sollte, können Sie den Archivierungsserver mithilfe des Cmdlets **"Set-CsArchivingServer"** auf eine neue Datenbank verweisen.
  
Im folgenden Beispiel wird der Speicherort der Archivierungsdatenbank für den ArchivingServer:atl-cs-001.contoso.com Archiving Server geändert. In diesem Beispiel befindet sich die neue Datenbank unter ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


