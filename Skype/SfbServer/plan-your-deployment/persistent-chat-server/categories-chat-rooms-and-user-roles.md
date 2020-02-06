---
title: Kategorien für beständigen Chat, Chatrooms und Benutzerrollen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu Kategorien, Chatrooms sowie Benutzer-und Administratorrollen für den Server für beständigen Chat in Skype for Business Server 2015 zu erhalten.'
ms.openlocfilehash: 03a7b68a9728b60ebae25081e3e974bb61b0fc5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815763"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Kategorien für beständigen Chat, Chatrooms und Benutzerrollen in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema finden Sie Informationen zu Kategorien, Chatrooms sowie Benutzer-und Administratorrollen für den Server für beständigen Chat in Skype for Business Server 2015.
  
Sie können den Zugriff auf Chatrooms regulieren, indem Sie Chatroomkategorien erstellen und dann den Zugriff auf die Kategorien sowie die Chatrooms innerhalb der Kategorien festlegen. Außerdem können Sie mehrere Administratorrollen bestimmen. In diesem Thema wird Folgendes beschrieben: 
  
- Kategorien für die Organisation von Chatrooms
    
- Chatrooms und Benutzerrollen
    
- Administratorrollen

> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Kategorien für die Organisation von Chatrooms

Mithilfe von Kategorien können Sie Chatrooms organisieren und bestimmen, welcher Benutzer und welche Gruppen die Chatrooms innerhalb dieser Kategorien erstellen oder ihnen beitreten können. Jeder Kategorie sind Eigenschaften zugeordnet, die die verfügbaren Optionen für den Chatroom innerhalb der Kategorie festlegen. Sie können den Zugriff auf eine bestimmte Kategorie regulieren, indem Sie bestimmen, ob ein Benutzer für den Zugriff zulässig ist oder abgelehnt wird.
  
Das primäre Grundprinzip für das Konzept der zulässigen und abgelehnten Mitglieder sind so genannte Chinesische Mauern. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen Chinesische Mauern definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Benutzer können einem Chatroom nicht hinzugefügt werden, wenn die übergeordnete Kategorie dies nicht zulässt.
  
> [!IMPORTANT]
> Zulässige und abgelehnte Mitglieder in einer Kategorie sind nicht identisch mit einer **Mitglieds** Rolle, die für einen beständigen Chatroom gilt. #a0 suchen werden alle geöffneten und geschlossenen Chatrooms angezeigt, für die der Benutzer, der die Suche ausführt, in der Liste zugelassene und verweigerte Mitglieder aufgeführt ist. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann. 
  
## <a name="chat-rooms-and-user-roles"></a>Chatrooms und Benutzerrollen

Zusätzlich zu den zugelassenen und abgelehnten Mitgliedern für Kategorien können Sie auch den Zugriff auf Chatrooms steuern, indem Sie die folgenden Benutzerrollen angeben: Creator, Manager, Member und Referent.
  
- **Ersteller**: Benutzer, die zum Erstellen von Chatrooms berechtigt sind. Diese Benutzer befinden sich in der Ersteller-Liste bestimmter Kategorien. Sie können Chatrooms in dieser Kategorie erstellen, eine Mitgliedschaft gemäß dieser Kategorie zuweisen sowie Manager zum Verwalten von Chatrooms zuweisen. Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.
    
    > [!NOTE]
    > Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern. 
  
    Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.
    
- **Manager**: Benutzer, die die Eigenschaften eines Chatrooms verwalten. Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen). Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können. Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen). Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern. Nur der Administrator des beständigen Chats kann die Kategorie nach dem Erstellen des Chatrooms ändern.
    
    > [!IMPORTANT]
    > Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt. 
  
- **Mitglied**: Benutzer, die Mitglieder eines Chatrooms sind. Diese Benutzer können die Chatrooms im Verzeichnis (auch wenn der Chatroom geheim ist) sehen sowie den Chatroom abonnieren (einschließlich metadateneinstellungen wie ungelesene Nachrichten, Ego-Filter und Keyword-Filter) und am Chatroom teilnehmen (kann Posten, es sei denn, der Raum ist ein Hörsaal Raum, in dem nur Referenten Beiträge Posten, Inhalte abrufen und suchen können. Benutzer, die keine Mitglieder des Chatrooms sind, können nach dem Chatroom suchen, wenn Sie sich in der Liste der zulässigen Mitglieder der Kategorie befinden, müssen aber Zugriff auf die Teilnahme an diesen Chatrooms anfordern, um auf Inhalte zugreifen zu können. (Es sind keine Zugriffs-oder Genehmigungsanfragen in das System integriert; diese werden extern per e-Mail, Telefon oder anderen Kontaktarten durchgeführt.)
    
- **Referent**: Benutzer, die Nachrichten in einem Auditorium senden können.
    
## <a name="administrator-roles"></a>Administratorrollen

Im folgenden finden Sie Administratorrollen für den Server für beständigen Chat:
  
- **Administrator für beständigen Chat**: die Administratorrolle des beständigen Chats kann Chatrooms verwalten (alle Eigenschaften einschließlich Mitgliedschaft, Manager, Kategorien, als deaktiviert kennzeichnen) sowie Chatrooms erstellen und verwalten, die definieren, wer Chatrooms erstellen und darauf zugreifen kann. Administratoren können Chatrooms auch als deaktiviert kennzeichnen und Chatrooms bereinigen, die nicht mehr aktiv sind. Administratoren unterliegen nicht den Einschränkungen des Erstellers oder der zulässigen Mitglieder. Administratoren können jede Art von Chatroom erstellen und sich selbst als Mitglied zu einem Chatroom hinzufügen. Administratoren können auch die Konfiguration beständiger Chats ändern und verwalten (Pooleigenschaften, globale Einstellungen und Kompatibilitäts Konfiguration) und auch die Migration von einer älteren Gruppen-Chat Server Bereitstellung in Skype for Business Server 2015 planen und implementieren. Beständiger Chat Server.
    
    Administratoren für beständigen Chat können den Server für beständigen Chat mithilfe von Windows PowerShell-Cmdlets remote verwalten (also von einem anderen Computer als dem beständigen Chat Server). Der beständige Chat Server überprüft, ob der Administrator des beständigen Chats ein Mitglied der lokalen Gruppe RTC Local Administrator auf dem Front-End-Server des beständigen Chats ist.
    
- **Skype for Business Server 2015 Administrator**: Gesamtunternehmens Administrator für Skype for Business Server 2015, der für die Bereitstellung verantwortlich ist.
    
- **Operations Manager**: Benutzer, der für die täglichen Abläufe verantwortlich ist.
    
- **Drittanbieterentwickler und Partner**: Drittanbieterentwickler erweitern das System und liefern insbesondere Lösungen zum Errichten von Chinesischen Mauern für Gruppenunterhaltungen. Zudem stellen sie Konformitätsunterstützung und -tools, Web- und mobile Clients sowie ein Framework für die Bot-Entwicklung bereit.
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zum Konfigurieren und Verwalten von Chatrooms und Benutzerrollen finden Sie in den folgenden Themen:
  
- [Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Verwalten von Chatrooms im Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

