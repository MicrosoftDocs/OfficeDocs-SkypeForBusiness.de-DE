---
title: Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihrer Skype for Business Server Bereitstellung Archivierungsdatenbanken hinzufügen.'
ms.openlocfilehash: d7174919ef34cd77bf7da316d23808ea1cfaff7f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778935"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server Bereitstellung Archivierungsdatenbanken hinzufügen.
  
Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. In den Informationen in diesem Thema wird erläutert, wie Sie den Topologie-Generator für Folgendes verwenden:
  
- Fügen Sie Ihrer Topologie eine Archivierungsdatenbank hinzu.
    
- Veröffentlichen Sie die aktualisierte Topologie, um ihrer Skype for Business Server Bereitstellung die Archivierungsdatenbank hinzuzufügen.
    
> [!NOTE]
> Wenn Sie Microsoft Exchange Integration verwenden möchten, um Archivierungsdaten und Dateien für alle Benutzer in Ihrer Bereitstellung auf Exchange Servern zu speichern, geben Sie weder **archivierungs- SQL Server speichern** noch **SQL Server Store Spiegelungsinformationen verwenden.**
  
### <a name="add-an-archiving-database-to-your-topology"></a>Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mithilfe eines Kontos an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitstellen möchten, und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Archivierung bereitstellen möchten.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zu **Archivierung** durch.
    
7. Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
8. Führen Sie unter **"Archivierung SQL Server Speichers** eine der folgenden Aktionen aus:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn alle Ihre Benutzer am Microsoft Exchange Server 2013 oder höher verwaltet werden, können Sie Skype for Business Kommunikation für alle Ihre Benutzer in Exchange archivieren. In diesem Fall müssen Sie SQL Server Archivierungsspeicher nicht konfigurieren.
    
   - Klicken Sie zum Angeben eines neuen SQL Server Speichers auf **Neu,** und führen Sie dann im Dialogfeld **"Neuen SQL Server Store definieren"** die folgenden Schritte aus:
    
   - Geben Sie **in SQL Server FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server Speicher erstellen möchten.
    
   - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
   - Wenn sich die angegebene SQL Server Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen "Diese SQL Instanz befindet sich **in der Spiegelungsbeziehung",** und geben Sie dann in der **Spiegelportnummer** die Portnummer an.
    
9. Wenn Sie SQL Server Speicherspiegelung verwenden möchten, wählen **Sie SQL Server Store Spiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:
    
   - Um einen vorhandenen SQL Server Speicher für die Spiegelung zu verwenden, klicken Sie im Dropdown-Listenfeld **"Archivierung SQL Server Speicherspiegel"** auf den Namen des SQL Server Speichers, den Sie für die Spiegelung verwenden möchten.
    
   - Um einen neuen SQL Server Speicher für die Spiegelung anzugeben, klicken Sie auf **Neu,** und führen Sie dann im Dialogfeld Neue **SQL Server Store definieren** eine der folgenden Aktionen aus:
    
     a. Geben Sie **in SQL Server FQDN** den FQDN des SQL Server an, in dem Sie den neuen SQL Server Speicher erstellen möchten.
    
     b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
     c. Wenn sich die angegebene SQL Server Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen "Diese SQL Instanz befindet sich **in der Spiegelungsbeziehung",** und geben Sie dann in der **Spiegelportnummer** die Portnummer an.
    
   - Wenn Sie SQL Server Spiegelung aktivieren und einen SQL Server Spiegelungszeugen einschließen möchten (eine dritte, separate SQL Server Instanz, die die Integrität der primären SQL Server und Spiegelinstanzen erkennen kann), aktivieren Sie das Kontrollkästchen **"Automatisches Failover" mithilfe SQL Server Spiegelungszeugen,** und aktivieren Sie dann eine der folgenden Schritte: e following:
    
     a. Geben Sie **in SQL Server FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server Spiegelungszeugen erstellen möchten.
    
     b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
     c. Wenn sich die angegebene SQL Server Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen "Diese SQL Instanz befindet sich **in der Spiegelungsbeziehung",** und geben Sie dann in der **Spiegelportnummer** die Portnummer an.
    
10. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen einer Archivierungsdatenbank zu Ihrer Bereitstellung

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber um eine Topologie zu veröffentlichen, die zum Hinzufügen eines Servers zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe **"Domänenadministratoren"** und der Gruppe **"RTCUniversalServerAdmins"** ist und über Vollzugriffsberechtigungen verfügt (Lesen,  Schreiben und Ändern) der Dateifreigabe, die Sie für den Skype for Business Server Dateispeicher verwenden (sodass der Topologie-Generator die erforderliche freie Zugriffssteuerungsliste (Discretionary Access Control List, DACLs) oder ein Konto mit entsprechenden Rechten konfigurieren kann.
  
2. Öffnen Sie die Topologie, die Sie im vorherigen Abschnitt mithilfe des Topologie-Generators erstellt haben.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**. 
    
    > [!NOTE]
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. > Nur Datenbanken auf dedizierten SQL Servern können mithilfe des Topologie-Generators installiert werden. Datenbanken auf SQL Server-Computern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden. 
  
6. Überprüfen Sie auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, ob die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Ausführliche Informationen finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md) und Konfigurieren von [Archivierungsrichtlinien für Skype for Business Server.](configure-archiving-policies.md) 
  

