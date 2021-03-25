---
title: Aktualisieren von AAD Connect, um mehrere Gesamtstrukturen einzubeziehen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren von AAD Connect, um mehr als eine Gesamtstruktur als Teil der Cloudkonsolidierung für Teams und Skype for Business zu enthalten.
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120374"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Aktualisieren von AAD Connect, um mehrere Gesamtstrukturen einzubeziehen

Azure AD Connect unterstützt [die Synchronisierung aus mehreren Gesamtstrukturen](/azure/active-directory/connect/active-directory-aadconnect-topologies). Es unterstützt jedoch nur eine Instanz der Azure AD Connect-Synchronisierung mit AAD. Daher muss in Fällen, in denen Azure AD bereits in einer Gesamtstruktur installiert ist, die vorhandene Instanz von AAD Connect aktualisiert werden, damit sie von der zusätzlichen Gesamtstruktur synchronisiert wird.

 - Wenn alle Identitäten nur einmal in beiden Gesamtstrukturen dargestellt werden (d. h., Sie haben keine E-Mail-aktivierten Kontakte hergestellt), können Sie einfach  den Assistenten für AAD-Verbindungen erneut ausführen, "Synchronisierungsoptionen anpassen" auswählen und dann auf der Seite Ihre Verzeichnisse verbinden den Namen der zusätzlichen Gesamtstruktur und der zusätzlichen Spalten eingeben.<br><br>
 ![Die Seite "Ihre Verzeichnisse verbinden"](../media/cloud-consolidation-connect-your-directories.png)
 - Wenn Benutzer jedoch in mehreren Verzeichnissen vorhanden sein können und Sie die Daten zusammenführen (z. B. wenn Kontaktobjekte in einer Gesamtstruktur vorhanden sind, die Benutzern in einer anderen Gesamtstruktur entspricht), müssen Sie Azure AD Connect deinstallieren und erneut installieren.  Dies liegt daran, dass die bedingung für gesamtstrukturübergreifende Verknüpfungsregeln nur während der ersten Installation konfiguriert werden kann. Dies geschieht auf der folgenden Seite:<br><br>
 ![Die Seite Eindeutig identifizieren ihrer Benutzer](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Siehe auch

[Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)