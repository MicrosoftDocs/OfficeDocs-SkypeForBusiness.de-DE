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
description: Erfahren Sie mehr über das Feature Für Teams freigeben, mit dem Benutzer E-Mails und E-Mail-Anlagen aus Outlook in jedem Chat oder Kanal in Teams freigeben können.
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
# <a name="share-to-teams-from-outlook"></a>Freigeben in Teams aus Outlook

Die Freigabe in Teams über Outlook (Freigeben für Teams) ermöglicht Benutzern das Teilen von E-Mails, einschließlich Anlagen, von Outlook in beliebige Chats oder Kanäle in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook-Add-In für "Für Teams freigeben" 

Für das Feature Für Teams freigeben ist ein Add-In für Outlook erforderlich. Dieses Add-In wird automatisch installiert, wenn sich ein Benutzer bei der Teams Web App oder dem Teams-Desktopclient anmeldet.

> [!NOTE]
> Überprüfen Sie die [Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) für Outlook in Exchange Online und [die Clientzugriffsregeln in Exchange Online,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) um sicherzustellen, dass Ihre Add-Ins für Outlook ordnungsgemäß funktionieren. Durch das Deaktivieren verbundener Benutzererfahrungen kann außerdem verhindert werden, dass Add-Ins für Outlook ordnungsgemäß funktionieren. Weitere Informationen finden Sie unter Verbundene Erfahrungen [in Office.](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)  

"Für Teams freigeben" verwendet den gleichen Transportmechanismus wie beim E-Mail-Senden eines Kanals durch einen Benutzer. Für die Freigabe in Chats werden E-Mails (einschließlich E-Mail-Anlagen) auf das OneDrive des Absenders kopiert. Für die Freigabe in Kanälen werden E-Mails und Anlagen in den Ordner **E-Mail-Nachrichten** in SharePoint kopiert.

Das Outlook-Add-In für "Freigeben für Teams" verwendet den Anforderungssatz 1.7, wie in der Dokumentation zu [Outlook-Add-Ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)beschrieben, die Details zu Outlook-Add-Ins, Umgebungsanforderungen für Outlook-Add-Ins und bestimmten Outlook-Clients enthält, die mit Anforderungssatz 1.7 unterstützt werden.

## <a name="enabling-or-disabling-share-to-teams"></a>Aktivieren oder Deaktivieren der Freigabe für Teams

Das Outlook-Add-In für "Für Teams freigeben" kann mithilfe der folgenden PowerShell-Cmdlets selektiv deaktiviert oder auf Benutzerbasis aktiviert werden.

> [!NOTE]
> Das Deaktivieren des Add-Ins ist erst nach der Installation des Add-Ins möglich. Wenn Sie die Deaktivierung für alle Benutzer in Ihrem Mandanten erzwingen möchten, führen Sie in regelmäßigen Abständen ein Skript aus.

Um das von Share to Teams verwendete Add-In für Outlook zu deaktivieren, führen Sie das hier [gefundene Cmdlet aus.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Um das von Share to Teams verwendete Add-In für Outlook zu aktivieren, führen Sie das hier [gefundene Cmdlet aus.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Browser und einmaliges Anmelden

Die Freigabe für Teams sowohl in Outlook im Web als auch in Outlook-Desktopclients basiert auf einem Browser-WebView. Details dazu, welche Clients welche bestimmten Browser verwenden, finden Sie unter Browser, die von [Office-Add-Ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) verwendet werden. 

> [!IMPORTANT]
> Für die Freigabe in Teams ist es erforderlich, dass cookies von Drittanbietern und der lokale Speicherzugriff für die Browser der Benutzer aktiviert werden.

Für die Freigabe in Teams wird einmaliges Anmelden (Single Sign-On, SSO) verwendet, was bedeutet, dass Benutzer ihre Anmeldeinformationen nicht angeben müssen, wenn sie das Add-In über Freigeben für Teams verwenden. SSO für Outlook im Web unterstützt https://outlook.office365.com/owa/extSSO.aspx standardmäßig URLs und https://outlook.office.com/owa/extSSO.aspx antwortet darauf. Bei Vanitydomänen müssen Administratoren die entsprechende Azure Active Directory-Antwort-URL hinzufügen.