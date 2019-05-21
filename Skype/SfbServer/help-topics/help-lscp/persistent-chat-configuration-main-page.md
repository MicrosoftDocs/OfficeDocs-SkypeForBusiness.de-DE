---
title: Konfiguration für beständigen Chat – Hauptseite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: Ihre beständige Chat Server-Bereitstellung kann viele gleichzeitig beständige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und übernimmt die Einstellungen dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zur Identifikation von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
ms.openlocfilehash: de5ce1825a31f37dadbe36e7bcedaa5ec52542dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278433"
---
# <a name="persistent-chat-configuration-main-page"></a>Konfiguration für beständigen Chat – Hauptseite
 
Ihre beständige Chat Server-Bereitstellung kann viele gleichzeitig beständige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und übernimmt die Einstellungen dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zur Identifikation von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
  
> [!NOTE]
> Obwohl viele der Verwaltungsfeatures von Chatrooms auf Computern verfügbar sind, auf denen der Benutzer den beständigen Chat ausführt, müssen beständige chatadministratoren (in der **cspersistentchatadministrator** -Rolle) die Cmdlets "Control Panel" oder "Verwaltungsshell" verwenden. zum Erstellen oder Verwalten von Kategorien.
  
Beständige Chat-Administratoren verwenden die Skype for Business Server-Systemsteuerung oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Kategorien sowie zum Entwerfen des Zugriffs für Chatrooms für die Benutzer in Ihrer Organisation.
  
Beständige Chatroom-Manager, die in der Lage sind, einen oder mehrere Chatrooms zu verwalten, können mithilfe des Clients eine Webanwendung für die Raumverwaltung starten, um Räume zu erstellen und zu verwalten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden sollen). 
  
Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:
  
- Deaktivieren eines Chatrooms
    
- Ändern des Namens eines Chatrooms
    
- Ändern der Beschreibung eines Chatrooms
    
- Ändern des Chatroomtyps („Auditorium“ bzw. „Normal“)
    
- Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)
    
- Hinzufügen oder Entfernen von Mitgliedern
    
- Hinzufügen oder Entfernen von Chatroommanagern
    
- Hinzufügen oder Entfernen eines Add-Ins
    
- Ändern von Einstellungen wie Einladungen (entsprechend den von der Kategorie zulässigen)
    
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Konfigurationsseite für beständigen **Chat** können Sie die folgenden Aufgaben ausführen: Konfigurieren der Server Optionen für beständigen Chats auf globaler Ebene oder für einen bestimmten Pool
  
## <a name="to-configure-persistent-chat-options-globally"></a>So konfigurieren Sie beständige Chat Optionen Global

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **persistent Chat Configuration** auf **neu,** und klicken Sie dann auf **Websitekonfiguration**.
    
    > [!IMPORTANT]
    > Wählen Sie diese Option aus, wenn die Konfiguration auf alle beständigen Chat Server Pools angewendet werden soll, die auf der Website bereitgestellt werden. Klicken Sie auf **Poolkonfiguration** , wenn die Konfiguration auf einen bestimmten beständigen Chat Server Pool angewendet werden soll.
  
5. Wählen Sie unter **Website auswählen**die Website aus, die für die Websitekonfiguration des beständigen Chat Servers konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
   - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
     > [!IMPORTANT]
     > Der beständige Chat Server speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Zahl erhöhen, werden weitere Nachrichten zwischengespeichert. Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie suchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen. 
  
   - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
   - Wählen Sie in der **Teilnehmer Aktualisierungs Grenze**das Limit für Teilnehmer Updates aus. Der beständige Chat Server sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Nutzer diese Nummer erreicht hat. Standardmäßig ist die Nummer 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der beständige Chat Server keine Dienstplan Updates mehr an verbundene Clients sendet, die im Chatroom anwesend sind.
    
   - (Optional) Wählen Sie in der **Raum Verwaltungs-URL**die URL für die Raumverwaltung aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und einfach die Standardeinstellung verwenden, lassen Sie diese Option leer. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
    
     Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den beständigen Chat Server Software Development Kit (SDK) verwenden, ihn an einer beliebigen Stelle hosten und die URL hier platzieren. Diese URL wird an den Client gesendet, sodass ein Benutzer, der versucht, einen Raum anzuzeigen oder zu erstellen, an Ihre benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>So konfigurieren Sie beständige Chat-Optionen für einen bestimmten beständigen Chat-Server Pool

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.
    
5. Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat zugeordnet ist und konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
   - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
     > [!IMPORTANT]
     > Der beständige Chat Server speichert diese Nachrichten im Arbeitsspeicher, wenn Sie also diese Zahl erhöhen, werden weitere Nachrichten zwischengespeichert. Sie können jederzeit auf Verlaufs Inhalte zugreifen, indem Sie suchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die Sie beim Herstellen einer Verbindung mit einem Chatroom anfänglich sehen. 
  
   - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
   - Wählen Sie in der **Teilnehmer Aktualisierungs Grenze**das Limit für Teilnehmer Updates aus. Der beständige Chat Server sendet Dienstplan Informationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Nutzer diese Nummer erreicht hat. Standardmäßig ist die Nummer 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, über die der beständige Chat Server keine Dienstplan Updates mehr an verbundene Clients sendet, die im Chatroom anwesend sind.
    
   - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und einfach die Standardeinstellung verwenden, lassen Sie diese Option leer.
    
     Wenn Sie Ihre Raum Erstellungs Erfahrung anpassen und ihren spezifischen geschäftsworkflow einbeziehen möchten, können Sie eine benutzerdefinierte Raum Verwaltungslösung erstellen, indem Sie den beständigen Chat Server Software Development Kit (SDK) verwenden, ihn an einer beliebigen Stelle hosten und die URL hier platzieren. Diese URL wird an den Client gesendet, damit ein Benutzer, der versucht, einen Raum anzuzeigen/zu erstellen, an Ihre benutzerdefinierte Raum Verwaltungslösung weitergeleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Bereitstellen eines beständigen Chat Servers in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und Verwalten des beständigen [Chat Servers in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

