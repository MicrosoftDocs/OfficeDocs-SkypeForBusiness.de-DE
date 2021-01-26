---
title: Upgrade auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Zusammenfassung: Informationen zum Upgrade von Lync Server 2013 auf Skype for Business Server 2015. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820425"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade auf Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein Upgrade von Lync Server 2013 auf Skype for Business Server 2015 durchführen. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem [Microsoft Evaluation Center herunter.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Verwenden Sie die Verfahren in diesem Dokument zum Upgrade von Lync Server 2013 auf Skype for Business Server 2015 mithilfe des Skype for Business Server-Topologie-Generators und der neuen In-Place-Upgrade-Funktion. Informationen zum Upgrade von Lync Server 2010 oder Office Communications Server 2007 R2 finden Sie unter [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die nebeneinander ausgeführte Koexistenz wird unterstützt. Weitere Informationen finden Sie unter ["Migration zu Skype for Business Server 2019".](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)
  
## <a name="upgrade-from-lync-server-2013"></a>Upgrade von Lync Server 2013

Das Upgrade von Lync Server 2013 auf Skype for Business Server 2015 umfasst die Installation der erforderlichen Software, die Verwendung des Skype for Business Server-Topologie-Generators zum Aktualisieren von Datenbanken im Pool und das Skype for Business Server In-Place Upgrade auf jedem server, der dem Pool zugeordnet ist. Führen Sie zum Abschließen des Upgrades die acht Schritte in diesem Thema aus.
  
### <a name="before-you-begin"></a>Bevor Sie beginnen

- Überprüfen [Sie den Plan für das Upgrade auf Skype for Business Server 2015.](../plan-your-deployment/upgrade.md)
    
- Überprüfen [Der Serveranforderungen für Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installieren Sie die erforderlichen Komponenten für Skype for Business Server 2015.](install/install-prerequisites.md)
    
