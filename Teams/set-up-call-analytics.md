---
title: Einrichten der Anrufanalyse für Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Richten Sie die Anrufanalyse pro Benutzer für ein, um Probleme mit der Microsoft Teams zu identifizieren und zu behandeln.
ms.openlocfilehash: 968a4c06d4b1be1384303241d0eb6b45721e833560d46169acf96caa1f18a576
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332537"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Einrichten der Anrufanalyse für Microsoft Teams

Als ein Microsoft Teams können Sie die Anrufanalyse pro Benutzer verwenden, um Probleme Teams Anrufqualität und Verbindungen für **einzelne Benutzer zu beheben.** Um die Anrufanalyse in vollem Nutzen zu nutzen, richten Sie Folgendes ein:
  
- Weisen Sie Personen, z. B. Helpdesk-Agents, spezielle Supportrollen zu, damit diese Anrufanalysen für Benutzer anzeigen können. Diese Supportrollen können nicht auf die restlichen Teams Admin Center zugreifen. 
    
- Fügen Sie Informationen zu Gebäude, Standort und Mandanten zur Anrufanalyse pro Benutzer hinzu, indem Sie eine TSV- .csv Datendatei hochladen.
    
Wenn Sie bereit sind, die Anrufanalyse pro Benutzer zu verwenden, lesen Sie Verwenden der Anrufanalyse pro Benutzer zur Problembehandlung bei schlechter [Anrufqualität.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Erteilen der Berechtigung für Support- und Helpdesk-Mitarbeiter

Als Teams haben Sie Vollzugriff auf Anrufanalyseinformationen für alle Benutzer. Wir haben einige spezielle Azure Active Directory-Rollen erstellt, die Sie supportmitarbeitern und Helpdesk-Agents zuweisen können, damit diese auch auf die Anrufanalyse pro Benutzer zugreifen können (ohne Zugriff auf den Rest des Teams Admin Centers). Weisen Sie **Teams die** Rolle des Experten für die Kommunikationsunterstützung Benutzern zu, die eine eingeschränkte Ansicht der Anrufanalyse pro Benutzer haben sollten (Unterstützung der Stufe 1). Weisen Sie Teams die Rolle des **Kommunikationssupporttechnikers** zu Benutzern zu, die vollständigen Zugriff auf die Anrufanalyse pro Benutzer benötigen (Support der Stufe 2). Keine rolle hat Zugriff auf die restlichen Teams Admin Center.

Informationen dazu, welche Aufgaben jede dieser Rollen hat, finden Sie unter Was Teams [der Rolle "Support" ?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Weitere Informationen zu Teams Administratorrollen finden Sie unter Verwenden Teams administratorrollen zum [Verwalten Teams.](using-admin-roles.md) Informationen zum Zuweisen von Administratorrollen in Azure Active Directory Sie unter Anzeigen und [Zuweisen von Rollen in Azure Active Directory.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Informationen zum Zuweisen von Administratorrollen in einer Azure Active Directory Sie unter Anzeigen und [Zuweisen von Rollen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen

Sie können Gebäude-, Website- und Mandanteninformationen zur Anrufanalyse pro Benutzer hinzufügen, indem Sie eine .csv TSV-Datei hochladen. Mit all diesen Informationen können mit der Anrufanalyse IP-Adressen zu physischen Standorten zugeordnet werden. Administratoren und Helpdesk-Agents können diese Informationen verwenden, um Trends bei Anrufproblemen zu erkennen. Beispiel: Warum haben Benutzer im gleichen Gebäude ähnliche Probleme mit der Anrufqualität? 

Wenn Sie ein Teams oder Skype for Business-Administrator sind, können Sie einen vorhandenen Mandanten verwenden und eine Datendatei aus dem Teams- oder Skype for Business Anrufqualitätsdashboard (CQD) erstellen. Zuerst laden Sie die Datei aus dem AQD herunter und dann in die Anrufanalyse hoch. 

- Um eine vorhandene Datendatei herunterzuladen, wechseln Sie Microsoft Teams Admin Center-Anrufqualitätsdashboard   >    >  **Hochladen .** Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**. 

- Um die neue Datei hochzuladen, wechseln Sie zu **Microsoft Teams Admin Center** Speicherorte , und wählen Sie dann Hochladen  >   **oder** **Speicherortdaten ersetzen aus.**
  
Wenn Sie die TSV- oder .csv-Datei von Grund auf neu erstellen, lesen Hochladen [und Erstellen von Daten.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Verwenden der Anrufanalyse pro Benutzer zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)