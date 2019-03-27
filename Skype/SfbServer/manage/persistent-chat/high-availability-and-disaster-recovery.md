---
title: Verwalten der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Persistent Chat Server hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015.'
ms.openlocfilehash: b7c898be275a4a3642eae88412a14686b258130f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897479"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Verwalten von Persistent Chat Server hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015.
  
In diesem Thema wird beschrieben, wie Failover und wieder Persistent Chatserver fehl. Sollten Sie bevor dieses Thema lesen [für hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015 planen](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) und [Konfigurieren hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Lesen Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 
  
## <a name="fail-over-persistent-chat-server"></a>Ausführen eines Failovers Persistent Chat-Server

Failover für Persistent Chat Server soll in erster Linie als manueller Prozess konzipiert.
  
Das Failover-Verfahren basiert auf der Annahme, der im sekundären Rechenzentrum installiert ist und ausgeführt wird, aber die Persistent Chat Server-Dienste, wo sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar ist, einschließlich der folgenden:
  
- Persistent Chat Server-Primärdatenbank und Persistent Chat Server-Spiegeldatenbank sind ausgefallen.
    
- Skype für Business Server-Front-End-Server ist ausgefallen.
    
Das Verfahren basiert auf zwei grundlegenden Schritten:
  
- Wiederherstellen der Persistent Chat-Primärdatenbank (Mgc).
    
- Einrichten der Spiegelung für die neue Primärdatenbank
    
Die beständigen Chat Kompatibilitätsdatenbank (Mgccomp) ist nicht über fehlgeschlagen ist. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Es liegt in Ihrer Verantwortung, als Persistent Chat Administrator richtig verwalten die Ausgabe Adapter um Datenverluste zu vermeiden.
  
Ausführen eines Failovers für den Server für beständigen Chat
  
1. Entfernt den Protokollversand aus der Datenbank Persistent Chat Server-Sicherung für den Protokollversand.
    
   - Verbinden Sie über SQL Server Management Studio mit der Datenbankinstanz, wo sich die Mgc-Sicherungsdatenbank Persistent Chat Server befindet.
    
   - Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
   - Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.
    
3. Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Weitere Informationen hierzu finden Sie unter [Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
   - Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
    
   - Geben Sie **exec sp_who2** ein, um Verbindungen mit der mgc-Datenbank zu identifizieren.
    
   - **kill \<Spid\> ** an diese Verbindungen zu beenden.
    
   - Stellen Sie die Datenbank online bereit:
    
   - **restore database mgc with recovery**.
    
5. In Skype für Business Server-Verwaltungsshell, verwenden Sie den Befehl **"Set-cspersistentchatstate"-Identity "Service: Atl-Cs-001.litwareinc.com" - PoolState FailedOver** Failover auf die Mgc-Sicherungsdatenbank. Achten Sie darauf, den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch „atl-cs-001.litwareinc.com“ zu ersetzen.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.
    
6. Verwenden Sie in Skype für Business Server-Verwaltungsshell das Cmdlet **Install-csmirrordatabase anfügen** , eine hohe Verfügbarkeit Spiegelung für die Sicherungsdatenbank herzustellen, die jetzt als die primäre Datenbank fungiert. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde.
    
7. Legen Sie die aktiven Server für Persistent Chat Server. Verwenden Sie das Cmdlet " **Set-CsPersistentChatActiveServer** " aus der Skype für Business Server-Verwaltungsshell Festlegen der Liste der aktiven Server.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt. 
  
    Zu diesem Zeitpunkt wird das Failover aus der primären Datenbank Persistent Chat Server zu der Persistent Chat Server-Sicherungsdatenbank erfolgreich abgeschlossen.
    
## <a name="fail-back-persistent-chat-server"></a>Fail Persistent Chatserver

In diesem Verfahren wird beschrieben, die Schritte zum Wiederherstellen nach einem Fehler für Persistent Chat Server und Betriebs im primären Rechenzentrum wiederherzustellen.
  
Bei Ausfall der Persistent Chat Server im primären Rechenzentrum sinkt vollständige Ausfall und die primäre und Spiegeldatenbanken nicht mehr verfügbar sind. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.
  
Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Das Verfahren wird davon ausgegangen, dass im primären Rechenzentrum aus insgesamt Ausfall wiederhergestellt wurde und die Mgc-Datenbank und der Mgccomp-Datenbank neu erstellt und mithilfe des Topologie-Generators neu installiert wurden.
  
Des Weiteren wird vorausgesetzt, dass während der Dauer des Ausfalls keine neuen Spiegel- und Sicherungsserver bereitgestellt wurden und dass die einzigen bereitgestellten Server der Sicherungsserver und sein Spiegelserver sind (wie in „Ausführen eines Failovers für den Server für beständigen Chat“ festgelegt).
  
Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall vorlag, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat.
  
1. Deaktivieren Sie alle Server aus der Liste Persistent Chat Server Active Server mit dem Cmdlet **Set-CsPersistentChatActiveServer** aus der Skype für Business Server-Verwaltungsshell. Dadurch werden alle Persistent Chat-Server eine Verbindung zu der Mgc-Datenbank und der Mgccomp-Datenbank während des Failbacks beendet.
    
    > [!IMPORTANT]
    > Der SQL Server-Agent auf die sekundäre sollte unter eines privilegierten Kontos Persistent Chat Server Back-End Server ausgeführt werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
  
   - Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen
    
   - Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen
    
2. Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
   - Mithilfe von SQL Server Management Studio eine Verbindung mit der Mgc-Sicherungsdatenbank-Instanz.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Spiegeln**.
    
   - Klicken Sie auf **Spiegelung entfernen**.
    
   - Klicken Sie anschließend auf **OK**.
    
   - Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.
    
3. Sichern Sie die mgc-Datenbank, damit sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
   - Mithilfe von SQL Server Management Studio eine Verbindung mit der Mgc-Sicherungsdatenbank-Instanz.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
   - Wählen Sie unter **Sicherungstyp** die Option **Vollständig** aus.
    
   - Klicken Sie unter **Sicherungskomponente** auf **Datenbank**.
    
   - Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie einen anderen Namen ein.
    
   -  * \<Optional\> *  Geben Sie im Feld **Beschreibung**eine Beschreibung für den Sicherungssatz ein.
    
   - Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
   - Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
   - Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.
    
4. Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
   - Mithilfe von SQL Server Management Studio, eine Verbindung mit der primären Mgc-Instanz.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen** und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
   - Wählen Sie **Von Medium** aus.
    
   - Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.
    
   - Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
   - Klicken Sie im Bereich **Seite auswählen** auf **Optionen**.
    
   - Aktivieren Sie unter **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.
    
   - Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.
    
   - Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.
    
5. Konfigurieren von SQL Server-Protokollversand für die primäre Datenbank. Führen Sie die Verfahren in [Configure hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) Protokollversand für die primären Mgc-Datenbank herstellen.
    
6. Legen Sie die aktiven Server für Persistent Chat Server. Verwenden Sie das Cmdlet " **Set-CsPersistentChatActiveServer** " aus der Skype für Business Server-Verwaltungsshell Festlegen der Liste der aktiven Server.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt. 
  
Um den Pool, führen Sie den folgenden Windows PowerShell-Befehl Normalzustand wiederherzustellen:
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).
  

