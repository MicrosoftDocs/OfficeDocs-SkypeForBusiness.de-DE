---
title: Für Teams freigeben
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über das Feature "Freigeben für Teams", mit dem Benutzer E-Mails und E-Mail-Anlagen von Outlook für jeden Chat oder Kanal in Teams freigeben können.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682026"
---
# <a name="share-to-teams-from-outlook"></a>Freigeben für Teams von Outlook

Die Freigabe für Teams von Outlook (Freigeben für Teams) ermöglicht Benutzern das Freigeben von E-Mails, einschließlich Anlagen, von Outlook zu jedem Chat oder Kanal in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook add-in for Share to Teams 

Das Feature "Für Teams freigeben" erfordert ein Add-In für Outlook. Dieses Add-In wird automatisch installiert, wenn sich ein Benutzer bei der Teams Web-App oder dem Teams Desktopclient anmeldet.

> [!NOTE]
> Achten Sie darauf[, Add-Ins auf Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) und [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) zu überprüfen, um sicherzustellen, dass Ihre Add-Ins für Outlook ordnungsgemäß funktionieren. Außerdem kann das Deaktivieren verbundener Erfahrungen verhindern, dass Add-Ins für Outlook ordnungsgemäß funktionieren. Weitere Informationen finden Sie [unter "Verbundene Erfahrungen in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)".  

"Für Teams freigeben" verwendet denselben Transportmechanismus wie beim Senden eines Kanals per E-Mail durch einen Benutzer. Für die Freigabe für Chats werden E-Mails (einschließlich E-Mail-Anlagen) in die OneDrive des Absenders kopiert. Für die Freigabe für Kanäle werden E-Mails und Anlagen in den Ordner "**E-Mail-Nachrichten**" in SharePoint kopiert.

Das Outlook-Add-In für "Freigeben für Teams" verwendet den Anforderungssatz 1.7, wie in [Outlook Dokumentation zu Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) beschrieben, die Details zu Outlook-Add-Ins, Umgebungsanforderungen für Outlook-Add-Ins und die spezifischen Outlook Clients enthält, die mit Anforderungssatz 1.7 unterstützt werden.

## <a name="enabling-or-disabling-share-to-teams"></a>Aktivieren oder Deaktivieren der Freigabe für Teams

Das Outlook-Add-In für "Freigeben für Teams" kann mithilfe der folgenden PowerShell-Cmdlets selektiv deaktiviert oder aktiviert werden.

> [!NOTE]
> Das Deaktivieren des Add-Ins ist erst möglich, nachdem das Add-In installiert wurde. Wenn Sie die Deaktivierung für alle Benutzer in Ihrem Mandanten erzwingen möchten, führen Sie regelmäßig ein Skript aus.

Um das Add-In für Outlook zu deaktivieren, das von Share zum Teams verwendet wird, führen Sie das [hier gefundene Cmdlet](/powershell/module/exchange/disable-app) aus.

Um das Add-In für Outlook zu aktivieren, das von Share zum Teams verwendet wird, führen Sie das [hier gefundene Cmdlet](/powershell/module/exchange/enable-app) aus.

## <a name="browsers-and-single-sign-on"></a>Browser und einmaliges Anmelden

Die Freigabe für Teams in Outlook im Web und Outlook Desktopclients basiert auf einem Browser-WebView. Details dazu, welche Clients welche bestimmten Browser verwenden, finden Sie [in den von Office-Add-Ins verwendeten](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) Browsern. 

> [!IMPORTANT]
> Die Freigabe für Teams erfordert, dass sowohl Cookies von Drittanbietern als auch der lokale Speicherzugriff für die Browser der Benutzer aktiviert werden.

Die Freigabe für Teams verwendet einmaliges Anmelden (Single Sign-On, SSO), was bedeutet, dass Benutzer ihre Anmeldeinformationen nicht angeben müssen, wenn sie das Add-In über "Freigeben" verwenden, um Teams. SSO für Outlook im Web unterstützt <https://outlook.office365.com/owa/extSSO.aspx> urLs standardmäßig und <https://outlook.office.com/owa/extSSO.aspx> antwortet darauf. Für Vanity-Domänen müssen Administratoren die entsprechende Azure Active Directory Antwort-URL hinzufügen.
