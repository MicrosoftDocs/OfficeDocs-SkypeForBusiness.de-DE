---
title: Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Zusammenfassung: In diesem Themenbereich erfahren Sie, wie Sie Archivierungsdatenbanken zu Ihrer -Bereitstellung hinzufügen können.'
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a>Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server 2015
 
Zusammenfassung: In diesem Themenbereich erfahren Sie, wie Sie Archivierungsdatenbanken zu Ihrer -Bereitstellung hinzufügen können.
  
Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. In diesem Thema wird erläutert, wie Sie das  für Folgendes verwenden:
  
- Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie
    
- Veröffentlichen der aktualisierten Topologie zum Hinzufügen der Archivierungsdatenbank zu Ihrer -Bereitstellung
    
> [!NOTE]
> Wenn Sie die -Integration zum Speichern von Archivierungsdaten und -dateien auf -Servern für alle Benutzer in der Bereitstellung verwenden möchten, geben Sie nicht  oder  an.
  
### <a name="add-an-archiving-database-to-your-topology"></a>Hinzufügen einer Archivierungsdatenbank zu Ihrer Topologie

1. Melden Sie sich auf einem Computer, auf dem  ausgeführt wird oder auf dem die -Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe „Benutzer“ ist (oder mit einem Konto mit äquivalenten Benutzerrechten).
    
2. Start Topology Builder.
    
3. Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des entsprechenden Front-End-Pools.
    
4. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**. 
    
5. Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.
    
6. Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.
    
7. Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
8. Under **Archiving SQL Server store,** do one of the following:
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn alle Benutzer in  oder höher verwaltet werden, können Sie die -Kommunikation für alle Benutzer  archivieren. In diesem Fall muss der -Archivierungsspeicher nicht konfiguriert werden.
    
   - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
    
   - Geben Sie im Feld SQL Server-FQDN den FQDN des Servers an, auf dem Sie den neuen -Speicher erstellen möchten.
    
   - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
   - Wenn sich die angegebene -Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung und geben Sie dann im Feld Spiegelportnummer die Portnummer an.
    
9. If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:
    
   - Zum Verwenden eines vorhandenen -Speichers zur Spiegelung klicken Sie im Dropdown-Listenfeld SQL Server-Speicherspiegel für Archivierung auf den Namen des -Speichers, den Sie für die Spiegelung verwenden möchten.
    
   - Zum Angeben eines neuen -Speichers zur Spiegelung klicken Sie auf Neu und führen Sie dann im Dialogfeld Neuen SQL Server-Speicher definieren einen der folgenden Schritte aus:
    
    a. Geben Sie in SQL-Server-FQDN den FQDN des Computers mit SQL Server an, auf dem Sie den neuen -Speicher erstellen möchten.
    
    b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
    
    c. Wenn sich die angegebene -Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung und geben Sie dann im Feld Spiegelportnummer die Portnummer an.
    
   - Wenn Sie die -Spiegelung aktivieren und einen -Spiegelungszeugen hinzufügen oder ändern möchten (eine dritte, separate -Instanz, die die Integrität des primären -Servers und der Spiegelinstanzen erkennen kann), aktivieren Sie das Kontrollkästchen Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren und führen Sie dann einen der folgenden Schritte aus:
    
    a. Geben Sie im Feld SQL Server-FQDN den FQDN des Servers an, auf dem Sie den neuen -Spiegelungszeugen erstellen möchten.
    
    b. Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
    
    c. Wenn sich die angegebene -Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung und geben Sie dann im Feld Spiegelportnummer die Portnummer an.
    
10. Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen einer Archivierungsdatenbank zu Ihrer Bereitstellung

1. Melden Sie sich bei einem Computer, der  ausführt oder auf dem die -Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist. Zum Veröffentlichen einer Topologie (Voraussetzung für das Hinzufügen eines Servers zur Topologie) müssen Sie ein Konto verwenden, das Mitglied der Gruppe Domänen-Admins und der Gruppe RTCUniversalServerAdmins ist und über Vollzugriff (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den -Dateispeicher verwenden möchten, damit der  die erforderlichen DACLs (Discretionary Access Control Lists) konfigurieren kann. Alternativ dazu können Sie ein Konto mit äquivalenten Rechten verwenden.
  
2. Öffnen Sie die Topologie, die Sie im vorigen Abschnitt mithilfe von  erstellt haben.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **** und dann auf **Topologie veröffentlichen**.
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**. 
    
    > [!NOTE]
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. Über den  können nur Datenbanken auf dedizierten SQL-Servern installiert werden. Datenbanken auf SQL-Servern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden. 
  
6. Vergewissern Sie sich auf der Seite **Assistent für die Veröffentlichung abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md). 
  

