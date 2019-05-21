---
title: Konfigurieren von Optionen des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Server Optionen für beständigen Chat auf globaler, Website-oder Poolebene in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: 6305ba9a961248b24fe1a2fc28d5944efb6adeac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273868"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Konfigurieren von Optionen des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Server Optionen für beständigen Chat auf globaler, Website-oder Poolebene in Skype for Business Server 2015 konfigurieren.
  
Sie können mehrere Optionen für beständigen Chat Server angeben, die Global angewendet werden können, auf alle Pools innerhalb einer Website oder auf einen bestimmten Pool innerhalb einer Website. Für den beständigen Chat stehen folgende Serveroptionen zur Verfügung: 
  
- Standard-Chat-Protokoll. Die Anzahl von Chat-Nachrichten, die bei der ersten Anforderung für jeden Chatroom zur Verfügung stehen. Der globale Standardwert ist 30 Chatnachrichten. 
    
- Maximale Dateigröße: Die maximale Größe einer Datei, die in einen Chatroom hochgeladen oder daraus heruntergeladen werden kann. Der globale Standardwert ist 20 MB.
    
- Grenzwert für Teilnehmer Aktualisierung. Die maximale Anzahl von Teilnehmern in einem bestimmten Chatroom, für die der beständige Chatdienst Plan Updates sendet. Der globale Standardwert ist 75.
    
- URL für die Raumverwaltung Die URL, die für die benutzerdefinierte Chat Raumverwaltung verwendet wird. Die Einstellung ermöglicht die Verwendung einer benutzerdefinierten Raum Verwaltungslösung. 
   
> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.
 
## <a name="configure-persistent-chat-server-global-options"></a>Globale Optionen für den beständigen Chat Server konfigurieren

So konfigurieren Sie die globalen Optionen für beständigen Chat Server:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Konfigurieren von Optionen für einen bestimmten beständigen Chat Server Pool

So konfigurieren Sie Optionen für einen bestimmten beständigen Chat Server Pool.
  
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
    

