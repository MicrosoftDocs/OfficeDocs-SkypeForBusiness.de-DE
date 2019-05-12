---
title: Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Ihre Skype für Business Server 2015 Topologie Persistent Chat Server hinzufügen.'
ms.openlocfilehash: edd04ce781c3f91190b2c7baf9e0575f6dba5b1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894500"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie Ihre Skype für Business Server 2015 Topologie Persistent Chat Server hinzufügen.
  
Nachdem Sie die erforderliche Software auf jedem Server installieren, auf denen Sie Persistent Chat Server bereitstellen möchten, verwenden Sie zum Topologie-Generator: 
  
- Aktualisieren Ihrer Topologie unter Einbeziehung des Servers für beständigen Chat
    
- Veröffentlichen der aktualisierten Topologie
    
> [!NOTE] 
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aktualisieren Ihrer Topologie unter Einbeziehung des Servers für beständigen Chat

Führen Sie die folgenden Schritte aus, für die Installation von einem einzelnen Persistent Chat Server Pool ohne Disaster Recovery-Konfiguration. Konfigurieren eines ausgedehnten Persistent Chat Server Pools für hohe Verfügbarkeit und notfallwiederherstellung, finden Sie unter [Configure hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Wiederholen Sie für die Bereitstellung mehrerer Persistent Chat Server-Pools das gleiche Verfahren für jeden Pool.
  
1. Auf einem Computer, der Skype für Business Server ausgeführt wird, oder auf dem die Skype für Business Server-Verwaltungstools installiert sind, melden Sie sich mit einem Konto, das Mitglied der lokalen Benutzergruppe (oder ein Konto mit gleichwertigen Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie mit einem Konto, das Mitglied der lokalen Benutzergruppe ist definieren, aber um eine Topologie veröffentlichen, die zur Installation von Skype für Business Server erforderlich ist, müssen Sie ein Konto, das Mitglied der Gruppe **Domänen-Admins** und der **ist verwenden RTCUniversalServerAdmins** Gruppe und, verfügt über Vollzugriff-Berechtigungen (Lesen, schreiben und ändern) auf den Dateispeicher, die Sie beabsichtigen, verwenden Sie für die Persistent Chat Server Dateispeicher (damit diese Topologie-Generator die erforderlichen freigegebenen Zugriffssteuerungslisten konfiguriert werden kann), oder ein Konto mit entsprechende Rechte.
  
2. Starten Sie Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Knoten **Persistent Chat-Pools** , und erweitern Sie, um einen Skype für Business Server-Pool wählen oder mit der rechten Maustaste in des Knotens, und wählen **Neuer Pool für beständigen Chat**. Sie müssen vollqualifizierten Domänennamen (FQDN) des Pools definieren und geben Sie an, ob der Pool einen Pool mit einem einzelnen Server oder mit mehreren Servern poolbereitstellung sein soll.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie die erste, wenn Sie beabsichtigen, mehrere Front-End-Server im Pool Persistent Chat Server verfügen. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen Front-End-Server, die den Pool umfassen.
    
    > [!IMPORTANT]
    > Wenn die Persistent Chat Server-Rolle auf einem Standard Edition-Server installiert wird, muss der FQDN den FQDN des Standard Edition-Servers entsprechen. 
  
4. Definieren Sie einen einfachen **Anzeigenamen** für den Pool Persistent Chat Server. Der Anzeigename kann durch benutzerdefinierte Clients verwendet werden, insbesondere, wenn es sind mehrere Persistent Chat Server-Pools Chatrooms unterscheiden.
    
5. Definieren Sie den Port von Persistent Chat-Server verwendet, um die Kommunikation mit Skype für Business Server Front-End-Server. Der Standardport lautet 5041.
    
6. Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**. Wenn ausgewählt, wird der Persistent Chat Server Compliance-Dienst auf demselben Computer wie der Persistent Chat Server-Front-End-Server installiert. Sie werden aufgefordert, eine SQL Server Back End-Server für die Einhaltung der Persistent Chat Server später auswählen.
    
7. Affinität für Persistent Chat Server Pool zuweisen. Wählen Sie die **Verwenden Sie diesen Pool als Standard für Website \<SiteName\> ** das Kontrollkästchen oder **diesem Pool als Standard für alle Websites verwenden** , um diese Persistent Chat Server Pool als Standard-Pools für die aktuelle Website oder alle Websites festzulegen. Wenn die Skype für Business-Client zum Erstellen und Verwalten von Chatrooms verwendet wird, wird der Standard-Pool des Benutzers Website zugeordnet durch die Erstellung und Verwaltung von wie im Besprechungsraum verwendet, sodass Raum und-Verwaltung Vorgänge an diesen Pool geleitet werden kann. Dies gilt nur, wenn Sie mehrere Persistent Chat Server-Pools bereitgestellt haben und den Chatroom erstellen und Verwalten von Features von Persistent Chat Server verwenden möchten.
    
    > [!IMPORTANT]
    > Sie können den Chatroom erstellen und Verwalten von Features mithilfe der Persistent Chat Server Software Development Kit (SDK) anpassen. 
  
8. Definieren Sie die **SQL-Speicher für die Persistent Chat Server Back-End (, auf dem Inhalt des Chatrooms gespeichert ist)** , indem Sie einen der folgenden Schritte ausführen:
    
   - Klicken Sie zum Verwenden eines vorhandenen SQL Server-Speichers in der Dropdown-Liste auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
   - Um eine neue SQL Server-Datenbank anzugeben, klicken Sie auf **neu**, und führen Sie im **Neuen SQL-Speicher definieren**, Folgendes:
    
   - Geben Sie in **SQL Server-FQDN**: den FQDN des SQL-Servers, auf dem Sie die neue SQL Server-Datenbank erstellen möchten.
    
   - Wählen Sie entweder **Standardinstanz** aus, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.
    
     > [!NOTE]
     > Ausführliche Informationen zum Konfigurieren von SQL Server-Sicherung Datenbanken für die Wiederherstellung finden Sie unter [Configure hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Definieren Sie SQL Server-Speichers Compliance, wenn Kompatibilität aktiviert.
    
    > [!IMPORTANT]
    > Ausführliche Informationen zum Konfigurieren von SQL Server-Spiegelung für hohe Verfügbarkeit für die Persistent Chat Server-Datenbank und die Kompatibilitätsdatenbank Persistent Chat Server finden Sie unter [Konfigurieren hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Definieren des Dateispeichers an. Dateispeicher ist ein Ordner, in dem eine Kopie aller im dateirepository hochgeladen (beispielsweise das Speichern von Anlagen in einem Chatroom veröffentlicht) gespeichert ist. Im Fall einer Topologie mit mehreren Servern Persistent Chat Server muss dies einen Pfad (UNC = Universal Naming Convention) sein. und für eine Topologie mit einem einzelnen Server Persistent Chat Server, können sie einen lokalen Pfad sein.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
    - Geben Sie in **Dateiserver-FQDN** den FQDN des Dateispeichers an, auf dem Sie den neuen Dateispeicher erstellen möchten.
    
    - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    
      > [!IMPORTANT]
      > Sie können im Topologie-Generator den Dateispeicher definieren, bevor Sie den Dateispeicher erstellen, aber Sie den Dateispeicher, in der definierten Position, den, die Sie definieren erstellen müssen, bevor Sie die Topologie zu veröffentlichen. Wenn der Speicher noch nicht vorhanden ist, schlagen alle Veröffentlichungsversuche für die Topologie fehl. 
  
11. Wählen Sie den Front-End-Server-Pool als nächsten Hop für Persistent Chat Server Pool verwendet werden. Dies ist der Front-End-Server-Pool, die zur Weiterleitung von Anforderungen Persistent Chat Server in diesem Pool können.
    
12. Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern. Persistent Chat Server Pool wird im Topologie-Generator begleitet durch die Einstellungen der bestimmten Pool angezeigt.
    
    Zum Veröffentlichen Ihrer aktualisierten Topologie, die Sie Persistent Chat Server hinzugefügt haben, finden Sie unter Veröffentlichen der aktualisierten Topologie.
    
    > [!NOTE]
    > Durch Topology Builder bereits geöffnet ist können Sie mit Schritt 3 unter veröffentlichen die aktualisierte Topologie zum Veröffentlichen Ihrer aktualisierten Topologie fortfahren. 
  
## <a name="publish-the-updated-topology"></a>Veröffentlichen der aktualisierten Topologie
<a name="BKMK_PublishTopology"> </a>

Nach dem Aktualisieren der Topologie im Topologie-Generator, müssen Sie den zentralen Verwaltungsspeicher die Topologie veröffentlichen, bevor Sie konfigurieren und Skype für Business Server verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.
  
Bevor Sie Ihre Topologie veröffentlichen, installieren Sie die Datenbanken für Persistent Chat Server. Verwenden Sie Topologie-Generator, um Datenbanken zu installieren, indem Sie die **Aktion** "und" **Datenbank installieren**auswählen.
  
1. Auf einem Computer, der Skype für Business Server ausgeführt wird, oder auf dem die Skype für Business Server-Verwaltungstools installiert sind, melden Sie sich mit einem Konto, das Mitglied der Gruppe **Domänen-Admins** und **RTCUniversalServerAdmins** ist, und verfügt über Vollzugriff-Berechtigungen (Lesen, schreiben und ändern), die auf den Dateispeicher für die Persistent Chat Server Dateispeicher (damit diese Topologie-Generator die erforderlichen discretionary Access Control Lists (DACL) konfiguriert werden kann), verwendet werden, oder ein Konto mit gleichwertigen Verwaltung von Informationsrechten.
    
2. Starten Sie Topologie-Generator. Wählen Sie **Topologie aus lokaler Datei öffnen**, wenn das Programm lokal gespeichert ist.
    
3. In der Konsolenstruktur mit der rechten Maustaste **Skype für Business Server 2015**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    

