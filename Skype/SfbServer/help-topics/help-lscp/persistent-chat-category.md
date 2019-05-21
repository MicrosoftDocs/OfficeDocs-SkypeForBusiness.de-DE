---
title: Kategorie für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: Auf der Seite Beständiger Chat können Sie den Abschnitt Kategorie verwenden, um Kategorien zu konfigurieren. Eine beständige Chatroom-Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen von oder zum Beitreten zu Chatrooms berechtigt sind. Sie können Kategorien verwenden, um „Chinesische Mauern“ zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.
ms.openlocfilehash: fc430c7d61ad4662d28f81594d59bf95d03f84c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302664"
---
# <a name="persistent-chat-category"></a>Kategorie für beständigen Chat
 
Auf der Seite **Beständiger Chat** können Sie den Abschnitt **Kategorie** verwenden, um Kategorien zu konfigurieren. Eine beständige Chatroom-Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen von oder zum Beitreten zu Chatrooms berechtigt sind. Sie können Kategorien verwenden, um „Chinesische Mauern“ zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.
  
Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien. Jede Kategorie beschreibt ihren Inhalt mit Metadaten wie _Name_ und _Beschreibung_. Darüber hinaus verfügt die Kategorie über Eigenschaften, die so eingestellt werden können, dass Sie das Verhalten der zugehörigen Chatrooms steuern, beispielsweise wenn die Chatrooms _Einladungen_ oder _Dateiuploads_zulassen oder Chat- _Protokoll_enthalten.
  
Informationen zum Erstellen einer neuen Kategorie finden Sie unter [Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/categories.md). Wenn Sie ein beständiger Chat-Administrator sind, können Sie mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets Kategorien erstellen.
  
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Kategorie** können Sie die folgenden Aufgaben ausführen:
  
- Erstellen oder Bearbeiten einer neuen Kategorie
    
- Verschieben eines Chatrooms von einer Kategorie in eine andere
    
- Löschen eines Chatrooms oder einer Kategorie
    
## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.
    
4. Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten**.
    
5. Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, auf dem die Kategorie erstellt werden muss. Bei dem Dienst handelt es sich um den Server Pool für beständigen Chat, den der beständige Chat (Client) verwendet, um zu ermitteln, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur einem beständigen Chat Server Pool angehören und kann nicht in eine andere Gruppe verschoben oder für einen anderen Pool freigegeben werden.
    
6. Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
7. Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.
    
8. Geben Sie unter **Beschreibung** Einzelheiten über die Raumkategorie an (z. B. eine Raumkategorie für Contoso).
    
9. Wenn Sie steuern möchten, ob Einladungen für Chatrooms, die zu dieser Kategorie gehören, aktiviert werden können, aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** . Wenn diese Option ausgewählt ist, können Chatrooms in dieser Kategorie möglicherweise Einladungen aktivieren oder deaktivieren. Wenn diese Option deaktiviert ist, dürfen die Räume in dieser Kategorie keine Einladungen haben. Wenn ein Raum Einladungen enthält, wenn ein neues Mitglied zu einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in seinem beständigen Chat-Client.
    
10. Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.
    
     > [!IMPORTANT]
     > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients, die den Office Communications Server 2007 R2-Gruppen-Chat Server oder lync Server 2010 verwenden, Gruppen-Chat Dateien in einem Raum bereitstellen können. Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten. 
  
11. Aktivieren oder deaktivieren Sie das Kontrollkästchen Chat- **Protokoll aktivieren** , um das Chat-Protokoll zu kontrollieren. Wenn diese Option ausgewählt ist, werden Chatroom-Chats persistent; Andernfalls bleiben Chatnachrichten nicht erhalten. Wenn Compliance aktiviert ist, werden Chatroom-Chats unter Compliance gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen. Diese Option kann für Chatrooms verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit vorgesehen sind und keine Beibehaltung des Chat-Verlaufs erforderlich machen.
    
12. Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
    - Fügen Sie unter **Mitgliedschaft**im Abschnitt **zulässige Mitglieder** Benutzer und andere Active Directory-Domänendienst Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms hinzugefügt werden dürfen. gehören zur Kategorie. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
    - Fügen Sie in der **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory-Prinzipale hinzu, die Mitgliedern zugeordnet sind, die aus dem Chatroom verweigert werden.
    
    - Fügen Sie unter **Mitgliedschaft**im **** Abschnitt Creators Benutzer und andere Active Directory-Prinzipale hinzu, die den Erstellern für die Kategorie zugeordnet sind. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.
    
13. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Bereitstellen eines beständigen Chat Servers in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und Verwalten des beständigen [Chat Servers in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

