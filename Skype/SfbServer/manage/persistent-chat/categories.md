---
title: Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server 2015 Kategorien für beständigen Chat Server verwalten.'
ms.openlocfilehash: f0c85c2246c85c93f96e6c13cef0a5d4360213cb
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992000"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server 2015 Kategorien für beständigen Chat Server verwalten.
  
Eine Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. Durch eine Kategorie wird ein Standardsatz an Zugriffssteuerungslisten (ACLs) definiert, mit dem die Benutzer und Benutzergruppen gesteuert werden, die Chatrooms erstellen oder diesen beitreten können. Chatroomkategorien enthalten Chatrooms, jedoch keine anderen Kategorien. Jede Kategorie beschreibt ihren Inhalt mithilfe von Metadaten wie „Name“ und „Beschreibung“. Die Kategorie besitzt Eigenschaften, die im Hinblick auf die Steuerung des Verhaltens der zu ihr gehörenden Chatrooms eingerichtet werden können, beispielsweise ob die Chatrooms Einladungen oder Dateiuploads erlauben oder einen Chatverlauf beinhalten. 
  
Chatrooms können mit der Verwendung der richtigen Kategorien viel einfacher erstellt und verwaltet werden. Als Administrator für einen Server für beständigen Chat können Sie für jede Kategorie „Zugelassene Mitglieder“ und „Ersteller“ definieren, aber auch die Standardeinstellung für Chatrooms sowie Verhaltensweisen, die für alle in der Kategorie erstellen Chatrooms gelten. Wenn Sie beispielsweise die AllowedMembers der Kategorie auf contoso.com festzulegen, können Sie eine beliebige Gruppe oder einen Benutzer bei Contoso als Mitglied zu Chatrooms in dieser Kategorie hinzufügen. Wenn Sie als Eigenschaft der „zugelassenen Mitglieder“ einer Kategorie „Verkauf“ festlegen, können nur Gruppen und Benutzer in dieser Verteilerliste als Mitglieder für Chatrooms in dieser Kategorie hinzufügt werden. Die Eigenschaft „Ersteller“ ermöglicht Ihnen zu kontrollieren, wer Chatrooms in dieser Kategorie erstellen kann. Nach der Erstellung des Chatrooms kann jeder aus der Gruppe „Zugelassene Mitglieder“ als Manager für laufende Verwaltungsaufgaben in den Chatrooms bestimmt werden (beispielsweise bei Änderung und Genehmigung einer Mitgliedschaft).
  
Das Definieren von „zugelassenen Mitgliedern“ und „Erstellern“ für eine Kategorie hat folgende Vorteile:
  
- Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.
    
- Ein Benutzer, der in der Liste „Ersteller“ vorhanden ist, kann in der betreffenden Kategorie neue Chatrooms erstellen. Falls Sie ein System implementieren möchten, in dem nur eine beschränkte Anzahl von Mitarbeitern der Organisation Chatrooms erstellen kann, können Sie dies nach diesem Verfahren realisieren. 
    
Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die in einer Kategorie als „Ersteller“ festgelegt werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in dieser Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können Sie Benutzer, Organisationseinheiten und Benutzergruppen in der Liste „Zugelassene Mitglieder“ der Kategorie als Chatroommanager und Mitglieder auswählen, die den Chatroom verwalten und an diesem teilnehmen. 
  
Bevor Sie Kategorien konfigurieren, müssen Sie sicherstellen, dass Sie [in Skype for Business Server 2015 beständige Chatkategorien, Chatrooms und Benutzerrollen](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)lesen.
  
Sie können Kategorien über die Systemsteuerung oder mit Windows PowerShell-Cmdlets konfigurieren und verwalten.

> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Konfigurieren von Kategorien mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.
    
4. Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten**.
    
5. Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, auf dem die Kategorie erstellt werden muss. Bei dem Dienst handelt es sich um den Server Pool für beständigen Chat, den der beständige Chat Client verwendet, um zu ermitteln, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur zu einem beständigen Chat Server Pool gehören und kann nicht in einen anderen Pool verschoben oder für Sie freigegeben werden.
    
6. Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.
    
   - Geben Sie unter **Beschreibung** Einzelheiten über die Raumkategorie an (z. B. eine Raumkategorie für Contoso).
    
   - Wenn Sie steuern möchten, ob Einladungen für Chatrooms, die zu dieser Kategorie gehören, aktiviert werden können, aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** . Wenn diese Option ausgewählt ist, können Chatrooms in dieser Kategorie möglicherweise Einladungen aktivieren oder deaktivieren. Wenn diese Option deaktiviert ist, dürfen die Räume in dieser Kategorie keine Einladungen haben. Wenn ein Raum Einladungen enthält, wenn ein neues Mitglied zu einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in seinem beständigen Chat-Client.
    
   - Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen Chat- **Protokoll aktivieren** , um das Chat-Protokoll zu kontrollieren. Wenn diese Option ausgewählt ist, werden Chatroom-Chats persistent; Andernfalls bleiben Chatnachrichten nicht erhalten. Wenn Compliance aktiviert ist, werden Chatroom-Chats unter Compliance gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen. Diese Option kann für Chatrooms verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit vorgesehen sind und keine Beibehaltung des Chat-Verlaufs erforderlich machen.
    
7. Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
   - Fügen Sie unter **Mitgliedschaft**im Abschnitt **zulässige Mitglieder** Benutzer und andere Active Directory-Domänendienst Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms, die der Kategorie angehören, hinzugefügt werden dürfen. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
   - Fügen Sie in der **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory-Prinzipale hinzu, die Mitgliedern zugeordnet sind, die aus dem Chatroom verweigert werden.
    
   - Fügen Sie unter **Mitgliedschaft**im Abschnitt **Creators** Benutzer und andere Active Directory-Prinzipale hinzu, die den Erstellern für die Kategorie zugeordnet sind. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Konfigurieren von Kategorien mithilfe von Windows PowerShell

Sie können Kategorien mithilfe der folgenden Windows PowerShell-Cmdlets konfigurieren:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Erstellen einer neuen Kategorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Konfigurieren von Einstellungen für eine vorhandene Kategorie  <br/> |
|Get-CsPersistentChatCategory  <br/> |Abrufen von Informationen über Kategorien  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Löschen einer Kategorie  <br/> |
   
Sie können die folgenden Parameter für Kategorien konfigurieren:
  
- EnableFileUpload. Ist dieser Parameter angegeben, können Dateien an die Chatrooms in dieser Kategorie hochgeladen werden.
    
- EnableInvitations. Ermöglicht Einladungen für die Kategorie. Benutzer in der AllowedMembers-Liste erhalten automatisch eine Einladung zum Beitritt zu einem neuen Chatroom, wenn der neue Chatroom erstellt wird.
    
- ChatHistory. Zum Aktivieren oder Deaktivieren der Funktion des Chatverlaufs.
    
- Creators. Führt die Benutzer auf, die zum Erstellen von Chatrooms in der Kategorie berechtigt sind.
    
- AllowedMembers. Führt die Benutzer auf, denen der Zugriff auf Chatrooms in der Kategorie gestattet wird.
    
- DeniedMembers. Führt die Benutzer auf, denen der Zugriff auf Chatrooms in der Kategorie nicht gestattet ist.
    
Umfassende Informationen über die Cmdlet-Syntax sowie alle Parameter finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Erstellen einer neuen Kategorie

Mithilfe des Cmdlets **New-CsPersistentChatCategory** können Sie eine neue Kategorie erstellen. Beispielsweise wird mit dem folgenden Befehl eine neue Kategorie mit dem Namen „HelpDesk“ im Pool atl-cs-001.contoso.com erstellt. In diesem Beispiel ist das Hochladen von Dateien aktiviert:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Konfigurieren einer vorhandenen Kategorie

Mithilfe des Cmdlets **Set-CsPersistentCategory** können Sie eine vorhandene Kategorie konfigurieren.
  
Der folgende Befehl gibt beispielsweise an, dass Benutzer1 ein AllowedMember und ein Ersteller ist, während User2 Zugriff auf die Räume in der Kategorie verweigert wird:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Informationen über Kategorien abrufen

Mithilfe des Cmdlets **Get-CsPersistentChatCategory** können Sie Informationen über Kategorien abrufen. Mit dem folgenden Befehl werden beispielsweise Informationen über alle Kategorien für den beständigen Chat in der Organisation zurückgegeben:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Löschen einer Kategorie

Mithilfe des Cmdlets **Remove-CsPersistentChatCategory** können Sie eine Kategorie löschen. Bevor Sie eine Kategorie löschen, müssen Sie zunächst alle darin befindlichen Chatrooms entweder löschen oder in eine neue Kategorie verschieben. Beispielsweise wird mit dem folgenden Befehl die Kategorie mit der Identität „atl-cs-001.contoso.com\helpdesk“ gelöscht:
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
