---
title: Für Teams freigeben
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über das Feature "In Teams teilen", mit dem Benutzer E-Mails und E-Mail-Anlagen aus Outlook für jeden Chat oder Kanal in Teams freigeben können.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2ac9a38e16000829b391e77dffdd718ed349299
ms.sourcegitcommit: f5546acf02ec644225f6d0fb41f38b1912da6adf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2022
ms.locfileid: "66952759"
---
# <a name="share-to-teams-from-outlook"></a>Freigeben für Teams aus Outlook

Mithilfe von Outlook (Für Teams freigeben) können Benutzer E-Mails, einschließlich Anlagen, aus Outlook für jeden Chat oder Kanal in Teams freigeben.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook-Add-In für die Freigabe in Teams 

Das Feature "Für Teams freigeben" erfordert ein Add-In für Outlook. Dieses Add-In wird automatisch installiert, wenn sich ein Benutzer bei der Teams-Web-App oder dem Teams-Desktopclient anmeldet.

> [!NOTE]
> Achten Sie darauf[, Add-Ins für Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) und [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) zu überprüfen, um sicherzustellen, dass Ihre Add-Ins für Outlook ordnungsgemäß funktionieren. Außerdem kann das Deaktivieren verbundener Erfahrungen verhindern, dass Add-Ins für Outlook ordnungsgemäß funktionieren. Weitere Informationen finden Sie [unter "Verbundene Erfahrungen in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) ". Freigegebene Postfächer werden vom Add-In nicht unterstützt. 

Die Freigabe für Teams verwendet den gleichen Transportmechanismus wie bei einem Benutzer per E-Mail an einen Kanal. Für die Freigabe für Chats werden E-Mails (einschließlich E-Mail-Anlagen) auf das OneDrive des Absenders kopiert. Für die Freigabe für Kanäle werden E-Mails und Anlagen in den **Ordner Email Nachrichten** in SharePoint kopiert.

Das Outlook-Add-In für "Freigeben für Teams" verwendet den Anforderungssatz 1.7, wie in der [Dokumentation zu Outlook-Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) beschrieben, der Details zu Outlook-Add-Ins, Umgebungsanforderungen für Outlook-Add-Ins und die spezifischen Outlook-Clients enthält, die mit Anforderungssatz 1.7 unterstützt werden.

## <a name="enabling-or-disabling-share-to-teams"></a>Aktivieren oder Deaktivieren der Freigabe für Teams

Das Outlook-Add-In für "Für Teams freigeben" kann mithilfe der folgenden PowerShell-Cmdlets selektiv deaktiviert oder benutzerspezifisch aktiviert werden.

> [!NOTE]
> Das Deaktivieren des Add-Ins ist erst möglich, nachdem das Add-In installiert wurde. Wenn Sie die Deaktivierung für alle Benutzer in Ihrem Mandanten erzwingen möchten, führen Sie regelmäßig ein Skript aus.

Führen Sie das [hier gefundene Cmdlet](/powershell/module/exchange/disable-app) aus, um das add-in für Outlook zu deaktivieren, das von Share to Teams verwendet wird.

Führen Sie das [hier gefundene Cmdlet](/powershell/module/exchange/enable-app) aus, um das add-in für Outlook zu aktivieren, das von Share to Teams verwendet wird.

## <a name="browsers-and-single-sign-on"></a>Browser und einmaliges Anmelden

Die Freigabe für Microsoft Teams in Outlook im Web- und Outlook-Desktopclients basiert auf einem Browser-WebView. Details dazu, welche Clients welche bestimmten Browser verwenden, finden [Sie in den von Office-Add-Ins verwendeten](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) Browsern. 

> [!IMPORTANT]
> Die Freigabe für Teams erfordert, dass sowohl Cookies von Drittanbietern als auch der lokale Speicherzugriff für die Browser der Benutzer aktiviert werden.

Die Freigabe für Teams verwendet einmaliges Anmelden (Single Sign-On, SSO), was bedeutet, dass Benutzer ihre Anmeldeinformationen nicht angeben müssen, wenn sie das Add-In über "Für Teams freigeben" verwenden. SSO für Outlook im Web unterstützt <https://outlook.office365.com/owa/extSSO.aspx> urLs standardmäßig und <https://outlook.office.com/owa/extSSO.aspx> antwortet darauf. Für Vanity-Domänen müssen Administratoren die entsprechende Azure Active Directory-Antwort-URL hinzufügen.
