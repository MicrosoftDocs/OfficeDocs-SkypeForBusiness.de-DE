---
title: Upgrade auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Zusammenfassung: Erfahren Sie, wie Sie ein Upgrade von Lync Server 2013 auf Skype for Business Server 2015 durchführen. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 02455d4c013f55363e173f16c9f4de60b71939d9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740081"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade auf Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein Upgrade von Lync Server 2013 auf Skype for Business Server 2015 durchführen. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Verwenden Sie die Verfahren in diesem Dokument, um ein Upgrade von Lync Server 2013 auf Skype for Business Server 2015 mithilfe des Skype for Business Server Topologie-Generators und des neuen In-Place Upgrade-Features durchzuführen. Wenn Sie ein Upgrade von Lync Server 2010 oder Office Communications Server 2007 R2 durchführen möchten, lesen Sie den [Plan zum Upgrade auf Skype for Business Server 2015.](../plan-your-deployment/upgrade.md)

> [!NOTE]
> Direkte Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Parallele Koexistenz wird unterstützt. Weitere Informationen finden Sie unter [Migration zu Skype for Business Server 2019.](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)
  
## <a name="upgrade-from-lync-server-2013"></a>Upgrade von Lync Server 2013

Das Upgrade von Lync Server 2013 auf Skype for Business Server 2015 umfasst die Installation der erforderlichen Software, die Verwendung des Skype for Business Server Topologie-Generators zum Aktualisieren von Datenbanken im Pool und die Verwendung des Skype for Business Server In-Place Upgrades auf jedem Server, der dem Pool zugeordnet ist. Führen Sie die acht Schritte in diesem Thema aus, um das Upgrade abzuschließen.
  
### <a name="before-you-begin"></a>Bevor Sie loslegen

- Überprüfen Sie [den Plan für das Upgrade auf Skype for Business Server 2015.](../plan-your-deployment/upgrade.md)
    
- Überprüfen Sie [die Serveranforderungen für Skype for Business Server 2015.](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Installieren Sie die erforderlichen Komponenten für Skype for Business Server 2015.](install/install-prerequisites.md)
    
- [Installieren Sie Skype for Business Server 2015.](install/install.md)
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Schritt 1: Installieren von Administratortools und Herunterladen der Topologie

1. Verbinden an den Computer in der Topologie, auf dem lync OCSCore oder andere Lync-Komponenten nicht installiert sind.
    
2. Führen Sie ab Skype for Business Server Installationsmedium 2015 **Setup.exe** aus **OCS_Volume\Setup\AMD64** aus. 
    
3. Klicken Sie auf **Installieren**. 
    
4. Lizenzvertrag akzeptieren.
    
