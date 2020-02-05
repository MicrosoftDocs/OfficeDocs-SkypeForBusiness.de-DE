---
title: Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihrer Skype for Business Server-Bereitstellung Archivierungsdatenbanken hinzufügen.'
ms.openlocfilehash: 26cdd1befb695fbaf0656611ed65c7afa778af6c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769048"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server-Bereitstellung Archivierungsdatenbanken hinzufügen.
  
Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. Die Informationen in diesem Thema erläutern die Verwendung des Topologie-Generators für folgende Zwecke:
  
- Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie
    
- Veröffentlichen Sie die aktualisierte Topologie, um die Archivierungsdatenbank zu Ihrer Skype for Business Server-Bereitstellung hinzuzufügen.
    
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange-Servern für alle Benutzer in Ihrer Bereitstellung verwenden möchten, geben Sie keinen **Archivierungs-SQL Server-Speicher** an, oder verwenden Sie die **Spiegelungsinformationen des SQL Server-Speichers** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird, oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des entsprechenden Front-End-Pools.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.
    
7. Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
8. Führen Sie unter **SQL Server-Archivierungsspeicher** eine der folgenden Aktionen aus:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn sich alle Ihre Benutzer auf Microsoft Exchange Server 2013 oder höher befinden, können Sie die Kommunikation zwischen Skype for Business für alle Ihre Benutzer in Exchange archivieren. In diesem Fall müssen Sie den SQL Server-Archivierungsspeicher nicht konfigurieren.
    
   - Wenn Sie einen neuen SQL Server-Speicher angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** die folgenden Aktionen aus:
    
   - Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
   - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
   - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer**die Portnummer an.
    
9. Wenn Sie die SQL Server Store-Spiegelung verwenden möchten, wählen Sie **SQL Server Store-Spiegelung aktivieren**aus, und gehen Sie dann wie folgt vor:
    
   - Wenn Sie einen vorhandenen SQL Server-Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **SQL Server Store Mirror-Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
    
   - Wenn Sie einen neuen SQL Server-Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** eine der folgenden Aktionen aus:
    
     a. Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
    
     b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
     c. Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer**die Portnummer an.
    
   - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte, separate SQL Server-Instanz, die den Zustand der primären SQL Server-und Spiegelinstanzen erkennen kann) einbeziehen möchten, aktivieren Sie das Kontrollkästchen **SQL Server-Spiegelungs Zeuge zum Aktivieren des automatischen Failovers verwenden** , und führen Sie dann eine der folgenden Aktionen aus:
    
     a. Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.
    
     b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
     c. Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer**die Portnummer an.
    
10. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen einer Archivierungsdatenbank zu Ihrer Bereitstellung

1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird, oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das ein Mitglied der lokalen Benutzergruppe ist, aber eine Topologie veröffentlichen, die zum Hinzufügen eines Servers zur Topologie erforderlich ist. Sie müssen ein Konto verwenden, das ein Mitglied der Gruppe " **Domänen-Admins** " und der Gruppe " **RTCUniversalServerAdmins** " ist und über Vollzugriffsberechtigungen (lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den Dateispeicher von Skype for Business Server verwenden (damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control List) oder eine Konto mit entsprechenden Rechten.
  
2. Öffnen Sie die im vorherigen Abschnitt erstellte Topologie mithilfe des Topologie-Generators.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**. 
    
    > [!NOTE]
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. > nur Datenbanken auf dedizierten SQL-Servern können mithilfe des Topologie-Generators installiert werden. Datenbanken auf SQL-Servern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden. 
  
6. Vergewissern Sie sich auf der Seite **Assistent für die Veröffentlichung abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Ausführliche Informationen finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md) und [Konfigurieren von Archivierungsrichtlinien für Skype for Business Server](configure-archiving-policies.md). 
  

