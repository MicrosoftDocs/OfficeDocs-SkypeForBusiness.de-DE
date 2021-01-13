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
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Zusammenfassung: Erfahren Sie, wie Sie die hohe Verfügbarkeit und Notfallwiederherstellung des Servers für beständigen Chat in Skype for Business Server 2015 verwalten.'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815045"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie die hohe Verfügbarkeit und Notfallwiederherstellung des Servers für beständigen Chat in Skype for Business Server 2015 verwalten.
  
In diesem Thema wird beschrieben, wie Sie ein Failover und ein Fail back für den Server für beständigen Chat erstellen. Lesen Sie vor dem Lesen dieses Themas unbedingt ["Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015",](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) und konfigurieren Sie hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen [Chat in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="fail-over-persistent-chat-server"></a>Failover des Servers für beständigen Chat

Das Failover für den Server für beständigen Chat ist in erster Linie als manueller Prozess konzipiert.
  
Das Failoververfahren basiert auf der Annahme, dass das sekundäre Rechenzentrum ausgeführt wird, aber die Serverdienste für beständigen Chat, in denen sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar, einschließlich der folgenden:
  
- Die primäre Datenbank des Servers für beständigen Chat und die Spiegeldatenbank des Servers für beständigen Chat sind nicht verfügbar.
    
- Der Skype for Business Server-Front-End-Server ist nicht verfügbar.
    
Das Verfahren basiert auf zwei grundlegenden Schritten:
  
- Stellen Sie die primäre Datenbank für den beständigen Chat (mgc) wiederher.
    
- Einrichten der Spiegelung für die neue Primärdatenbank
    
Die Kompatibilitätsdatenbank für beständigen Chat (mgccomp) ist nicht fehlgeschlagen. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Als Administrator für beständigen Chat liegt es in Ihrer Verantwortung, die Adapterausgabe korrekt zu verwalten, um Datenverluste zu vermeiden.
  
So führen Sie ein Failover des Servers für beständigen Chat durch:
  
1. Entfernen Sie den Protokollversand aus der Datenbank für den Protokollversand für den Server für beständigen Chat.
    
   - Stellen SQL Server Management Studio sie eine Verbindung mit der Datenbankinstanz her, in der sich die mgc-Datenbank für die Sicherung des Servers für beständigen Chat befindet.
    
   - Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
   - Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.
    
3. Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Weitere Informationen finden Sie unter [How to: Apply a Transaction Log Backup (Transact-SQL).](https://go.microsoft.com/fwlink/p/?linkid=247428)
    
4. Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
   - Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
    
   - **exec sp_who2,** um Verbindungen mit der mgc-Datenbank zu identifizieren.
    
   - **kill \<spid\>** um diese Verbindungen zu beenden.
    
   - Stellen Sie die Datenbank online bereit:
    
   - **Datenbank mgc mit Wiederherstellung wiederherstellen.**
    
5. Verwenden Sie in der Skype for Business Server-Verwaltungsshell den Befehl **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver,** um ein Failover zur mgc-Sicherungsdatenbank auszuführen. Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch atl-cs-001.litwareinc.com.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.
    
6. Verwenden Sie in der Skype for Business Server-Verwaltungsshell das Cmdlet **"Install-CsMirrorDatabase",** um einen Hochverfügbarkeitsspiegel für die Sicherungsdatenbank herzustellen, die jetzt als primäre Datenbank dient. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde.
    
7. Legen Sie die aktiven Server für den Server für beständigen Chat festgelegt. Verwenden Sie in der Skype for Business Server-Verwaltungsshell das **Cmdlet "Set-CsPersistentChatActiveServer",** um die Liste der aktiven Server festlegen.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich in demselben Datencenter wie die neue Primärdatenbank befinden oder in einem Datencenter, das über eine Datenbankverbindung mit geringer Wartezeit und hoher Bandbreite verfügt. 
  
    An diesem Punkt wird das Failover von der primären Datenbank des Servers für beständigen Chat zur Sicherungsdatenbank des Servers für beständigen Chat erfolgreich abgeschlossen.
    
## <a name="fail-back-persistent-chat-server"></a>Fail back Persistent Chat Server

In diesem Verfahren werden die Schritte erläutert, die zum Wiederherstellen nach einem Ausfall des Servers für beständigen Chat und zum Wiederherstellen von Vorgängen aus dem primären Rechenzentrum erforderlich sind.
  
Während des Ausfalls des Servers für beständigen Chat ist das primäre Rechenzentrum vollständig ausfallen, und die primäre und die Spiegeldatenbank sind nicht mehr verfügbar. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.
  
Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Bei dem Verfahren wird davon ausgegangen, dass das primäre Rechenzentrum nach einem Totalausfall wiederhergestellt wurde und dass die mgc-Datenbank und die mgccomp-Datenbank mithilfe des Topologie-Generators neu erstellt und neu installiert wurden.
  
Außerdem wird davon ausgegangen, dass während des Failoverzeitraums keine neuen Spiegel- und Sicherungsserver bereitgestellt wurden und dass der einzige bereitgestellte Server der Sicherungsserver und sein Spiegelserver sind, wie zuvor in Fail over Persistent Chat Server definiert.
  
Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat, vorlag.
  
1. Löschen Sie alle Server aus der Liste "Aktiver Server für beständigen Chatserver", indem Sie das Cmdlet **"Set-CsPersistentChatActiveServer"** aus der Skype for Business Server-Verwaltungsshell verwenden. Dadurch wird verhindert, dass alle Server für beständigen Chat während eines Failbacks eine Verbindung mit der mgc- und der mgccomp-Datenbank herstellen.
    
    > [!IMPORTANT]
    > Der SQL Server Agent auf dem sekundären Back-End-Server für beständigen Chat sollte unter einem privilegierten Konto ausgeführt werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
  
   - Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen
    
   - Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen
    
2. Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
   - Stellen SQL Server Management Studio sie eine Verbindung mit der mgc-Sicherungsinstanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, und klicken Sie dann auf **Spiegeln**.
    
   - Klicken Sie auf **Spiegelung entfernen**.
    
   - Klicken Sie auf **OK**.
    
   - Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.
    
3. Sichern Sie die mgc-Datenbank, damit Sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
   - Stellen SQL Server Management Studio sie eine Verbindung mit der mgc-Sicherungsinstanz her.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
   - Wählen Sie in **Sicherungstyp** die Option **Vollständig** aus.
    
   - Klicken Sie bei **Sicherungskomponente** auf **Datenbank**.
    
   - Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie eine anderen Namen ein.
    
   -  *\<Optional\>*  Geben **Sie** in "Beschreibung" eine Beschreibung des Sicherungssatz ein.
    
   - Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
   - Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
   - Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.
    
4. Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
   - Stellen SQL Server Management Studio sie eine Verbindung mit der primären mgc-Instanz.
    
   - Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen**, und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
   - Wählen Sie **Von Medium** aus.
    
   - Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.
    
   - Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
   - Klicken Sie auf **Optionen** im Bereich **Seite auswählen**.
    
   - Aktivieren Sie in **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.
    
   - Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.
    
   - Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.
    
5. Konfigurieren SQL Server Protokollversand für die primäre Datenbank. Führen Sie die Verfahren unter "Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen [Chat" in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) aus, um den Protokollversand für die primäre mgc-Datenbank herzustellen.
    
6. Legen Sie die aktiven Server für den Server für beständigen Chat festgelegt. Verwenden Sie in der Skype for Business Server-Verwaltungsshell das **Cmdlet "Set-CsPersistentChatActiveServer",** um die Liste der aktiven Server festlegen.
    
    > [!IMPORTANT]
    > Alle aktiven Server müssen sich in demselben Datencenter wie die neue Primärdatenbank befinden oder in einem Datencenter, das über eine Datenbankverbindung mit geringer Wartezeit und hoher Bandbreite verfügt. 
  
Führen Sie zum Wiederherstellen des Normalenzustands des Pools den folgenden Windows PowerShell aus:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsPersistentChatState".](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)
  

