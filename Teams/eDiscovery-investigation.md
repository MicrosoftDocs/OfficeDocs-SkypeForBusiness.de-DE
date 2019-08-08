---
title: Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, was Sie tun müssen, wenn Sie eine eDiscovery durchführen, zum Beispiel, wenn Sie alle elektronisch gespeicherten Informationen für Gerichtsverfahren eingereicht müssen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236359"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams
============================

Große Unternehmen sind häufig hohen strafrechtlichen Verfahren ausgesetzt, die die Übermittlung aller elektronisch gespeicherten Informationen (ESI) fordern.

Alle Teams 1:1-oder Gruppen-Chats werden über die Postfächer der jeweiligen Benutzer in Journalen durchlaufen, und alle Kanal Nachrichten werden in das Gruppenpostfach, das das Team darstellt, in Journalen gespeichert. Hochgeladene Dateien werden unter der eDiscovery-Funktion für SharePoint Online und OneDrive for Business behandelt.

1.  Wenn Sie eine eDiscovery-Untersuchung mit Microsoft Teams-Inhalten durchführen möchten, lesen Sie Schritt 1 in [diesem](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) Link.

2.  Microsoft Teams-Daten werden als Chatnachrichten oder Unterhaltungen in der Excel-eDiscovery-Exportausgabe angezeigt, und Sie können das bereitstellen. PST in Outlook, um diese Nachrichten nach dem Export anzuzeigen.

    Beim montieren des. PST für das Team beachten Sie, dass alle Unterhaltungen im Teamchat-Ordner unter Konversationsprotokoll gespeichert werden. Der Titel der Nachricht wird an Team und Kanal ausgerichtet. Wenn Sie das Bild unten überprüfen, können Sie diese Nachricht von Bob sehen, der den Project 7-Kanal des Teams "Manufacturing Specs" gesendet hat.

    ![Screenshot eines Team-Chat-Ordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Wenn Sie private Chats in einem Benutzerpostfach sehen möchten – diese befinden sich ebenfalls im Ordner „Teamchat“ unter „Aufgezeichnete Unterhaltungen“.

## <a name="ediscovery-of-guest-to-guest-chats"></a>eDiscovery von Gast-zu-Gast-Chats

Ohne ein Postfach würden Gast-zu-Gast-Chats (1xN-Chats, in denen keine Home-Tenant-Benutzer vorhanden sind) nicht indiziert und daher nicht in eDiscovery enthalten sein. Um eDiscovery für Gast-zu-Gast-Chats zu vereinfachen, wird ein Cloud-basiertes Postfach (oder ein Phantom Postfach) zum Speichern der 1xN-Daten erstellt. Nachdem die Chat-Daten des Teams im cloudbasierten Postfach gespeichert wurden, ist es für die eDiscovery-und Compliance-Inhaltssuche indiziert.

Die folgende Abbildung zeigt, wie eDiscovery für Gast-zu-Gast-Chats funktioniert, in denen kein Postfach vorhanden ist.

![Gast-zu-Gast-Chats-mit-ohne-Postfach](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
