---
title: Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihrer Skype for Business Server 2015-Topologie einen Server für beständigen Chat hinzufügen.'
---

# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server 2015-Topologie einen Server für beständigen Chat hinzufügen.
  
Nachdem Sie die erforderliche Software auf jedem Server installiert haben, auf dem Sie den Server für beständigen Chat bereitstellen möchten, verwenden Sie den Topologie-Generator für Folgendes: 
  
- Aktualisieren Der Topologie, um den Server für beständigen Chat einzuschließen
    
- Veröffentlichen der aktualisierten Topologie
    
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aktualisieren Der Topologie, um den Server für beständigen Chat einzuschließen

Führen Sie die folgenden Schritte aus, um einen einzelnen Serverpool für beständigen Chat ohne Notfallwiederherstellungskonfiguration zu installieren. Informationen zum Konfigurieren eines gestreckten Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung finden [Sie unter Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Um mehrere Pools für den Server für beständigen Chat bereitzustellen, wiederholen Sie den gleichen Prozess für jeden Pool.
  
1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber um eine Topologie zu veröffentlichen, die zum Installieren Skype for Business Server erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe **"Domänenadministratoren**" und "**RTCUniversalServerAdmins**" ist.  gruppe, die vollzugriffsberechtigungen (Lesen, Schreiben und Ändern) für den Dateispeicher hat, den Sie für den Dateispeicher des Servers für beständigen Chat verwenden möchten (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein Konto mit entsprechenden Rechten.
  
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Knoten "**Pools für beständigen Chat**", und erweitern Sie ihn, um einen Skype for Business Server Pool auszuwählen, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **"Neuer Pool für beständigen Chat" aus**. Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und angeben, ob es sich bei dem Pool um einen Pool mit einem Server oder um eine Bereitstellung mit mehreren Servern handelt.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie erstere aus, wenn Sie mehr als einen Front-End-Server in Ihrem Serverpool für beständigen Chat verwenden möchten. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen Front-End-Server ein, aus denen der Pool besteht.
    
    > [!IMPORTANT]
    > Wenn die Rolle "Server für beständigen Chat" auf einem Standard Edition Server installiert wird, muss der FQDN mit dem FQDN des Standard Edition Servers übereinstimmen. 
  
4. Definieren Sie einen einfachen **Anzeigenamen** für den Serverpool für beständigen Chat. Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere, wenn mehrere Serverpools für beständigen Chat zur Unterscheidung von Chatrooms vorhanden sind.
    
5. Definieren Sie den Port, der vom Server für beständigen Chat für die Kommunikation mit Skype for Business Server Front-End-Servern verwendet wird. Der Standardport lautet 5041.
    
6. Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**. Wenn sie ausgewählt wird, wird der Serverkompatibilitätsdienst für beständigen Chat auf demselben Computer wie der Front-End-Server des Servers für beständigen Chat installiert. Sie werden aufgefordert, später einen SQL Server Back-End-Server für die Serverkompatibilität für beständigen Chat auszuwählen.
    
7. Zuweisen der Websiteaffinität für den Serverpool für beständigen Chat. Aktivieren Sie das Kontrollkästchen "Diesen **Pool als Standard für Standort \<SiteName\>** verwenden", oder **verwenden Sie diesen Pool als Standard für alle Standorte** , um diesen Pool für den Server für beständigen Chat als Standardpool für den aktuellen Standort oder alle Standorte festzulegen. Wenn der Skype for Business-Client zum Erstellen und Verwalten von Chatrooms verwendet wird, wird der Standardpool, der dem Standort des Benutzers zugeordnet ist, von der Raumerstellungs- und Verwaltungsumgebung verwendet, sodass Raumerstellungs- und Verwaltungsvorgänge an diesen Pool weitergeleitet werden können. Dies gilt nur, wenn Sie mehrere Pools für den Server für beständigen Chat bereitgestellt haben und die Raumerstellungs- und Verwaltungsfeatures des Servers für beständigen Chat verwenden möchten.
    
    > [!IMPORTANT]
    > Sie können die Raumerstellungs- und Verwaltungsfeatures mithilfe des Software Development Kit (SDK) für den Server für beständigen Chat anpassen. 
  
8. Definieren Sie den **SQL Speicher für den Back-End-Server für beständigen Chat (in dem Chatroominhalte gespeichert sind),** indem Sie eine der folgenden Aktionen ausführen:
    
   - Um einen vorhandenen SQL Server Speicher zu verwenden, klicken Sie in der Dropdownliste auf den Namen des SQL Server Speichers, den Sie verwenden möchten.
    
   - Um eine neue SQL Server Datenbank anzugeben, klicken Sie auf **"Neu**", und führen **Sie unter "Neuen SQL Store definieren**" die folgenden Schritte aus:
    
   - Geben Sie in **SQL Server FQDN** den FQDN des SQL Server an, für das Sie die neue SQL Server-Datenbank erstellen möchten.
    
   - Wählen Sie entweder **Standardinstanz**, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.
    
     > [!NOTE]
     > Ausführliche Informationen zum Konfigurieren SQL Server Sicherungsdatenbanken für die Notfallwiederherstellung finden Sie unter [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Definieren Sie den SQL Server Compliancespeicher, wenn Sie "Compliance" aktiviert haben.
    
    > [!IMPORTANT]
    > Ausführliche Informationen zum Konfigurieren SQL Server Spiegelungen für hohe Verfügbarkeit für die Datenbank des Servers für beständigen Chat und die Kompatibilitätsdatenbank für den Server für beständigen Chat finden Sie unter [Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Definieren Sie den Dateispeicher. Ein Dateispeicher ist ein Ordner, in dem eine Kopie einer beliebigen Datei, die in das Dateirepository hochgeladen wurde, gespeichert wird (z. B. speichern von Dateianlagen, die in einem Chatroom veröffentlicht wurden). Bei einer Topologie für den Server für beständigen Chat mit mehreren Servern muss dies ein UNC-Pfad (Universal Naming Convention) sein. und für eine Topologie mit einem serverbasierten Server für beständigen Chat kann dies ein lokaler Dateipfad sein.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
    - Geben Sie im **Dateiserver-FQDN** den FQDN des Computers an, auf dem Sie den neuen Dateispeicher erstellen möchten.
    
    - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    
      > [!IMPORTANT]
      > Sie können den Dateispeicher im Topologie-Generator definieren, bevor Sie den Dateispeicher erstellen. Sie müssen den Dateispeicher jedoch an dem definierten Speicherort erstellen, den Sie definieren, bevor Sie die Topologie veröffentlichen. Wenn der Dateispeicher noch nicht vorhanden ist, schlagen versuche, die Topologie zu veröffentlichen, fehl. 
  
11. Wählen Sie den Front-End-Serverpool aus, der als nächster Hop für diesen Serverpool für beständigen Chat verwendet werden soll. Dies ist der Front-End-Serverpool, der Serveranforderungen für beständigen Chat an diesen Pool weiterleiten kann.
    
12. Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern. Der Pool für den Server für beständigen Chat wird im Topologie-Generator zusammen mit Ihren spezifischen Pooleinstellungen angezeigt.
    
    Informationen zum Veröffentlichen der aktualisierten Topologie, der Sie den Server für beständigen Chat hinzugefügt haben, finden Sie unter Veröffentlichen der aktualisierten Topologie.
    
    > [!NOTE]
    > Nachdem der Topologie-Generator bereits geöffnet ist, können Sie mit Schritt 3 in "Veröffentlichen der aktualisierten Topologie" fortfahren, um mit der Veröffentlichung der aktualisierten Topologie zu beginnen. 
  
## <a name="publish-the-updated-topology"></a>Veröffentlichen der aktualisierten Topologie
<a name="BKMK_PublishTopology"> </a>

Nach dem Aktualisieren der Topologie im Topologie-Generator müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie Skype for Business Server konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.
  
Installieren Sie vor der Veröffentlichung der Topologie die Datenbanken für den Server für beständigen Chat. Verwenden Sie den Topologie-Generator, um Datenbanken zu installieren, indem Sie **"Aktion** " und " **Datenbank installieren"** auswählen.
  
1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der Gruppe "**Domänenadministratoren**" und "**RTCUniversalServerAdmins**" ist.  mit Vollzugriffsberechtigungen (Lesen, Schreiben und Ändern) für den Dateispeicher, der für den Dateispeicher des Servers für beständigen Chat verwendet werden soll (sodass der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) konfigurieren kann) oder ein Konto mit entsprechenden Benutzerrechten.
    
2. Starten Sie den Topologie-Generator. Wählen Sie " **Topologie öffnen" aus einer lokalen Datei aus** , wenn Sie sie lokal gespeichert haben.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server 2015**, und klicken Sie dann auf "**Topologie veröffentlichen**".
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    

