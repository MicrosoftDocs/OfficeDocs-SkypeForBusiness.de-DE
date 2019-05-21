---
title: Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server konfigurieren.'
ms.openlocfilehash: 152797229dc02bfcd1991a9ac6f67370c9154593
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282294"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server konfigurieren.
  
Skype for Business Server unterstützt mehrere Modi mit höherer Verfügbarkeit für Ihre Back-End-Server, einschließlich der Datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden von beständigen Chat Servern nicht unterstützt. 

> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.
  
Stellen Sie sicher, dass Sie mit den Konzepten in [Plan für Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)vertraut sind, bevor Sie die Bereitstellung des beständigen Chats für eine höhere Verfügbarkeit und Disaster Recovery konfigurieren. Die in diesen Themen beschriebene Disaster Recovery-Lösung für beständigen Chat Server basiert auf einem gedehnten beständigen Chat Serverpool. Der Planning-Inhalt beschreibt die Ressourcenanforderungen und die gedehnte Pooltopologie, die eine höhere Verfügbarkeit und Disaster Recovery für beständigen Chat Server ermöglicht, einschließlich der Verwendung der SQL Server-Spiegelung für die höchst Verfügbarkeit und des SQL Server-Protokollversands für Disaster Recovery.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators

Führen Sie mit dem Topologie-Generator die folgenden Schritte aus, um die Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.
  
1. Hinzufügen der Spiegeldatenbanken und der sekundären Datenbank des Protokollversands SQL Server Stores.
    
2. Bearbeiten Sie die Diensteigenschaften des beständigen Chat-Servers wie folgt:
    
    a. Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    b. Fügen Sie den primären Spiegelungs-SQL Server-Speicher hinzu.
    
    c. Aktivieren Sie die SQL Server-Protokollversanddatenbank.
    
    d. Fügen Sie den SQL Server-Protokollversand-sekundären SQL Server-Speicher hinzu.
    
    e. Fügen Sie die SQL Server Store-Spiegelung für die sekundäre Datenbank hinzu.
    
    f. Veröffentlichen Sie die Topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat

Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Protokollversand-Datenbankinstanz des beständigen Chat Servers her, und stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird. Stellen Sie dann eine Verbindung mit der primären Datenbankinstanz des persistenten Chats her, und führen Sie die folgenden Schritte aus
  
1. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.
    
2. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
3. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
4. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
5. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.
    
6. Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (Beispiel: c:\Sicherung)** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben. 
  
7. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
8. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.
    
9. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus und klicken Sie dann auf **OK**.
    
10. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.
    
11. Klicken Sie auf **verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.
    
12. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.
    
13. Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist)**.
    
14. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.
    
15. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
16. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.
    
17. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.
    
18. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.
    
19. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an, und klicken Sie auf **OK**. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
20. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank

Führen Sie die folgenden Schritte aus, damit der Protokollversand fortgesetzt wird, wenn die primäre Datenbank für beständige Chats auf die Spiegeldatenbank übertragen wird.
  
1. Manuelles Failover der primären persistent-Chat-Datenbank auf die Spiegelung. Dies erfolgt über die Skype for Business Server-Verwaltungsshell und das Cmdlet **Invoke-CsDatabaseFailover** .
    
2. Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären persistent Chat Server-Spiegelungs Instanz her.
    
3. Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.
    
4. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.
    
5. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
6. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
7. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
8. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.
    
9. Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben. 
  
10. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
11. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.
    
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
    
20. Wählen Sie die erste Hälfte der Abfrage aus, und führen Sie Sie aus (siehe Schritt 18) bis zur \* \* \* \* \* \* Zeile:--Ende: Skript, das \* \* \* \* \* \*bei primär ausgeführt werden soll:.
    
    > [!IMPORTANT]
    > Das manuelle Ausführen dieses Skripts ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Protokollversandkonfiguration nicht unterstützt. 
  
21. Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert. 
    
22. Manuelles Zurücksetzen der primären beständigen Chat Datenbank auf das primäre. Dies erfolgt über die Skype for Business Server-Verwaltungsshell und das Cmdlet **Invoke-CsDatabaseFailover** .
    

