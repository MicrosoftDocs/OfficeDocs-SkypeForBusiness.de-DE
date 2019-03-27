---
title: Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015.'
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880483"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zum Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015.
  
Skype für Business Server unterstützt mehrere Unterhaltungsmodi hohe Verfügbarkeit für die Back-End-Server, die einschließlich der datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> AlwaysOn Availability Groups werden für Persistent Chatserver nicht unterstützt. 
  
Bevor Sie Ihre Bereitstellung beständigen Chat für hohe Verfügbarkeit und notfallwiederherstellung konfigurieren, achten Sie darauf, dass Sie mit den Konzepten in [Planen für hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)vertraut sind. Die Lösung für die notfallwiederherstellung für Persistent Chat Server in diesen Themen beschriebenen basiert auf einer ausgedehnten Persistent Chat Server Pool. Der Planung Inhalt beschreibt Ressourcenbedarf und die ausgedehnte pooltopologie, die hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server, einschließlich der Verwendung von SQL Server-Spiegelung für hohe Verfügbarkeit und SQL Server-Protokollversand für ermöglicht Disaster Recovery.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators

Führen Sie mit dem Topologie-Generator die folgenden Schritte aus, um die Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.
  
1. Fügen Sie die Spiegeldatenbanken und die Protokolldateien des Protokollversands sekundäre Datenbank, die SQL Server-Speicher.
    
2. Bearbeiten der Eigenschaften des Persistent Chat Server zu:
    
    a. Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    b. Fügen Sie den primären spiegelspeicher für SQL Server.
    
    c. Aktivieren Sie die SQL Server-Protokollversand-Datenbank.
    
    d. Fügen Sie den SQL Server-Protokollversand sekundären SQL Server-Speicher.
    
    e. Fügen Sie der SQL Server-speicherspiegel für die sekundäre Datenbank hinzu.
    
    f. Veröffentlichen Sie die Topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat

Mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Protokollversand Datenbankinstanz von Persistent Chat Server, und stellen Sie sicher, dass SQL Server-Agent ausgeführt wird. Klicken Sie dann eine Verbindung mit der primären Datenbank-Instanz beständigen Chat, und führen Sie die folgenden Schritte aus:
  
1. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.
    
2. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
3. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
4. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
5. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.
    
6. Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (Beispiel: c:\Sicherung)** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie Ihren Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad dieses Ordners angeben. 
  
7. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
8. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Um den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, und passen Sie den SQL Server-Agent Zeitplan nach Bedarf.
    
9. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus und klicken Sie dann auf **OK**.
    
10. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.
    
11. Klicken Sie auf **Verbinden** , und eine Verbindung mit der Instanz von SQL Server, die Sie als sekundären Server konfiguriert haben.
    
12. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.
    
13. Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist)**.
    
14. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.
    
15. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Um den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, und passen Sie den SQL Server-Agent Zeitplan nach Bedarf. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
16. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.
    
17. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.
    
18. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.
    
19. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Um den Zeitplan für die Installation anzupassen, klicken Sie auf **Zeitplan**, passen Sie den SQL Server-Agent Zeitplan nach Bedarf, und klicken Sie auf **OK**. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
20. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank

Führen Sie die folgenden Schritte für den Protokollversand, um fortzufahren, wenn die primäre Datenbank für beständigen Chat ein Failover auf die Spiegeldatenbank durchgeführt wird.
  
1. Manuell ein Failover der primären Datenbank für beständigen Chat mit dem Spiegelserver. Dies erfolgt mithilfe der Skype für Business Server-Verwaltungsshell und das Cmdlet " **Invoke-CsDatabaseFailover** ".
    
2. Verwenden das SQL Server Management Studio, verbinden Sie mit der primären Persistent Chat Server-Spiegelinstanz.
    
3. Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.
    
4. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.
    
5. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
6. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
7. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
8. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.
    
9. Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie Ihren Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad dieses Ordners angeben. 
  
10. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
11. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Um den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, und passen Sie den SQL Server-Agent-Zeitplan, nach Bedarf.
    
    > [!IMPORTANT]
    > Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben. 
  
12. Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus und klicken Sie auf **OK**.
    
13. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.
    
14. Klicken Sie auf **Verbinden** und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.
    
15. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.
    
16. Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus.
    
17. Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK**. Dieser Ordner befindet sich in der Regel auf dem sekundären Server.
    
18. Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen** und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.
    
19. Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK**, um mit der Konfiguration zu beginnen.
    
20. Wählen Sie aus, und führen Sie der erste Hälfte der Abfrage (siehe Schritt 18) oben in die Zeile:-- \* \* \* \* \* \* End: Skript zum be run at Primary: \* \* \* \* \* \*.
    
    > [!IMPORTANT]
    > Dieses Skript muss manuell ausgeführt ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Protokollversand Konfiguration nicht unterstützt wird. 
  
21. Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert. 
    
22. Manuell ein Failback der primären Datenbank für beständigen Chat auf die primäre. Dies erfolgt mithilfe der Skype für Business Server-Verwaltungsshell, und das Cmdlet " **Invoke-CsDatabaseFailover** ".
    

