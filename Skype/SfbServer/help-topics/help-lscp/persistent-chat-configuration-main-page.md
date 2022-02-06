---
title: Konfiguration für beständigen Chat – Hauptseite
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: Ihre Bereitstellung des Servers für beständigen Chat kann viele gleichzeitige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
---

# <a name="persistent-chat-configuration-main-page"></a>Konfiguration für beständigen Chat – Hauptseite
 
Ihre Bereitstellung des Servers für beständigen Chat kann viele gleichzeitige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
  
> [!NOTE]
> Obwohl viele der Verwaltungsfunktionen von Chatrooms auf Computern mit beständigem Chat für den Benutzer verfügbar sind, müssen Administratoren für beständigen Chat (in der Rolle **"cspersistentchatadministrator** ") die Systemsteuerung oder Verwaltungsshell-Cmdlets verwenden, um Kategorien zu erstellen oder zu verwalten.
  
Administratoren für beständigen Chat verwenden Skype for Business Server Systemsteuerung oder Windows PowerShell Cmdlets, um Kategorien zu erstellen und zu verwalten und den Zugriff für Chatrooms für die Benutzer in ihrer Organisation zu entwerfen.
  
Manager für beständige Chatrooms, die in der Lage sind, einen oder mehrere Chatrooms zu verwalten, können den Client verwenden, um eine Raumverwaltungswebanwendung zum Erstellen und Verwalten von Chatrooms zu starten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden sollen). 
  
Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:
  
- Deaktivieren eines Chatrooms
    
- Ändern des Namens eines Chatrooms
    
- Ändern der Beschreibung eines Chatrooms
    
- Ändern des Chatroomtyps ("Auditorium" bzw. "Normal")
    
- Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)
    
- Hinzufügen oder Entfernen von Mitgliedern
    
- Hinzufügen oder Entfernen von Chatroommanagern
    
- Hinzufügen oder Entfernen eines Add-Ins
    
- Ändern von Einstellungen wie Einladungen (gemäß den von der Kategorie zulässigen Angaben)
    
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite **"Konfiguration für beständigen Chat** " ausführen: Konfigurieren der Optionen für den Server für beständigen Chat global oder für einen bestimmten Pool
  
## <a name="to-configure-persistent-chat-options-globally"></a>So konfigurieren Sie Optionen für beständigen Chat global

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **"Konfiguration für beständigen Chat** " auf **"Neu** " und dann auf " **Standortkonfiguration**".
    
    > [!IMPORTANT]
    > Wählen Sie diese Option aus, wenn die Konfiguration auf alle Serverpools für beständigen Chat angewendet werden soll, die am Standort bereitgestellt werden. Klicken Sie auf **"Poolkonfiguration** ", wenn die Konfiguration auf einen bestimmten Serverpool für beständigen Chat angewendet werden soll.
  
5. Wählen **Sie in "Standort auswählen**" den Standort aus, der für die Standortkonfiguration des Servers für beständigen Chat konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
   - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
     > [!IMPORTANT]
     > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher zwischen. Wenn Sie diese Anzahl erhöhen, werden also weitere Nachrichten zwischengespeichert. Sie können jederzeit über die Suche auf verlaufshistorische Inhalte zugreifen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die beim Herstellen einer Verbindung mit einem Chatroom angezeigt werden. 
  
   - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
   - Wählen Sie im **Grenzwert für Teilnehmerupdates** das Limit für Teilnehmerupdates aus. Der Server für beständigen Chat sendet Listeninformationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Zahl erreicht. Standardmäßig ist die Zahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der Server für beständigen Chat das Senden von Listenaktualisierungen an verbundene Clients über die Im Raum anwesenden Personen beendet.
    
   - (Optional.) Wählen Sie in der **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und einfach die Standardeinstellung verwenden, lassen Sie diese Option leer. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
    
     Wenn Sie Ihre Raumerstellung anpassen und Ihren spezifischen Geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen, indem Sie das Software Development Kit (SDK) für den Server für beständigen Chat verwenden, es an einer bestimmten Stelle hosten und die URL hier platzieren. Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Raum anzuzeigen oder zu erstellen, zu Ihrer benutzerdefinierten Raumverwaltungslösung weitergeleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>So konfigurieren Sie Optionen für beständigen Chat für einen bestimmten Serverpool für beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.
    
5. Wählen **Sie in "Dienst auswählen**" den Dienst aus, der dem Serverpool für beständigen Chat zugeordnet ist, der konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
   - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
     > [!IMPORTANT]
     > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher zwischen. Wenn Sie diese Anzahl erhöhen, werden also weitere Nachrichten zwischengespeichert. Sie können jederzeit über die Suche auf verlaufshistorische Inhalte zugreifen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die beim Herstellen einer Verbindung mit einem Chatroom angezeigt werden. 
  
   - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
   - Wählen Sie im **Grenzwert für Teilnehmerupdates** das Limit für Teilnehmerupdates aus. Der Server für beständigen Chat sendet Listeninformationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Zahl erreicht. Standardmäßig ist die Zahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der Server für beständigen Chat das Senden von Listenaktualisierungen an verbundene Clients über die Im Raum anwesenden Personen beendet.
    
   - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und einfach die Standardeinstellung verwenden, lassen Sie diese Option leer.
    
     Wenn Sie Ihre Raumerstellung anpassen und Ihren spezifischen Geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen, indem Sie das Software Development Kit (SDK) für den Server für beständigen Chat verwenden, es an einer bestimmten Stelle hosten und die URL hier platzieren. Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Raum anzuzeigen/zu erstellen, zu Ihrer benutzerdefinierten Raumverwaltungslösung weitergeleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

Ausführliche Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

