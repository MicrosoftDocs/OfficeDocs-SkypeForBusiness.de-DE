---
title: "Office 365-Abhängigkeiten für Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams nutzt Office 365-Gruppen, SharePoint Online und OneDrive for Business."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Office 365-Abhängigkeiten für Microsoft Teams
===========================================

Microsoft Teams nutzt Office 365-Gruppen zum Speichern von Teammitgliedschaften und anderen Eigenschaften, wie zum Beispiel Einstellungen zur Klassifizierung von Teamdaten. Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann. 

Microsoft Teams nutzt außerdem SharePoint Online und OneDrive for Business zum Speichern von Dateien und Dokumenten für Kanäle und Chatunterhaltungen. Microsoft Teams nutzt darüber hinaus Office 365-Gruppen zum Speichern von Teammitgliedschaften und anderen Eigenschaften, wie zum Beispiel Einstellungen zur Klassifizierung von Teamdaten. Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.
  
    
    
Um alle Gastzugriffsfunktionen in Microsoft Teams zu aktivieren, müssen Office 365-Administratoren für die folgenden Einstellungen die Option **Ein** auswählen:
  
    
    

- In SharePoint Online: **Freigabe nur für bereits im Verzeichnis enthaltenen externen Benutzern zulassen**
    
    Weitere Informationen finden Sie unter [Verwalten von externer Freigabe für Ihre SharePoint Online-Umgebung](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- In Office 365-Gruppen: **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen**
    
    Weitere Informationen finden Sie unter [Steuern des Gastzugriffs auf Microsoft Teams](#controlguest).
  

Sie können SharePoint Online-Einstellungen für externe Benutzer für die mit Microsoft Teams verbundene Teamwebsite verwalten. Weitere Einzelheiten finden Sie unter [Verwalten der Einstellungen Ihrer SharePoint-Teamwebsite](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