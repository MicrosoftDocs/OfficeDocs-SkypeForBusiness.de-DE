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
description: Erfahren Sie, wie Sie die Verzeichnissuche im Microsoft Teams-Bereich verwenden, um angepasste Ansichten des Verzeichnisses zur Verfügung zu stellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094025"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Die Suche im Microsoft Teams-Bereich ermöglicht Es Organisationen, virtuelle Grenzen zu erstellen, die steuern, wie Benutzer andere Benutzer in ihrer Organisation finden und mit ihnen kommunizieren können. 

Microsoft Teams ermöglicht Es Organisationen, ihren Benutzern benutzerdefinierte Ansichten des Verzeichnisses zur Verfügung zu stellen. Microsoft Teams verwendet [Richtlinien für Informationsbarrieren,](/microsoft-365/compliance/information-barriers) um diese benutzerdefinierten Ansichten zu unterstützen. Nachdem die Richtlinien aktiviert wurden, werden die ergebnisse, die von der Suche nach anderen Benutzern zurückgegeben werden (z. B. zum Initiieren eines Chats oder zum Hinzufügen von Mitgliedern zu einem Team), gemäß den konfigurierten Richtlinien in den Bereich geschaltet. Benutzer können keine Teams durchsuchen oder entdecken, wenn die Bereichssuche wirksam ist, aber vorhandene Mitglieder in diesen Teams können Benutzer hinzufügen, wie dies durch aktive Richtlinien zur Informationsbarriere zulässig ist.

> [!NOTE]
> In Exchange-Hybridumgebungen funktioniert dieses Feature nur mit Exchange Online-Postfächern und nicht mit lokalen Postfächern.

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie Bereichsverzeichnissuchen verwenden?

Szenarien, die von Bereichsverzeichnissuchen profitieren, ähneln Szenarien für Adressbuchrichtlinien. Sie können beispielsweise die Bereichsverzeichnissuche in den folgenden Situationen verwenden:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 
 
Informationen zur Verwendung von Adressbuchrichtlinien finden Sie unter [Richtlinien zur Informationsbarriere in Exchange Online.](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> Adressbuchrichtlinien bieten nur eine virtuelle Trennung von Benutzern aus Verzeichnisperspektive. Es ist auch wichtig zu beachten, dass alle Benutzerdaten, die vor der Erzwingung neuer oder aktualisierter Adressbuchrichtlinien bereits zwischengespeichert wurden, benutzern bis zu 30 Tage lang zur Verfügung stehen.

## <a name="turn-on-scoped-directory-search"></a>Aktivieren der Bereichsverzeichnissuche

1. Verwenden Sie Richtlinien zur Informationsbarriere, um Ihre Organisation in virtuelle Untergruppen zu konfigurieren. Weitere Informationen finden Sie unter [Definieren von Informationsbarriererichtlinien](/microsoft-365/compliance/information-barriers-policies).

2. Wählen Sie im Microsoft Teams Admin Center **die Option Organisationsweite Einstellungen**  >  **Teams-Einstellungen aus.**

3. Aktivieren **Sie unter** Suchen neben Bereichsverzeichnissuche in Teams mit einer **Exchange-Adressbuchrichtlinie (ABP)** die Umschaltfunktion **Ein.**

    ![Bereichsverzeichnissuche im Microsoft Teams Admin Center](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Die Replikation dieser Änderung kann einige Stunden dauern.