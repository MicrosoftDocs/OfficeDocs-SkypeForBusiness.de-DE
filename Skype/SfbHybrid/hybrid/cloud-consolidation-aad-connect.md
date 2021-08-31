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
ms.localizationpriority: medium
description: Dieser Anhang enthält ausführliche Schritte zum Aktualisieren von AAD-Verbinden, um mehr als eine Gesamtstruktur als Teil der Cloudkonsolidierung für Teams und Skype for Business einzuschließen.
ms.openlocfilehash: 261085c85b9b3114bce49216e7b63173cd37d55e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731884"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Aktualisieren von AAD Connect, um mehrere Gesamtstrukturen einzubeziehen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD Verbinden unterstützt [die Synchronisierung aus mehreren Gesamtstrukturen.](/azure/active-directory/connect/active-directory-aadconnect-topologies) Es unterstützt jedoch nur eine Instanz von Azure AD Verbinden Synchronisierung mit AAD. Daher muss in Fällen, in denen Azure AD bereits in einer Gesamtstruktur installiert ist, die vorhandene Instanz von AAD Verbinden für die Synchronisierung aus der zusätzlichen Gesamtstruktur aktualisiert werden.

 - Wenn alle Identitäten nur einmal in beiden Gesamtstrukturen dargestellt werden (d. h., Sie haben keine E-Mail-aktivierten Kontakte erstellt), können Sie einfach den AAD-Verbinden-Assistenten erneut ausführen, "Synchronisierungsoptionen anpassen" auswählen und dann auf der Seite **Verbinden Ihre Verzeichnisse** den Namen der zusätzlichen Gesamtstruktur und creds eingeben.<br><br>
 ![Die Verbinden Seite "Ihre Verzeichnisse".](../media/cloud-consolidation-connect-your-directories.png)
 - Wenn Benutzer jedoch in mehreren Verzeichnissen vorhanden sein können und Sie die Daten zusammenführen (z. B. wenn Kontaktobjekte in einer Gesamtstruktur vorhanden sind, die Benutzern in einer anderen Gesamtstruktur entspricht), müssen Sie Azure AD Verbinden deinstallieren und erneut installieren.  Dies liegt daran, dass die Bedingung für die gesamtstrukturübergreifende Verknüpfung nur während der ersten Installation konfiguriert werden kann. Dies geschieht auf der folgenden Seite:<br><br>
 ![Die Seite "Eindeutig identifizierende Benutzer".](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Siehe auch

[Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)