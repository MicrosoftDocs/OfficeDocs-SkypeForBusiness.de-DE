---
title: Freigeben für Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über das Feature "Teams freigeben", mit dem Benutzer E-Mails und E-Mail-Anlagen von Outlook in beliebigen Chats oder Kanälen in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd8e31f83927c459f4a188f7316d000c13e5ef91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774265"
---
# <a name="share-to-teams-from-outlook"></a>Freigeben für Teams von Outlook

Mit "Freigeben für Teams von Outlook (Für Teams freigeben) können Benutzer E-Mails, einschließlich Anlagen, von Outlook an beliebige Chats oder Kanäle in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook add-in for Share to Teams 

Das Feature "Teams Freigeben für Benutzer" erfordert ein Add-In für Outlook. Dieses Add-In wird automatisch installiert, sobald sich ein Benutzer entweder bei der Teams Web App oder beim Teams Anmeldeclient anmeldet.

> [!NOTE]
> Lesen Sie unbedingt [Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) für Outlook in Exchange Online und [Clientzugriffsregeln in Exchange Online,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) um sicherzustellen, dass Ihre Add-Ins ordnungsgemäß Outlook funktionieren. Außerdem kann das Deaktivieren von verbundenen Funktionen verhindern, dass Add-Ins für Outlook ordnungsgemäß funktionieren. Weitere [Informationen finden Sie unter Verbundene Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Ihrem Unternehmen.  

Freigeben für Teams verwendet denselben Transportmechanismus wie beim Senden von E-Mails an einen Kanal. Für die Freigabe in Chats werden E-Mails (einschließlich E-Mail-Anlagen) in die Liste des OneDrive. Für die Freigabe in Kanälen werden E-Mails und Anlagen in den **Ordner** E-Mail-Nachrichten in SharePoint.

Für das Outlook-Add-In für "Freigeben für Teams" wird der Anforderungssatz 1.7 verwendet, wie in der Dokumentation zu [Outlook-Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)beschrieben. Dieser enthält Details zu Outlook-Add-Ins, Die Umgebungsanforderungen für Outlook-Add-Ins und die speziellen Outlook-Clients, die mit Anforderungssatz 1.7 unterstützt werden.

## <a name="enabling-or-disabling-share-to-teams"></a>Aktivieren oder Deaktivieren von "Freigeben für Teams

Das Outlook-Add-In für "Freigeben für Teams" kann mithilfe der folgenden PowerShell-Cmdlets selektiv deaktiviert oder pro Benutzer aktiviert werden.

> [!NOTE]
> Das Deaktivieren des Add-Ins ist erst möglich, nachdem das Add-In installiert wurde. Wenn Sie die Deaktivierung für alle Benutzer in Ihrem Mandanten erzwingen möchten, führen Sie ein Skript regelmäßig aus.

Führen Sie zum Deaktivieren des Add-Outlook, das von "Freigeben für Teams" verwendet wird, das [cmdlet aus, das hier zu finden ist.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Führen Sie zum Aktivieren des Add-Outlook, das von Share to Teams verwendet wird, das [cmdlet aus, das hier zu finden ist.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Browser und einmaliges Anmelden

Die Freigabe Teams Browser basiert sowohl in Outlook im Web als Outlook Desktopclients auf einem Browserwebview. Unter [Von den Add-Office verwendete](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) Browser finden Sie Weitere Informationen dazu, welche Clients welche bestimmten Browser verwenden. 

> [!IMPORTANT]
> Die Freigabe Teams Browsern erfordert, dass sowohl Cookies von Drittanbietern als auch der lokale Speicherzugriff für die Browser der Benutzer aktiviert sind.

Bei der Freigabe für Teams wird einmaliges Anmelden (Single Sign-On, SSO) verwendet, was bedeutet, dass die Benutzer ihre Anmeldeinformationen nicht angeben müssen, wenn sie das Add-In über "Freigeben" für Teams. SSO für Outlook im Web https://outlook.office365.com/owa/extSSO.aspx unterstützt und https://outlook.office.com/owa/extSSO.aspx beantwortet standardmäßig URLs. Für Vanity-Domänen müssen Administratoren die entsprechende Antwort-URL Azure Active Directory hinzufügen.