5. Klicken Sie im Bereitstellungs-Assistenten auf **"Administratortools installieren",** und führen Sie die zu installierenden Schritte aus.
    
     ![Screenshot des Bereitstellungs-Assistenten mit aufgerufenen Links zu den Installationsadministratortools.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Öffnen Sie auf dem Windows Startbildschirm Skype for Business Server Topologie-Generator.
    
7. Klicken Sie auf **Topologie aus vorhandener Bereitstellung herunterladen,** und klicken Sie auf **"Weiter".**
    
8. Geben Sie einen Namen für die Topologie ein, und klicken Sie auf **"Speichern".**
    
9. Wechseln Sie zu dem Speicherort, an dem Sie die Topologie gespeichert haben, und erstellen Sie eine Kopie der Topologie.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Schritt 2: Aktualisieren und Veröffentlichen der Topologie mithilfe des Topologie-Generators

Bevor Sie mit dem Upgradevorgang beginnen, müssen alle Dienste für die Pools ausgeführt werden, die Sie aktualisieren möchten. Auf diese Weise werden die Topologieänderungen in die lokale Datenbank der Server im Pool repliziert.
  
> [!IMPORTANT]
>  Speichern Sie vor dem Upgrade eine Kopie der Topologiedatei. Nach dem Upgrade können Sie die Topologie nicht downgradeen.> Wenn sich Ihre Dienste auf denselben Servern wie Ihre Datenbanken befinden, z. B. der Dienst für beständigen Chat auf demselben Server wie die Datenbank für beständigen Chat, überspringen Sie diesen Schritt, und fahren Sie mit Schritt 4 fort. Nachdem Sie die Dienste beendet haben, führen Sie das setup In-Place Upgrade auf jedem Server aus, um die lokalen Datenbanken zu aktualisieren.
  
> [!NOTE]
> Wenn die Topologie über eine gespiegelte Back-End-Datenbank verfügt, werden sowohl die Prinzipaldatenbank als auch die gespiegelten Datenbanken **angezeigt, wenn Sie die Topologie** mithilfe des Topologie-Generators veröffentlichen. Stellen Sie sicher, dass alle Datenbanken auf dem Prinzipal ausgeführt werden, und wählen Sie beim Veröffentlichen der Topologie nur den Prinzipal und nicht den Spiegel aus. Andernfalls wird nach der Veröffentlichung der Topologie eine Warnung angezeigt.
  
Wählen Sie eine der folgenden Optionen aus, um eine neue Topologie mithilfe des Skype for Business Server 2015-Topologie-Generators zu aktualisieren und zu veröffentlichen. Nachdem Sie die Schritte abgeschlossen und die aktualisierte Topologie veröffentlicht haben, wechseln Sie zu Schritt 3 in diesem Thema.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Option 1: Upgrade eines isolierten Front-End-Pools und zugehöriger Archivierungs- und Überwachungsspeicher

Wenn der Pool, den Sie aktualisieren, eine Abhängigkeit vom Archivierungs- und Überwachungsspeicher aufweist, wird bei Verwendung der folgenden Schritte auch der Archivierungs- und Überwachungsspeicher aktualisiert.
  
1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen Lync Server 2013-Pool, wählen Sie **"Upgrade to Skype for Business Server 2015"** aus, und führen Sie die Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Klicken Sie im Topologie-Generator auf "Aktionsveröffentlichungstopologie"  >   oder **"Aktionstopologie**  >    >  **veröffentlichen".** 
    
     ![Screenshot des Aktionsmenüs mit der Option "Topologie veröffentlichen" im Topologie-Generator.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Wählen Sie während der Veröffentlichung die Installation einer Datenbank im Archivierungs- und Überwachungsspeicher aus.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Option 2: Upgrade des Front-End-Pools ohne Upgrade von Archivierungs- und Überwachungsspeichern

Wenn Sie die folgenden Schritte ausführen, ist die Archivierung und Überwachung für den ausgewählten Pool deaktiviert. Der Pool verfügt nach dem Upgrade nicht über Archivierungs- und Überwachungsspeicher.
  
1. Wählen Sie im Topologie-Generator den Lync Server 2013-Pool aus, den Sie aktualisieren möchten.
    
2. Entfernen Sie die Abhängigkeit von den Lync Server 2013-Speicher für Archivierung und Überwachung. 
    
   - Wechseln Sie zu  >  **Aktionsbearbeitungseigenschaften.**
    
   - Deaktivieren Sie das **Kontrollkästchen Archivierung.**
    
     ![Screenshot des Kontrollkästchens "Archivierung" im Dialogfeld "Eigenschaften bearbeiten".](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deaktivieren Sie das **Kontrollkästchen Überwachung.**
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem das Kontrollkästchen "Überwachung" angezeigt wird.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Pool, wählen Sie **"Upgrade to Skype for Business Server 2015"** aus, und führen Sie die Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Klicken Sie im Topologie-Generator auf "Aktionsveröffentlichungstopologie"  >   oder **"Aktionstopologie**  >    >  **veröffentlichen".** 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Option 3: Upgrade des Front-End-Pools und Zuordnung zu neuen Skype for Business Server 2015-Speicher für Archivierung und Überwachung

Wenn Sie die folgenden Schritte ausführen, wird die Archivierung und Überwachung im vorherigen Speicher beendet und im neuen Speicher gestartet, den Sie erstellt haben. 
  
1. Wählen Sie im Topologie-Generator den Lync Server 2013-Pool aus, den Sie aktualisieren möchten. 
    
2. Entfernen Sie die Abhängigkeit von den Lync Server 2013-Speicher für Archivierung und Überwachung. 
    
   - Wechseln Sie zu  >  **Aktionsbearbeitungseigenschaften.**
    
   - Deaktivieren Sie das **Kontrollkästchen Archivierung.**
    
     ![Screenshot des Kontrollkästchens "Archivierung" im Dialogfeld "Eigenschaften bearbeiten".](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deaktivieren Sie das **Kontrollkästchen Überwachung.**
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem das Kontrollkästchen "Überwachung" angezeigt wird.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Pool, wählen Sie **"Upgrade to Skype for Business Server 2015"** aus, und führen Sie die Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Erstellen Sie einen neuen SQL Speicher für die Archivierung. 
    
   - Wählen Sie die Eigenschaften **"Pool"** und  >  **"Aktion bearbeiten" aus.** 
    
   -  Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
   - Klicken Sie auf **Neu**.
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem die Schaltfläche "Neu" im Abschnitt "Archivierung" angezeigt wird.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Erstellen Sie einen neuen SQL Speicher für die Überwachung. 
    
   - Wählen Sie die Eigenschaften **"Pool"** und  >  **"Aktion bearbeiten" aus.** 
    
   -  Aktivieren Sie das **Kontrollkästchen Überwachung.**
    
   - Klicken Sie auf **Neu**.
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem die Schaltfläche "Neu" im Abschnitt "Überwachung" angezeigt wird.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Klicken Sie im Topologie-Generator auf "Aktionsveröffentlichungstopologie"  >   oder **"Aktionstopologie**  >    >  **veröffentlichen".** 
    
7. Wählen Sie während der Veröffentlichung die Installation der Datenbank im neuen Archivierungs- und Überwachungsspeicher aus.
    
### <a name="step-3-wait-for-replication"></a>Schritt 3: Warten auf die Replikation

Geben Sie der Replikation etwas Zeit, um die aktualisierte Topologie auf allen Servern in der Umgebung zu veröffentlichen.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Schritt 4: Beenden aller Dienste im Pool, die aktualisiert werden sollen

Führen Sie auf jedem Server, der den Pool wartet, den Sie aktualisieren möchten, das folgende Cmdlet in PowerShell aus:
  
```powershell
Disable-CsComputer -Scorch
```

Es wird empfohlen, Disable-CsComputer zu verwenden, da Sie den Server möglicherweise während des In-Place Upgrade-Prozesses neu starten müssen. Wenn Sie Stop-CsWindowsService verwenden, werden einige Dienste nach einem Neustart möglicherweise automatisch neu gestartet. Dies kann dazu führen, dass das In-Place Upgrade fehlschlägt.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Schritt 5: Upgrade von Front-End-Pools und Nicht-Front-End-Poolservern

> [!NOTE]
>  Installieren Sie vor dem Upgrade alle neuen erforderlichen Komponenten für Skype for Business Server 2015, die: > mindestens 32 GB freien Speicherplatz enthalten, bevor Sie ein Upgrade durchführen. Stellen Sie außerdem sicher, dass es sich bei dem Laufwerk um ein festes lokales Laufwerk handelt. ist nicht über USB oder Firewire verbunden, mit dem NTFS-Dateisystem formatiert, nicht komprimiert und enthält keine Seitendatei.> PowerShell-Version 6.2.9200.0 oder höher.> Das neueste kumulative Update für Lync Server 2013 installiert.> SQL Server 2012 SP1 installed.> Die folgenden KB werden installiert (automatisch installiert, wenn Microsoft Update verwendet wird): > Windows Server 2008 R2[– KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 –[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 –[KB2982006](https://support.microsoft.com/kb/2982006)
  
Verwenden Sie das In-Place Upgrade auf jedem Server, um den Front-End-Pool, den Edgepool, den Vermittlungsserver und den Pool für beständigen Chat zu aktualisieren.
  
1. Führen Sie auf jedem Server **Setup.exe** von **OCS_Volume\Setup\amd64** auf dem Installationsmedium Skype for Business Server 2015 aus.
    
2. Akzeptieren Sie den Lizenzvertrag, und folgen Sie den Anweisungen für das In-Place Upgrade.
    
3. Wiederholen Sie diese Schritte für jeden Server im Front-End-Pool und auf jedem Nicht-Front-End-Poolserver.
    
> [!NOTE]
> Möglicherweise werden Sie während des In-Place Upgrades aufgefordert, den Server neu zu starten. Das ist in Ordnung. Nach dem Neustart wird das In-Place Upgrade von dort fortgesetzt, wo es unterbrochen wurde. 
  
Wenn das In-Place Upgrade erfolgreich abgeschlossen wurde, wird die folgende Meldung angezeigt.
  
![Screenshot, der zeigt, dass das direkte Upgrade erfolgreich abgeschlossen wurde.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Schritt 6: Dienste auf allen aktualisierten Servern neu starten

> [!NOTE]
> Stellen Sie vor dem Neustart der Dienste sicher, dass %ProgramData%\WindowsFabric nicht auf allen Front-End-Servern vorhanden ist. Falls vorhanden, löschen Sie es, bevor Sie die Dienste starten. 
  
- Nachdem Sie alle Server im Front-End-Pool aktualisiert haben, starten Sie die Dienste mit dem folgenden PowerShell-Befehl neu: 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > Wenn bereits ein ausstehender Systemneustart erforderlich ist, bevor Sie mit der Ausführung In-Place Upgrades beginnen, werden Sie In-Place Upgrade am Ende der Installation nicht zum Neustart aufgefordert. Dadurch werden einige Assemblyausnahmen für den ersten Front-End-Server ausgelöst, wenn Sie versuchen, Dienste mithilfe des Cmdlets Start-CSPool zu starten. Um diese Fehler zu beheben, starten Sie alle Server im Pool neu, und führen Sie das Cmdlet erneut aus. 
  
- Starten Sie die Dienste auf den Nicht-Front-End-Poolservern mit dem folgenden Befehl neu:
    
  ```powershell
  Start-CsWindowsService
  ```

Nachdem Sie auf der Seite In-Place Upgrade auf **"OK"** geklickt haben, wird die folgende Erinnerung angezeigt, um diesen Schritt abzuschließen.
  
![Screenshot, der die nächsten Schritte zeigt, nachdem das direkte Upgrade erfolgreich abgeschlossen wurde.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Schritt 7: Überprüfen, ob Skype for Business Funktionalität funktioniert

Um sicherzustellen, dass das Upgrade erfolgreich war, testen Sie für den Pool, der aktualisiert wurde, Skype for Business, um sicherzustellen, dass die Funktionalität wie erwartet funktioniert. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Schritt 8: Aktualisieren sekundärer Pools

Wiederholen Sie die Schritte in diesem Thema, um zusätzliche Pools in Ihrer Umgebung zu aktualisieren.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Behandeln von Problemen mit dem In-Place-Upgrade

Wenn das In-Place Upgrade fehlschlägt, wird möglicherweise eine Meldung ähnlich wie in der folgenden Abbildung angezeigt. 
  
![Screenshot, der zeigt, dass das direkte Upgrade fehlschlägt, da kein erforderliches kumulatives Update installiert ist.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Überprüfen Sie die vollständige Meldung am unteren Rand der Seite, um ihnen bei der Problembehandlung zu helfen. Klicken Sie auf **"Protokolle anzeigen",** um weitere Details zu erhalten.
  
Wenn das In-Place Upgrade bei der Überprüfung der **Upgradebereitschaft** oder bei der **Installation fehlender Voraussetzungen** fehlschlägt, stellen Sie sicher, dass auf dem Server alle neuesten Windows Server-, Lync Server- und SQL Server Updates angewendet wurden und alle erforderlichen Software und Rollen installiert sind. Eine Liste der erforderlichen Komponenten finden Sie unter [server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and Install [prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Weitere Informationen

[Planen des Upgrades auf Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Serveranforderungen für Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installieren der erforderlichen Komponenten für Skype for Business Server 2015](install/install-prerequisites.md)
  
[Installieren Skype for Business Server 2015](install/install.md)
