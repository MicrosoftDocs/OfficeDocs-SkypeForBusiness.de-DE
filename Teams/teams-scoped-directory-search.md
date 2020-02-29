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
description: Hier erfahren Sie, wie Sie die Verzeichnissuche in Microsoft Teams verwenden, um angepasste Ansichten des Verzeichnisses bereitzustellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b06e675e93dd022847fc7af202045c3ecdebe63
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341769"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Mithilfe der Verzeichnissuche in Microsoft Teams können Organisationen virtuelle Grenzen erstellen, die Steuern, wie Benutzer andere Benutzer in Ihrer Organisation finden und mit Ihnen kommunizieren können. 

In Microsoft Teams können Organisationen ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung stellen. Microsoft Teams verwendet [Richtlinien für Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) , um diese benutzerdefinierten Ansichten zu unterstützen. Sobald die Richtlinien aktiviert sind, werden die Ergebnisse, die von Suchvorgängen nach anderen Benutzern zurückgegeben wurden (beispielsweise zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team), entsprechend den konfigurierten Richtlinien zugewiesen. Benutzer können keine Teams durchsuchen oder entdecken, wenn die Bereichssuche aktiviert ist. 

> [!NOTE]
> In Exchange-Hybrid Umgebungen funktioniert dieses Feature nur mit Exchange Online-Postfächern und nicht mit lokalen Postfächern.

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie Bereichs Verzeichnis suchen verwenden?

Szenarien, die von umfangreicheren Verzeichnis suchen profitieren, ähneln den Szenarien für adressbuchrichtlinien. So können Sie beispielsweise die bereichsbezogene Verzeichnissuche in den folgenden Situationen verwenden:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 
 
Informationen zum Verwenden von adressbuchrichtlinien finden Sie [unter Richtlinien für Informationsbarrieren in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).

> [!IMPORTANT]
> Adressbuchrichtlinien bieten nur eine virtuelle Trennung von Benutzern aus der Verzeichnis Perspektive. Benutzer können die Kommunikation mit anderen Personen weiterhin initiieren, indem Sie vollständige e-Mail-Adressen angeben. Beachten Sie auch, dass alle Benutzerdaten, die bereits vor der Erzwingung neuer oder aktualisierter adressbuchrichtlinien zwischengespeichert wurden, für Benutzer bis zu 30 Tage verfügbar bleiben können.

## <a name="turn-on-scoped-directory-search"></a>Aktivieren der Bereich-Verzeichnissuche

1. Verwenden Sie Richtlinien für Informationsbarrieren, um Ihre Organisation in virtuellen Untergruppen zu konfigurieren. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).

2. Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen** > **Teams Einstellungen**aus.

3. Aktivieren Sie unter **Suchen**neben **Bereichs Verzeichnissuche in Teams, die eine Exchange-adressbuchrichtlinie (ABP) verwenden**, **die Umschaltfläche**.

    ![Verzeichnissuche im Bereich "Bereich" im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Diese Änderung kann bis zu 24 Stunden dauern, bis Sie repliziert wurde.
