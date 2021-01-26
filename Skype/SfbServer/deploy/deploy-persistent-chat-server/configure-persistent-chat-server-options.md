---
title: Konfigurieren von Optionen für den Server für beständigen Chat in Skype for Business Server 2015
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
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Zusammenfassung: Informationen zum Konfigurieren von Optionen für den Server für beständigen Chat auf globaler, Standort- oder Poolebene in Skype for Business Server 2015.'
ms.openlocfilehash: 9c0b6d5e03b9bc4f7d955ea0dae3e1c45b14ada3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802125"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Konfigurieren von Optionen für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Optionen für den Server für beständigen Chat auf globaler, Standort- oder Poolebene in Skype for Business Server 2015 konfigurieren.
  
Sie können mehrere Optionen für den Server für beständigen Chat angeben, die global, auf alle Pools innerhalb eines Standorts oder auf einen bestimmten Pool innerhalb eines Standorts angewendet werden können. Zu den Serveroptionen für beständigen Chat gehören die folgenden: 
  
- Standardchatverlauf. Die Anzahl der Chatnachrichten, die bei der ersten Anforderung für jeden Chatroom verfügbar sind. Der globale Standardwert ist 30 Chatnachrichten. 
    
- Maximale Dateigröße. Die maximale Größe einer Datei, die in einen Raum hochgeladen oder aus einem Raum heruntergeladen werden kann. Der globale Standardwert ist 20 MB.
    
- Grenzwert für Teilnehmeraktualisierungen. Die maximale Anzahl von Teilnehmern in einem bestimmten Chatroom, für die der beständigen Chat Dienstplanaktualisierungen sendet. Der globale Standardwert ist 75.
    
- Raumverwaltungs-URL. Die URL für die benutzerdefinierte Chatroomverwaltung. Die Einstellung ermöglicht die Verwendung einer benutzerdefinierten Raumverwaltungslösung. 
   
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.
 
## <a name="configure-persistent-chat-server-global-options"></a>Konfigurieren globaler Optionen für den Server für beständigen Chat

So konfigurieren Sie globale Optionen für den Server für beständigen Chat:
  
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
    
     Wenn Sie Ihre Raumerstellungsumgebung anpassen und Ihren spezifischen Geschäftsworkflow integrieren möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen, indem Sie das Software Development Kit (SDK) für den Server für beständigen Chat verwenden, es an einem anderen Ort hosten und die URL hier einfügen. Diese URL wird an den Client gesendet, sodass ein Benutzer, wenn er versucht, einen Raum zu sehen oder zu erstellen, zu Ihrer benutzerdefinierten Raumverwaltungslösung geleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Konfigurieren von Optionen für einen bestimmten Serverpool für beständigen Chat

So konfigurieren Sie Optionen für einen bestimmten Pool für den Server für beständigen Chat.
  
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
    
     Wenn Sie Ihre Raumerstellungsumgebung anpassen und Ihren spezifischen Geschäftsworkflow integrieren möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen, indem Sie das Software Development Kit (SDK) für den Server für beständigen Chat verwenden, es an einem anderen Ort hosten und die URL hier einfügen. Diese URL wird an den Client gesendet, sodass ein Benutzer, wenn er versucht, einen Raum zu sehen/zu erstellen, zu Ihrer benutzerdefinierten Raumverwaltungslösung geleitet wird.
    
7. Klicken Sie auf **Commit ausführen**.
    

