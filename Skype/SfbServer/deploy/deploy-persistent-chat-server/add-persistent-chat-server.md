---
title: Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server 2015-Topologie den Server für beständigen Chat hinzufügen.'
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825105"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server 2015-Topologie den Server für beständigen Chat hinzufügen.
  
Nachdem Sie die erforderliche Software auf jedem Server installiert haben, auf dem Sie den Server für beständigen Chat bereitstellen möchten, verwenden Sie den Topologie-Generator für: 
  
- Aktualisieren der Topologie mit dem Server für beständigen Chat
    
- Veröffentlichen der aktualisierten Topologie
    
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aktualisieren der Topologie mit dem Server für beständigen Chat

Führen Sie die folgenden Schritte aus, um einen einzelnen Pool für den Server für beständigen Chat ohne Notfallwiederherstellungskonfiguration zu installieren. Informationen zum Konfigurieren eines gestreckten Pools für den Server für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung finden Sie unter "Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen [Chat in Skype for Business Server 2015".](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)
  
Wenn Sie mehrere Pools für den Server für beständigen Chat bereitstellen möchten, wiederholen Sie denselben Prozess für jeden Pool.
  
1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    
    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist. Um jedoch eine Topologie zu veröffentlichen, die für die Installation von Skype for Business Server erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe **"Domänen-Admins"** und der Gruppe **"RTCUniversalServerAdmins"** ist und über Vollzugriffsberechtigungen (Lesen, Schreiben und Ändern) für den Dateispeicher verfügt, den Sie für den Dateispeicher für den Server für beständigen Chat verwenden möchten (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein Konto mit entsprechenden Rechten.
  
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der  Konsolenstruktur zum Knoten "Pools für beständigen Chat", und erweitern Sie ihn, um einen Skype for Business Server-Pool auszuwählen, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie "Neuer Pool für beständigen **Chat" aus.** Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und angeben, ob es sich bei dem Pool um einen Pool mit einem oder mehreren Servern um eine Poolbereitstellung mit einem einzelnen Server oder um einen Pool mit mehreren Servern geht.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie die erste Option aus, wenn Sie planen, mehrere Front-End-Server in Ihrem Pool für den Server für beständigen Chat zu verwenden. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen Front-End-Server ein, aus denen der Pool besteht.
    
    > [!IMPORTANT]
    > Wenn die Serverrolle für beständigen Chat auf einem Standard Edition-Server installiert wird, muss der FQDN mit dem FQDN des Standard Edition-Servers übereinstimmen. 
  
4. Definieren Sie einen **einfachen Anzeigenamen** für den Serverpool für beständigen Chat. Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere wenn mehrere Pools für den Server für beständigen Chat vorhanden sind, um Chatrooms zu unterscheiden.
    
5. Definieren Sie den Port, der vom Server für beständigen Chat für die Kommunikation mit Skype for Business Server-Front-End-Servern verwendet wird. Der Standardport lautet 5041.
    
6. Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**. Falls ausgewählt, wird der Kompatibilitätsdienst für den Server für beständigen Chat auf demselben Computer wie der Front-End-Server für beständigen Chat installiert. Sie werden aufgefordert, später einen SQL Server für die Serverkonformität für beständigen Chat auszuwählen.
    
7. Weisen Sie die Standortaffinität für den Serverpool für beständigen Chat zu. Aktivieren **Sie \<SiteName\>** das Kontrollkästchen "Diesen  Pool als Standard für Standort verwenden", oder verwenden Sie diesen Pool als Standard für alle Standorte, um diesen Serverpool für beständigen Chat als Standardpool für den aktuellen Standort oder alle Standorte zu bestimmen. Wenn der Skype for Business-Client zum Erstellen und Verwalten von Chaträumen verwendet wird, wird der Standardpool, der der Website des Benutzers zugeordnet ist, von der Raumerstellungs- und -verwaltungserfahrung verwendet, sodass er die Raumerstellungs- und Verwaltungsvorgänge an diesen Pool weiterverarbeiten kann. Dies gilt nur, wenn Sie mehrere Pools für den Server für beständigen Chat bereitgestellt haben und die Funktionen für die Raumerstellung und -verwaltung des Servers für beständigen Chat verwenden möchten.
    
    > [!IMPORTANT]
    > Sie können die Funktionen für die Raumerstellung und -verwaltung mit dem Software Development Kit (SDK) für den Server für beständigen Chat anpassen. 
  
8. Definieren Sie SQL Speicher für das Back-End des Servers für beständigen Chat (in dem **Chatroominhalte** gespeichert sind), indem Sie einen der folgenden Schritte tun:
    
   - Um einen vorhandenen SQL Server zu verwenden, klicken Sie in der Dropdownliste auf den Namen des SQL Server, den Sie verwenden möchten.
    
   - Wenn Sie eine neue SQL Server angeben möchten, klicken Sie auf **"Neu",** und führen Sie in "Neuen SQL **Store** definieren" die folgenden Schritte aus:
    
   - Geben **SQL Server FQDN** des SQL Server an, auf dem Sie die neue SQL Server erstellen möchten.
    
   - Wählen Sie entweder **Standardinstanz**, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.
    
     > [!NOTE]
     > Weitere Informationen zum Konfigurieren SQL Server Sicherungsdatenbanken für die Notfallwiederherstellung finden Sie unter Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen [Chat in Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
9. Definieren Sie den SQL Server Compliancespeicher, wenn Sie die Compliance aktiviert haben.
    
    > [!IMPORTANT]
    > Weitere Informationen zum Konfigurieren von SQL Server-Spiegelung für hohe Verfügbarkeit für die Datenbank für den Server für beständigen Chat und die Konformitätsdatenbank für den Server für beständigen Chat finden Sie unter "Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen [Chat in Skype for Business Server 2015".](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
10. Definieren Sie den Dateispeicher. Ein Dateispeicher ist ein Ordner, in dem eine Kopie einer in das Dateirepository hochgeladenen Datei gespeichert wird (z. B. speichern von Dateianlagen, die in einem Chatroom bereitgestellt werden). Bei einer Topologie für den Server für beständigen Chat mit mehreren Servern muss es sich um einen #A0 (Universal Naming Convention) gehen. und für eine Topologie mit einem Server für den Server für beständigen Chat kann es sich um einen lokalen Dateipfad befinden.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
    - Geben **Sie im Dateiserver-FQDN** den FQDN des Computers an, auf dem Sie den neuen Dateispeicher erstellen möchten.
    
    - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    
      > [!IMPORTANT]
      > Sie können den Dateispeicher im Topologie-Generator definieren, bevor Sie den Dateispeicher erstellen. Sie müssen den Dateispeicher jedoch an dem von Ihnen definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen. Wenn der Dateispeicher noch nicht vorhanden ist, kann die Topologie nicht veröffentlicht werden. 
  
11. Wählen Sie den Front-End-Serverpool aus, der als nächster Hop für diesen Pool für den Server für beständigen Chat verwendet werden soll. Dies ist der Front-End-Serverpool, der Anforderungen des Servers für beständigen Chat an diesen Pool weiter routen kann.
    
12. Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern. Der Pool für den Server für beständigen Chat wird zusammen mit Ihren spezifischen Pooleinstellungen im Topologie-Generator angezeigt.
    
    Informationen zum Veröffentlichen der aktualisierten Topologie, der Sie den Server für beständigen Chat hinzugefügt haben, finden Sie unter Veröffentlichen der aktualisierten Topologie.
    
    > [!NOTE]
    > Wenn der Topologie-Generator bereits geöffnet ist, können Sie mit Schritt 3 in "Aktualisierte Topologie veröffentlichen" fortfahren, um mit der Veröffentlichung Der aktualisierten Topologie zu beginnen. 
  
## <a name="publish-the-updated-topology"></a>Veröffentlichen der aktualisierten Topologie
<a name="BKMK_PublishTopology"> </a>

Nachdem Sie Ihre Topologie im Topologie-Generator aktualisiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie Skype for Business Server konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.
  
Installieren Sie vor dem Veröffentlichen der Topologie die Datenbanken für den Server für beständigen Chat. Verwenden Sie den Topologie-Generator, um Datenbanken zu installieren, indem **Sie "Aktion"** und **"Datenbank installieren" auswählen.**
  
1. Auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, Melden Sie sich mit einem Konto an, das Mitglied der Gruppe **"Domänen-Admins"** und der Gruppe **"RTCUniversalServerAdmins"** ist und über Vollzugriffsberechtigungen (Lesen, Schreiben und Ändern) für den Dateispeicher verfügt, der für den Dateispeicher für den Server für beständigen Chat verwendet werden soll (damit der Topologie-Generator die erforderlichen discretionary Access Control Lists (DACLs) konfigurieren kann) oder ein Konto mit entsprechenden Benutzerrechten.
    
2. Starten Sie den Topologie-Generator. Wählen **Sie "Topologie öffnen" aus einer lokalen Datei aus,** wenn Sie sie lokal gespeichert haben.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server 2015,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    

