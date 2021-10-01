---
title: Verwenden der Verzeichnissuche in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Microsoft Teams Verzeichnissuche verwenden, um angepasste Ansichten des Verzeichnisses zur Verfügung zu stellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f69a4d94743e443fd20f53f5eb35d26b6d69e3b3
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046231"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Microsoft Teams bereichsisierte Verzeichnissuche ermöglicht es Organisationen, virtuelle Grenzen zu erstellen, die steuern, wie Benutzer andere Benutzer in ihrer Organisation finden und mit ihnen kommunizieren können. 

Microsoft Teams ermöglicht Es Organisationen, ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung zu stellen. Microsoft Teams verwendet [Informationsbarriererichtlinien, um](/microsoft-365/compliance/information-barriers) diese benutzerdefinierten Ansichten zu unterstützen. Nachdem die Richtlinien aktiviert wurden, werden die von Suchbegriffen für andere Benutzer zurückgegebenen Ergebnisse (z. B. zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team) gemäß den konfigurierten Richtlinien begrenzt. Benutzer können keine Teams suchen oder entdecken, wenn die Bereichssuche aktiv ist, aber vorhandene Mitglieder in diesen Teams können Benutzer hinzufügen, wie es in den Richtlinien für die aktive Informationsbarriere zulässig ist.

> [!NOTE]
> In Exchange hybriden Umgebungen funktioniert dieses Feature nur mit Exchange Online Postfächern und nicht mit lokalen Postfächern.

Siehe auch [Adressbuchrichtlinien in Exchange Online.](/exchange/address-books/address-book-policies/address-book-policies)

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie Verzeichnissuchen mit Bereichsbereich verwenden?

Szenarien, die von der Verzeichnissuche mit Bereichsbereich profitieren, sind mit den Szenarien mit Adressbuchrichtlinien vergleichbar. In den folgenden Situationen kann es z. B. sein, dass Sie die Verzeichnissuche mit Bereichsbereich verwenden möchten:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 
 
Informationen zur Verwendung von Adressbuchrichtlinien finden Sie unter Richtlinien zur Informationsbarriere [in Exchange Online.](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> Adressbuchrichtlinien ermöglichen nur eine virtuelle Trennung der Benutzer aus der Verzeichnisperspektive. Beachten Sie auch, dass alle Benutzerdaten, die vor der Erzwingung neuer oder aktualisierter Adressbuchrichtlinien bereits zwischengespeichert wurden, Benutzern bis zu 30 Tage lang zur Verfügung stehen.

## <a name="turn-on-scoped-directory-search"></a>Aktivieren der Verzeichnissuche mit Bereichsbereich

1. Verwenden Sie Richtlinien für Informationsbarrieren, um Ihre Organisation in virtuelle Untergruppen zu konfigurieren. Weitere Informationen finden Sie unter [Definieren von Informationsbarriererichtlinien.](/microsoft-365/compliance/information-barriers-policies)

2. Wählen Sie Microsoft Teams Admin Center **organisationsweite** Einstellungen und  >  **Teams aus.**

3. Schalten **Sie** unter Suche neben Bereichsverzeichnissuche in Teams, die eine Exchange-Adressbuchrichtlinie **(ABP)** verwendet, die Umschaltfunktion **Auf aus.**

    ![Bereichsierte Verzeichnissuche im Microsoft Teams Admin Center.](media/teams-scoped-directory-search-image1.png)

> [!IMPORTANT]
> Es kann einige Stunden dauern, bis diese Änderung repliziert wurde.
