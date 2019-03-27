---
title: Konfigurieren von Optionen des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von Persistent Chat Server-Optionen auf globaler, Standort- oder Poolebene in Skype für Business Server 2015.'
ms.openlocfilehash: fd4d9ed10c2629f714d336190e5c85b2dfe1621e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883756"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Konfigurieren von Optionen des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Konfigurieren von Persistent Chat Server-Optionen auf globaler, Standort- oder Poolebene in Skype für Business Server 2015.
  
Sie können mehrere Optionen für Persistent Chat Server angeben, die global für alle Pools in einer Website oder auf einem bestimmten Pool innerhalb einer Website angewendet werden können. Für den beständigen Chat stehen folgende Serveroptionen zur Verfügung: 
  
- Standard-Chatverlauf. Die Anzahl der Chatnachrichten, die für jeden Chatroom auf erste Anfrage verfügbar sind. Die globale Standardeinstellung ist 30 Chatnachrichten. 
    
- Maximale Dateigröße: Die maximale Größe einer Datei, die in einen Chatroom hochgeladen oder daraus heruntergeladen werden kann. Der globale Standardwert ist 20 MB.
    
- Teilnehmerliste Updatelimit. Die maximale Anzahl von Teilnehmern in einem bestimmten Chatroom für den beständigen Chat Teilnehmerliste Updates senden. Die globale Standardeinstellung ist 75.
    
- Raum Management-URL. Die URL für die Verwaltung von benutzerdefinierten Chatrooms verwendet. Die Einstellung ermöglicht die Verwendung einer benutzerdefinierten Raum Management-Lösung. 
   
> [!NOTE] 
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.
 
## <a name="configure-persistent-chat-server-global-options"></a>Konfigurieren Sie globale Optionen für Persistent Chat Server

So konfigurieren Sie globale Optionen für Persistent Chat Server
  
1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Konfigurieren von Optionen für einen bestimmten Pool Persistent Chat Server

So konfigurieren Sie Optionen für einen bestimmten Persistent Chat Server Pool.
  
1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
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
    

