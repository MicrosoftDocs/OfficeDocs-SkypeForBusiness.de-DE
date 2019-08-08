---
title: Upgrade auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie ein Upgrade von lync Server 2013 auf Skype for Business Server 2015 durchführen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237448"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade to Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein Upgrade von lync Server 2013 auf Skype for Business Server 2015 durchführen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server 2015 aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Führen Sie die in diesem Dokument beschriebenen Verfahren aus, um von lync Server 2013 auf Skype for Business Server 2015 mithilfe des Skype for Business Server-Topologie-Generators und des neuen in-Place-Upgrade-Features zu aktualisieren. Wenn Sie ein Upgrade von lync Server 2010 oder Office Communications Server 2007 R2 durchführen möchten, lesen Sie [Planen des Upgrades auf Skype for Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Nebeneinander koexistieren wird unterstützt, lesen Sie [Migration zu Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) , um weitere Informationen zu erhalten.
  
## <a name="upgrade-from-lync-server-2013"></a>Upgrade von lync Server 2013

Das Upgrade von lync Server 2013 auf Skype for Business Server 2015 beinhaltet die Installation der erforderlichen Software, die Verwendung des Skype for Business Server-Topologie-Generators zum Upgrade von Datenbanken im Pool und die Verwendung des in-Place-Upgrades von Skype for Business Server auf den einzelnen dem Pool zugeordnete Server. Zum Durchführen eines Upgrades führen Sie die acht Schritte im vorliegenden Thema aus.
  
### <a name="before-you-begin"></a>Vorbereitung

