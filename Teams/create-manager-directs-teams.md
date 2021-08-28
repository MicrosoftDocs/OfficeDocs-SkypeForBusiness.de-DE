---
title: Erstellen von Teams für Personalverantwortliche in Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Erfahren Sie, wie Sie mithilfe eines PowerShell-Skripts ein Team für jeden Manager mit seinen direkten Mitarbeitern als Teammitglieder erstellen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cad2ed4fdbcec7f13f5b2e932d34395fe4b4c339
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628357"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Erstellen von Teams für Personalverantwortliche in Microsoft Teams


Wenn Sie Microsoft Teams einführen, sollten Sie nicht mit einem „unbeschriebenen Blatt“ (ohne Teams oder Kanäle) starten, sondern es empfiehlt sich, ein Grundgerüst aus Teams und Kanälen einzurichten. Dadurch lässt sich die unkontrollierte Erstellung von Teams durch Benutzer verhindern, wenn eigentlich Kanäle in bestehenden Teams erstellt werden sollten. Um Ihnen bei der Gestaltung einer durchdachten Struktur aus Teams und Kanälen zu helfen, haben wir ein PowerShell-Skript erstellt, das ein Team für jeden Ihrer Personalverantwortlichen der ersten und zweiten Ebene erstellt, mit den direkten Mitarbeitern jedes Personalverantwortlichen als Teammitglieder. Dies ist ein „Point-in-Time“-Skript (d. h., Ihre Teams oder Kanäle werden nicht automatisch aktualisiert, wenn Personen hinzugefügt oder aus einer Organisation entfernt werden). Aber es ist ein wertvolles Werkzeug, mit dem Sie von Anfang an eine gewisse Ordnung in Ihre Teamstruktur bringen können. Dieses Skript liest Ihr Azure AD und ruft eine Liste der Manager und ihrer direkten Mitarbeiter ab. Anhand dieser Liste wird für jeden Personalverantwortlichen je ein Team erstellt. 

## <a name="how-to-use-the-powershell-script"></a>Verwenden des PowerShell-Skripts 

Führen Sie zunächst das Skript [Personalverantwortliche und ihre direkten Mitarbeiter exportieren](scripts/powershell-script-create-teams-from-managers-export-managers.md) aus (dies setzt voraus, dass Sie bereits die PowerShell-Module [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) und [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) ausgeführt haben). Das Skript *Personalverantwortliche und ihre direkten Mitarbeiter exportieren* erstellt eine Datei mit Tabstopptrennzeichen (ExportedManagerDirects.txt), die alle Personalverantwortlichen mit ihren direkten Mitarbeiter auflistet. 

Führen Sie dann das Skript [Neue Teams für Personalverantwortliche erstellen](scripts/powershell-script-create-teams-from-managers-new-teams.md) aus. Dieses Script liest die Datei „ExportedManagerDirects.txt“ ein, erstellt ein Team für jeden Personalverantwortlichen und fügt diesem seine direkten Mitarbeiter als Mitglieder hinzu. Personalverantwortliche oder Mitarbeiter, die nicht für Teams aktiviert sind, werden vom Skript übersprungen, und es wird es wird kein Team erstellt. (Überprüfen Sie den Bericht, und führen Sie das Skript erneut aus, nachdem Sie Teams für alle, die es benötigen, aktiviert haben. Das Skript erstellt kein zweites Team für einen Personalverantwortlichen, für den bereits ein Team erstellt wurde).

Für jedes Team erstellt das Skript einen allgemeinen und einen „Nur zum Spaß“-Kanal. 

## <a name="best-practices"></a>Bewährte Methoden

- Bitten Sie jeden Personalverantwortlichen, die Website für Krisenkommunikation Ihrer Organisation als Registerkarte zum Kanal „Allgemein“ für jedes Team hinzuzufügen. 

- Informieren Sie sich über die neue Krisenkommunikations-App in diesem Blogbeitrag vom 8. März 2020: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Verwandte Themen

[Bewährte Methoden zum Organisieren von Teams](best-practices-organizing.md)

[Erstellen eines organisationsweiten Teams in Teams](create-an-org-wide-team.md)