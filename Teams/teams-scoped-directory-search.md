---
title: Verwenden der Verzeichnissuche in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Hier erfahren Sie, wie Sie die Verzeichnissuche in Microsoft Teams verwenden, um angepasste Ansichten des Verzeichnisses bereitzustellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf65cec72c21e34e0aab8338d20ae36549497846
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221731"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Mithilfe der Verzeichnissuche in Microsoft Teams können Organisationen virtuelle Grenzen erstellen, die Steuern, wie Benutzer andere Benutzer in Ihrer Organisation finden und mit Ihnen kommunizieren können. 

In Microsoft Teams können Organisationen ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung stellen. Microsoft Teams verwendet [Exchange-adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) , um diese benutzerdefinierten Ansichten zu unterstützen. Sobald die Richtlinien aktiviert sind, werden die Ergebnisse, die von Suchvorgängen nach anderen Benutzern zurückgegeben wurden (beispielsweise zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team), entsprechend den konfigurierten Richtlinien zugewiesen. Benutzer können keine Teams durchsuchen oder entdecken, wenn die Bereichssuche aktiviert ist. 

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie Bereichs Verzeichnis suchen verwenden?

Szenarien, die von umfangreicheren Verzeichnis suchen profitieren, ähneln den Szenarien für adressbuchrichtlinien. So können Sie beispielsweise die bereichsbezogene Verzeichnissuche in den folgenden Situationen verwenden:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 
 
Informationen zum Verwenden von adressbuchrichtlinien finden Sie [unter adressbuchrichtlinien in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

> [!IMPORTANT]
> Adressbuchrichtlinien bieten nur eine virtuelle Trennung von Benutzern aus der Verzeichnis Perspektive. Benutzer können die Kommunikation mit anderen Personen weiterhin initiieren, indem Sie vollständige e-Mail-Adressen angeben. Beachten Sie auch, dass alle Benutzerdaten, die bereits vor der Erzwingung neuer oder aktualisierter adressbuchrichtlinien zwischengespeichert wurden, für Benutzer bis zu 30 Tage verfügbar bleiben können.

## <a name="turn-on-scoped-directory-search"></a>Aktivieren der Bereich-Verzeichnissuche

1. Verwenden Sie adressbuchrichtlinien, um Ihre Organisation in virtuellen Untergruppen zu konfigurieren. Weitere Informationen finden Sie unter [Verfahren für adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

2. Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen** > **Teams Einstellungen**aus.

3. Aktivieren Sie unter **Suchen**neben **Bereichs Verzeichnissuche in Teams mithilfe einer Exchange-adressbuchrichtlinie (Fahndung)** die Umschaltfläche ****.

    ![Verzeichnissuche im Bereich "Bereich" im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Hybrid Konfigurationen (Teams mit Exchange lokal) unterstützen den Bereich Such Modus nicht. 

