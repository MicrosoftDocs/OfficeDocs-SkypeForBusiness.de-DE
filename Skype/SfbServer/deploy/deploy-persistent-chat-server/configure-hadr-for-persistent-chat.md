---
title: Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: 8c5a219b803f38c4a2690f0b4ff213cb17446cd7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832879"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.
  
Skype for Business Server unterstützt mehrere Modi mit hoher Verfügbarkeit für Ihre Back-End-Server, einschließlich Datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden bei Servern für beständigen Chat nicht unterstützt. 

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.
  
Bevor Sie ihre Bereitstellung für den beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung konfigurieren, sollten Sie mit den Konzepten in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)vertraut sein. Die in diesen Themen beschriebene Notfallwiederherstellungslösung für den Server für beständigen Chat basiert auf einem gestreckten Serverpool für beständigen Chat. Der Planungsinhalt beschreibt die Ressourcenanforderungen und die Gestreckte Pooltopologie, die hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat ermöglicht, einschließlich der Verwendung SQL Server Spiegelung für hohe Verfügbarkeit und SQL Server Protokollversands für die Notfallwiederherstellung.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Verwenden des Topologie-Generators zum Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung

Führen Sie im Topologie-Generator die folgenden Schritte aus, um hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.
  
1. Fügen Sie die Spiegeldatenbanken und die sekundäre Protokollversanddatenbank SQL Server Speicher hinzu.
    
2. Bearbeiten Sie die Diensteigenschaften des Servers für beständigen Chat wie:
    
    a. Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    b. Fügen Sie den primären Spiegel SQL Server Speicher hinzu.
    
    c. Aktivieren Sie die SQL Server Protokollversanddatenbank.
    
    d. Fügen Sie den sekundären SQL Server Speicher SQL Server Protokollversand hinzu.
    
    e. Fügen Sie den SQL Server Speicherspiegel für die sekundäre Datenbank hinzu.
    
    f. Veröffentlichen Sie die Topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Einrichten SQL Server Protokollversands für die primäre Datenbank des Servers für beständigen Chat

Stellen Sie mit SQL Server Management Studio eine Verbindung mit der sekundären Datenbankinstanz des Servers für beständigen Chat her, und stellen Sie sicher, dass SQL Server Agent ausgeführt wird. Stellen Sie dann eine Verbindung mit der primären Datenbankinstanz für beständigen Chat her, und führen Sie die folgenden Schritte aus:
  
1. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, und klicken Sie auf **Eigenschaften**.
    
2. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
3. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
4. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
5. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.
    
6. Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (z. B. "c:/backup")** ein. (Befindet sich der Sicherungsordner nicht auf dem primären Server, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server Dienstkonto auf Ihrem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie ihren Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben. 
  
7. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
8. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan,** und passen Sie den SQL Server Agent-Zeitplan nach Bedarf an.
    
9. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus, und klicken Sie dann auf **OK**.
    
10. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.
    
11. Klicken Sie auf **Verbinden,** und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.
    
12. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.
    
13. Wählen Sie auf der Registerkarte **"Sekundäre Datenbank initialisieren"** die Option **"Ja", generieren Sie eine vollständige Sicherung der primären Datenbank, und stellen Sie sie in der sekundären Datenbank wieder her (und erstellen Sie die sekundäre Datenbank, wenn sie nicht vorhanden ist).**
    
14. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.
    
15. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan,** und passen Sie den SQL Server Agent-Zeitplan nach Bedarf an. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
16. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.
    
17. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.
    
18. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.
    
19. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **"Zeitplan",** passen Sie den SQL Server Agent-Zeitplan nach Bedarf an, und klicken Sie auf **"OK".** Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
20. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Einrichten SQL Server Protokollversands zwischen der primären Spiegelung und der sekundären Datenbank

Führen Sie die folgenden Schritte aus, damit der Protokollversand fortgesetzt wird, wenn die primäre Datenbank für beständigen Chat nicht zur Spiegeldatenbank übergeht.
  
1. Manuelles Failover der primären Datenbank für beständigen Chat auf die Spiegelung. Dies erfolgt mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets Invoke-CsDatabaseFailover.**
    
2. Stellen Sie mithilfe der SQL Server Management Studio eine Verbindung mit der primären Spiegelinstanz des Servers für beständigen Chat her.
    
3. Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.
    
4. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, und klicken Sie auf **Eigenschaften**.
    
5. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
6. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
7. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
8. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.
    
9. Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server Dienstkonto auf Ihrem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie ihren Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben. 
  
10. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
11. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan,** und passen Sie den Zeitplan des SQL Server Agents nach Bedarf an.
    
    > [!IMPORTANT]
    > Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben. 
  
12. Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus, und klicken Sie auf **OK**.
    
13. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.
    
14. Klicken Sie auf **Verbinden**, und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.
    
15. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.
    
16. Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus. aus.
    
17. Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK**. Dieser Ordner befindet sich i. d. R. auf dem sekundären Server.
    
18. Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen**, und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.
    
19. Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK**, um mit der Konfiguration zu beginnen.
    
20. Wählen Sie die erste Hälfte der Abfrage aus, und führen Sie sie aus (siehe Schritt 18) bis zur Zeile: -- \* \* \* \* \* \* Ende: Skript, das in der primären Ebene ausgeführt werden soll: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > Die manuelle Ausführung dieses Skripts ist erforderlich, da SQL Server Management Studio nicht mehrere primäre Datenbanken in einer SQL Server Log Shipping-Konfiguration unterstützt. 
  
21. Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert.
    
22. Führen Sie ein manuelles Failback der primären Datenbank für beständigen Chat auf die primäre aus. Dies erfolgt mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets Invoke-CsDatabaseFailover.**
    