- [Installieren Sie Skype for Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Schritt 1: Installieren von Administratortools und Herunterladen der Topologie

1. Stellen Sie eine Verbindung mit dem Computer in der Topologie ohne Lync OCSCore oder andere Lync-Komponenten sicher.
    
2. Führen Sie auf den Skype for Business  Server 2015-InstallationsmedienSetup.exeunter **OCS_Volume\Setup\AMD64 aus.** 
    
3. Klicken Sie auf **Installieren**. 
    
4. Lizenzvertrag akzeptieren.
    
5. Klicken Sie im Bereitstellungsassistenten auf **"Administratortools installieren",** und führen Sie die schritte zur Installation aus.
    
     ![Screenshot des Bereitstellungs-Assistenten mit einem Link zu den aufgerufenen Installationsadministratortools.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Öffnen Sie auf dem Startbildschirm von Windows den Skype for Business Server-Topologie-Generator.
    
7. Klicken **Sie auf "Topologie aus vorhandener Bereitstellung herunterladen"** und dann auf **"Weiter".**
    
8. Geben Sie einen Namen für die Topologie ein, und klicken Sie auf **"Speichern".**
    
9. Wechseln Sie zum Speicherort der Topologie, und erstellen Sie eine Kopie der Topologie.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Schritt 2: Aktualisieren und Veröffentlichen der Topologie mithilfe des Topologie-Generators

Bevor Sie mit dem Upgradeprozess beginnen, müssen alle Dienste für die Pools ausgeführt werden, die Sie aktualisieren möchten. Die Topologieänderungen werden daher in die lokale Datenbank der Server im Pool repliziert.
  
> [!IMPORTANT]
>  Speichern Sie vor dem Upgrade eine Kopie ihrer Topologiedatei. Nach dem Upgrade können Sie die Topologie nicht herunterstufen.> Wenn sich Ihre Dienste auf denselben Servern wie Ihre Datenbanken befinden, z. B. wenn sich der Dienst für beständigen Chat auf demselben Server wie die Datenbank für beständigen Chat befindet, überspringen Sie diesen Schritt, und fahren Sie mit Schritt 4 fort. Führen Sie nach dem Beenden der Dienste das Setupprogramm In-Place Auf jedem Server aus, um die lokalen Datenbanken zu aktualisieren.
  
> [!NOTE]
> Wenn die Topologie über eine gespiegelte Back-End-Datenbank verfügt, werden sowohl die  Prinzipaldatenbank als auch die gespiegelte Datenbank angezeigt, wenn Sie die Topologie mithilfe des Topologie-Generators veröffentlichen. Stellen Sie sicher, dass alle Datenbanken auf dem Prinzipal ausgeführt werden, und wählen Sie beim Veröffentlichen der Topologie nur den Prinzipal und nicht den Spiegel aus. Andernfalls wird nach der Veröffentlichung der Topologie eine Warnung angezeigt.
  
Wählen Sie eine der folgenden Optionen aus, um eine neue Topologie mithilfe des Skype for Business Server 2015-Topologie-Generators zu aktualisieren und zu veröffentlichen. Nachdem Sie die Schritte abgeschlossen und die aktualisierte Topologie veröffentlicht haben, wechseln Sie zu Schritt 3 in diesem Thema.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Option 1: Aktualisieren eines isolierten Front-End-Pools und zugehöriger Archivierungs- und Überwachungsspeicher

Wenn der Pool, den Sie aktualisieren, von einem Archivierungs- und Überwachungsspeicher abhängig ist, wird beim Ausführen der folgenden Schritte auch der Archivierungs- und Überwachungsspeicher aktualisiert.
  
1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen Lync Server 2013-Pool, wählen Sie **"Upgrade auf Skype for Business Server 2015"** aus, und führen Sie die folgenden Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Klicken Sie im Topologie-Generator auf **"Topologie**  >  **veröffentlichen" oder** **"Aktionstopologie**  >    >  **veröffentlichen".** 
    
     ![Screenshot des Menüs "Aktion" mit der Option "Topologie veröffentlichen" im Topologie-Generator.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Installieren Sie während der Veröffentlichung eine Datenbank im Archivierungs- und Überwachungsspeicher.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Option 2: Aktualisieren des Front-End-Pools ohne Upgrade von Archivierungs- und Überwachungsspeichern

Wenn Sie die folgenden Schritte ausführen, werden die Archivierung und Überwachung für den ausgewählten Pool deaktiviert. Der Pool enthält nach dem Upgrade keine Archivierungs- und Überwachungsspeicher.
  
1. Wählen Sie im Topologie-Generator den Lync Server 2013-Pool aus, den Sie aktualisieren möchten.
    
2. Entfernen Sie die Abhängigkeit zu den Archivierungs- und Überwachungsspeichern von Lync Server 2013. 
    
   - Wechseln Sie zu  >  **Aktionsbearbeitungseigenschaften.**
    
   - Aktivieren Sie **das Kontrollkästchen** "Archivierung".
    
     ![Screenshot des Kontrollkästchens "Archivierung" im Dialogfeld "Eigenschaften bearbeiten".](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Aktivieren Sie **das Kontrollkästchen "Überwachung".**
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem das Kontrollkästchen "Überwachung" angezeigt wird.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Pool, wählen Sie **"Upgrade auf Skype for Business Server 2015"** aus, und führen Sie die folgenden Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Klicken Sie im Topologie-Generator auf **"Topologie**  >  **veröffentlichen" oder** **"Aktionstopologie**  >    >  **veröffentlichen".** 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Option 3: Aktualisieren des Front-End-Pools und Bündeln des Pools mit neuen Archivierungs- und Überwachungsspeichern für Skype for Business Server 2015

Wenn Sie die folgenden Schritte ausführen, wird die Archivierung und Überwachung im vorherigen Speicher beendet und in dem neuen Speicher gestartet, den Sie erstellt haben. 
  
1. Wählen Sie im Topologie-Generator den Lync Server 2013-Pool aus, den Sie aktualisieren möchten. 
    
2. Entfernen Sie die Abhängigkeit zu den Archivierungs- und Überwachungsspeichern von Lync Server 2013. 
    
   - Wechseln Sie zu  >  **Aktionsbearbeitungseigenschaften.**
    
   - Aktivieren Sie **das Kontrollkästchen** "Archivierung".
    
     ![Screenshot des Kontrollkästchens "Archivierung" im Dialogfeld "Eigenschaften bearbeiten".](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Aktivieren Sie **das Kontrollkästchen "Überwachung".**
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem das Kontrollkästchen "Überwachung" angezeigt wird.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Pool, wählen Sie **"Upgrade auf Skype for Business Server 2015"** aus, und führen Sie die folgenden Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Erstellen Sie einen neuen SQL für die Archivierung. 
    
   - Wählen Sie die Pool- und  >  **Aktionsbearbeitungseigenschaften aus.** 
    
   -  Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
   - Klicken Sie auf **Neu**.
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem die Schaltfläche "Neu" im Abschnitt "Archivierung" angezeigt wird.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Erstellen Sie einen SQL für die Überwachung. 
    
   - Wählen Sie die Pool- und  >  **Aktionsbearbeitungseigenschaften aus.** 
    
   -  Aktivieren Sie das **Kontrollkästchen** "Überwachung".
    
   - Klicken Sie auf **Neu**.
    
     ![Screenshot des Dialogfelds "Eigenschaften bearbeiten", in dem die Schaltfläche "Neu" im Abschnitt "Überwachung" angezeigt wird.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Klicken Sie im Topologie-Generator auf **"Topologie**  >  **veröffentlichen" oder** **"Aktionstopologie**  >    >  **veröffentlichen".** 
    
7. Installieren Sie die Datenbank während der Veröffentlichung im neuen Archivierungs- und Überwachungsspeicher.
    
### <a name="step-3-wait-for-replication"></a>Schritt 3: Auf Replikation warten

Geben Sie der Replikation etwas Zeit, um die aktualisierte Topologie auf allen Servern in der Umgebung zu veröffentlichen.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Schritt 4: Beenden des Upgrades aller Dienste im Pool

Führen Sie auf jedem Server, der den Zu aktualisierenden Pool bedient, das folgende Cmdlet in PowerShell aus:
  
```powershell
Disable-CsComputer -Scorch
```

Es wird empfohlen, Disable-CsComputer zu verwenden, da Sie den Server während des In-Place möglicherweise neu starten müssen. Wenn Sie "Stop-CsWindowsService" verwenden, werden einige Dienste nach einem Neustart möglicherweise automatisch neu gestartet. Dies kann dazu führen, dass In-Place Upgrade fehlschlägt.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Schritt 5: Aktualisieren von Front-End-Pools und Nicht-Front-End-Poolservern

> [!NOTE]
>  Installieren Sie vor dem Upgrade alle neuen erforderlichen Komponenten für Skype for Business Server 2015, die Folgendes umfassen: > Mindestens 32 GB freier Speicherplatz vor dem Upgrade. Stellen Sie außerdem sicher, dass es sich bei dem Laufwerk um ein festes lokales Laufwerk handelt, das nicht über USB oder Firewire verbunden ist. ist mit dem NTFS-Dateisystem formatiert, nicht komprimiert und enthält keine Seitendatei.> PowerShell, Version 6. 2.9200.0 oder höher.> Das neueste kumulative Update für Lync Server 2013 wurde installiert.> SQL Server 2012 SP1 installiert.> Die folgenden installierten KB (bei Verwendung von Microsoft Update automatisch installiert):> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Verwenden Sie In-Place Upgrade auf jedem Server, um den Front-End-Pool, den Edgepool, den Vermittlungsserver und den Pool für beständigen Chat zu aktualisieren.
  
1. Führen Sie auf jedem Server **Setup.exe** unter **OCS_Volume\Setup\amd64** auf dem Skype for Business Server 2015-Installationsmedium aus.
    
2. Akzeptieren Sie den Lizenzvertrag, und folgen Sie den Eingabeaufforderungen für In-Place Upgrade.
    
3. Wiederholen Sie diese Schritte für jeden Server im Front-End-Pool und auf jedem Nicht-Front-End-Poolserver.
    
> [!NOTE]
> Möglicherweise werden Sie aufgefordert, den Server während des In-Place neu zu starten. Das ist in Ordnung. Nach dem Neustart wird das In-Place an der Stelle fortgesetzt, an der es nicht mehr ausgeführt wurde. 
  
Wenn das In-Place Upgrade erfolgreich abgeschlossen wurde, wird die folgende Meldung angezeigt.
  
![Screenshot, der zeigt, dass das in-Place-Upgrade erfolgreich abgeschlossen wurde.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Schritt 6: Neustarten von Diensten auf allen aktualisierten Servern

> [!NOTE]
> Stellen Sie vor dem Neustart der Dienste sicher, dass %ProgramData%\WindowsFabric nicht auf allen Front-End-Servern vorhanden ist. Falls vorhanden, löschen Sie ihn, bevor Sie die Dienste starten. 
  
- Nachdem Sie alle Server im Front-End-Pool aktualisiert haben, starten Sie die Dienste mithilfe des folgenden PowerShell-Befehls neu: 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > Wenn bereits ein ausstehender Systemneustart erforderlich ist, bevor Sie mit dem Ausführen des In-Place-Upgrades beginnen, werden Sie von In-Place Upgrade nicht zum Neustart am Ende der Installation gefragt. Dadurch werden einige Assemblyausnahmen für den ersten Front-End-Server ausgelöst, wenn Sie versuchen, Dienste mit dem cmdlet Start-CSPool starten. Um diese Fehler zu beheben, starten Sie alle Server im Pool neu, und führen Sie das Cmdlet erneut aus. 
  
- Starten Sie die Dienste auf den Nicht-Front-End-Poolservern mit dem folgenden Befehl neu:
    
  ```powershell
  Start-CsWindowsService
  ```

Nachdem Sie auf der Seite **In-Place** "Upgrade" auf "OK" geklickt haben, wird die folgende Erinnerung zum Abschließen dieses Schritts angezeigt.
  
![Screenshot, der die nächsten Schritte nach dem erfolgreichen Abschluss des in-Place-Upgrades zeigt.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Schritt 7: Überprüfen der Funktionsfähigkeit von Skype for Business

Um sicherzustellen, dass das Upgrade erfolgreich war, testen Sie für den Pool, für den ein Upgrade durchgeführt wurde, Skype for Business, um sicherzustellen, dass die Funktionalität wie erwartet funktioniert. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Schritt 8: Aktualisieren sekundärer Pools

Wiederholen Sie die Schritte in diesem Thema, um alle zusätzlichen Pools in Ihrer Umgebung zu aktualisieren.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Behandeln von Problemen mit dem In-Place Upgrade

Wenn beim In-Place Upgrade ein Fehler auftritt, wird möglicherweise eine Meldung ähnlich der folgenden Abbildung angezeigt. 
  
![Screen shot that shows in-place upgrade failing because a required cumulative update isn't installed.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Überprüfen Sie die vollständige Meldung am unteren Rand der Seite, um ihnen bei der Problembehandlung zu helfen. Klicken **Sie auf "Protokolle anzeigen",** um weitere Details zu erhalten.
  
Wenn beim In-Place-Upgrade beim  Überprüfen der Upgradebereitschaft oder beim Installieren fehlender Voraussetzungen ein Fehler **auftritt,** stellen Sie sicher, dass auf dem Server alle neuesten Windows Server-, Lync Server- und SQL Server-Updates angewendet sind und alle erforderlichen Software- und Rollen installiert sind. Eine Liste der erforderlichen Komponenten finden Sie unter ["Serveranforderungen für Skype for Business Server 2015"](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und "Installieren der erforderlichen Komponenten für Skype for Business Server [2015".](install/install-prerequisites.md)
  
## <a name="see-also"></a>Siehe auch

[Planen des Upgrades auf Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Serveranforderungen für Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installieren der erforderlichen Komponenten für Skype for Business Server 2015](install/install-prerequisites.md)
  
[Installieren von Skype for Business Server 2015](install/install.md)
