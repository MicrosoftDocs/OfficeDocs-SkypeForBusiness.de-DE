---
title: Kategorien, Chatrooms und Benutzerrollen für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über Kategorien, Chatrooms und Benutzer- und Administratorrollen für den Server für beständigen Chat in Skype for Business Server 2015 zu erfahren.'
ms.openlocfilehash: e3740702f43ae677ef451049bfce2a4497a0b992
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615561"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Kategorien, Chatrooms und Benutzerrollen für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über Kategorien, Chatrooms sowie Benutzer- und Administratorrollen für den Server für beständigen Chat in Skype for Business Server 2015.
  
Sie können den Zugriff auf Chatrooms steuern, indem Sie Chatroomkategorien erstellen und dann den Zugriff auf Kategorien und Chatrooms innerhalb von Kategorien angeben. Sie können auch verschiedene Administratorrollen angeben. In diesem Thema wird Folgendes beschrieben: 
  
- Kategorien für die Organisation von Chatrooms
    
- Chatrooms und Benutzerrollen
    
- Administratorrollen

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Kategorien für die Organisation von Chatrooms

Mithilfe von Kategorien können Sie Chatrooms organisieren und steuern, welche Benutzer und Gruppen chatrooms innerhalb dieser Kategorien erstellen oder daran teilnehmen dürfen. Jeder Kategorie sind Eigenschaften zugeordnet, die die verfügbaren Optionen für die Chatrooms in der Kategorie bestimmen. Sie steuern den Zugriff auf eine bestimmte Kategorie, indem Sie angeben, ob einem Benutzer der Zugriff gewährt oder verweigert wird.
  
Der Hauptgrund für das Konzept der zugelassenen und abgelehnten Mitglieder sind ethische Wände. Beispielsweise ist es bei Banken und Finanzinstitutionen üblich, dass beim Implementieren von Richtlinien und Konventionen ethische Grenzen definiert werden, die verhindern, dass Händler und Analysten Mitteilungen und Informationen austauschen. Um dieser Anforderung nachzukommen, kann ein Administrator Kategorien erstellen, sodass in einer Kategorie Chatrooms von Händlern und in einer anderen Kategorie Chatrooms von Analysten erstellt und verwendet werden können. Benutzer können nicht als Mitglied eines Chatrooms hinzugefügt werden, wenn die übergeordnete Kategorie dies verhindert.
  
> [!IMPORTANT]
> Zulässige und abgelehnte Mitglieder in einer Kategorie sind nicht identisch mit einer **Mitgliedsrolle,** die für einen beständigen Chatroom gilt.> Suchvorgänge zeigen alle geöffneten und geschlossenen Chatrooms an, für die sich der Benutzer, der die Suche durchführt, in der Liste zugelassener und abgelehnter Mitglieder befindet. Geheime Chatrooms werden nur angezeigt, wenn der Benutzer, der die Suche durchführt, Mitglied des geheimen Chatrooms ist. Der Benutzer kann nur nach Chatrooms suchen, bei denen er bereits Mitglied ist oder für die er eine Mitgliedschaft anfordern kann. 
  
## <a name="chat-rooms-and-user-roles"></a>Chatrooms und Benutzerrollen

Zusätzlich zu zulässigen und abgelehnten Mitgliedern für Kategorien können Sie auch den Zugriff auf Chatrooms steuern, indem Sie die folgenden Benutzerrollen angeben: Ersteller, Vorgesetzter, Mitglied und Referent.
  
- **Ersteller:** Benutzer, die über die Berechtigung zum Erstellen von Chatrooms verfügen. Diese Benutzer befinden sich in der Liste der Ersteller bestimmter Kategorien: Sie können Chatrooms in dieser Kategorie erstellen, und sie können auch Mitgliedschaften entsprechend der Kategorie zuweisen und Manager zum Verwalten des Chatrooms zuweisen. Der Benutzer, der einen Chatroom erstellt, wird automatisch als Manager des Chatrooms hinzugefügt.
    
    > [!NOTE]
    > Als Ersteller besitzt ein Benutzer lediglich die Rechte zum Erstellen von Chatrooms. Durch die automatische Heraufstufung zum Manager erhält der Ersteller die Berechtigung, Mitgliedschaften, Manager usw. für die erstellten Chatdienste zu verfeinern. 
  
    Mit dieser Rolle können Sie steuern, wer die Chatrooms in Ihrer Organisation erstellt. Dies ist insbesondere praktisch, wenn Sie das Erstellen von Chatrooms zentral verwalten möchten, um Richtlinien und Konventionen zu erzwingen, und anschließend die Chatroomverwaltung an andere Benutzer in der Organisation delegieren möchten.
    
