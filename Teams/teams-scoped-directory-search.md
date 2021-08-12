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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Microsoft Teams mit Bereichssuche verwenden können, um benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung zu stellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9602615d0c2217a828a2530564c49f9a1009c96b78ad06e78ba2ca79b9e29c05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285624"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Microsoft Teams bereichsisierte Verzeichnissuche ermöglicht es Organisationen, virtuelle Grenzen zu erstellen, die steuern, wie Benutzer Benutzer in ihrer Organisation suchen und mit anderen Benutzern kommunizieren können. 

Microsoft Teams ermöglicht Es Organisationen, ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung zu stellen. Microsoft Teams verwendet [Informationsbarriererichtlinien, um](/microsoft-365/compliance/information-barriers) diese benutzerdefinierten Ansichten zu unterstützen. Nachdem die Richtlinien aktiviert wurden, werden die von Suchbegriffen für andere Benutzer zurückgegebenen Ergebnisse (z. B. zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team) gemäß den konfigurierten Richtlinien begrenzt. Benutzer können keine Teams suchen oder entdecken, wenn die Bereichssuche aktiv ist, aber vorhandene Mitglieder in diesen Teams können Benutzer hinzufügen, wie es in den Richtlinien für die aktive Informationsbarriere zulässig ist.

> [!NOTE]
> In Exchange-Hybridumgebungen funktioniert dieses Feature nur mit Exchange Online Postfächern und nicht mit lokalen Postfächern.

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

3. Aktivieren **Sie** unter Suche neben Bereichsverzeichnissuche in Teams einem Exchange-Adressbuchrichtlinie **(ABP)** die Umschaltfunktion **Ein.**

    ![Bereichsverzeichnissuche im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Es kann einige Stunden dauern, bis diese Änderung repliziert wurde.
