---
title: Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server-Bereitstellung Archivierungsdatenbanken hinzufügen.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820675"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server-Bereitstellung Archivierungsdatenbanken hinzufügen.
  
Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. In den Informationen in diesem Thema wird erläutert, wie Sie den Topologie-Generator für:
  
- Fügen Sie Ihrer Topologie eine Archivierungsdatenbank hinzu.
    
- Veröffentlichen Sie die aktualisierte Topologie, um die Archivierungsdatenbank zu Ihrer Skype for Business Server-Bereitstellung hinzuzufügen.
    
> [!NOTE]
> Wenn Sie die Microsoft **Exchange-Integration** verwenden möchten, um Archivierungsdaten und Dateien auf den Exchange-Servern für  alle Benutzer in Ihrer Bereitstellung zu speichern, geben Sie weder archivierungs- noch SQL Server speicher- oder SQL Server speicher-Spiegelungsinformationen an.
  
### <a name="add-an-archiving-database-to-your-topology"></a>Hinzufügen einer Archivierungsdatenbank zur Topologie

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe (oder eines Kontos mit entsprechenden Benutzerrechten) ist.
    
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitstellen möchten, und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Archivierung bereitstellen möchten.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zu **Archivierung** durch.
    
7. Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
8. Gehen **Sie SQL Server unter "Archivierungsspeicher"** wie folgt vor:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn alle Ihre Benutzer auf Microsoft Exchange Server 2013 oder höher gespeichert sind, können Sie die Skype for Business-Kommunikation für alle Benutzer in Exchange archivieren. In diesem Fall müssen Sie den archivierungsspeicher nicht SQL Server konfigurieren.
    
   - Wenn Sie einen neuen SQL Server angeben möchten, klicken Sie auf "Neu", und gehen Sie dann im Dialogfeld "Neuen **SQL Server Speicher** definieren" wie folgt vor:
    
   - Geben **SQL Server FQDN** des Servers an, auf dem Sie den neuen SQL Server erstellen möchten.
    
   - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
   - Wenn sich die angegebene SQL Server in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen  **"This SQL instance is in mirroring relation",** und geben Sie dann in der Nummer des Spiegelports die Portnummer an.
    
9. Wenn Sie die SQL Server verwenden möchten, wählen Sie **"SQL Server Store-Spiegelung** aktivieren" aus, und gehen Sie dann wie folgt vor:
    
   - Um einen vorhandenen SQL Server speicher für die  Spiegelung zu verwenden, klicken Sie im Dropdownlistenfeld für den Archivierungsspeicher SQL Server auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
    
   - Um einen neuen SQL Server für die Spiegelung anzugeben, klicken Sie auf "Neu", **und** gehen Sie dann im Dialogfeld "Neuen SQL Server Speicher definieren" wie folgt vor:
    
     a. Geben **SQL Server FQDN** des SQL Server an, auf dem Sie den neuen SQL Server erstellen möchten.
    
     b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
    
     c. Wenn sich die angegebene SQL Server in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen  **"This SQL instance is in mirroring relation",** und geben Sie dann in der Nummer des Spiegelports die Portnummer an.
    
   - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungszeugen (eine dritte, separate SQL Server-Instanz, die die Integrität der primären SQL Server- und Spiegelinstanzen erkennen kann) verwenden möchten, aktivieren Sie das Kontrollkästchen SQL Server-Spiegelungszeugen verwenden, um das automatische Failover zu aktivieren, und führen Sie dann einen der folgenden Schritte aus: 
    
     a. Geben **SQL Server FQDN** des Servers, auf dem Sie den neuen Spiegelungszeugen erstellen möchten, SQL Server an.
    
     b. Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
     c. Wenn sich die angegebene SQL Server in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen  **"This SQL instance is in mirroring relation",** und geben Sie dann in der Nummer des Spiegelports die Portnummer an.
    
10. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen einer Archivierungsdatenbank zur Bereitstellung

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist. Um jedoch eine Topologie zu veröffentlichen, die erforderlich ist, um der Topologie einen Server hinzuzufügen, müssen Sie ein Konto verwenden, das Mitglied der Gruppe **"Domänen-Admins"** und der Gruppe **"RTCUniversalServerAdmins"** ist und über Vollzugriffsberechtigungen (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den Skype for Business Server-Dateispeicher verwenden (damit der Topologie-Generator die erforderliche discretionary Access Control List (DACLs) oder ein Konto mit entsprechenden Rechten konfigurieren kann.
  
2. Öffnen Sie die Topologie, die Sie im vorherigen Abschnitt mithilfe des Topologie-Generators erstellt haben.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste **auf Skype for Business Server,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**. 
    
    > [!NOTE]
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. > Nur Datenbanken auf dedizierten SQL Server können mithilfe des Topologie-Generators installiert werden. Datenbanken auf SQL Server-Computern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden. 
  
6. Überprüfen Sie auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, ob die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Weitere Informationen finden Sie unter ["Konfigurieren von Archivierungsoptionen für Skype for Business Server"](configure-archiving-options.md) und ["Konfigurieren von Archivierungsrichtlinien für Skype for Business Server".](configure-archiving-policies.md) 
  