- **Manager**: Benutzer, die die Eigenschaften eines Chatrooms verwalten. Chatroommanager können die Mitgliederliste ändern (Mitglieder hinzufügen und entfernen) und die Chatroommanager-Liste ändern (Manager hinzufügen und entfernen). Chatroommanager können sich selbst der Mitglieder- oder Referentenliste (für ein Auditorium) hinzufügen, damit sie am Chatroom teilnehmen können. Chatroommanager können Chatrooms auch deaktivieren (Administratoren können deaktivierte Chatrooms abfragen und dauerhaft löschen). Manager können bis auf die Chatroomkategorie alle Eigenschaften eines Chatrooms ändern. Nur der Administrator für beständigen Chat kann die Kategorie ändern, nachdem der Chatroom erstellt wurde.
    
    > [!IMPORTANT]
    > Wenn der Manager in einer anderen Kategorie auch der Ersteller ist, kann der Manager die Kategorie in eine Kategorie ändern, für die eine Berechtigung zum Erstellen von Chatrooms besitzt. 
  
- **Mitglied:** Benutzer, die Mitglieder eines Chatrooms sind. Diese Benutzer können die Chatrooms im Verzeichnis sehen (auch wenn der Chatroom geheim ist) sowie den Chatroom abonnieren (einschließlich Metadatenoptionen wie ungelesene Nachrichten, Egofilter und Schlüsselwortfilter) und am Chatroom teilnehmen (kann beiträgen, es sei denn, der Chatroom ist ein Auditorium-Raum, in dem nur Referenten beiträgen können,  Abrufen von Inhalten und Suchen). Benutzer, die nicht Mitglied des Chatrooms sind, können nach dem Chatroom suchen, wenn sie in der Liste der zugelassenen Mitglieder der Kategorie enthalten sind, aber den Zugriff anfordern müssen, um diesen Chatrooms beizutreten, um auf Inhalte zuzugreifen. (Es ist kein Anforderungszugriff oder Genehmigungen in das System integriert; diese erfolgen extern per E-Mail, Telefon oder anderen Kontakten.)
    
- **Referent**: Benutzer, die Nachrichten in einem Auditorium senden können.
    
## <a name="administrator-roles"></a>Administratorrollen

Im Folgenden sind Administratorrollen für den Server für beständigen Chat aufgeführt:
  
- **Administrator für beständigen Chat:** Die Administratorrolle für beständigen Chat kann Chatrooms verwalten (alle Eigenschaften einschließlich Mitgliedschaft, Manager, Kategorien, Chatrooms als deaktiviert markieren) sowie Chatroomkategorien erstellen und verwalten, die definieren, wer Chatrooms erstellen und darauf zugreifen kann. Administratoren können Chatrooms auch als deaktiviert markieren und chatrooms bereinigen, die nicht mehr aktiv sind. Administratoren unterliegen nicht den Einschränkungen für Ersteller oder zulässige Mitglieder. Administratoren können jede Art von Chatroom erstellen und sich selbst als Mitglied zu jedem Chatroom hinzufügen. Administratoren können auch die Konfiguration für beständigen Chat (Pooleigenschaften, globale Einstellungen und Compliancekonfiguration) ändern und verwalten sowie die Migration von einer älteren Bereitstellung des Gruppenchatservers zu Skype for Business Server 2015 Persistent Chat Server planen und implementieren.
    
    Administratoren für beständigen Chat können den Server für beständigen Chat mithilfe Windows PowerShell Cmdlets remote verwalten (d. b. von einem anderen Computer als dem Server für beständigen Chat). Der Server für beständigen Chat überprüft, ob der Administrator für beständigen Chat Mitglied der lokalen Gruppe des lokalen RTC-Administrators auf dem Front-End-Server für den Server für beständigen Chat ist.
    
- **Skype for Business Server 2015 Administrator:** Gesamter Unternehmensadministrator für Skype for Business Server 2015, der für die Bereitstellung verantwortlich ist.
    
- **Operations Manager**: Benutzer, der für die täglichen Abläufe verantwortlich ist.
    
- **Drittanbieterentwickler und Partner**: Drittanbieterentwickler erweitern das System und liefern insbesondere eine Lösung zum Errichten einer Chinesischen Mauer für Gruppenunterhaltungen. Zudem stellen sie Konformitätsunterstützung und -tools, Web- und mobile Clients sowie ein Framework für Bot-Entwicklung bereit.
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zum Konfigurieren und Verwalten von Chatrooms und Benutzerrollen finden Sie in den folgenden Themen:
  
- [Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Verwalten von Chatrooms auf dem Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

