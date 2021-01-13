---
title: Konfiguration für beständigen Chat – Hauptseite
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: Die Bereitstellung des Servers für beständigen Chat kann viele gleichzeitige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
ms.openlocfilehash: eb444869c036396ee490b38ea1b0bcd149cf29c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822065"
---
# <a name="persistent-chat-configuration-main-page"></a>Konfiguration für beständigen Chat – Hauptseite
 
Die Bereitstellung des Servers für beständigen Chat kann viele gleichzeitige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.
  
> [!NOTE]
> Obwohl viele verwaltungsfeatures von Chatrooms auf Computern verfügbar sind, auf denen der beständigen Chat für den Benutzer ausgeführt wird, müssen Administratoren für beständigen Chat (in der Rolle **"cspersistentchatadministrator")** die Systemsteuerung oder die Verwaltungsshell-Cmdlets verwenden, um Kategorien zu erstellen oder zu verwalten.
  
Administratoren für beständigen Chat verwenden die Skype for Business Server-Systemsteuerung oder Windows PowerShell-Cmdlets, um Kategorien zu erstellen und zu verwalten und den Zugriff für Chatrooms für die Benutzer in ihrer Organisation zu entwerfen.
  
Chatroommanager für beständigen Chat, die einen oder mehrere Chatrooms verwalten können, können den Client verwenden, um eine Webanwendung für die Raumverwaltung zum Erstellen und Verwalten von Chatrooms zu starten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden sollen). 
  
Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:
  
- Deaktivieren eines Chatrooms
    
- Ändern des Namens eines Chatrooms
    
- Ändern der Beschreibung eines Chatrooms
    
- Ändern des Chatroomtyps ("Auditorium" bzw. "Normal")
    
- Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)
    
- Hinzufügen oder Entfernen von Mitgliedern
    
- Hinzufügen oder Entfernen von Chatroommanagern
    
- Hinzufügen oder Entfernen eines Add-Ins
    
- Ändern von Einstellungen wie Einladungen (je nach den von der Kategorie zugelassenen Einstellungen)
    
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite "Konfiguration für beständigen **Chat"** ausführen: Konfigurieren von Optionen für den Server für beständigen Chat global oder für einen bestimmten Pool
  
## <a name="to-configure-persistent-chat-options-globally"></a>So konfigurieren Sie Optionen für beständigen Chat global

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **"Konfiguration für beständigen Chat"** auf **"Neu" und** dann auf **"Standortkonfiguration".**
    
    > [!IMPORTANT]
    > Wählen Sie diese Option aus, wenn die Konfiguration auf alle Pools für den Server für beständigen Chat angewendet werden soll, die am Standort bereitgestellt werden. Klicken **Sie auf "Poolkonfiguration",** wenn die Konfiguration auf einen bestimmten Serverpool für beständigen Chat angewendet werden soll.
  
5. Wählen **Sie in "Standort auswählen"** den Standort aus, der für die Standortkonfiguration für den Server für beständigen Chat konfiguriert werden soll.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
   - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
     > [!IMPORTANT]
     > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher zwischen. Wenn Sie diese Anzahl erhöhen, werden also mehr Nachrichten zwischengespeichert. Sie können immer auf verlaufshistorische Inhalte zugreifen, indem Sie suchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die beim Herstellen einer Verbindung mit einem Chatroom angezeigt werden. 
  
   - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
   - Wählen **Sie im Teilnehmeraktualisierungslimit** den Grenzwert für Teilnehmerupdates aus. Der Server für beständigen Chat sendet Dienstplaninformationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Anzahl erreicht. Standardmäßig ist die Zahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, ab der der Server für beständigen Chat das Senden von Dienstplanupdates an verbundene Clients unterbricht, um anzugeben, wer im Raum vorhanden ist.
    
   - (Optional.) Wählen **Sie in der Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und einfach die Standardeinstellung verwenden, lassen Sie diese Option leer. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
    
     Wenn Sie Die Raumerstellung anpassen und Ihren spezifischen Geschäftsworkflow integrieren möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen, indem Sie das Software Development Kit (SDK) für den Server für beständigen Chat verwenden, es an einem anderen Ort hosten und die URL hier einfügen. Diese URL wird an den Client gesendet, sodass ein Benutzer, wenn er versucht, einen Raum zu sehen oder zu erstellen, zu Ihrer benutzerdefinierten Raumverwaltungslösung geleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>So konfigurieren Sie Optionen für beständigen Chat für einen bestimmten Serverpool für beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Konfiguration für beständigen Chat**.
    
4. Klicken Sie auf der Seite **Konfiguration für beständigen Chat** auf **Neu** und dann auf **Poolkonfiguration**.
    
5. Wählen **Sie in "Dienst auswählen"** den Dienst aus, der dem Zu konfigurierenden Pool für den Server für beständigen Chat zugeordnet ist.
    
6. Führen Sie unter **Neue Konfiguration für beständigen Chat** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
   - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
    
     > [!IMPORTANT]
     > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher zwischen. Wenn Sie diese Anzahl erhöhen, werden also mehr Nachrichten zwischengespeichert. Sie können immer auf verlaufshistorische Inhalte zugreifen, indem Sie suchen. Die Standardnummer bestimmt einfach die maximale Anzahl von Nachrichten, die beim Herstellen einer Verbindung mit einem Chatroom angezeigt werden. 
  
   - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
    
   - Wählen **Sie im Teilnehmeraktualisierungslimit** den Grenzwert für Teilnehmerupdates aus. Der Server für beständigen Chat sendet Dienstplaninformationen (die mit einem Chatroom verbunden sind) an alle Teilnehmer, bis die Anzahl der verbundenen Benutzer diese Anzahl erreicht. Standardmäßig ist die Zahl 75. Dieser Grenzwert gibt die maximale Anzahl von Teilnehmern in einem bestimmten Raum an, ab der der Server für beständigen Chat das Senden von Dienstplanupdates an verbundene Clients unterbricht, um anzugeben, wer im Raum vorhanden ist.
    
   - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und einfach die Standardeinstellung verwenden, lassen Sie diese Option leer.
    
     Wenn Sie Die Raumerstellung anpassen und Ihren spezifischen Geschäftsworkflow integrieren möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen, indem Sie das Software Development Kit (SDK) für den Server für beständigen Chat verwenden, es an einem anderen Ort hosten und die URL hier einfügen. Diese URL wird an den Client gesendet, sodass ein Benutzer, wenn er versucht, einen Raum zu sehen/zu erstellen, zu Ihrer benutzerdefinierten Raumverwaltungslösung geleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

Weitere Informationen zu den Features und Funktionen des Servers für beständigen Chat finden Sie unter ["Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) ["Deploy Persistent Chat Server in Skype for Business Server 2015"](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und ["Manage Persistent Chat Server in Skype for Business Server 2015".](../../manage/persistent-chat/persistent-chat.md)
  

