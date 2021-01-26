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
description: Erfahren Sie, wie Sie mithilfe der mit Microsoft Teams begrenzten Verzeichnissuche benutzerdefinierte Ansichten des Verzeichnisses bereitstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779929"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Mit der mit Microsoft Teams begrenzten Verzeichnissuche können Organisationen virtuelle Grenzen erstellen, die steuern, wie Benutzer andere Benutzer in ihrer Organisation finden und mit ihnen kommunizieren können. 

Mit Microsoft Teams können Organisationen ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses bereitstellen. Microsoft Teams verwendet [Informationsbarriererichtlinien, um](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) diese benutzerdefinierten Ansichten zu unterstützen. Nachdem die Richtlinien aktiviert wurden, werden die von suchten nach anderen Benutzern zurückgegebenen Ergebnisse (z. B. zum Starten eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team) gemäß den konfigurierten Richtlinien begrenzt. Benutzer können Teams nicht durchsuchen oder entdecken, wenn die Suche mit Bereichsfunktion in Kraft ist. 

> [!NOTE]
> In Exchange-Hybridumgebungen funktioniert dieses Feature nur mit Exchange Online-Postfächern, nicht mit lokalen Postfächern.

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie Verzeichnissuchen mit Bereichsbereich verwenden?

Szenarien, die von Bereichsverzeichnissuchen profitieren, ähneln Szenarien mit Adressbuchrichtlinien. So können Sie beispielsweise in den folgenden Situationen die Verzeichnissuche mit Bereichsbereich verwenden:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 
 
Informationen zur Verwendung von Adressbuchrichtlinien finden Sie in den [Richtlinien zur Informationsbarriere in Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> Adressbuchrichtlinien ermöglichen nur eine virtuelle Trennung der Benutzer aus der Verzeichnisperspektive. Beachten Sie außerdem, dass alle Benutzerdaten, die vor der Erzwingung neuer oder aktualisierter Adressbuchrichtlinien bereits zwischengespeichert wurden, benutzern bis zu 30 Tage zur Verfügung stehen.

## <a name="turn-on-scoped-directory-search"></a>Aktivieren der Bereichsverzeichnissuche

1. Verwenden Sie Informationsbarriererichtlinien, um Ihre Organisation in virtuelle Untergruppen zu konfigurieren. Weitere Informationen finden Sie unter ["Richtlinien für Informationsbarriere definieren".](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)

2. Wählen Sie im Microsoft Teams Admin Center **"Organisationsweite Einstellungen" aus.**  >  

3. Aktivieren **Sie unter "Suche"** neben der Bereichsverzeichnissuche in Teams mit einer Exchange-Adressbuchrichtlinie **(ABP)** die **Umschaltfunktion**.

    ![Bereichssuche im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Es kann einige Stunden dauern, bis diese Änderung repliziert wurde.
