---
title: Freigeben für Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 'Erfahren Sie mehr über das Feature "Freigeben für Teams", mit dem Benutzer E-Mails und E-Mail-Anlagen von Outlook in beliebigen Chats oder Kanälen in Teams.'
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="share-to-teams-from-outlook"></a>Freigeben für Teams von Outlook

Mit "Freigeben für Teams von Outlook (Für Teams freigeben) können Benutzer E-Mails, einschließlich Anlagen, von Outlook an beliebige Chats oder Kanäle in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook add-in for Share to Teams 

Für das Feature Teams Freigeben für Benutzer ist ein Add-In für den Outlook. Dieses Add-In wird automatisch installiert, wenn sich ein Benutzer entweder bei der Teams Web App oder beim Teams Anmeldeclient anmeldet.

> [!NOTE]
> Lesen Sie unbedingt [Add-Ins für Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) und [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules), um sicherzustellen, dass Ihre Add-Ins für Outlook funktionieren. Außerdem kann das Deaktivieren von verbundenen Funktionen verhindern, dass Add-Ins für Outlook ordnungsgemäß funktionieren. Weitere [Informationen finden Sie unter Verbundene Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Ihrem Unternehmen.  

Freigeben für Teams verwendet denselben Transportmechanismus wie beim Senden von E-Mails an einen Kanal. Für die Freigabe in Chats werden E-Mails (einschließlich E-Mail-Anlagen) in die Liste OneDrive. Für die Freigabe in Kanälen werden E-Mails und Anlagen in **den Ordner** E-Mail-Nachrichten in SharePoint.

Das Outlook-Add-In für "Freigeben für Teams" verwendet den Anforderungssatz 1.7, wie in der Dokumentation zu [Outlook-Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) beschrieben. Dieser enthält Details zu Outlook-Add-Ins, die Umgebungsanforderungen für Outlook-Add-Ins und die speziellen Outlook-Clients, die mit Anforderungssatz 1.7 unterstützt werden.

## <a name="enabling-or-disabling-share-to-teams"></a>Aktivieren oder Deaktivieren von "Freigeben für Teams

Das Outlook-Add-In für "Freigeben für Teams kann mithilfe der folgenden PowerShell-Cmdlets selektiv deaktiviert oder pro Benutzer aktiviert werden.

> [!NOTE]
> Das Deaktivieren des Add-Ins ist erst möglich, nachdem das Add-In installiert wurde. Wenn Sie die Deaktivierung für alle Benutzer in Ihrem Mandanten erzwingen möchten, führen Sie ein Skript regelmäßig aus.

Führen Sie zum Deaktivieren des Add-Outlook, das von "Freigeben für Teams" verwendet wird, das hier [gefundene Cmdlet aus](/powershell/module/exchange/disable-app?view=exchange-ps). 

Zum Aktivieren des Add-Ins für Outlook, das von "Freigeben für Teams" verwendet wird, führen Sie das hier [gefundene Cmdlet aus](/powershell/module/exchange/enable-app?view=exchange-ps).

## <a name="browsers-and-single-sign-on"></a>Browser und einmaliges Anmelden

Die Freigabe Teams Browser basiert sowohl in Outlook im Web als Outlook Desktopclients auf einem Webbrowser-WebView-System. Unter [Browser, die von Office-Add-Ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) verwendet werden, finden Sie Details dazu, welche Clients welche bestimmten Browser verwenden. 

> [!IMPORTANT]
> Für die Freigabe Teams Browser muss sowohl Cookies von Drittanbietern als auch der lokale Speicherzugriff aktiviert sein.

Die Freigabe für Teams verwendet einmaliges Anmelden (Single Sign-On, SSO), was bedeutet, dass die Benutzer ihre Anmeldeinformationen nicht angeben müssen, wenn sie das Add-In über "Freigeben" für Teams. SSO für Outlook im Web standardmäßig https://outlook.office365.com/owa/extSSO.aspx URLs https://outlook.office.com/owa/extSSO.aspx unterstützt und beantwortet. Für Vanity-Domänen müssen Administratoren die entsprechende Antwort-URL Azure Active Directory hinzufügen.