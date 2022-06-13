---
title: Einschränken, wer Benutzern beim Durchsuchen des Verzeichnisses in Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie einschränken können, wen Benutzer beim Durchsuchen des Verzeichnisses in Teams sehen können.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046427"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Einschränken, wer Benutzern beim Durchsuchen des Verzeichnisses in Teams

Microsoft Teams können Organisationen ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses bereitstellen. Diese Ansichten können hilfreich sein, wenn:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen.
- Ihre Geschäftsrichtlinien erfordern, dass Sie verhindern, dass bestimmte Gruppen innerhalb Ihrer Organisation miteinander kommunizieren.
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen.

Es gibt zwei Optionen zum Einschränken, wer Benutzern angezeigt werden kann, wenn sie das Verzeichnis in Teams durchsuchen:

- [Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Adressbuchrichtlinien in Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)

Wenn Sie eine der beiden Optionen verwenden, müssen Sie die Suche nach Namen im Teams Admin Center aktivieren.

Wir empfehlen die Verwendung von Informationsbarrieren, wenn Ihre Organisation die [erforderlichen Lizenzen und Berechtigungen](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions) erfüllt.

So aktivieren Sie die Suche nach Namen

1. Wählen Sie im Microsoft Teams Admin Center **Teams** >  **Teams Einstellungen** aus.

1. Aktivieren **Sie unter "Nach Name suchen**" neben der **Bereichsverzeichnissuche mithilfe einer Exchange Adressbuchrichtlinie** die **Umschaltfläche**.

> [!Note]
> Es kann einige Stunden dauern, bis diese Änderung wirksam wird.
> 
> Wenn Sie die Suche nach Namen aktivieren, werden das Feld **"Teams suchen**" und der Eintrag für öffentliche Teams in **"Beitreten" oder "Erstellen eines Teams** in Teams" ausgeblendet. Außerdem wird der Beitritt zu einem Team durch Eingabe `/join` in das Befehlsfeld oben in Teams deaktiviert.
