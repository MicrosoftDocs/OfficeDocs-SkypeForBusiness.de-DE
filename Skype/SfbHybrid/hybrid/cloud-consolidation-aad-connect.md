---
title: Aktualisieren von Aad Connect, um mehr als eine Gesamtstruktur einzubeziehen
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren von Aad Connect, um mehr als eine Gesamtstruktur als Teil der Cloud-Konsolidierung für Teams und Skype for Business einzubeziehen.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160581"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="78c88-103">Aktualisieren von Aad Connect, um mehr als eine Gesamtstruktur einzubeziehen</span><span class="sxs-lookup"><span data-stu-id="78c88-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="78c88-104">Azure AD Connect unterstützt die [Synchronisierung von mehreren Gesamtstrukturen](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="78c88-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="78c88-105">Es unterstützt jedoch nur eine Instanz von Azure AD Connect-Synchronisierung mit Aad.</span><span class="sxs-lookup"><span data-stu-id="78c88-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="78c88-106">In Fällen, in denen Azure AD bereits in einer Gesamtstruktur installiert ist, muss die vorhandene Instanz von Aad Connect daher zur Synchronisierung von der zusätzlichen Gesamtstruktur aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="78c88-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="78c88-107">Wenn alle Identitäten nur einmal in beiden Gesamtstrukturen dargestellt werden (das heißt, Sie haben keine e-Mail-aktivierten Kontakte hergestellt), können Sie einfach den Aad-Verbindungs-Assistenten erneut ausführen, die Option "Synchronisierungsoptionen anpassen" auswählen und dann auf der Seite " \*\*Ihre Verzeichnisse verbinden" \*\*den Namen der zusätzlichen Gesamtstruktur und creds ein.</span><span class="sxs-lookup"><span data-stu-id="78c88-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="78c88-108">![Die Seite "Ihre Verzeichnisse verbinden"](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="78c88-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="78c88-109">Wenn Benutzer jedoch in mehr als einem Verzeichnis vorhanden sein können und Sie die Daten zusammenführen (beispielsweise wenn Kontaktobjekte in einer Gesamtstruktur vorhanden sind, die Benutzern in einer anderen Gesamtstruktur entspricht), müssen Sie Azure AD Connect deinstallieren und erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="78c88-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="78c88-110">Dies liegt daran, dass die Bedingung "gesamtstrukturübergreifende Join Rules" nur während der ersten Installation konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="78c88-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="78c88-111">Dies geschieht auf der folgenden Seite:</span><span class="sxs-lookup"><span data-stu-id="78c88-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="78c88-112">![Die Seite zum eindeutigen Identifizieren Ihrer Benutzer](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="78c88-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="78c88-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78c88-113">See also</span></span>

[<span data-ttu-id="78c88-114">Cloud-Konsolidierung für Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="78c88-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)