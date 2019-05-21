---
title: Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihrer Skype for Business Server 2015-Topologie einen beständigen Chat Server hinzufügen.'
ms.openlocfilehash: c953b93d8ea20b8878269c8be0540ba8e032ce87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282301"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihrer Skype for Business Server 2015-Topologie einen beständigen Chat Server hinzufügen.
  
Nachdem Sie die erforderliche Software auf jedem Server installiert haben, auf dem Sie den beständigen Chat Server bereitstellen möchten, verwenden Sie den Topologie-Generator für folgende Zwecke: 
  
- Aktualisieren Ihrer Topologie unter Einbeziehung des Servers für beständigen Chat
    
- Veröffentlichen der aktualisierten Topologie
    
> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aktualisieren Ihrer Topologie unter Einbeziehung des Servers für beständigen Chat

Führen Sie die folgenden Schritte aus, um einen einzelnen beständigen Chat Server Pool ohne Disaster Recovery-Konfiguration zu installieren. Informationen zum Konfigurieren eines gestreckten beständigen Chat-Server Pools für die Hochverfügbarkeits-und Disaster Recovery finden Sie unter Konfigurieren von Hochverfügbarkeits [-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Zum Bereitstellen mehrerer beständiger Chat Server-Pools wiederholen Sie diesen Vorgang für jeden Pool.
  
1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die für die Installation von Skype for Business Server erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe " **Domain Admins** " und das ** RTCUniversalServerAdmins** -Gruppe, die über Vollzugriffsberechtigungen (lesen, schreiben und ändern) für den Dateispeicher verfügt, den Sie für den Dateispeicher des beständigen Chat Servers verwenden möchten (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein Konto mit gleichwertige Rechte.
  
2. Starten Sie den Topologie-Generator.
    
3. Navigieren Sie in der Konsolenstruktur zum Knoten **persistente Chat Pools** , erweitern Sie ihn, und wählen Sie einen Skype for Business-Server Pool aus, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **neuer beständiger Chat Pool**aus. Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und angeben, ob es sich bei dem Pool um eine Einzelserver Pool-oder um die Bereitstellung mehrerer Server Pools handelt.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie die erste Option aus, wenn Sie beabsichtigen, mehr als einen Front-End-Server in Ihrem beständigen Chat Serverpool zu haben. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen Front-End-Server ein, aus denen sich der Pool zusammensetzt.
    
    > [!IMPORTANT]
    > Wenn die Serverrolle "beständiger Chat" auf einem Standard Edition-Server installiert wird, muss der FQDN dem FQDN des Standard Edition-Servers entsprechen. 
  
4. Definieren Sie einen einfachen **Anzeige Namen** für den Server Pool des beständigen Chats. Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere dann, wenn mehrere beständige Chat Server Pools vorhanden sind, um Räume zu unterscheiden.
    
5. Definieren Sie den Port, der vom beständigen Chat Server für die Kommunikation mit Skype for Business Server-Front-End-Servern verwendet wird. Der Standardport lautet 5041.
    
6. Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**. Falls ausgewählt, wird der beständige Chat Server-Kompatibilitätsdienst auf demselben Computer wie der Front-End-Server des beständigen Chats installiert. Sie werden aufgefordert, einen SQL Server-Back-End-Server für die beständige Chat Server-Kompatibilität zu einem späteren Zeitpunkt auszuwählen.
    
7. Zuweisen einer Website Affinität für den Server Pool für beständigen Chat Aktivieren Sie das Kontrollkästchen **diesen Pool als Standard \<für\> Website Sitename verwenden** , oder **verwenden Sie diesen Pool als Standard für alle Websites** , um diesen Server Pool für beständigen Chat als Standardpool für die aktuelle Website oder alle Websites festzulegen. Wenn der Skype for Business-Client zum Erstellen und Verwalten von Räumen verwendet wird, wird der Standardpool, der der Website des Benutzers zugeordnet ist, von der raumerstellung und-Verwaltung verwendet, um Raum Erstellungs-und Verwaltungsvorgänge an diesen Pool weiterleiten zu können. Dies gilt nur, wenn Sie mehrere beständige Chat Server Pools bereitgestellt haben und die Funktionen zur raumerstellung und-Verwaltung des beständigen Chat Servers verwenden möchten.
    
    > [!IMPORTANT]
    > Sie können die Funktionen zur raumerstellung und-Verwaltung mithilfe des beständigen Chat-Servers Software Development Kit (SDK) anpassen. 
  
8. Definieren Sie den **SQL Store für den beständigen Chat Server-Back-End (wobei Chatroom-Inhalte gespeichert werden)** , indem Sie eine der folgenden Aktionen ausführen:
    
   - Wenn Sie einen vorhandenen SQL Server-Speicher verwenden möchten, klicken Sie in der Dropdownliste auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
    
   - Wenn Sie eine neue SQL Server-Datenbank angeben möchten, klicken Sie auf **neu**, und führen Sie im **neuen SQL Store definieren**die folgenden Aktionen aus:
    
   - Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie die neue SQL Server-Datenbank erstellen möchten.
    
   - Wählen Sie entweder **Standardinstanz** aus, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.
    
     > [!NOTE]
     > Weitere Informationen zum Konfigurieren von SQL Server-Sicherungsdatenbanken für die Disaster Recovery finden Sie unter Konfigurieren von Hochverfügbarkeits [-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Definieren Sie den SQL Server-Kompatibilitäts Speicher, wenn Sie die Kompatibilität aktiviert haben.
    
    > [!IMPORTANT]
    > Informationen zum Konfigurieren von SQL Server-Spiegelungen für die Hochverfügbarkeits-Datenbank für die persistente Chat Server-Datenbank und die Datenbank für beständigen Chat Server finden Sie unter Konfigurieren von Hochverfügbarkeits [-und Disaster Recovery für beständigen Chat Server in Skype. für Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Definieren Sie den Dateispeicher. Bei einem Dateispeicher handelt es sich um einen Ordner, in dem eine Kopie einer Datei, die in das Datei-Repository hochgeladen wurde, gespeichert wird (beispielsweise das Speichern von Dateianlagen, die in einem Chatroom gepostet wurden). Bei einer persistenten Chat Server Topologie mit mehreren Servern muss es sich um einen UNC-Pfad (Universal Naming Convention) handeln. und bei einer Server Topologie mit einem Server für beständigen Chat kann es sich um einen lokalen Dateipfad handeln.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
    - Geben Sie in **Dateiserver-FQDN** den FQDN des Dateispeichers an, auf dem Sie den neuen Dateispeicher erstellen möchten.
    
    - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    
      > [!IMPORTANT]
      > Sie können den Dateispeicher in Topology Builder definieren, bevor Sie den Dateispeicher erstellen, aber Sie müssen den Dateispeicher am definierten Speicherort erstellen, den Sie definieren, bevor Sie die Topologie veröffentlichen. Wenn der Speicher noch nicht vorhanden ist, schlagen alle Veröffentlichungsversuche für die Topologie fehl. 
  
11. Wählen Sie den Front-End-Serverpool aus, der als nächster Hop für diesen beständigen Chat Serverpool verwendet werden soll. Dies ist der Front-End-Serverpool, der beständige Chat Server Anforderungen an diesen Pool weiterleiten kann.
    
12. Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern. Der Server Pool für beständigen Chat wird im Topologie-Generator mit ihren spezifischen Pooleinstellungen angezeigt.
    
    Informationen zum Veröffentlichen Ihrer aktualisierten Topologie, auf der Sie den beständigen Chat Server hinzugefügt haben, finden Sie unter Veröffentlichen der aktualisierten Topologie.
    
    > [!NOTE]
    > Wenn der Topologie-Generator bereits geöffnet ist, können Sie mit Schritt 3 in veröffentlichen der aktualisierten Topologie fortfahren, um mit der Veröffentlichung ihrer aktualisierten Topologie zu beginnen. 
  
## <a name="publish-the-updated-topology"></a>Veröffentlichen der aktualisierten Topologie
<a name="BKMK_PublishTopology"> </a>

Nachdem Sie Ihre Topologie im Topologie-Generator aktualisiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie Skype for Business Server konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.
  
Bevor Sie Ihre Topologie veröffentlichen, installieren Sie die Datenbanken für beständigen Chat Server. Mithilfe des Topologie-Generators können Sie Datenbanken installieren, indem Sie **Aktion** und **Datenbank installieren**auswählen.
  
1. Melden Sie sich auf einem Computer, auf dem Skype for Business Server ausgeführt wird oder auf dem die Skype for Business Server-Verwaltungstools installiert sind, mit einem Konto an, das ein Mitglied der Gruppe " **Domain Admins** " und der **RTCUniversalServerAdmins** -Gruppe ist. und die über die Berechtigung "Vollzugriff" (lesen, schreiben und ändern) im Dateispeicher für den Dateispeicher für beständigen Chat Server verfügt (damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) oder ein Konto mit einem entsprechenden Benutzer konfigurieren kann. Rechte.
    
2. Starten Sie den Topologie-Generator. Wählen Sie **Topologie aus lokaler Datei öffnen**, wenn das Programm lokal gespeichert ist.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server 2015**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
4. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
5. Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    

