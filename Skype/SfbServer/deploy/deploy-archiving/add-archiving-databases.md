---
title: Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Hinzufügen von Archivierungsdatenbanken zu Ihrer Skype für Business Server-Bereitstellung.'
ms.openlocfilehash: c2e92b1da9dd5e9827b362bf4979ffba075c4402
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372951"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype für Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zum Hinzufügen von Archivierungsdatenbanken zu Ihrer Skype für Business Server-Bereitstellung.
  
Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. Die Informationen in diesem Thema wird erläutert, wie Topologie-Generator zu verwenden:
  
- Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie
    
- Veröffentlichen der aktualisierten Topologie, um die Archivierungsdatenbank Ihrer Skype für Business Server-Bereitstellung hinzuzufügen.
    
> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange-Servern für alle Ihre Benutzer in Ihrer Bereitstellung verwenden möchten, geben Sie **Archivierung SQL Server-Speicher** oder **verwenden SQL Server-speicherspiegelung** Informationen nicht.
  
### <a name="add-an-archiving-database-to-your-topology"></a>Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie

1. Auf einem Computer, der Skype für Business Server ausgeführt wird, oder auf dem die Skype für Business Server-Verwaltungstools installiert sind, melden Sie sich mit einem Konto, das Mitglied der lokalen Benutzergruppe (oder ein Konto mit gleichwertigen Benutzerrechten) ist.
    
2. Starten Sie Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des entsprechenden Front-End-Pools.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.
    
7. Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
8. Unter **SQL Server-Archivierungsspeicher gespeichert werden sollen,** führen Sie eine der folgenden Aktionen aus:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn alle Benutzer von Microsoft Exchange Server 2013 oder höher befinden, können Sie Skype für die geschäftliche Kommunikation für alle Benutzer im Exchange archivieren. In diesem Fall müssen Sie nicht SQL Server-Archivierung Store zu konfigurieren.
    
   - Klicken Sie zum Angeben eines neuen SQL Server-Speichers, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** die folgenden:
    
   - Geben Sie in **SQL Server-FQDN**: den FQDN des Servers, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
   - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
   - Wenn die angegebene Instanz von SQL Server in einer spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz in einer spiegelverbindung ist** , und in **spiegelportnummer**Geben Sie die Portnummer an.
    
9. Wenn Sie SQL Server-speicherspiegelung verwenden möchten, wählen Sie **SQL Server-speicherspiegelung aktivieren**, und klicken Sie dann die folgenden Schritte aus:
    
   - Klicken Sie auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten, um eines vorhandenen SQL Server-Speichers zur Spiegelung klicken Sie im Dropdown-Listenfeld **-speicherspiegel für Archivierung SQL Server** verwenden.
    
   - Um eine neue SQL Server-Speicher für Spiegelung anzugeben, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** einen der folgenden:
    
     a. Geben Sie in **SQL Server-FQDN**: den FQDN des SQL-Servers, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
     b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
     c. Wenn die angegebene Instanz von SQL Server in einer spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz in einer spiegelverbindung ist** , und in **spiegelportnummer**Geben Sie die Portnummer an.
    
   - Wenn Sie SQL Server-Spiegelung aktivieren und eine SQL Server-spiegelungszeugen (eine dritte, separate SQL Server-Instanz, die die Integrität der primären Instanzen von SQL Server und den Spiegelserver erkennt) einschließen möchten, wählen Sie zum Aktivieren der **mithilfe von SQL Server-spiegelungszeugen Failover** Kontrollkästchen, und führen Sie dann eine der folgenden:
    
     a. Geben Sie in **SQL Server-FQDN**: den FQDN des Servers, auf dem Sie die neue SQL Server-spiegelungszeugen erstellen möchten.
    
     b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
     c. Wenn die angegebene Instanz von SQL Server in einer spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz in einer spiegelverbindung ist** , und in **spiegelportnummer**Geben Sie die Portnummer an.
    
10. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen einer Archivierungsdatenbank zu Ihrer Bereitstellung

1. Auf einem Computer, der Skype für Business Server ausgeführt wird, oder auf dem die Skype für Business Server-Verwaltungstools installiert sind, melden Sie sich mit einem Konto, das Mitglied der lokalen Benutzergruppe (oder ein Konto mit gleichwertigen Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie mit einem Konto, das Mitglied der lokalen Benutzergruppe ist definieren, aber um eine Topologie veröffentlichen, die zum Hinzufügen eines Servers zur Topologie erforderlich ist, müssen Sie ein Konto, das Mitglied der Gruppe **Domänen-Admins** und die **RTCUniversalServer ist verwenden Administratoren** Gruppe und, verfügt über Vollzugriff-Berechtigungen (Lesen, schreiben und ändern) für die Dateifreigabe, die Sie für die Skype für Business Server-Dateispeicher verwenden, (sodass Topologie-Generator die erforderlichen discretionary Access Control List (DACL) konfigurieren können, oder ein Konto mit gleichwertigen Berechtigungen.
  
2. Öffnen Sie die Topologie, die Sie im vorherigen Abschnitt des Topologie-Generators erstellt haben.
    
3. In der Konsolenstruktur mit der rechten Maustaste **Skype für Business Server**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**. 
    
    > [!NOTE]
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. > Nur die Datenbanken auf dedizierten SQL Server können mithilfe des Topologie-Generator installiert werden. Datenbanken auf SQL-Servern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden. 
  
6. Vergewissern Sie sich auf der Seite **Assistent für die Veröffentlichung abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype für Business Server](configure-archiving-options.md) und [Konfigurieren von Archivierungsrichtlinien für Skype für Business Server](configure-archiving-policies.md). 
  

