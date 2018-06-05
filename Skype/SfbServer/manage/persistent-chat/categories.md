---
title: Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Persistent Chat Server-Kategorien in Skype für Business Server 2015.'
ms.openlocfilehash: 418cdc395a611c880da5b9455c10367fe19c6843
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568619"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Verwalten von Persistent Chat Server-Kategorien in Skype für Business Server 2015.
  
Eine Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. Durch eine Kategorie wird ein Standardsatz an Zugriffssteuerungslisten (ACLs) definiert, mit dem die Benutzer und Benutzergruppen gesteuert werden, die Chatrooms erstellen oder diesen beitreten können. Chatroomkategorien enthalten Chatrooms, jedoch keine anderen Kategorien. Jede Kategorie beschreibt ihren Inhalt mithilfe von Metadaten wie „Name“ und „Beschreibung“. Die Kategorie besitzt Eigenschaften, die im Hinblick auf die Steuerung des Verhaltens der zu ihr gehörenden Chatrooms eingerichtet werden können, beispielsweise ob die Chatrooms Einladungen oder Dateiuploads erlauben oder einen Chatverlauf beinhalten. 
  
Chatrooms können mit der Verwendung der richtigen Kategorien viel einfacher erstellt und verwaltet werden. Als Administrator für einen Server für beständigen Chat können Sie für jede Kategorie „Zugelassene Mitglieder“ und „Ersteller“ definieren, aber auch die Standardeinstellung für Chatrooms sowie Verhaltensweisen, die für alle in der Kategorie erstellen Chatrooms gelten. Angenommen, wenn Sie die Kategorie AllowedMembers auf "contoso.com" festlegen, können Sie eine beliebige Gruppen- oder Benutzernamen bei Contoso als Mitglied in Chatrooms in dieser Kategorie hinzufügen. Wenn Sie als Eigenschaft der „zugelassenen Mitglieder“ einer Kategorie „Verkauf“ festlegen, können nur Gruppen und Benutzer in dieser Verteilerliste als Mitglieder für Chatrooms in dieser Kategorie hinzufügt werden. Die Eigenschaft „Ersteller“ ermöglicht Ihnen zu kontrollieren, wer Chatrooms in dieser Kategorie erstellen kann. Nach der Erstellung des Chatrooms kann jeder aus der Gruppe „Zugelassene Mitglieder“ als Manager für laufende Verwaltungsaufgaben in den Chatrooms bestimmt werden (beispielsweise bei Änderung und Genehmigung einer Mitgliedschaft).
  
Das Definieren von „zugelassenen Mitgliedern“ und „Erstellern“ für eine Kategorie hat folgende Vorteile:
  
- Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.
    
- Ein Benutzer, der in der Liste „Ersteller“ vorhanden ist, kann in der betreffenden Kategorie neue Chatrooms erstellen. Falls Sie ein System implementieren möchten, in dem nur eine beschränkte Anzahl von Mitarbeitern der Organisation Chatrooms erstellen kann, können Sie dies nach diesem Verfahren realisieren. 
    
Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die in einer Kategorie als „Ersteller“ festgelegt werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in dieser Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können Sie Benutzer, Organisationseinheiten und Benutzergruppen in der Liste „Zugelassene Mitglieder“ der Kategorie als Chatroommanager und Mitglieder auswählen, die den Chatroom verwalten und an diesem teilnehmen. 
  
Bevor Sie Kategorien konfigurieren, müssen Sie unbedingt [Persistent Chatkategorien, Chatrooms, und Benutzerrollen in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)vertraut zu machen.
  
Sie können Kategorien über die Systemsteuerung oder mit Windows PowerShell-Cmdlets konfigurieren und verwalten.
  
## <a name="configure-categories-by-using-the-control-panel"></a>Konfigurieren von Kategorien mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für Bereitstellungen mit mehreren Persistent Chat Server Pool den entsprechenden Pool aus der Dropdownliste aus.
    
4. Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten**.
    
5. Wählen Sie unter **Wählen Sie einen Dienst**Dienst entspricht dem Persistent Chat Server Pool, auf dem die Kategorie erstellt werden soll. Der Dienst ist die Persistent Chat-Server-Pool, die der Persistent Chat-Client zum Identifizieren verwendet der pool-Kategorie gehört. Eine Kategorie werden kann nur einen Persistent Chat Server Pool angehören und nicht in verschoben oder für einen anderen Pool freigegeben.
    
6. Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.
    
   - Geben Sie unter **Beschreibung** Einzelheiten zur Raumkategorie an (z. B. eine Raumkategorie für Contoso).
    
   - Klicken Sie zum Steuern, ob Einladungen für Chatrooms aktiviert werden können, die dieser Kategorie angehören, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Einladungen zu aktivieren** . Wenn ausgewählt haben, können in dieser Kategorie Chatrooms Einladungen aktiviert oder deaktiviert haben; Wenn deaktiviert, dürfen die Chatrooms in dieser Kategorie nicht Einladungen haben. Wenn ein Chatroom Einladungen weist auf, wenn ein neues Mitglied in einem Raum hinzugefügt wird, ruft er eine Benachrichtigung über die neuen Raums in ihrem Persistent Chat-Client ab.
    
   - Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.
    
   - Um den Chatverlauf zu kontrollieren, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **aktivieren den Chatverlauf** . Wenn Sie ausgewählt haben, werden Raum Chats persistent. Andernfalls werden Chatnachrichten nicht beibehalten. Wenn Kompatibilität aktiviert ist, Raum Chats werden in Compliance gespeichert, aber Benutzer werden nicht auf ältere Nachrichten zugreifen. Diese Option kann verwendet werden, für Räume vorgesehen für in Echtzeit, ad-hoc-Zusammenarbeit, die den Chatverlauf beibehalten werden nicht benötigen.
    
7. Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
   - Unter **Mitgliedschaft**im Abschnitt **Zugelassene Mitglieder** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Domänendienste Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.), die als Mitglieder des Chatrooms hinzugefügt werden dürfen für die Kategorie gehören. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
   - **Die Mitgliedschaft**in den Abschnitt **abgelehnten Mitglieder** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Prinzipale wird diesen Raum Mitgliedern zugeordnet sind.
    
   - **Die Mitgliedschaft**in den Abschnitt **Ersteller** hinzufügen oder Entfernen von Benutzern und anderen Active Directory-Prinzipale Ersteller für die Kategorie zugeordnet. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Konfigurieren von Kategorien mithilfe von Windows PowerShell

Sie können Kategorien mithilfe der folgenden Windows PowerShell-Cmdlets konfigurieren:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|"New-cspersistentchatcategory"  <br/> |Erstellen einer neuen Kategorie  <br/> |
|"Set-cspersistentchatcategory"  <br/> |Konfigurieren von Einstellungen für eine vorhandene Kategorie  <br/> |
|"Get-cspersistentchatcategory"  <br/> |Abrufen von Informationen über Kategorien  <br/> |
|"Remove-cspersistentchatcategory"  <br/> |Löschen einer Kategorie  <br/> |
   
Sie können die folgenden Parameter für Kategorien konfigurieren:
  
- EnableFileUpload. Ist dieser Parameter angegeben, können Dateien an die Chatrooms in dieser Kategorie hochgeladen werden.
    
- EnableInvitations. Ermöglicht es Einladungen für die Kategorie ein. Benutzer in der Liste AllowedMembers erhalten automatisch eine Einladung zur Teilnahme an einer neuen Chatroom zur Zeit, dass die neuen Raums erstellt wird.
    
- ChatHistory. Zum Aktivieren oder Deaktivieren der Funktion des Chatverlaufs.
    
- Creators. Führt die Benutzer auf, die zum Erstellen von Chatrooms in der Kategorie berechtigt sind.
    
- AllowedMembers. Führt die Benutzer auf, denen der Zugriff auf Chatrooms in der Kategorie gestattet wird.
    
- DeniedMembers. Führt die Benutzer auf, denen der Zugriff auf Chatrooms in der Kategorie nicht gestattet ist.
    
Umfassende Informationen zum Cmdlet Syntax, einschließlich aller Parameter finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Erstellen einer neuen Kategorie

Mithilfe des Cmdlets **New-CsPersistentChatCategory** können Sie eine neue Kategorie erstellen. Beispielsweise wird mit dem folgenden Befehl eine neue Kategorie mit dem Namen „HelpDesk“ im Pool atl-cs-001.contoso.com erstellt. In diesem Beispiel ist das Hochladen von Dateien aktiviert:
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Konfigurieren einer vorhandenen Kategorie

Mithilfe des Cmdlets **Set-CsPersistentCategory** können Sie eine vorhandene Kategorie konfigurieren.
  
Der folgende Befehl gibt beispielsweise an, dass diese user1 ist ein AllowedMember und Creator während Benutzer2 Zugriff auf die Chatrooms in der Kategorie verweigert wird:
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Informationen über Kategorien abrufen

Mithilfe des Cmdlets **Get-CsPersistentChatCategory** können Sie Informationen über Kategorien abrufen. Mit dem folgenden Befehl werden beispielsweise Informationen über alle Kategorien für den beständigen Chat in der Organisation zurückgegeben:
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Löschen einer Kategorie

Mithilfe des Cmdlets **Remove-CsPersistentChatCategory** können Sie eine Kategorie löschen. Bevor Sie eine Kategorie löschen, müssen Sie zunächst alle darin befindlichen Chatrooms entweder löschen oder in eine neue Kategorie verschieben. Beispielsweise wird mit dem folgenden Befehl die Kategorie mit der Identität „atl-cs-001.contoso.com\helpdesk“ gelöscht:
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```