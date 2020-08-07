---
title: Erstellen von Personen-Manager-Teams in Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Hier erfahren Sie, wie Sie ein PowerShell-Skript verwenden, um ein Team für jeden Manager zu erstellen, dessen Direct-Teammitglieder sind.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583674"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Erstellen von Personen-Manager-Teams in Microsoft Teams


Wenn Sie Microsoft Teams ausrollen, anstatt mit einem "leeren Schiefer" (keine Teams oder Kanäle) zu starten, wird dringend empfohlen, ein Basisframework für Teams und Kanäle einzurichten. Auf diese Weise können Sie die "Team-Ausbreitung" verhindern, bei der Benutzerzahl reiche Teams erstellen, wenn Sie Kanäle in vorhandenen Teams erstellen sollten. Um Ihnen den Einstieg in eine gut durchdachte Teams-und Kanalstruktur zu erleichtern, haben wir ein PowerShell-Skript erstellt, das ein Team für jeden Ihrer ersten und zweiten Personen Manager erstellt, wobei die direkten Berichte jedes Managers als Teammitglieder erstellt werden. Hierbei handelt es sich um ein "Point-in-Time"-Skript (es werden Ihre Teams oder Kanäle nicht automatisch aktualisiert, wenn Personen zu einer Organisation hinzugefügt oder daraus entfernt werden). Aber es ist ein wertvolles Tool, mit dem Sie von Anfang an eine bestimmte Reihenfolge für Ihre Teamstruktur aufzwingen können. Dieses Skript liest Ihre Azure AD, ruft eine Liste der Manager und deren direkte Berichte ab. In dieser Liste wird ein Team pro Personalmanager erstellt. 

## <a name="how-to-use-the-powershell-script"></a>Verwenden des PowerShell-Skripts 

Beginnen Sie mit der Ausführung der [Export Manager und Ihres Direct-Skripts](scripts/powershell-script-create-teams-from-managers-export-managers.md) (wobei davon ausgegangen wird, dass Sie die PowerShell [-Module Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) und [Connect-Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) bereits ausgeführt haben). Die *Export Manager und deren directs* -Skript erstellen eine tabstoppgetrennte Datei (ExportedManagerDirects.txt), in der alle Manager mit ihren direkten Berichten aufgelistet sind. 

Führen Sie dann das [Skript "neue Personen-Manager-Teams erstellen](scripts/powershell-script-create-teams-from-managers-new-teams.md)" aus. Dieses Skript liest in der ExportedManagerDirects.txt-Datei und erstellt ein Team für jeden Manager, dessen direkte Berichte dieser Manager als Mitglieder sind. Wenn Manager oder Direct für Teams nicht aktiviert ist, werden Sie vom Skript übersprungen, und es wird kein Team erstellt. (Überprüfen Sie den Bericht, und führen Sie dann das Skript erneut aus, nachdem Sie die Teams für alle Benutzer aktiviert haben, die Sie benötigen. Das Skript erstellt kein zweites Team für einen Manager, für den es bereits ein Team erstellt hat.)

Für jedes Team erstellt das Skript einen allgemeinen und "nur für Spaß"-Kanal. 

## <a name="best-practices"></a>Bewährte Methoden

- Bitten Sie jeden Personen Manager, die Website für die Krisenkommunikation Ihrer Organisation als Registerkarte zum Kanal "Allgemein" für jedes Team hinzuzufügen. 

- Schauen Sie sich die neue APP für Krisenkommunikation an, indem Sie diesen Blogbeitrag vom 8. März 2020: [koordinieren der Krisenkommunikation mit Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Verwandte Themen

[Bewährte Methoden zum Organisieren von Teams](best-practices-organizing.md)

[Erstellen eines organisationsweiten Teams in Teams](create-an-org-wide-team.md)
