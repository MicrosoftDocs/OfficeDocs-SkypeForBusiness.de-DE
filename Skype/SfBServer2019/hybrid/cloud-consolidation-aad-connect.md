---
title: Update AAD Herstellen einer Verbindung mit mehr als einer Gesamtstruktur einschließen
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren der AAD Herstellen einer Verbindung mit mehreren Gesamtstrukturen als Teil der Konsolidierung für Teams und Skype für Business Cloud aufnehmen.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247669"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Update AAD Herstellen einer Verbindung mit mehr als einer Gesamtstruktur einschließen

Azure Active Directory verbinden unterstützt [aus mehreren Gesamtstrukturen synchronisiert wird](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Es unterstützt jedoch nur eine Instanz des Azure Active Directory verbinden mit AAD synchronisieren. Aus diesem Grund in Fällen, in dem Azure AD in einer Gesamtstruktur bereits installiert ist, die vorhandene Instanz von AAD Connect muss aktualisiert werden aus der zusätzlichen Gesamtstruktur synchronisieren.

 - Wenn alle Identitäten in beiden Gesamtstrukturen nur einmal dargestellt werden (d. h., Sie noch keine e-Mail-aktivierten Kontakte hergestellt), können Sie einfach den AAD verbinden-Assistenten erneut ausführen, wählen Sie "Synchronisierungsoptionen anpassen", und klicken Sie dann auf die **Verbinden Ihrer Verzeichnisse **Seite, geben Sie den Namen der Gesamtstruktur zusätzliche und Anmeldeinformationen.<br><br>
 ![Verbinden der Seite Verzeichnisse](../media/cloud-consolidation-connect-your-directories.png)
 - Wenn Benutzer in vorhanden sind, können mehr als ein Verzeichnis und Sie werden werden Zusammenführen von Daten (z. B., wenn Contact-Objekte in einer Gesamtstruktur, die Benutzern in einer anderen Gesamtstruktur entsprechen vorhanden), müssen Sie Deinstallieren von Azure Active Directory verbinden und installieren Sie ihn neu.  Dies ist, weil die Bedingung gesamtstrukturübergreifenden Join Regeln nur während der ersten Installation konfiguriert werden kann. Dies geschieht auf der nächsten Seite:<br><br>
 ![Zur eindeutigen Identifizierung der Benutzerseite](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype für Unternehmen](cloud-consolidation.md)