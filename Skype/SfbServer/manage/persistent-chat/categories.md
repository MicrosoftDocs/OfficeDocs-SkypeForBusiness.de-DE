---
title: Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Zusammenfassung: Informationen zum Verwalten von Serverkategorien für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 1785f541765075160573907955630ee395d4f9773daebff7895842689327a3ef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276750"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Kategorien des Servers für beständigen Chat in Skype for Business Server 2015 verwalten.
  
Eine Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. Eine Kategorie definiert einen Standardsatz von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen, die Chatrooms erstellen oder daran teilnehmen können. Chatroomkategorien enthalten Chatrooms, aber keine anderen Kategorien. In jeder Kategorie wird der Inhalt mithilfe von Metadaten beschrieben, z. B. Name und Beschreibung. Die Kategorie verfügt über Eigenschaften, die festgelegt werden können, um das Verhalten der chatrooms zu steuern, die zu ihr gehören. Beispielsweise, ob die Chatrooms Einladungen oder Dateiuploads zulassen oder den Chatverlauf enthalten. 
  
Das Erstellen und Verwalten von Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Als Administrator für den Server für beständigen Chat können Sie "AllowedMembers" und "Creators" für jede Kategorie sowie die Standardeinstellungen und Verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Wenn Sie beispielsweise die AllowedMembers der Kategorie auf contoso.com festlegen, können Sie eine beliebige Gruppe oder einen beliebigen Benutzer bei Contoso als Mitglied zu Chatrooms in dieser Kategorie hinzufügen. Wenn Sie die zulässigen Mitglieder in einer Kategorie auf "Vertrieb" festlegen, können nur Gruppen und Benutzer in dieser Verteilerliste als Mitglieder zu Chatrooms in dieser Kategorie hinzugefügt werden. Mit der Creators-Eigenschaft können Sie steuern, wer Chatrooms in dieser Kategorie erstellen kann. Nachdem der Chatroom erstellt wurde, kann jeder aus der Gruppe "AllowedMembers" als Manager für laufende Verwaltungsvorgänge in den Chatrooms festgelegt werden (z. B. Mitgliedschaftsänderungen und Genehmigung).
  
Das Definieren von AllowedMembers und Creators für eine Kategorie hat folgende Vorteile:
  
- Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.
    
- Ein Benutzer, der in der Liste Creators vorhanden ist, kann in der Kategorie neue Chatrooms erstellen. Wenn Sie ein System implementieren möchten, in dem eine eingeschränkte Anzahl von Mitarbeitern in der Organisation Chatrooms erstellen kann, kann dieses Steuerelement verwendet werden, um diese Anforderungen zu erfüllen. 
    
