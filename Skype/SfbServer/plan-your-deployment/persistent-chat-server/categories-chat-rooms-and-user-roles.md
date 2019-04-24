---
title: Kategorien für beständigen Chat, Chatrooms und Benutzerrollen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu Kategorien, Chatrooms und Benutzer und Administrator Rollen für Persistent Chat Server in Skype für Business Server 2015 erhalten.'
ms.openlocfilehash: 0a65d5d8944d28ba834fac461051f23fcdd98800
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213781"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Kategorien für beständigen Chat, Chatrooms und Benutzerrollen in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zu Kategorien, Chatrooms und Benutzer und Administrator Rollen für Persistent Chat Server in Skype für Business Server 2015 erhalten.
  
Sie können den Zugriff auf Chatrooms regulieren, indem Sie Chatroomkategorien erstellen und dann den Zugriff auf die Kategorien sowie die Chatrooms innerhalb der Kategorien festlegen. Außerdem können Sie mehrere Administratorrollen bestimmen. In diesem Thema wird Folgendes beschrieben: 
  
- Kategorien für die Organisation von Chatrooms
    
- Chatrooms und Benutzerrollen
    
- Administratorrollen

> [!NOTE] 
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Kategorien für die Organisation von Chatrooms

Mithilfe von Kategorien können Sie Chatrooms organisieren und bestimmen, welcher Benutzer und welche Gruppen die Chatrooms innerhalb dieser Kategorien erstellen oder ihnen beitreten können. Jeder Kategorie sind Eigenschaften zugeordnet, die die verfügbaren Optionen für den Chatroom innerhalb der Kategorie festlegen. Sie können den Zugriff auf eine bestimmte Kategorie regulieren, indem Sie bestimmen, ob ein Benutzer für den Zugriff zulässig ist oder abgelehnt wird.
  
Das primäre Grundprinzip für das Konzept der zulässigen und abgelehnten Mitglieder sind so genannte Chinesische Mauern. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen Chinesische Mauern definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Benutzer können einem Chatroom nicht hinzugefügt werden, wenn die übergeordnete Kategorie dies nicht zulässt.
  
> [!IMPORTANT]
> Zugelassene und abgelehnte Elemente in einer Kategorie sind nicht identisch mit der Rolle **Mitglied** , die ein beständiger Chat Room.> Suchvorgänge anzeigen betrifft alle öffnen und Chatrooms für die der Benutzer den Suchvorgang darf wurde geschlossen und Mitgliederliste verweigert. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann. 
  
## <a name="chat-rooms-and-user-roles"></a>Chatrooms und Benutzerrollen

Zusätzlich zur zugelassene und abgelehnte Elemente für Kategorien können Sie auch Zugriff auf Chatrooms durch Angeben von den folgenden Benutzern steuern: Ersteller, Manager, Member und Referent.
  
- **Ersteller**: Benutzer, die zum Erstellen von Chatrooms berechtigt sind. Diese Benutzer befinden sich in der Ersteller-Liste bestimmter Kategorien. Sie können Chatrooms in dieser Kategorie erstellen, eine Mitgliedschaft gemäß dieser Kategorie zuweisen sowie Manager zum Verwalten von Chatrooms zuweisen. Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.
    
    > [!NOTE]
    > Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern. 
  
    Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.
    
- **Manager**: Benutzer, die die Eigenschaften eines Chatrooms verwalten. Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen). Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können. Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen). Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern. Nur der Persistent Chat Administrator kann die Kategorie ändern, nachdem den Chatroom erstellt wurde.
    
    > [!IMPORTANT]
    > Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt. 
  
- **Member**: Benutzer, die Mitglied eines Chatrooms sind. Diese Benutzer können die Chatrooms in das Verzeichnis (auch, wenn die Chatroom geheimen ist), finden Sie unter als auch abonnieren Sie den Chatroom (einschließlich Metadatenoptionen wie ungelesene Nachrichten, Ego-Filter und stichwortfilter) und die Teilnahme Chatrooms (vornehmen können, es sei denn, die Raum wird von einem Auditorium, in dem nur Referenten können buchen, Content erhalten möchten, und die Suche). Benutzer, die keine des Chatrooms Gruppenmitglieder können für den Chatroom suchen, wenn sie in der Liste zugelassene Mitglieder der Kategorie sind, jedoch müssen Zugriff auf, um auf Inhalte zugreifen, diese Chatrooms beitreten anfordern. (Es ist kein Zugriff beantragen oder im System integriert Genehmigungen; diese per e-Mail, Telefon oder anderen Formen der Kontakt extern fertig sind.)
    
- **Referent**: Benutzer, die Nachrichten in einem Auditorium senden können.
    
## <a name="administrator-roles"></a>Administratorrollen

Im folgenden sind die Administratorrollen für Persistent Chat Server:
  
- **Persistent Chat Administrator**: die Persistent Chat Administrator Rolle Chatrooms (alle Eigenschaften einschließlich der Mitgliedschaft, Manager, Kategorien, Chatrooms als deaktiviert Mark ändern), sowie erstellen und Verwalten von Kategorien für Chatrooms, die definieren, die verwalten Erstellen und Chatrooms zugreifen können. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Administratoren können auch ändern und Verwalten von Persistent Chat-Konfiguration (Pooleigenschaften, globale Einstellungen und Kompatibilitätskonfiguration) und können auch planen und implementieren Migration von einer älteren Group-Chat-Server-Bereitstellung zu Skype für Business Server 2015 Persistent Chat-Server.
    
    Persistent Chat-Administratoren sind Persistent Chat Server mithilfe von Windows PowerShell-Cmdlets Remote zu verwalten (d. h., von einem anderen Computer als dem Persistent Chat Server). Persistent Chat Server überprüft, ob der Persistent Chat Administrator ein Mitglied der RTC Local lokalen Administratorgruppe auf dem Persistent Chat Server-Front-End-Server.
    
- **Skype für Business 2015 Serveradministrator**: insgesamt Unternehmensadministrator für Skype für Business Server 2015 Bereitstellung verantwortlich ist.
    
- **Operations Manager**: Benutzer, der für die täglichen Abläufe verantwortlich ist.
    
- **Drittanbieterentwickler und Partner**: Drittanbieterentwickler erweitern das System und liefern insbesondere Lösungen zum Errichten von Chinesischen Mauern für Gruppenunterhaltungen. Zudem stellen sie Konformitätsunterstützung und -tools, Web- und mobile Clients sowie ein Framework für die Bot-Entwicklung bereit.
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zum Konfigurieren und Verwalten von Chatrooms und Benutzerrollen finden Sie in den folgenden Themen:
  
- [Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Verwalten von Chatrooms im Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

