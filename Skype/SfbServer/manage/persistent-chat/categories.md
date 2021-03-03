---
title: Verwalten von Kategorien auf dem Server für beständigen Chat in Skype for Business Server 2015
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
description: 'Zusammenfassung: Informationen zum Verwalten von Kategorien für den Server für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815125"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Kategorien im Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Kategorien für den Server für beständigen Chat in Skype for Business Server 2015 verwalten.
  
Eine Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. Eine Kategorie definiert einen Standardsatz von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen, die Chatrooms erstellen oder beitreten können. Chatroomkategorien enthalten Chatrooms, aber keine anderen Kategorien. In jeder Kategorie wird der Inhalt mithilfe von Metadaten beschrieben, z. B. Name und Beschreibung. Die Kategorie verfügt über Eigenschaften, die festgelegt werden können, um das Verhalten der ihr gehörenden Chatrooms zu steuern. Beispielsweise, ob die Chatrooms Einladungen oder Dateiuploads zulassen oder den Chatverlauf enthalten. 
  
Das Erstellen und Verwalten von Chatrooms ist mit der richtigen Verwendung von Kategorien wesentlich einfacher. Als Administrator für den Server für beständigen Chat können Sie "AllowedMembers" und "Creators" für jede Kategorie sowie die Standardeinstellungen und Verhaltensweisen für Chatrooms definieren, die auf alle in der Kategorie erstellten Chatrooms angewendet werden. Wenn Sie beispielsweise die "AllowedMembers" der Kategorie auf contoso.com festlegen, können Sie beliebige Gruppen oder Benutzer bei Contoso als Mitglied zu Chatrooms in dieser Kategorie hinzufügen. Wenn Sie die zulässigen Mitglieder für eine Kategorie auf "Vertrieb" festlegen, können nur Gruppen und Benutzer in dieser Verteilerliste chatrooms in dieser Kategorie als Mitglieder hinzugefügt werden. Mit der Eigenschaft "Creators" können Sie steuern, wer Chatrooms in dieser Kategorie erstellen kann. Nachdem der Chatroom erstellt wurde, kann jeder aus der Gruppe "AllowedMembers" als Manager für laufende Verwaltungsvorgänge in den Chatrooms festgelegt werden (z. B. Mitgliedschaftsänderungen und Genehmigung).
  
Das Definieren von AllowedMembers und Creators für eine Kategorie hat folgende Vorteile:
  
- Alle in dieser Kategorie enthaltenen Chatrooms unterliegen den auf Kategorieebene festgelegten Einschränkungen. Hierdurch können Sie Chatrooms auf der Grundlage von Unternehmensanforderungen und Zugangsrichtlinien isolieren.
    
- Ein Benutzer, der in der Liste Creators vorhanden ist, kann in der Kategorie neue Chatrooms erstellen. Wenn Sie ein System implementieren möchten, in dem eine eingeschränkte Anzahl von Mitarbeitern in der Organisation Chatrooms erstellen kann, kann dieses Steuerelement verwendet werden, um diese Anforderungen zu erfüllen. 
    
