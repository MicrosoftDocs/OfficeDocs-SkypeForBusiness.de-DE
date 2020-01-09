---
title: Verwalten der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server verwalten.'
ms.openlocfilehash: d46e34485f231d313475b4fdc5948a7262b324ed
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991980"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server verwalten.
  
In diesem Thema wird beschrieben, wie ein Failover und ein Failback des beständigen Chat Servers ausgeführt werden. Bevor Sie dieses Thema lesen, stellen Sie sicher, dass Sie [Plan für Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) lesen und die Funktion " [höhere Verfügbarkeit und Disaster Recovery für beständigen Chat Server" in Skype for Business Server 2015 konfigurieren](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
  
## <a name="fail-over-persistent-chat-server"></a>Failover für beständigen Chat Server

Das Failover für beständigen Chat Server ist hauptsächlich ein manueller Prozess.
  
Das Failover-Verfahren basiert auf der Annahme, dass das sekundäre Rechenzentrum in Betrieb ist, aber die Server Dienste für beständigen Chat, bei denen sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar, einschließlich der folgenden:
  
- Die primäre Datenbank des beständigen Chat Servers und die Spiegeldatenbank des beständigen Chat Servers sind nicht mehr vorhanden.
    
- Der Skype for Business Server-Front-End-Server ist ausgefallen.
    
Das Verfahren basiert auf zwei grundlegenden Schritten:
  
- Wiederherstellen der primären persistent Chat-Datenbank (MGC)
    
- Einrichten der Spiegelung für die neue Primärdatenbank
    
Die beständige Chat-Kompatibilitätsdatenbank (mgccomp) ist nicht fehlerhaft. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Es liegt in ihrer Verantwortung als Administrator des beständigen Chats, die Adapter Ausgabe ordnungsgemäß zu verwalten, um Datenverluste zu vermeiden.
  
Ausführen eines Failovers für den Server für beständigen Chat
  
1. Entfernen Sie den Protokollversand aus der Datenbank des beständigen Chat Server-Sicherungs Protokolls.
    
   - Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Datenbankinstanz her, in der sich die Datenbank des beständigen Chat Server-Backup MGC befindet.
    
   - Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
   - Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.
    
3. Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Ausführliche Informationen finden Sie unter [Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
   - Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
    
   - Geben Sie **exec sp_who2** ein, um Verbindungen mit der mgc-Datenbank zu identifizieren.
    
   - **Kill \<SPID\> ** , um diese Verbindungen zu beenden.
    
   - Stellen Sie die Datenbank online bereit:
    
   - **restore database mgc with recovery**.
    
5. Verwenden Sie in der Skype for Business Server-Verwaltungsshell die Befehls **Satz-CsPersistentChatState-Identity "Service: ATL-CS-001.litwareinc.com"-PoolState FailedOver** , um ein Failover zur MGC-Sicherungsdatenbank durchführen zu können. Achten Sie darauf, den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch „atl-cs-001.litwareinc.com“ zu ersetzen.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.
    
6. Verwenden Sie in der Skype for Business Server-Verwaltungsshell das Cmdlet **install-CsMirrorDatabase** , um einen Hochverfügbarkeits-Spiegel für die Sicherungsdatenbank einzurichten, die jetzt als primäre Datenbank fungiert. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde.
    
7. Setzen Sie die aktiven Server für den beständigen Chat Server. Verwenden Sie in der Skype for Business Server-Verwaltungsshell das Cmdlet " **Satz-CsPersistentChatActiveServer** ", um die Liste der aktiven Server einzurichten.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt. 
  
    An diesem Punkt wird das Failover von der primären Datenbank des beständigen Chat Servers zur Datenbank des beständigen Chat Servers erfolgreich abgeschlossen.
    
## <a name="fail-back-persistent-chat-server"></a>Zurücksetzen des beständigen Chat Servers

In diesem Verfahren werden die erforderlichen Schritte zum Wiederherstellen nach einem Server Fehler des beständigen Chats und zum Wiederherstellen von Vorgängen aus dem primären Rechenzentrum erläutert.
  
Beim Server Ausfall des beständigen Chats leidet das primäre Rechenzentrum unter einem vollständigen Ausfall, und die primäre und die Spiegeldatenbank werden nicht mehr zur Verfügung gestellt. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.
  
Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Bei diesem Verfahren wird davon ausgegangen, dass das primäre Rechenzentrum vom Totalausfall wiederhergestellt wurde und dass die MGC-Datenbank und die mgccomp-Datenbank mithilfe des Topologie-Generators neu erstellt und neu installiert wurden.
  
Des Weiteren wird vorausgesetzt, dass während der Dauer des Ausfalls keine neuen Spiegel- und Sicherungsserver bereitgestellt wurden und dass die einzigen bereitgestellten Server der Sicherungsserver und sein Spiegelserver sind (wie in „Ausführen eines Failovers für den Server für beständigen Chat“ festgelegt).
  
Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall vorlag, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat.
  
1. Löschen Sie alle Server aus der Active Server-Liste des beständigen Chat Servers mithilfe des Cmdlets " **Satz-CsPersistentChatActiveServer** " aus der Skype for Business Server-Verwaltungsshell. Dadurch wird verhindert, dass alle beständigen Chat Server während des Failback eine Verbindung mit der MGC-Datenbank und der mgccomp-Datenbank herstellen.
    
    > [!IMPORTANT]
    > Der SQL Server-Agent auf dem Back-End-Server des sekundären beständigen Chat Servers sollte unter einem privilegierten Konto ausgeführt werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
  
   - Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen
    
   - Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen
    
2. Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
   - Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Sicherungs MGC-Instanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Spiegeln**.
    
   - Klicken Sie auf **Spiegelung entfernen**.
    
   - Klicken Sie anschließend auf **OK**.
    
   - Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.
    
3. Sichern Sie die mgc-Datenbank, damit sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
   - Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Sicherungs MGC-Instanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
   - Wählen Sie unter **Sicherungstyp** die Option **Vollständig** aus.
    
   - Klicken Sie unter **Sicherungskomponente** auf **Datenbank**.
    
   - Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie einen anderen Namen ein.
    
   -  * \<Optional\> *  Geben Sie im Feld **Beschreibung**eine Beschreibung für den Sicherungssatz ein.
    
   - Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
   - Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
   - Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.
    
4. Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
   - Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären MGC-Instanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen** und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
   - Wählen Sie **Von Medium** aus.
    
   - Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.
    
   - Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
   - Klicken Sie im Bereich **Seite auswählen** auf **Optionen**.
    
   - Aktivieren Sie unter **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.
    
   - Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.
    
   - Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.
    
5. Konfigurieren Sie den SQL Server-Protokollversand für die primäre Datenbank. Führen Sie die Vorgehensweisen unter [Konfigurieren von Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) aus, um den Protokollversand für die primäre MGC-Datenbank festzulegen.
    
6. Setzen Sie die aktiven Server für den beständigen Chat Server. Verwenden Sie in der Skype for Business Server-Verwaltungsshell das Cmdlet " **Satz-CsPersistentChatActiveServer** ", um die Liste der aktiven Server einzurichten.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt. 
  
Führen Sie den folgenden Windows PowerShell-Befehl aus, um den Pool auf seinen normalen Zustand zurückzusetzen:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).
  

