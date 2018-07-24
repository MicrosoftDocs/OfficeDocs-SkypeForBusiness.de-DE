---
title: Konfiguration für beständigen Chat
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: Die Persistent Chat Server-Bereitstellung kann viele gleichzeitige beständigen Chat Rooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und übernimmt die Einstellungen dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zur Identifikation von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
ms.openlocfilehash: 04e74e9c70b2740f192d16ba6968228c7ac65b33
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986393"
---
# <a name="persistent-chat-configuration"></a>Konfiguration für beständigen Chat
 
Die Persistent Chat Server-Bereitstellung kann viele gleichzeitige beständigen Chat Rooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und übernimmt die Einstellungen dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zur Identifikation von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
  
> [!NOTE]
> Obwohl viele der Verwaltungsfeatures von Chatrooms in Persistent Chat-Computern für den Benutzer verfügbar sind, müssen Persistent Chat-Administratoren (in der Rolle **Cspersistentchatadministrator** ) entweder die Control Panel oder Management-Shell verwenden. Cmdlets zum Erstellen oder Verwalten von Kategorien.
  
Persistent Chat-Administratoren können Skype für Business Server-Systemsteuerung oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Kategorien, und Entwerfen von Benutzerzugriff für Chatrooms für die Benutzer in ihrer Organisation.
  
Beständigen Chatrooms-Manager, die die haben die Möglichkeit, eine oder mehrere Chatrooms zu verwalten, mit dem Client zum Starten einer chatroomverwaltung Web-Anwendung zum Erstellen und Verwalten von Chatrooms (oder Kunden können Erstellen benutzerdefinierter Lösungen und Workflows an, die aufgerufen werden). Beständiger Chat
  
Persistente Chat-Administratoren können auch Systemsteuerung oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Chatrooms.
  
Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:
  
- Deaktivieren eines Chatrooms
    
- Ändern des Namens eines Chatrooms
    
- Ändern der Beschreibung eines Chatrooms
    
- Ändern des Chatroomtyps („Auditorium“ bzw. „Normal“)
    
- Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)
    
- Hinzufügen oder Entfernen von Mitgliedern
    
- Hinzufügen oder Entfernen von Chatroommanagern
    
- Hinzufügen oder Entfernen eines Add-Ins
    
- Ändern der Einstellungen wie Einladungen (gemäß was nach der Kategorie zulässig ist)
    
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben ausführen, auf der Seite **Konfiguration für beständigen Chat** : Konfigurieren von Persistent Chat Server-Optionen global oder für einen bestimmten Pool.
  
## <a name="to-configure-persistent-chat-options-globally"></a>So konfigurieren Sie Optionen für beständigen Chat Global

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **Konfiguration für beständigen Chat** klicken Sie auf **neu,** und klicken Sie dann auf **Standortkonfiguration**.
    
    > [!IMPORTANT]
    > Wählen Sie diese Option, wenn die Konfiguration für alle Persistent Chat Server-Pools in der Website bereitgestellte angewendet werden soll. Klicken Sie auf **Poolkonfiguration** , wenn die Konfiguration auf einem bestimmten Persistent Chat Server Pool angewendet werden soll.
  
5. Wählen Sie im **Dialogfeld Standort auswählen**der Website für die Konfiguration eines Persistent Chat Server konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
  - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
  - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
    > [!IMPORTANT]
    > Persistent Chat Server diese Nachrichten im Arbeitsspeicher zwischengespeichert wird, wenn Sie diese Zahl erhöhen, weitere Nachrichten zwischengespeichert werden. Sie können von der Suche immer zurückliegenden Inhalte zugreifen. Die Standardanzahl einfach bestimmt die maximale Anzahl von Nachrichten, die Sie anfänglich finden Sie unter beim Verbinden mit einem Chatroom. 
  
  - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
  - **Teilnehmer aktualisieren Grenzwert**wählen Sie den Grenzwert für Teilnehmer Updates. Persistent Chat-Server sendet Teilnehmerliste Informationen (, die in einem Chatroom verbunden ist) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Nummer erreicht. Standardmäßig ist die Anzahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum jenseits dessen Persistent Chat Server beendet das Senden von Updates der Teilnehmerliste einer verbundenen Clients zu, die im Raum vorhanden ist.
    
  - (Optional). Wählen Sie in **Raum Management URL**den Chatroom Management-URL ein. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie nicht mehr benötigen zum Verwalten von Chatrooms anpassen, verwenden Sie einfach die Standardeinstellung, lassen Sie diese Option leer. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
    
    Wenn Sie Anpassen Ihrer Erstellung wie im Besprechungsraum und Ihren Workflow bestimmter geschäftlicher einschließen möchten, können Sie eine benutzerdefinierte Raum Management-Lösung mithilfe der Persistent Chat Server Software Development Kit (SDK) erstellen, es irgendwo hosten und die URL hier einfügen. Diese URL wird an den Client gesendet nach unten, wenn ein Benutzer versucht, anzeigen oder einen Chatroom erstellen, kann er an der benutzerdefinierten Raum Management-Lösung gerichtet ist.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>So konfigurieren Sie Optionen für einen bestimmten Persistent Chat Server Pool beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.
    
5. Wählen Sie im, **Wählen Sie einen Dienst**den Dienst zugeordnet Persistent Chat Server Pool konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
  - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
  - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
    > [!IMPORTANT]
    > Persistent Chat Server diese Nachrichten im Arbeitsspeicher zwischengespeichert wird, wenn Sie diese Zahl erhöhen, weitere Nachrichten zwischengespeichert werden. Sie können von der Suche immer zurückliegenden Inhalte zugreifen. Die Standardanzahl einfach bestimmt die maximale Anzahl von Nachrichten, die Sie anfänglich finden Sie unter beim Verbinden mit einem Chatroom. 
  
  - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
  - **Teilnehmer aktualisieren Grenzwert**wählen Sie den Grenzwert für Teilnehmer Updates. Persistent Chat-Server sendet Teilnehmerliste Informationen (, die in einem Chatroom verbunden ist) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Nummer erreicht. Standardmäßig ist die Anzahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum jenseits dessen Persistent Chat Server beendet das Senden von Updates der Teilnehmerliste einer verbundenen Clients zu, die im Raum vorhanden ist.
    
  - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie nicht mehr benötigen zum Verwalten von Chatrooms anpassen, verwenden Sie einfach die Standardeinstellung, lassen Sie diese Option leer.
    
    Wenn Sie Anpassen Ihrer Erstellung wie im Besprechungsraum und Ihren Workflow bestimmter geschäftlicher einschließen möchten, können Sie eine benutzerdefinierte Raum Management-Lösung mithilfe der Persistent Chat Server Software Development Kit (SDK) erstellen, es irgendwo hosten und die URL hier einfügen. Diese URL wird an den Client gesendet nach unten, wenn ein Benutzer versucht, einen Raum anzeigen/erstellen, kann er an der benutzerdefinierten Raum Management-Lösung gerichtet ist.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

Details zu Persistent Chat Server-Features und Funktionen, finden Sie unter [Planen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Persistent Chatserver in Skype für Business Server 2015 bereitstellen](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und [Verwalten Persistent Chat Server in Skype für Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