- Überprüfen Sie [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Überprüfen Sie die [Server Anforderungen für Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installieren Sie die Voraussetzungen für Skype for Business Server 2015](install/install-prerequisites.md) .
    
- [Installieren Sie Skype for Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Schritt 1: Administratortools installieren und Topologie herunterladen

1. Stellen Sie eine Verbindung mit dem Computer in der Topologie her, auf der lync-OCSCore oder andere lync-Komponenten nicht installiert sind.
    
2. Führen Sie in Skype for Business Server 2015-Installationsmedien die Datei " **Setup. exe** " von **OCS_Volume\Setup\AMD64**aus. 
    
3. Klicken Sie auf **Installieren**. 
    
4. Akzeptieren Sie die Lizenzvereinbarungen.
    
5. Klicken Sie im Bereitstellungs-Assistenten auf **Administratortools installieren** und befolgen Sie die Schritte zur Installation.
    
     ![Screenshot des Bereitstellungsassistenten mit der aufgerufenen Verknüpfung „Administratortools installieren“.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Öffnen Sie auf dem Windows-Start Bildschirm Skype for Business Server Topology Builder.
    
7. Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen** und anschließend auf **Weiter**.
    
8. Geben Sie einen Namen für die Topologie ein und klicken Sie auf **Speichern**.
    
9. Gehen Sie zu dem Speicherort, an dem die Topologie gespeichert ist, und erstellen Sie eine Kopie der Topologie.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Schritt 2: Upgrade und Veröffentlichen der Topologie mit dem Topologie-Generator

Bevor Sie den Upgradevorgang starten, müssen alle Dienste für die Pools ausgeführt werden, die Sie aktualisieren möchten. Die Topologieänderungen werden in der lokalen Datenbank der Server im Pool repliziert.
  
> [!IMPORTANT]
>  Speichern Sie vor dem Upgrade eine Kopie Ihrer Topologiedatei. Nachdem Sie ein Upgrade ausgeführt haben, können Sie die Topologie nicht downgraden. #a0 Wenn sich ihre Dienste auf denselben Servern wie Ihre Datenbanken befinden, wie sich der beständige Chatdienst auf demselben Server wie die persistente Chat-Datenbank befindet, überspringen Sie diesen Schritt, und fahren Sie mit Schritt 4 fort. Wenn Sie die Dienste angehalten haben, führen Sie das Setup der Funktion für direkte Upgrades auf jedem Server zum Aktualisieren der lokalen Datenbanken aus.
  
> [!NOTE]
> Wenn die Topologie eine gespiegelte Back-End-Datenbank hat, werden Sie feststellen, dass sowohl der Prinzipalserver als auch die gespiegelten Datenbanken angezeigt werden, **wenn Sie die Topologie mithilfe des Topologie-Generators veröffentlichen**. Stellen Sie sicher, dass sämtliche Datenbanken auf dem Prinzipalserver laufen und dass Sie beim Veröffentlichen der Topologie nur die Prinzipaldatenbank und nicht die Spiegelung auswählen, andernfalls wird nach der Veröffentlichung der Topologie eine Warnung angezeigt.
  
Wählen Sie eine der folgenden Optionen aus, um eine neue Topologie mithilfe des Skype for Business Server 2015-Topologie-Generators zu aktualisieren und zu veröffentlichen. Nachdem Sie die Schritte vollständig ausgeführt haben und die Topologie veröffentlicht haben, für die das Upgrade ausgeführt wurde, fahren Sie mit Schritt 3 in diesem Thema fort.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Option 1: Upgrade eines isolierten Front-End-Pools und der zugehörigen Speicher für die Archivierung und Überwachung

Wenn der Pool, für den Sie ein Upgrade durchführen möchten, vom Speicher zur Archivierung und Überwachung abhängig ist, wird mithilfe der folgenden Schritte auch für den Speicher zur Archivierung und Überwachung ein Upgrade durchgeführt.
  
1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen lync Server 2013-Pool, wählen Sie **Upgrade auf Skype for Business Server 2015**aus, und führen Sie die folgenden Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit der Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Klicken Sie im Topologie-Generator auf **Aktion** > **Veröffentlichungs Topologie** oder **Aktions** > **Topologie** > **veröffentlichen**. 
    
     ![Screenshot des Menüs „Aktion“ mit der Option „Topologie veröffentlichen“ im Topology-Generator.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Wählen Sie während der Veröffentlichung die Installation einer Datenbank im Speicher für die Archivierung und Überwachung aus.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Option 2: Upgrade des Front-End-Pools ohne Upgrade der Archivierungs-und Überwachungsspeicher

Mithilfe der folgenden Anweisungen wird die Archivierung und Überwachung für den ausgewählten Pool deaktiviert. Der Pool weist nach dem Upgrade keine Speicher für die Archivierung und Überwachung auf.
  
1. Wählen Sie im Topologie-Generator den lync Server 2013-Pool aus, den Sie aktualisieren möchten.
    
2. Entfernen Sie die Abhängigkeit zu den lync Server 2013-Archivierungs-und-überwachungsspeichern. 
    
   - Wechseln Sie zu **Aktion** > **Eigenschaften bearbeiten**.
    
   - Deaktivieren Sie das Kontrollkästchen **Archivierung**.
    
     ![Screenshot des Kontrollkästchens „Archivierung“ im Dialogfeld „Eigenschaften bearbeiten“.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deaktivieren Sie das Kontrollkästchen **Überwachung**.
    
     ![Screenshot des Dialogfelds „Eigenschaften bearbeiten“ mit dem Kontrollkästchen „Überwachung“.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Klicken Sie mit der rechten Maustaste auf den lync Server 2013-Pool, wählen Sie **Upgrade auf Skype for Business Server 2015**aus, und führen Sie die folgenden Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit der Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Klicken Sie im Topologie-Generator auf **Aktion** > **Veröffentlichungs Topologie** oder **Aktions** > **Topologie** > **veröffentlichen**. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Option 3: Upgrade des Front-End-Pools und zugehöriges zu neuen Skype for Business Server 2015-Archivierungs-und überwachungsspeichern

Wenn Sie die folgenden Anweisungen ausführen, wird die Archivierung und Überwachung im vorherigen Speicher abgebrochen und im neuen, von Ihnen erstellten Speicher gestartet. 
  
1. Wählen Sie im Topologie-Generator den lync Server 2013-Pool aus, den Sie aktualisieren möchten. 
    
2. Entfernen Sie die Abhängigkeit zu den lync Server 2013-Archivierungs-und-überwachungsspeichern. 
    
   - Wechseln Sie zu **Aktion** > **Eigenschaften bearbeiten**.
    
   - Deaktivieren Sie das Kontrollkästchen **Archivierung**.
    
     ![Screenshot des Kontrollkästchens „Archivierung“ im Dialogfeld „Eigenschaften bearbeiten“.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deaktivieren Sie das Kontrollkästchen **Überwachung**.
    
     ![Screenshot des Dialogfelds „Eigenschaften bearbeiten“ mit dem Kontrollkästchen „Überwachung“.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Klicken Sie mit der rechten Maustaste auf den lync Server 2013-Pool, wählen Sie **Upgrade auf Skype for Business Server 2015**aus, und führen Sie die folgenden Schritte aus. 
    
     ![Screenshot des Kontextmenüs mit der Upgradeoption für Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Erstellen Sie einen neuen SQL-Speicher für die Archivierung. 
    
   - Wählen Sie den Pool und die **Aktion** > **Eigenschaften bearbeiten**aus. 
    
   -  Aktivieren Sie das Kontrollkästchen **Archivierung**.
    
   - Klicken Sie auf **Neu**.
    
     ![Screenshot des Dialogfelds „Bearbeiten von Eigenschaften“, in dem im Bereich „Archivierung“ die Schaltfläche „Neu“ angezeigt wird.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Erstellen Sie einen neuen SQL-Speicher für die Überwachung. 
    
   - Wählen Sie den Pool und die **Aktion** > **Eigenschaften bearbeiten**aus. 
    
   -  Wählen Sie das Kontrollkästchen **Überwachung** aus.
    
   - Klicken Sie auf **Neu**.
    
     ![Screenshot des Dialogfelds „Eigenschaften bearbeiten“, in dem im Bereich „Überwachung“ die Schaltfläche „Neu“ angezeigt wird.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Klicken Sie im Topologie-Generator auf **Aktion** > **Veröffentlichungs Topologie** oder **Aktions** > **Topologie** > **veröffentlichen**. 
    
7. Wählen Sie während der Veröffentlichung die Installation einer Datenbank im neuen Speicher für die Archivierung und Überwachung aus.
    
### <a name="step-3-wait-for-replication"></a>Schritt 3: Auf die Replikation warten

Die Replikation nimmt etwas Zeit in Anspruch, um die aktualisierte Topologie auf allen Servern der Umgebung zu veröffentlichen.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Schritt 4: Alle Dienste im Pool abbrechen, für den ein Upgrade durchgeführt werden soll

Führen Sie auf jedem Server, der den Pool bedient, den Sie aktualisieren möchten, das folgende Cmdlet in PowerShell aus:
  
```
Disable-CsComputer -Scorch
```

Es wird empfohlen, Disable-CsComputer zu verwenden, da Sie möglicherweise den Server während des direkten Aktualisierungsvorgangs neu starten müssen. Wenn Sie „Stop-CsWindowsService“ verwenden, werden einige Dienste nach einem Computerneustart eventuell automatisch neu gestartet. Dies kann dazu führen, dass das direkte Upgrade nicht ordnungsgemäß ausgeführt werden kann.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Schritt 5: Upgrades für Front-End-Pools und Nicht-Front-End-Pool-Server durchführen

> [!NOTE]
>  Vor dem Upgrade installieren Sie bitte alle neuen Voraussetzungen für Skype for Business Server 2015, die Folgendes beinhalten: #a0 mindestens 32 GB freien Speicherplatz, bevor Sie ein Upgrade durchführen. Stellen Sie außerdem sicher, dass es sich um ein festes lokales Laufwerk handelt, das nicht über USB oder FireWire verbunden ist, mit dem NTFS-Dateisystem formatiert ist, nicht komprimiert ist und keine Auslagerungsdatei enthält. #a0 PowerShell-Version 6.2.9200.0 oder höher. #a1 der neuesten lync Server 2013 Kumulatives Update installiert. #a2 SQL Server 2012 SP1 installiert. #a3 die folgenden KB installiert (automatisch bei Verwendung von Microsoft Update installiert): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
Verwenden Sie das in-Place-Upgrade auf jedem Server zum Aktualisieren des Front-End-Pools, des Edge-Pools, des Vermittlungsservers und des beständigen Chat Pools.
  
1. Führen Sie auf jedem Server **Setup. exe** auf dem Skype for Business Server 2015-Installationsmedium von **OCS_Volume\Setup\amd64** aus.
    
2. Akzeptieren Sie den Lizenzvertrag, und folgen Sie den Anweisungen für das in-Place-Upgrade.
    
3. Wiederholen Sie diese Schritte für jeden Server im Front-End-Pool und auf jedem nicht-Front-End-Pool Server.
    
> [!NOTE]
> Sie werden möglicherweise während des direkten Upgrades zum Neustarten des Servers aufgefordert. Das ist normal. Nachdem Sie einen Neustart durchgeführt haben, wird das in-Place-Upgrade von dort fortgesetzt, wo es aufgehört hat. 
  
Nach dem erfolgreichen direkten Upgrade wird Ihnen die folgende Meldung angezeigt.
  
![Screenshot mit erfolgreich abgeschlossenem direktem Upgrade.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Schritt 6: Dienste auf den Servern mit Upgrade neu starten

> [!NOTE]
> Bevor Sie die Dienste neu starten, stellen Sie sicher, dass%ProgramData%\WindowsFabric nicht auf allen Front-End-Servern vorhanden ist. Falls doch, löschen Sie es, bevor Sie die Dienste starten. 
  
- Nachdem Sie alle Server im Front-End-Pool aktualisiert haben, starten Sie die Dienste mithilfe des folgenden PowerShell-Befehls neu: 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > Wenn bereits ein anstehender Systemstart erforderlich ist, bevor sie das direkte Upgrade ausführen, werden Sie beim direkten Upgrade am Ende der Installation nicht zu einem Neustart aufgefordert. Dies führt zu Assembly-Ausnahmen gegenüber dem ersten Front-End-Server, wenn Sie versuchen, die Services mit dem Start-CSPool-Cmdlet zu starten. Nehmen Sie zur Fehlerbehebung einen Neustart aller Server im Pool vor und führen Sie das Cmdlet dann erneut aus. 
  
- Für Nicht-Front-End-Poolserver starten Sie die Dienste mithilfe des folgenden Befehls neu:
    
  ```
  Start-CsWindowsService
  ```

Nachdem Sie auf der Seite für das direkte Upgrade auf **OK** geklickt haben, wird folgende Erinnerung an die Ausführung dieses Schritts angezeigt.
  
![Screenshot, der die nächsten Schritte nach dem erfolgreichen Abschluss eines direkten Upgrades zeigt.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Schritt 7: Überprüfen der Funktionalität von Skype for Business

Um sicherzustellen, dass das Upgrade erfolgreich war, testen Sie für den Pool, der aktualisiert wurde, Skype for Business, um sicherzustellen, dass die Funktionalität wie erwartet funktioniert. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Schritt 8: Ein Upgrade der sekundären Pools durchführen

Wiederholen Sie die Schritte in diesem Thema, um ein Upgrade aller zusätzlichen Pools durchzuführen, die in Ihrer Umgebung vorhanden sind.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Problembehandlung beim direkten Upgrade

Wenn das direkte Upgrade fehlschlägt, wird Ihnen ggf. eine Meldung angezeigt, die in etwa dem folgenden Bild entspricht. 
  
![Screenshot, der einen Fehler bei einem direkten Upgrade zeigt, das fehlschlägt, weil ein benötigtes kumulatives Update nicht installiert war.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Überprüfen Sie die vollständige Meldung unten auf der Seite, um Hilfe zur Fehlerbehebung zu erhalten. Klicken Sie auf **Protokoll anzeigen**, um mehr Informationen zu erhalten.
  
Wenn das direkte Upgrade bei der **Überprüfung der Upgrade-Bereitschaft** oder bei der **Installation fehlender voraus**setzungen fehlschlägt, stellen Sie sicher, dass auf dem Server alle neuesten Windows Server-, lync Server-und SQL Server-Updates installiert sind, und alle erforderlichen Software-und Rollen sind installiert. Eine Liste der erforderlichen Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Installieren von Voraussetzungen für Skype for Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Siehe auch

[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installieren der erforderlichen Komponenten für Skype for Business Server 2015](install/install-prerequisites.md)
  
[Installieren von Skype for Business Server 2015](install/install.md)