Benutzer, Organisationseinheiten (OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können Sie Benutzer, Organisationsgruppen und Benutzergruppen aus der Liste "AllowedMembers" der Kategorie als Chatroommanager und -mitglieder auswählen, um den Chatroom zu verwalten und daran teilzunehmen. 
  
Lesen Sie vor dem Konfigurieren von Kategorien unbedingt die Kategorien für beständigen Chat, Chatrooms und Benutzerrollen [in Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)
  
Sie können Kategorien mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell verwalten.

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Konfigurieren von Kategorien mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für mehrere Bereitstellungen des Pools für beständigen Chat in der Dropdownliste den entsprechenden Pool aus.
    
4. Klicken Sie auf der Seite **Kategorie** auf **Neu** oder **Bearbeiten**.
    
5. Wählen **Sie in "Dienst auswählen"** den Dienst aus, der dem Serverpool für beständigen Chat entspricht, für den die Kategorie erstellt werden muss. Der Dienst ist der Serverpool für beständigen Chat, den der Client für beständigen Chat verwendet, um zu ermitteln, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur zu einem Pool für den Server für beständigen Chat gehören und kann nicht in einen anderen Pool verschoben oder für diesen freigegeben werden.
    
6. Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Chatroomkategorie an.
    
   - Geben Sie unter **Beschreibung** eine ausführliche Beschreibung der Chatroomkategorie an (z. B. eine Chatroomkategorie für Contoso).
    
   - Um zu steuern, ob Einladungen für Chatrooms aktiviert werden können, die zu dieser Kategorie gehören, aktivieren oder aktivieren Sie das Kontrollkästchen **Einladungen** aktivieren. Wenn diese Option ausgewählt ist, können Räume in dieser Kategorie Einladungen ein- oder ausschalten. Wenn sie nicht mehr angezeigt werden, dürfen die Räume in dieser Kategorie keine Einladungen haben. Wenn ein Raum Einladungen hat, erhält er beim Hinzufügen eines neuen Mitglieds zu einem Raum eine Benachrichtigung über den neuen Raum im Client für beständigen Chat.
    
   - Um Dateiuploads in Chatrooms dieser Kategorie zu steuern, aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Ist diese Option aktiviert, können für die Chatrooms dieser Kategorie Dateiuploads aktiviert und deaktiviert werden. Ist die Option deaktiviert, sind Dateiuploads für die Chatrooms dieser Kategorie nicht zulässig.
    
   - Aktivieren oder löschen Sie das Kontrollkästchen "Chatverlauf aktivieren", um den **Chatverlauf** zu steuern. Wenn diese Option ausgewählt ist, werden Chatrooms dauerhaft. Andernfalls werden Chatnachrichten nicht beibehalten. Wenn die Kompatibilität aktiviert ist, werden Chatrooms in der Compliance gespeichert, benutzer können jedoch nicht auf ältere Nachrichten zugreifen. Diese Option kann für Chatrooms verwendet werden, die für Ad-hoc-Zusammenarbeiten in Echtzeit bestimmt sind, für die kein Chatverlauf beibehalten werden muss.
    
7. Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
   - Fügen Sie in  "Mitgliedschaft" im Abschnitt "Zulässige Mitglieder" Benutzer und andere Active Directory-Domänendienste-Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten und so weiter) hinzu, die als Mitglieder von Chatrooms hinzugefügt werden dürfen, die zur Kategorie gehören. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
   - Fügen Sie in  **der** Mitgliedschaft im Abschnitt "Abgelehnte Mitglieder" Benutzer und andere Active Directory-Prinzipale hinzu oder entfernen Sie diese, die Mitgliedern zugeordnet sind, die aus dem Raum verweigert wurden.
    
   - Fügen **Sie in der** Mitgliedschaft im Abschnitt **"Creators"** Benutzer und andere Active Directory-Prinzipale hinzu, die Erstellern für die Kategorie zugeordnet sind, oder entfernen Sie diese. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Konfigurieren von Kategorien mithilfe von Windows PowerShell

Sie können Kategorien mithilfe der folgenden cmdlets Windows PowerShell konfigurieren:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Erstellen einer neuen Kategorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Konfigurieren von Einstellungen für eine vorhandene Kategorie  <br/> |
|Get-CsPersistentChatCategory  <br/> |Abrufen von Informationen zu Kategorien  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Entfernen einer Kategorie  <br/> |
   
Sie können die folgenden Parameter für Kategorien konfigurieren:
  
- EnableFileUpload. Ermöglicht Dateiuploads in die Chatrooms in der Kategorie.
    
- EnableInvitations. Aktiviert Einladungen für die Kategorie. Benutzer in der Liste "AllowedMembers" erhalten beim Erstellen des neuen Chatrooms automatisch eine Einladung zum Beitreten zu einem neuen Chatroom.
    
- ChatHistory. Aktiviert oder deaktiviert die Chatverlaufsfunktion.
    
- Ersteller. Gibt die Benutzer an, die Chatrooms innerhalb der Kategorie erstellen dürfen.
    
- AllowedMembers. Gibt die Benutzer an, die auf Chatrooms innerhalb der Kategorie zugreifen dürfen.
    
- DeniedMembers. Führt die Benutzer auf, denen der Zugriff auf Chatrooms in der Kategorie nicht gestattet ist.
    
Vollständige Informationen zur Cmdletsyntax, einschließlich aller Parameter, finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Erstellen einer neuen Kategorie

Mit dem Cmdlet **"New-CsPersistentChatCategory"** können Sie eine neue Kategorie erstellen. Der folgende Befehl erstellt beispielsweise eine neue Kategorie mit dem Namen "HelpDesk" im atl-cs-001.contoso.com. In diesem Beispiel ist der Dateiupload aktiviert:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Konfigurieren einer vorhandenen Kategorie

Sie können eine vorhandene Kategorie mithilfe des **Cmdlets "Set-CsPersistentCategory"** konfigurieren.
  
Der folgende Befehl gibt beispielsweise an, dass Benutzer1 ein "AllowedMember" und ein "Creator" ist, während Benutzer2 der Zugriff auf die Räume in der Kategorie verweigert wird:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Informationen zu Kategorien erhalten

Mithilfe des Cmdlets **"Get-CsPersistentChatCategory"** können Sie Informationen zu Kategorien erhalten. Der folgende Befehl gibt beispielsweise Informationen zu allen Kategorien für den beständigen Chat in der Organisation zurück:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Entfernen einer Kategorie

Sie können eine Kategorie mithilfe des Cmdlets **"Remove-CsPersistentChatCategory"** entfernen. Bevor Sie eine Kategorie entfernen, müssen Sie zuerst alle Chatrooms löschen oder die Chatrooms in eine neue Kategorie verschieben. Der folgende Befehl entfernt beispielsweise die Kategorie mit der Identität "atl-cs-001.contoso.com\helpdesk":
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
