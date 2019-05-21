---
title: Ändern der Optionen für die Archivierungsdatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Optionen für die Archivierungsdatenbank für Skype for Business Server ändern.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299986"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Ändern der Optionen für die Archivierungsdatenbank in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie die Archivierungsdaten Bank Optionen für Skype for Business Server ändern.
  
Wenn Sie die Archivierung mithilfe des SQL Server-Speichers zum Archivieren von Speicher für Ihre Benutzer bereitstellen, können Sie die folgenden Datenbankspeicher Änderungen vornehmen:
  
- Verwenden Sie eine andere SQL Server-Datenbank zum Archivieren von Speicher. Dazu gehören die primäre Archivierungsdatenbank und jede Datenbank, die Sie für die SQL Server-Spiegelung verwenden.
    
- Wechseln Sie zur Microsoft Exchange-Integration, um Archivierungsdaten und-Dateien auf Exchange-Servern zu speichern. Wenn sich alle Ihre Benutzer auf Ihren Exchange-Servern befinden und Sie Microsoft Exchange-Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server-Speicher Datenbanken aus Ihrer Topologie entfernen. 
    
Wenn Sie eine dieser Änderungen vornehmen möchten, müssen Sie den Topologie-Generator ausführen, die Änderungen vornehmen und die Topologie dann erneut veröffentlichen. Geben Sie keinen **Archivierungs-SQL Server-Speicher** an, oder aktivieren Sie die Spiegelungsinformationen für **SQL Server Store** , es sei denn, Sie verfügen über Skype for Business-Benutzer, die nicht auf Exchange-Servern gehostet werden
  
## <a name="change-archiving-database-options"></a>Ändern von Optionen für Archivierungsdatenbanken

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird, oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die zum Hinzufügen einer Komponente zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe der **Domänenadministratoren** und der RTCUniversalSer ist. ** verAdmins** -Gruppe, die über Vollzugriffsberechtigungen (also lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den Skype for Business Server-Dateispeicher verwenden (Dies bedeutet, dass der Topologie-Generator die erforderliche Discretionary Access-Steuerung konfigurieren kann. Listen (DACLs) oder ein Konto mit entsprechenden Rechten.
  
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.
    
7. Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:
    
   - Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
   - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
    
     - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
     - Wenn Sie einen neuen SQL Server-Speicher angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** die folgenden Aktionen aus:
    
       - Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
       - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
       - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in** der Spiegelungs Beziehung, und geben Sie dann in Spiegelungs- **Portnummer**die Portnummer an.
    
   - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus und gehen Sie dann wie folgt vor:
    
     - Wenn Sie einen vorhandenen SQL Server-Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **SQL Server Store Mirror-Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
    
     - Wenn Sie einen neuen SQL Server-Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** eine der folgenden Aktionen aus:
    
       a. Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
       b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
       c. Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in** der Spiegelungs Beziehung, und geben Sie dann in Spiegelungs- **Portnummer**die Portnummer an.
    
   - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte, separate SQL Server-Instanz, die den Zustand des primären SQL Server-Servers und der Spiegelungs Instanzen erkennen kann) hinzufügen oder ändern möchten, wählen Sie den **SQL Server-Spiegelungs Zeugen verwenden aus, um Aktivieren** Sie das Kontrollkästchen Automatisches Failover, und führen Sie dann eine der folgenden Aktionen aus:
    
      a. Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.
    
      b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
      c. Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in** der Spiegelungs Beziehung, und geben Sie dann in Spiegelungs- **Portnummer**die Portnummer an.
    
   - Wenn Sie zur Microsoft Exchange-Integration wechseln möchten, um Archivierungsdaten und-Dateien auf Exchange-Servern zu speichern (wenn alle Benutzer in Ihrer Bereitstellung auf Ihren Exchange-Servern verwaltet werden), löschen Sie alle Informationen für das Archivieren von Datenbanken.
    
     > [!IMPORTANT]
     > Wenn Sie über Skype for Business-Benutzer verfügen, die nicht auf Exchange-Servern gehostet werden, löschen Sie die SQL Server-Informationsspeicherinformationen nicht. 
  
8. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
    > [!IMPORTANT]
    > Die Änderungen, die Sie im Topologie-Generator vornehmen, werden erst wirksam, nachdem Sie die neue Topologie veröffentlicht haben. Ausführliche Informationen finden Sie unter [Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Ändern des Speicherorts der Archivierungsdatenbank mithilfe von Windows PowerShell

In den meisten Fällen müssen Sie den Speicherort der Archivierungsdatenbank, der angegeben wird, wenn Sie den Archivierungsserver installieren, nicht ändern. Sollte jedoch ein Hardwareausfall oder ein anderes Problem auftreten, können Sie den Archivierungsserver mit dem Cmdlet **Set-CsArchivingServer** auf eine neue Datenbank verweisen lassen.
  
Im folgenden Beispiel wird der Speicherort der Archivierungsdatenbank für den ArchivingServer: ATL-CS-001.contoso.com-Archivierungs Server geändert. In diesem Beispiel befindet sich die neue Datenbank unter „ArchivingDatabase:atl-sql-001.contoso.com“:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


