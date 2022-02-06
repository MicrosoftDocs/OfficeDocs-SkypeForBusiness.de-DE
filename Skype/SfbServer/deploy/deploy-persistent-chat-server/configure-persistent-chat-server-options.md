---
title: Konfigurieren von Optionen für den Server für beständigen Chat in Skype for Business Server 2015
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
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Zusammenfassung: Erfahren Sie, wie Sie optionen für den Server für beständigen Chat auf globaler, Standort- oder Poolebene in Skype for Business Server 2015 konfigurieren.'
---

# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Konfigurieren von Optionen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie optionen für den Server für beständigen Chat auf globaler, Standort- oder Poolebene in Skype for Business Server 2015 konfigurieren.
  
Sie können mehrere Optionen für den Server für beständigen Chat angeben, die global, auf alle Pools innerhalb eines Standorts oder auf einen bestimmten Pool innerhalb eines Standorts angewendet werden können. Zu den Serveroptionen für beständigen Chat gehören: 
  
- Standardchatverlauf. Die Anzahl der Chatnachrichten, die bei der ersten Anforderung für jeden Chatroom verfügbar sind. Der globale Standardwert ist 30 Chatnachrichten. 
    
- Maximale Dateigröße. Die maximale Größe einer Datei, die in einen Raum hochgeladen oder aus einem Raum heruntergeladen werden kann. Der globale Standardwert ist 20 MB.
    
- Grenzwert für Teilnehmerupdates. Die maximale Anzahl von Teilnehmern in einem bestimmten Chatroom, für den der beständige Chat Listenupdates sendet. Der globale Standardwert ist 75.
    
- Raumverwaltungs-URL. Die URL, die für die benutzerdefinierte Chatroomverwaltung verwendet wird. Die Einstellung ermöglicht die Verwendung einer benutzerdefinierten Raumverwaltungslösung. 
   
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.
 
## <a name="configure-persistent-chat-server-global-options"></a>Konfigurieren globaler Optionen für den Server für beständigen Chat

So konfigurieren Sie globale Optionen für den Server für beständigen Chat:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Konfigurieren von Optionen für einen bestimmten Serverpool für beständigen Chat

So konfigurieren Sie Optionen für einen bestimmten Serverpool für beständigen Chat.
  
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
    

