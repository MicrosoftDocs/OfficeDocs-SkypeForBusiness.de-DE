---
title: Verwalten der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Zusammenfassung: Erfahren Sie, wie Sie die hohe Verfügbarkeit und Notfallwiederherstellung des Servers für beständigen Chat in Skype for Business Server 2015 verwalten.'
ms.openlocfilehash: 5383a5bc1cb61e4886dcbe2087c6fb319ec4701e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580569"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie die hohe Verfügbarkeit und Notfallwiederherstellung des Servers für beständigen Chat in Skype for Business Server 2015 verwalten.
  
In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat failoveren und zurücksetzen. Lesen Sie vor dem Lesen dieses Themas unbedingt plan [for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="fail-over-persistent-chat-server"></a>Failover des Servers für beständigen Chat

Failover für den Server für beständigen Chat ist in erster Linie ein manueller Prozess.
  
Das Failoververfahren basiert auf der Annahme, dass das sekundäre Rechenzentrum eingerichtet und ausgeführt wird, aber die Serverdienste für beständigen Chat, in denen sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar, einschließlich der folgenden:
  
- Die primäre Datenbank des Servers für beständigen Chat und die Spiegeldatenbank des Servers für beständigen Chat sind ausgefallen.
    
- Skype for Business Server Der Front-End-Server ist ausgefallen.
    
Das Verfahren basiert auf zwei grundlegenden Schritten:
  
- Wiederherstellen der primären Datenbank für beständigen Chat (mgc).
    
- Einrichten der Spiegelung für die neue Primärdatenbank
    
Die Kompatibilitätsdatenbank für beständigen Chat (mgccomp) ist nicht erfolgreich. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Als Administrator für beständigen Chat liegt es in Ihrer Verantwortung, die Adapterausgabe ordnungsgemäß zu verwalten, um Datenverluste zu vermeiden.
  
So führen Sie einen Failover für den Server für beständigen Chat durch:
  
1. Entfernen Sie den Protokollversand aus der Sicherungsprotokollversanddatenbank des Servers für beständigen Chat.
    
   - Stellen Sie mit SQL Server Management Studio eine Verbindung mit der Datenbankinstanz her, in der sich die mgc-Sicherungsdatenbank des Servers für beständigen Chat befindet.
    
   - Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
   - Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.
    
3. Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Ausführliche Informationen finden Sie unter [How to: Apply a Transaction Log Backup (Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).
    
4. Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
   - Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
    
   - **exec sp_who2,** um Verbindungen mit der mgc-Datenbank zu identifizieren.
    
   - **kill \<spid\>** um diese Verbindungen zu beenden.
    
   - Stellen Sie die Datenbank online bereit:
    
   - **Datenbank mgc mit Wiederherstellung wiederherstellen.**
    
5. Verwenden Sie in Skype for Business Server Verwaltungsshell den Befehl **"Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver,** um einen Failover zur mgc-Sicherungsdatenbank auszuführen. Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch atl-cs-001.litwareinc.com ersetzen.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.
    
6. Verwenden Sie in Skype for Business Server Verwaltungsshell das Cmdlet **"Install-CsMirrorDatabase",** um einen Hochverfügbarkeitsspiegel für die Sicherungsdatenbank einzurichten, die jetzt als primäre Datenbank dient. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde.
    
7. Legen Sie die aktiven Server für den Server für beständigen Chat fest. Verwenden Sie in der Skype for Business Server Verwaltungsshell das Cmdlet **"Set-CsPersistentChatActiveServer",** um die Liste der aktiven Server festzulegen.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich in demselben Datencenter wie die neue Primärdatenbank befinden oder in einem Datencenter, das über eine Datenbankverbindung mit geringer Wartezeit und hoher Bandbreite verfügt. 
  
    An diesem Punkt wird das Failover von der primären Datenbank des Servers für beständigen Chat auf die Sicherungsdatenbank des Servers für beständigen Chat erfolgreich abgeschlossen.
    
## <a name="fail-back-persistent-chat-server"></a>Failback für den Server für beständigen Chat

In diesem Verfahren werden die Schritte beschrieben, die erforderlich sind, um nach einem Serverfehler für beständigen Chat wiederherzustellen und Vorgänge aus dem primären Rechenzentrum wiederherzustellen.
  
Während des Ausfalls des Servers für beständigen Chat tritt im primären Rechenzentrum ein vollständiger Ausfall auf, und die Primären- und Spiegeldatenbanken sind nicht mehr verfügbar. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.
  
Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Bei dem Verfahren wird davon ausgegangen, dass das primäre Rechenzentrum nach dem totalen Ausfall wiederhergestellt wurde und dass die mgc-Datenbank und die mgccomp-Datenbank mithilfe des Topologie-Generators neu erstellt und neu installiert wurden.
  
Außerdem wird davon ausgegangen, dass während des Failoverzeitraums keine neuen Spiegel- und Sicherungsserver bereitgestellt wurden und dass der einzige bereitgestellte Server der Sicherungsserver und dessen Spiegelserver ist, wie zuvor unter "Failover über den Server für beständigen Chat" definiert.
  
Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat, vorlag.
  
1. Löschen Sie alle Server aus der Active Server-Liste für den Server für beständigen Chat mithilfe des Cmdlets **"Set-CsPersistentChatActiveServer"** aus der Skype for Business Server Verwaltungsshell. Dadurch wird verhindert, dass alle Server für beständigen Chat während des Failbacks eine Verbindung mit der mgc-Datenbank und der mgccomp-Datenbank herstellen.
    
    > [!IMPORTANT]
    > Der SQL Server-Agent auf dem sekundären Back-End-Server für beständigen Chat sollte unter einem privilegierten Konto ausgeführt werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
  
   - Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen
    
   - Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen
    
2. Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
   - Stellen Sie mit SQL Server Management Studio eine Verbindung mit der mgc-Sicherungsinstanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, und klicken Sie dann auf **Spiegeln**.
    
   - Klicken Sie auf **Spiegelung entfernen**.
    
   - Klicken Sie auf **OK**.
    
   - Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.
    
3. Sichern Sie die mgc-Datenbank, damit Sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
   - Stellen Sie mit SQL Server Management Studio eine Verbindung mit der mgc-Sicherungsinstanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
   - Wählen Sie in **Sicherungstyp** die Option **Vollständig** aus.
    
   - Klicken Sie bei **Sicherungskomponente** auf **Datenbank**.
    
   - Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie eine anderen Namen ein.
    
   -  *\<Optional\>* Geben Sie in Beschreibung eine Beschreibung des Sicherungssatzes ein.
    
   - Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
   - Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
   - Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.
    
4. Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
   - Stellen Sie mit SQL Server Management Studio eine Verbindung mit der primären mgc-Instanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen**, und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
   - Wählen Sie **Von Medium** aus.
    
   - Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.
    
   - Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
   - Klicken Sie auf **Optionen** im Bereich **Seite auswählen**.
    
   - Aktivieren Sie in **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.
    
   - Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.
    
   - Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.
    
5. Konfigurieren Sie SQL Server Protokollversand für die primäre Datenbank. Befolgen Sie die Verfahren unter [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015,](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) um den Protokollversand für die primäre mgc-Datenbank einzurichten.
    
6. Legen Sie die aktiven Server für den Server für beständigen Chat fest. Verwenden Sie in der Skype for Business Server Verwaltungsshell das Cmdlet **"Set-CsPersistentChatActiveServer",** um die Liste der aktiven Server festzulegen.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich in demselben Datencenter wie die neue Primärdatenbank befinden oder in einem Datencenter, das über eine Datenbankverbindung mit geringer Wartezeit und hoher Bandbreite verfügt. 
  
Führen Sie den folgenden befehl Windows PowerShell aus, um den Pool in seinen normalen Zustand wiederherzustellen:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Set-CsPersistentChatState".](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)
