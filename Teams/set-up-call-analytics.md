---
title: Einrichten der Anrufanalyse für Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Richten Sie die Anrufanalyse pro Benutzer ein, um Probleme mit der Anrufqualität in Microsoft Teams zu identifizieren und zu beheben.
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789940"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Einrichten der Anrufanalyse für Microsoft Teams

Als Microsoft Teams-Administrator können Sie die Anrufanalyse pro Benutzer verwenden, um Probleme mit der Qualität von Teams-Anrufen und Verbindungsproblemen für **einzelne Benutzer** zu beheben. Um die Anrufanalyse in vollem Umfang nutzen zu können, richten Sie Folgendes ein:
  
- Weisen Sie Personen spezielle Supportrollen zu, z. B. Helpdesk-Agents, damit diese anrufanalyse für Benutzer anzeigen können. Diese Supportrollen können nicht auf den Rest des Teams Admin Centers zugreifen. 
    
- Fügen Sie Gebäude-, Website- und Mandanteninformationen zur Anrufanalyse pro Benutzer hinzu, indem Sie eine TSV- oder .csv-Datendatei hochladen.
    
Wenn Sie bereit sind, mit der Verwendung der Anrufanalyse pro Benutzer zu beginnen, lesen [Sie "Verwenden der Anrufanalyse pro Benutzer", um probleme mit schlechter Anrufqualität zu beheben](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Erteilen der Berechtigung für Support- und Helpdeskmitarbeiter

Als Teams-Administrator haben Sie vollumfänglichen Zugriff auf Anrufanalyseinformationen für alle Benutzer. Wir haben einige spezielle Azure Active Directory-Rollen erstellt, die Sie Supportmitarbeitern und Helpdesk-Agents zuweisen können, damit diese auch auf die Anrufanalyse pro Benutzer zugreifen können (ohne Zugriff auf den Rest des Teams Admin Centers zu haben). Weisen Sie die **Rolle des Teams-Kommunikationssupports** Benutzern zu, die eine eingeschränkte Ansicht der Anrufanalyse pro Benutzer haben sollten (Unterstützung der Stufe 1). Weisen Sie die Rolle des **Teams-Kommunikationssupporttechnikers** Benutzern zu, die Vollzugriff auf die Anrufanalyse pro Benutzer benötigen (Unterstützung der Stufe 2). Keine der Rollen hat Zugriff auf den Rest des Teams Admin Centers.

Um zu erfahren, was jede dieser Rollen bewirkt, lesen Sie [, was die einzelnen Teams-Supportrollen tun](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Weitere Informationen zu Teams-Administratorrollen finden [Sie unter Verwenden von Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md). Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie [unter "Anzeigen und Zuweisen von Rollen in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)".

Informationen zum Zuweisen administrativer Rollen in Azure Active Directory finden Sie [unter "Anzeigen und Zuweisen von Rollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)".

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen

Sie können Gebäude-, Website- und Mandanteninformationen zur Anrufanalyse pro Benutzer hinzufügen, indem Sie eine .csv- oder TSV-Datei hochladen. Mit all diesen Informationen kann die Anrufanalyse IP-Adressen physischen Standorten zuordnen. Administratoren und Helpdesk-Agents können diese Informationen verwenden, um Trends bei Anrufproblemen zu erkennen. Warum haben Benutzer im selben Gebäude beispielsweise ähnliche Probleme mit der Anrufqualität? 

Wenn Sie ein Teams- oder Skype for Business-Administrator sind, können Sie eine vorhandene Mandanten- und Gebäudedatendatei aus dem Teams- oder Skype for Business Anrufqualitätsdashboard (Call Quality Dashboard, CQD) verwenden. Zuerst laden Sie die Datei aus dem CQD herunter und laden sie dann in die Anrufanalyse hoch. 

- Um eine vorhandene Datendatei herunterzuladen, wechseln Sie zu **Microsoft Teams Admin Center** > **Analytics & berichtet, dass** >  das **Anrufqualitätsdashboard** > **jetzt hochgeladen wird**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**. 

- Informationen zum Hochladen der neuen Datei finden [Sie unter Hinzufügen und Aktualisieren von Berichtsbezeichnungen](/microsoftteams/learn-more-about-site-upload).
  
Wenn Sie die TSV- oder .csv-Datei von Grund auf neu erstellen, lesen Sie ["Mandanten- und Gebäudedaten hochladen"](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Verwandte Themen

[Verwenden der Anrufanalyse pro Benutzer zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
