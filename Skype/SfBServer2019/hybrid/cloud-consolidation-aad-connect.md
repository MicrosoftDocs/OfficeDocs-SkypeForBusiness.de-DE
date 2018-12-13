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
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="1f41a-103">Update AAD Herstellen einer Verbindung mit mehr als einer Gesamtstruktur einschließen</span><span class="sxs-lookup"><span data-stu-id="1f41a-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="1f41a-104">Azure Active Directory verbinden unterstützt [aus mehreren Gesamtstrukturen synchronisiert wird](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="1f41a-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="1f41a-105">Es unterstützt jedoch nur eine Instanz des Azure Active Directory verbinden mit AAD synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="1f41a-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="1f41a-106">Aus diesem Grund in Fällen, in dem Azure AD in einer Gesamtstruktur bereits installiert ist, die vorhandene Instanz von AAD Connect muss aktualisiert werden aus der zusätzlichen Gesamtstruktur synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="1f41a-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="1f41a-107">Wenn alle Identitäten in beiden Gesamtstrukturen nur einmal dargestellt werden (d. h., Sie noch keine e-Mail-aktivierten Kontakte hergestellt), können Sie einfach den AAD verbinden-Assistenten erneut ausführen, wählen Sie "Synchronisierungsoptionen anpassen", und klicken Sie dann auf die \*\*Verbinden Ihrer Verzeichnisse \*\*Seite, geben Sie den Namen der Gesamtstruktur zusätzliche und Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="1f41a-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="1f41a-108">![Verbinden der Seite Verzeichnisse](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="1f41a-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="1f41a-109">Wenn Benutzer in vorhanden sind, können mehr als ein Verzeichnis und Sie werden werden Zusammenführen von Daten (z. B., wenn Contact-Objekte in einer Gesamtstruktur, die Benutzern in einer anderen Gesamtstruktur entsprechen vorhanden), müssen Sie Deinstallieren von Azure Active Directory verbinden und installieren Sie ihn neu.</span><span class="sxs-lookup"><span data-stu-id="1f41a-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="1f41a-110">Dies ist, weil die Bedingung gesamtstrukturübergreifenden Join Regeln nur während der ersten Installation konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1f41a-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="1f41a-111">Dies geschieht auf der nächsten Seite:</span><span class="sxs-lookup"><span data-stu-id="1f41a-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="1f41a-112">![Zur eindeutigen Identifizierung der Benutzerseite](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="1f41a-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="1f41a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f41a-113">See also</span></span>

[<span data-ttu-id="1f41a-114">Cloud-Konsolidierung für Teams und Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="1f41a-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)