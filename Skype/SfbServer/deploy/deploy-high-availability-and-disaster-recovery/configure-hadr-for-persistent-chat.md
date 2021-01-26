---
title: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830625"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.
  
Skype for Business Server unterstützt mehrere Modi der hohen Verfügbarkeit für Ihre Back-End-Server, einschließlich Datenbankspiegelung. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden von Servern für beständigen Chat nicht unterstützt. 
  
Bevor Sie Ihre Bereitstellung für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung konfigurieren, sollten Sie mit den Konzepten in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)vertraut sein. Die in diesen Themen beschriebene Notfallwiederherstellungslösung für den Server für beständigen Chat baut auf einem gestreckten Serverpool für beständigen Chat auf. In den Planungsinhalten werden ressourcenanforderungen und die Topologie mit gestrecktem Pool beschrieben, die hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat ermöglicht, einschließlich der Verwendung der SQL Server-Spiegelung für hohe Verfügbarkeit und SQL Server Protokollversand für die Notfallwiederherstellung.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Verwenden des Topologie-Generators zum Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung

Führen Sie im Topologie-Generator die folgenden Schritte aus, um hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.
  
1. Fügen Sie die Spiegeldatenbanken und die sekundäre Datenbank für den Protokollversand hinzu, SQL Server speichern.
    
2. Bearbeiten Sie die Eigenschaften des Diensts für den Server für beständigen Chat zu:
    
    a. Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    b. Fügen Sie den primären Spiegelspeicher SQL Server hinzu.
    
    c. Aktivieren Sie die SQL Server Protokollversanddatenbank.
    
    d. Fügen Sie den sekundären SQL Server protokollversand SQL Server hinzu.
    
    e. Fügen Sie SQL Server Speicherspiegel für die sekundäre Datenbank hinzu.
    
    f. Veröffentlichen Sie die Topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Einrichten SQL Server Protokollversands für die primäre Datenbank des Servers für beständigen Chat

Stellen SQL Server Management Studio sie eine Verbindung mit der sekundären Protokollversanddatenbankinstanz des Servers für beständigen Chat sicher, und stellen Sie sicher, dass SQL Server Agent ausgeführt wird. Stellen Sie dann eine Verbindung mit der primären Datenbankinstanz des beständigen Chats herzustellen, und führen Sie die folgenden Schritte aus:
  
1. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, und klicken Sie auf **Eigenschaften**.
    
2. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
3. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
4. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
5. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.
    
6. Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (z. B. "c:/backup")** ein. (Befindet sich der Sicherungsordner nicht auf dem primären Server, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server Auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben. 
  
7. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
8. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Klicken Sie auf "Zeitplan", und passen Sie den Zeitplan SQL Server Agent nach Bedarf an, um den Zeitplan für Ihre Installation anzupassen. 
    
9. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus, und klicken Sie dann auf **OK**.
    
10. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.
    
11. Klicken **Sie auf** "Verbinden", und stellen Sie eine Verbindung mit der Instanz SQL Server, die Sie als sekundären Server konfiguriert haben.
    
12. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.
    
13. Wählen Sie **auf** der Registerkarte "Sekundäre Datenbank initialisieren" die Option "Ja", generieren Sie eine vollständige Sicherung der primären Datenbank, und stellen Sie sie in der sekundären Datenbank wieder her (und erstellen Sie die sekundäre Datenbank, falls sie nicht vorhanden **ist).**
    
14. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.
    
15. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Klicken Sie auf "Zeitplan", und passen Sie den Zeitplan SQL Server Agent nach Bedarf an, um den Zeitplan für Ihre Installation anzupassen.  Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
16. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.
    
17. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.
    
18. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.
    
19. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf "Zeitplan", passen Sie den SQL Server -Agent-Zeitplan nach Bedarf an, und klicken Sie auf **"OK".** Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.
    
20. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Einrichten SQL Server Protokollversands zwischen dem primären Spiegel und der sekundären Datenbank

Führen Sie die folgenden Schritte aus, damit der Protokollversand fortgesetzt wird, wenn für die primäre Datenbank für den beständigen Chat ein Fehler bei der Spiegeldatenbank auftritt.
  
1. Führen Sie manuell ein Failover der primären Datenbank für den beständigen Chat auf den Spiegel durch. Dies erfolgt mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets "Invoke-CsDatabaseFailover".**
    
2. Stellen Sie mithilfe SQL Server Management Studio A0 eine Verbindung mit der primären Spiegelinstanz des Servers für beständigen Chat herzustellen.
    
3. Stellen Sie sicher, dass SQL Server Agent ausgeführt wird.
    
4. Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, und klicken Sie auf **Eigenschaften**.
    
5. Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.
    
6. Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.
    
7. Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.
    
8. Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.
    
9. Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    > [!IMPORTANT]
    > Wenn das SQL Server Auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben. 
  
10. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.
    
11. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Um den Zeitplan für Ihre Installation anzupassen, klicken Sie auf "Zeitplan", und passen Sie den Zeitplan SQL Server Agent nach Bedarf an.
    
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
    
20. Wählen Sie die erste Hälfte der Abfrage (siehe Schritt 18) bis zur Zeile aus, und führen Sie sie aus: -- End: Skript, das bei Primär \* \* \* \* \* \* ausgeführt werden soll: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > Die manuelle Ausführung dieses Skripts ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer Konfiguration SQL Server Protokollversand nicht unterstützt. 
  
21. Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert.
    
22. Führen Sie manuell ein Fail back the primary Persistent Chat database to the primary. Dies erfolgt mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets "Invoke-CsDatabaseFailover".**
    

