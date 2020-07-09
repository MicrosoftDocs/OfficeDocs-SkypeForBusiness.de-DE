---
title: Einrichten von Anruf Analysen für Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
description: Richten Sie eine pro-Benutzer-anrufanalyse ein, um Probleme mit der Anrufqualität von Microsoft Teams zu identifizieren und zu beheben.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085311"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Einrichten von Anruf Analysen für Microsoft Teams

Als Microsoft Teams-Administrator können Sie benutzerspezifische Anruf Analysen verwenden, um die Anrufqualität von Teams und Verbindungsprobleme für **einzelne Benutzer**zu beheben. Um die Vorteile der anrufanalyse optimal zu nutzen, müssen Sie Folgendes einrichten:
  
- Weisen Sie Personen wie Helpdesk-Agents spezielle Support Rollen zu, damit Sie die anrufanalyse für Benutzer anzeigen können. Diese Support Rollen können nicht auf das restliche Team Admin Center zugreifen. 
    
- Fügen Sie Informationen zu Gebäude-, Website-und Mandanteninformationen für die benutzerspezifische anrufanalyse hinzu, indem Sie eine TSV-oder CSV-Datendatei hochladen.
    
Wenn Sie bereit sind, die benutzerspezifische anrufanalyse zu verwenden, lesen Sie [Verwenden von benutzerspezifischer anrufanalyse, um eine schlechte Anrufqualität zu beheben](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Erteilen der Berechtigung für Support-und Helpdesk-Mitarbeiter

Als Team-Administrator haben Sie vollständigen Zugriff auf die anrufanalyse Informationen für alle Benutzer. Wir haben einige spezielle Azure Active Directory-Rollen erstellt, die Sie den Supportmitarbeitern und Helpdesk-Agents zuweisen können, damit Sie auch auf die benutzerspezifische anrufanalyse zugreifen können (ohne Zugriff auf das restliche Team Admin Center). Weisen Sie die Rolle des **Teams Communications Support Specialist** für Benutzer zu, die eine begrenzte Ansicht der pro-Benutzer-anrufanalyse (Stufe 1-Unterstützung) haben sollten. Weisen Sie die Rolle **Teams Communications Support Engineer** Benutzern zu, die vollständigen Zugriff auf die pro-Benutzer-anrufanalyse benötigen (Support für Stufe 2). Keine der Rollen hat Zugriff auf das restliche Team Admin Center.

Wenn Sie wissen möchten, was jede dieser Rollen tut, lesen Sie [Was ist die Rolle jedes Teams unterstützen](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Weitere Informationen zu Teams-Administratorrollen finden Sie unter Verwenden von Teams- [Administratorrollen zum Verwalten von Teams](using-admin-roles.md). Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [anzeigen und Zuweisen von Rollen in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [anzeigen und Zuweisen von Rollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen

Sie können der pro-Benutzer-anrufanalyse Gebäude-, Website-und Mandanteninformationen hinzufügen, indem Sie eine CSV-oder TSV-Datei hochladen. Mit all diesen Informationen können Anruf Analysen IP-Adressen physikalischen Speicherorten zuordnen. Administratoren und Helpdesk-Agents können diese Informationen dazu verwenden, Trends bei Anruf Problemen zu erkennen. Warum haben Benutzer im gleichen Gebäude beispielsweise ähnliche Probleme mit der Anrufqualität? 

Wenn Sie ein Team oder ein Skype for Business-Administrator sind, können Sie eine vorhandene Mandanten-und Gebäude Datendatei aus dem Dashboard Teams oder Skype for Business-Anrufqualität (CQD) verwenden. Zuerst laden Sie die Datei von CQD herunter, und laden Sie Sie dann in die anrufanalyse hoch. 

- Wenn Sie eine vorhandene Datendatei herunterladen möchten, wechseln Sie jetzt zum **Microsoft Teams Admin Center**-  >  **Anruf Quality-Dashboard**  >  **hochladen**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**. 

- Wenn Sie die neue Datei hochladen möchten, wechseln Sie zu den **Microsoft Teams Admin Center**-  >  **Speicherorten**, und wählen Sie dann **Standortdaten hochladen** oder **Standortdaten ersetzen**aus.
  
Wenn Sie die TSV-oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Verwandte Themen

[Verwenden von pro-Benutzer-Anruf Analysen zur Behandlung schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
