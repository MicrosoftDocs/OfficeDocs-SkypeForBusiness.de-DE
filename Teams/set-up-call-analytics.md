---
title: Einrichten von Anrufanalysen für Microsoft Teams
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
description: Richten Sie die Anrufanalyse pro Benutzer ein, um Probleme mit der Anrufqualität von Microsoft Teams zu identifizieren und zu beheben.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117133"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Einrichten von Anrufanalysen für Microsoft Teams

Als Microsoft Teams-Administrator können Sie die Anrufanalyse pro Benutzer verwenden, um Probleme mit der Anrufqualität und Verbindung von Teams für **einzelne Benutzer zu beheben.** Um die Anrufanalyse in vollem Nutzen zu nutzen, richten Sie Folgendes ein:
  
- Weisen Sie Bestimmten, z. B. Helpdeskmitarbeitern, spezielle Supportrollen zu, damit sie Anrufanalysen für Benutzer anzeigen können. Diese Supportrollen können nicht auf den Rest des Teams Admin Centers zugreifen. 
    
- Fügen Sie Gebäude-, Website- und Mandanteninformationen zur Anrufanalyse pro Benutzer hinzu, indem Sie eine TSV- oder CSV-Datendatei hochladen.
    
Wenn Sie bereit sind, die Anrufanalyse pro Benutzer zu verwenden, lesen Sie Verwenden der Anrufanalyse pro Benutzer zur Problembehandlung bei schlechter [Anrufqualität.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Erteilen von Berechtigungen für Support- und Helpdeskmitarbeiter

Als Teams-Administrator haben Sie vollzugriff auf Anrufanalyseinformationen für alle Benutzer. Wir haben einige spezialisierte Azure Active Directory-Rollen erstellt, die Sie Supportmitarbeitern und Helpdeskmitarbeitern zuweisen können, damit sie auch auf Anrufanalysen pro Benutzer zugreifen können (ohne Zugriff auf das restliche Teams Admin Center). Weisen Sie **den Benutzern,** die über eine eingeschränkte Ansicht der Anrufanalyse pro Benutzer verfügen sollten (Support der Stufe 1), die Spezielle Rolle des Teams-Kommunikationssupports zu. Weisen Sie den **Benutzern,** die vollzugriff auf die Anrufanalyse pro Benutzer benötigen (Support der Stufe 2), die Rolle des Teams Communications Support Engineering zu. Keine rolle hat Zugriff auf den Rest des Teams Admin Centers.

Informationen dazu, welche Funktionen jede dieser Rollen hat, finden Sie unter Was macht [jede Teams-Support-Rolle?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Weitere Informationen zu Teams-Administratorrollen finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams.](using-admin-roles.md) Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [Anzeigen und Zuweisen von Rollen in Azure Active Directory.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Informationen zum Zuweisen administrativer Rollen in Azure Active Directory finden Sie unter [Anzeigen und Zuweisen von Rollen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen

Sie können Gebäude-, Website- und Mandanteninformationen zur Anrufanalyse pro Benutzer hinzufügen, indem Sie eine CSV- oder TSV-Datei hochladen. Bei all diesen Informationen kann die Anrufanalyse IP-Adressen physischen Speicherorten zuordnungen. Administratoren und Helpdeskmitarbeiter können diese Informationen verwenden, um Trends bei Anrufproblemen zu erkennen. Warum haben Benutzer im gleichen Gebäude beispielsweise ähnliche Probleme mit der Anrufqualität? 

Wenn Sie ein Teams- oder Skype for Business-Administrator sind, können Sie einen vorhandenen Mandanten verwenden und datendatei aus dem Teams oder Skype for Business Call Quality Dashboard (CQD) erstellen. Zuerst laden Sie die Datei aus CQD herunter, und laden Sie sie dann in die Anrufanalyse hoch. 

- Wenn Sie eine vorhandene Datendatei herunterladen möchten, wechseln Sie jetzt zum **Microsoft Teams Admin Center** Call Quality  >  **Dashboard**  >  **Upload**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**. 

- Um die neue Datei hochzuladen, wechseln Sie zu **Microsoft Teams Admin Center** Locations , und wählen Sie dann Standortdaten hochladen oder  >   **Standortdaten ersetzen aus.** 
  
Wenn Sie die TSV- oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Hochladen von Mandanten- und Gebäudedaten.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Verwenden der Anrufanalyse pro Benutzer zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)