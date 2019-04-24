---
title: Kategorie für beständigen Chat – Hauptseite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: Auf der Seite Beständiger Chat können Sie den Abschnitt Kategorie verwenden, um Kategorien zu konfigurieren. Eine Kategorie für beständigen Chat Raum ist eine logische Struktur zum Organisieren von Chatrooms. In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen von oder zum Beitreten zu Chatrooms berechtigt sind. Sie können Kategorien verwenden, um „Chinesische Mauern“ zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.
ms.openlocfilehash: b54a8d5299049f33bc366cde0988bcb92be5640e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200688"
---
# <a name="persistent-chat-category-main-page"></a>Kategorie für beständigen Chat – Hauptseite
 
Auf der Seite **Beständiger Chat** können Sie den Abschnitt **Kategorie** verwenden, um Kategorien zu konfigurieren. Eine Kategorie für beständigen Chat Raum ist eine logische Struktur zum Organisieren von Chatrooms. In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen von oder zum Beitreten zu Chatrooms berechtigt sind. Sie können Kategorien verwenden, um „Chinesische Mauern“ zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.
  
Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien. Jeder Kategorie beschrieben, dessen Inhalt mit Metadaten wie der _Name_ und _Beschreibung_. Darüber hinaus wurde die Kategorie Eigenschaften, die zum Steuern des Verhaltens von der zugehörigen, Chatrooms festgelegt werden können beispielsweise, wenn die Chatrooms _Einladungen_ oder _Dateiuploads_zulassen oder _Den Chatverlauf_enthalten.
  
Um eine neue Kategorie erstellen, finden Sie unter [Verwalten von Kategorien in Persistent Chat Server in Skype für Business Server 2015](../../manage/persistent-chat/categories.md). Wenn Sie eine Persistent Chat Administrator sind, können Sie Kategorien mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets erstellen.
  
## <a name="tasks-that-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Kategorie** können Sie die folgenden Aufgaben ausführen:
  
- Erstellen oder Bearbeiten einer neuen Kategorie
    
- Verschieben eines Chatrooms von einer Kategorie in eine andere
    
- Löschen eines Chatrooms oder einer Kategorie
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms für beständigen Chat

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL. .
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für Bereitstellungen mit mehreren Persistent Chat Server Pool den entsprechenden Pool aus der Dropdownliste aus.
    
4. Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten**.
    
5. Wählen Sie unter **Wählen Sie einen Dienst**Dienst entspricht dem Persistent Chat Server Pool, auf dem die Kategorie erstellt werden soll. Der Dienst ist die Persistent Chat-Server-Pool, der den beständigen Chat (Client) verwendet, um zu identifizieren der pool-Kategorie gehört. Eine Kategorie werden kann nur einen Persistent Chat Server Pool angehören und nicht in eine andere verschoben oder einen anderen Pool freigegeben.
    
6. Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
7. Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.
    
8. Geben Sie unter **Beschreibung** Einzelheiten über die Raumkategorie an (z. B. eine Raumkategorie für Contoso).
    
9. Klicken Sie zum Steuern, ob Einladungen für Chatrooms aktiviert werden können, die dieser Kategorie angehören, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Einladungen zu aktivieren** . Wenn ausgewählt haben, können in dieser Kategorie Chatrooms Einladungen aktiviert oder deaktiviert haben; Wenn deaktiviert, dürfen die Chatrooms in dieser Kategorie nicht Einladungen haben. Wenn ein Chatroom Einladungen weist auf, wenn ein neues Mitglied in einem Raum hinzugefügt wird, ruft er eine Benachrichtigung über die neuen Raums in ihrem Persistent Chat-Client ab.
    
10. Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.
    
11. Um den Chatverlauf zu kontrollieren, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **aktivieren den Chatverlauf** . Wenn Sie ausgewählt haben, werden Raum Chats persistent. Andernfalls werden Chatnachrichten nicht beibehalten. Wenn Kompatibilität aktiviert ist, Raum Chats werden in Compliance gespeichert, aber Benutzer werden nicht auf ältere Nachrichten zugreifen. Diese Option kann verwendet werden, für Räume vorgesehen für in Echtzeit, ad-hoc-Zusammenarbeit, die den Chatverlauf beibehalten werden nicht benötigen.
    
12. Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
    - Unter **Mitgliedschaft**im Abschnitt **Zugelassene Mitglieder** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Domänendienste Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.), die als Mitglieder des Chatrooms hinzugefügt werden dürfen für die Kategorie gehören. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
    - **Die Mitgliedschaft**in den Abschnitt **abgelehnten Mitglieder** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Prinzipale wird diesen Raum Mitgliedern zugeordnet sind.
    
    - **Die Mitgliedschaft**in den Abschnitt **Ersteller** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Prinzipale Ersteller für die Kategorie zugeordnet. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.
    
13. Klicken Sie auf **Commit ausführen**.
    
## <a name="see-also"></a>Siehe auch

Details zu Persistent Chat Server-Features und Funktionen, finden Sie unter [Planen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Persistent Chatserver in Skype für Business Server 2015 bereitstellen](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und [Verwalten Persistent Chat Server in Skype für Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

