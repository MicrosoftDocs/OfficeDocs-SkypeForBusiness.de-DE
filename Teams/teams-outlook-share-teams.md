---
title: Freigeben für Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über das Feature "Teams freigeben", mit dem Benutzer E-Mails und E-Mail-Anlagen von Outlook in beliebigen Chats oder Kanälen in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098221"
---
# <a name="share-to-teams-from-outlook"></a>Freigeben für Teams von Outlook

"Freigeben für Teams von Outlook (Für Teams freigeben) ermöglicht Benutzern das Teilen von E-Mails, einschließlich Anlagen, von Outlook in beliebige Chats oder Kanäle in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook add-in for Share to Teams 

Für das Feature Teams Freigeben für Benutzer ist ein Add-In für den Outlook. Dieses Add-In wird automatisch installiert, wenn sich ein Benutzer entweder bei der Teams Web App oder beim Teams Anmeldeclient anmeldet.

> [!NOTE]
> Lesen Sie unbedingt [Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) für Outlook in Exchange Online und [Clientzugriffsregeln in Exchange Online,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) um sicherzustellen, dass Ihre Add-Ins für Outlook funktionieren. Außerdem kann das Deaktivieren von verbundenen Funktionen verhindern, dass Add-Ins für Outlook ordnungsgemäß funktionieren. Weitere [Informationen finden Sie unter Verbundene Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Ihrem Unternehmen.  

Freigeben für Teams verwendet denselben Transportmechanismus wie beim Senden von E-Mails an einen Kanal. Für die Freigabe in Chats werden E-Mails (einschließlich E-Mail-Anlagen) in die Liste OneDrive. Für die Freigabe in Kanälen werden E-Mails und Anlagen in den **Ordner** E-Mail-Nachrichten in SharePoint.

Für das Outlook-Add-In für "Freigeben für Teams" wird der Anforderungssatz 1.7 verwendet, wie in der Dokumentation zu [Outlook-Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)beschrieben. Dieser enthält Details zu Outlook-Add-Ins, die Umgebungsanforderungen für Outlook-Add-Ins und die speziellen Outlook-Clients, die mit Anforderungssatz 1.7 unterstützt werden.

## <a name="enabling-or-disabling-share-to-teams"></a>Aktivieren oder Deaktivieren von "Freigeben für Teams

Das Outlook-Add-Ins "Freigeben für Teams" kann mithilfe der folgenden PowerShell-Cmdlets selektiv deaktiviert oder auf Benutzerbasis aktiviert werden.

> [!NOTE]
> Das Deaktivieren des Add-Ins ist erst möglich, nachdem das Add-In installiert wurde. Wenn Sie die Deaktivierung für alle Benutzer in Ihrem Mandanten erzwingen möchten, führen Sie ein Skript regelmäßig aus.

Führen Sie zum Deaktivieren des Add-Outlook, das von "Teilen für Benutzer Teams" verwendet wird, das [cmdlet aus, das hier zu finden ist.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Führen Sie zum Aktivieren des Add-Outlook, das von Share to Teams verwendet wird, das [cmdlet aus, das hier zu finden ist.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Browser und einmaliges Anmelden

Die Freigabe Teams -Clients im Web Outlook Outlook Desktopclients basiert auf einer Webbrowser-Webansicht. Details dazu, welche Clients welche bestimmten Browser verwenden, finden Sie unter von [Office-Add-Ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) verwendete Browser. 

> [!IMPORTANT]
> Für die Freigabe Teams Browser muss sowohl Cookies von Drittanbietern als auch der lokale Speicherzugriff aktiviert sein.

Die Freigabe für Teams verwendet einmaliges Anmelden (Single Sign-On, SSO), was bedeutet, dass die Benutzer ihre Anmeldeinformationen nicht angeben müssen, wenn sie das Add-In über "Freigeben" für Teams. SSO für Outlook im Web unterstützt https://outlook.office365.com/owa/extSSO.aspx und beantwortet https://outlook.office.com/owa/extSSO.aspx standardmäßig URLs. Für Vanity-Domänen müssen Administratoren die entsprechende Antwort-URL Azure Active Directory hinzufügen.