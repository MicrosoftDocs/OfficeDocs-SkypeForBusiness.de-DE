---
title: Ändern von Optionen für Archivierungsdatenbanken in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Zusammenfassung: Informationen Sie zum Ändern der Optionen für Archivierungsdatenbanken für Skype für Business Server 2015.'
ms.openlocfilehash: 5bb7ee9329cc3fa7a0795115f9a0d11768ab7aa4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="change-archiving-database-options-in-skype-for-business-server-2015"></a>Ändern von Optionen für Archivierungsdatenbanken in Skype for Business Server 2015

**Zusammenfassung:** Informationen Sie zum Ändern der Optionen für Archivierungsdatenbanken für Skype für Business Server 2015.
  
Wenn Sie die Archivierung mithilfe von SQL Server-Speicher als Archivierungsspeicher für beliebige Benutzer bereitstellen, können Sie die folgenden Datenbank Speicher Änderungen vornehmen:
  
- Verwenden Sie eine andere SQL Server-Datenbank als Archivierungsspeicher. Dazu gehören die primäre Archivierungsdatenbank und jede Datenbank, die Sie für die SQL Server-Spiegelung verwenden.
    
- Wechseln Sie zu Microsoft Exchange-Integration, um Archivierungsdaten und-Dateien auf Exchange-Servern zu speichern. Wenn alle Benutzer auf Ihren Exchange-Servern verwaltet werden, und Sie Microsoft Exchange-Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server-Speicher-Datenbanken aus der Topologie entfernen. 
    
Um eine der folgenden Änderungen vornehmen, müssen Sie führen Topologie-Generator, nehmen Sie die Änderungen, und veröffentlichen die Topologie dann erneut. **Archivierung von SQL Server-Speicher** oder **Aktivieren Sie SQL Server-speicherspiegelung** Informationen nicht Geben Sie an, es sei denn, Sie Skype für Unternehmensbenutzer verfügen, die nicht auf Exchange-Servern verwaltet werden.
  
## <a name="change-archiving-database-options"></a>Ändern von Optionen für Archivierungsdatenbanken

1. Auf einem Computer, der Skype für Business Server ausgeführt wird, oder auf dem die Skype für Business Server-Verwaltungstools installiert sind, melden Sie sich mit einem Konto, das Mitglied der lokalen Benutzergruppe (oder ein Konto mit gleichwertigen Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie mit einem Konto, das Mitglied der lokalen Benutzergruppe ist definieren, aber um eine Topologie veröffentlichen, die erforderlich ist, eine Komponente zur Topologie hinzugefügt werden, müssen Sie ein Konto, das Mitglied der Gruppe **Domänen-Admins** und die **RTCUniversalSer ist verwenden VerAdmins** Gruppe und, verfügt über Vollzugriff-Berechtigungen (d. h., lesen, schreiben und ändern) für die Dateifreigabe, die Sie für die Skype für Business Server-Dateispeicher verwenden werden (d. h., sodass Topologie-Generator erforderlichen discretionary Access Control konfigurieren können Zugriffssteuerungslisten (DACL) oder einem Konto mit gleichwertigen Berechtigungen.
  
2. Starten Sie Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.
    
7. Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:
    
  - Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:
    
  - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
  - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
    
    - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
    - Klicken Sie zum Angeben eines neuen SQL Server-Speichers, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** die folgenden:
    
      - Geben Sie in **SQL Server-FQDN**: den FQDN des Servers, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
      - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
      - Wenn die angegebene Instanz von SQL Server in einer spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz in einer spiegelverbindung ist** , und in **spiegelportnummer**Geben Sie die Portnummer an.
    
  - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus und gehen Sie dann wie folgt vor:
    
    - Klicken Sie auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten, um eines vorhandenen SQL Server-Speichers zur Spiegelung klicken Sie im Dropdown-Listenfeld **-speicherspiegel für Archivierung SQL Server** verwenden.
    
    - Um eine neue SQL Server-Speicher für Spiegelung anzugeben, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** einen der folgenden:
    
      a. Geben Sie in **SQL Server-FQDN**: den FQDN des SQL-Servers, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
      b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
      c. Wenn die angegebene Instanz von SQL Server in einer spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz in einer spiegelverbindung ist** , und in **spiegelportnummer**Geben Sie die Portnummer an.
    
  - Wenn Sie SQL Server-Spiegelung aktivieren und hinzufügen oder Ändern einer SQL Server-spiegelungszeugen (eine dritte, separate SQL Server-Instanz, die die Integrität der primären SQL Server und den Spiegelserver Serverinstanzen erkennt) möchten, wählen Sie die **mithilfe von SQL Server-spiegelungszeugen zu Aktivierung des automatischen Failovers** Kontrollkästchen, und führen Sie dann eine der folgenden:
    
      a. Geben Sie in **SQL Server-FQDN**: den FQDN des Servers, auf dem Sie die neue SQL Server-spiegelungszeugen erstellen möchten.
    
      b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
      c. Wenn die angegebene Instanz von SQL Server in einer spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz in einer spiegelverbindung ist** , und in **spiegelportnummer**Geben Sie die Portnummer an.
    
  - Zum Wechseln zur Integration von Microsoft Exchange zum Speichern von Archivierungsdaten und-Dateien auf Exchange-Servern (wenn alle Benutzer in Ihrer Bereitstellung auf Ihren Exchange-Servern verwaltet werden), löschen Sie alle Informationen für Archivierungsdatenbanken.
    
    > [!IMPORTANT]
    > Wenn Sie Skype für Unternehmensbenutzer, die nicht auf Exchange-Servern verwaltet werden verfügen, löschen Sie die SQL Server-Speicherinformationen nicht. 
  
8. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
    > [!IMPORTANT]
    > Im Topologie-Generator vorgenommenen Änderungen werden nicht wirksam, bis Sie die neue Topologie veröffentlichen. Weitere Informationen hierzu finden Sie unter [Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype für Business Server 2015](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Ändern des Speicherorts der Archivierungsdatenbank mithilfe von Windows PowerShell

In den meisten Fällen müssen Sie den Speicherort der Archivierungsdatenbank, der angegeben wird, wenn Sie den Archivierungsserver installieren, nicht ändern. Sollte jedoch ein Hardwareausfall oder ein anderes Problem auftreten, können Sie den Archivierungsserver mit dem Cmdlet **Set-CsArchivingServer** auf eine neue Datenbank verweisen lassen.
  
Das folgende Beispiel ändert den Speicherort der für die ArchivingServer:atl die Archivierungsdatenbank-Cs-001.contoso.com Archivierungsserver. In diesem Beispiel befindet sich die neue Datenbank unter „ArchivingDatabase:atl-sql-001.contoso.com“:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