Benutzer, Organisationseinheiten (OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können Sie Benutzer, Organisationseinheiten und Benutzergruppen aus der Liste der zugelassenen Mitglieder der Kategorie als Chatroommanager und Mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen. 
  
Bevor Sie Kategorien konfigurieren, müssen Sie [die Kategorien für beständigen Chat, Chatrooms und Benutzerrollen in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)lesen.
  
Sie können Kategorien mithilfe der Systemsteuerung oder mit Windows PowerShell Cmdlets konfigurieren und verwalten.

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Konfigurieren von Kategorien mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für mehrere Bereitstellungen des Servers für beständigen Chat in der Dropdownliste den entsprechenden Pool aus.
    
4. Klicken Sie auf der Seite **Kategorie** auf **Neu** oder **Bearbeiten**.
    
5. Wählen Sie in **"Dienst auswählen"** den Dienst aus, der dem Serverpool für beständigen Chat entspricht, in dem die Kategorie erstellt werden muss. Der Dienst ist der Serverpool für beständigen Chat, den der Client für beständigen Chat verwendet, um zu identifizieren, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur einem Serverpool für beständigen Chat angehören und kann nicht in einen anderen Pool verschoben oder für diesen freigegeben werden.
    
6. Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Chatroomkategorie an.
    
   - Geben Sie unter **Beschreibung** eine ausführliche Beschreibung der Chatroomkategorie an (z. B. eine Chatroomkategorie für Contoso).
    
   - Um zu steuern, ob Einladungen für Chatrooms aktiviert werden können, die zu dieser Kategorie gehören, aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren.** Wenn diese Option ausgewählt ist, können Für Räume in dieser Kategorie Einladungen aktiviert oder deaktiviert werden. wenn dies deaktiviert ist, dürfen die Räume in dieser Kategorie keine Einladungen haben. Wenn ein Raum Einladungen eingeht und ein neues Mitglied zu einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in ihrem Client für beständigen Chat.
    
   - Um Dateiuploads in Chatrooms dieser Kategorie zu steuern, aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Ist diese Option aktiviert, können für die Chatrooms dieser Kategorie Dateiuploads aktiviert und deaktiviert werden. Ist die Option deaktiviert, sind Dateiuploads für die Chatrooms dieser Kategorie nicht zulässig.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Chatverlauf aktivieren** oder deaktivieren, um den Chatverlauf zu steuern. Wenn diese Option ausgewählt ist, werden Chatrooms beständig. andernfalls werden Chatnachrichten nicht beibehalten. Wenn die Kompatibilität aktiviert ist, werden Chatrooms in Der Compliance gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen. Diese Option kann für Chatrooms verwendet werden, die für Ad-hoc-Zusammenarbeiten in Echtzeit vorgesehen sind, für die kein Chatverlauf beibehalten werden muss.
    
7. Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
   - Fügen Sie in **"Mitgliedschaft"** im Abschnitt **"Zugelassene Mitglieder"** Benutzer und andere Active Directory Domain Services-Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms der Kategorie hinzugefügt werden dürfen. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
   - Fügen Sie in **"Mitgliedschaft"** im Abschnitt **"Abgelehnte Mitglieder"** Benutzer und andere Active Directory-Prinzipale hinzu, die Mitgliedern zugeordnet sind, denen aus dem Raum verweigert wird, oder entfernen Sie sie.
    
   - Fügen Sie in **"Mitgliedschaft"** im Abschnitt **"Ersteller"** Benutzer und andere Active Directory-Prinzipale hinzu, die den Erstellern für die Kategorie zugeordnet sind, oder entfernen Sie sie. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Konfigurieren von Kategorien mithilfe von Windows PowerShell

Sie können Kategorien mithilfe der folgenden Windows PowerShell Cmdlets konfigurieren:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Erstellen einer neuen Kategorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Konfigurieren von Einstellungen für eine vorhandene Kategorie  <br/> |
|Get-CsPersistentChatCategory  <br/> |Abrufen von Informationen zu Kategorien  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Entfernen einer Kategorie  <br/> |
   
Sie können die folgenden Parameter für Kategorien konfigurieren:
  
- EnableFileUpload. Ermöglicht das Hochladen von Dateien in die Chatrooms in der Kategorie.
    
- EnableInvitations. Aktiviert Einladungen für die Kategorie. Benutzer in der Liste "AllowedMembers" erhalten automatisch eine Einladung zum Beitreten zu einem neuen Chatroom zum Zeitpunkt der Erstellung des neuen Chatrooms.
    
- ChatHistory. Aktiviert oder deaktiviert das Chatverlaufsfeature.
    
- Schöpfer. Gibt die Benutzer an, die Chatrooms innerhalb der Kategorie erstellen dürfen.
    
- AllowedMembers. Gibt die Benutzer an, die auf Chatrooms innerhalb der Kategorie zugreifen dürfen.
    
- DeniedMembers. Führt die Benutzer auf, denen der Zugriff auf Chatrooms in der Kategorie nicht gestattet ist.
    
Vollständige Informationen zur Cmdlet-Syntax, einschließlich aller Parameter, finden Sie unter [Skype for Business Server 2015-Verwaltungsshell.](../management-shell.md)
  
### <a name="create-a-new-category"></a>Erstellen einer neuen Kategorie

Mit dem Cmdlet **"New-CsPersistentChatCategory"** können Sie eine neue Kategorie erstellen. Mit dem folgenden Befehl wird beispielsweise eine neue Kategorie namens "HelpDesk" im Pool atl-cs-001.contoso.com erstellt. In diesem Beispiel ist der Dateiupload aktiviert:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Konfigurieren einer vorhandenen Kategorie

Sie können eine vorhandene Kategorie mithilfe des Cmdlets **"Set-CsPersistentCategory"** konfigurieren.
  
Beispielsweise gibt der folgende Befehl an, dass Benutzer1 ein AllowedMember und ein Creator ist, während Benutzer2 der Zugriff auf die Räume in der Kategorie verweigert wird:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Abrufen von Informationen zu Kategorien

Mit dem Cmdlet **"Get-CsPersistentChatCategory"** können Sie Informationen zu Kategorien abrufen. Der folgende Befehl gibt beispielsweise Informationen für alle Kategorien für beständigen Chat in der Organisation zurück:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Entfernen einer Kategorie

Sie können eine Kategorie mithilfe des **Cmdlets "Remove-CsPersistentChatCategory"** entfernen. Bevor Sie eine Kategorie entfernen, müssen Sie zunächst entweder alle Chatrooms darunter löschen oder die Chatrooms in eine neue Kategorie verschieben. Mit dem folgenden Befehl wird beispielsweise die Kategorie mit dem Identitätswert "atl-cs-001.contoso.com\helpdesk" entfernt:
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
