---
title: Gastzugriff in Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
localization_priority: Normal
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae1f3149ca915e2fd5a9ddf59fdb0bfad2be2ca2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235563"
---
<a name="guest-access-in-microsoft-teams"></a>Gastzugriff in Microsoft Teams
======================================

## <a name="guest-access-overview"></a>Übersicht Über Gastzugriff

Bei Gastzugriff handelt es sich um eine der meistgewünschten Funktionen. So können Sie sich über unsere Fortschritte beim Gastzugriff auf dem Laufenden halten und uns Ihre Meinung sagen:

- Wenn Sie Probleme mit dem Gastzugriff haben, lesen Sie [Bekannte Probleme für Microsoft Teams](Known-issues.md).
- Informationen zu geplanten neuen oder aktualisierten Funktionen finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).
- Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.
- Berichten Sie unten im Abschnitt „Kommentare“ über Ihre Erfahrungen.

Gastzugriff ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb der Organisation zusammenzuarbeiten, indem ihnen Zugriff auf vorhandene Teams und Kanäle auf einem oder mehreren Ihrer Mandanten gewährt wird. Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams.

Gastzugriff ist in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements ohne zusätzliche Lizenzanforderungen enthalten. Sie können bis zu 5 Gäste pro lizenziertem Benutzer auf Ihrem Mandanten unterstützen. Weitere Informationen zu Lizenzierung finden Sie unter [Lizenzierungsanleitung zur Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance). 

Der Gastzugriff ist eine Einstellung auf Mandantenebene in Microsoft Teams, die standardmäßig deaktiviert ist. Gastzugriff unterliegt Azure AD- und Office 365-Dienstbegrenzungen.

> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutze Teams verwenden können, müssen Sie über ein Office 365 Business Premium-, Office 365 Enterprise- oder Office 365 Education-Abonnement verfügen. 

## <a name="who-is-a-guest"></a>Wer ist ein Gast?

Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation. Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein. Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden. Dies bedeutet, dass jeder Benutzer mit einem Business-Konto (d. h. ein Azure Active Directory-Konto) oder E-Mail-Consumer-Konto (mit Outlook.com, Gmail.com oder einer sonstigen Adresse) als Gast in Teams teilnehmen kann – mit vollständigem Zugriff auf Team- und Kanalfunktionen. (Informationen zu Gastbeschränkungen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md).) Für alle Gäste in Microsoft Teams gelten die gleichen Compliance- und Überwachungsmaßnahmen wie überall in Office 365. Gäste können in Azure AD sicher verwaltet werden.

## <a name="why-use-guest-access"></a>Warum Gastzugriff verwenden?
      
Mit Gastzugriff können Organisationen, die Teams verwenden, ihren Partnern externen Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über ihre eigenen Unternehmensdaten behalten. Für alle Gäste in Microsoft Teams gelten die gleichen Compliance- und Überwachungsmaßnahmen wie überall in Office 365. Gäste können in Azure AD sicher verwaltet werden.  

Teams basiert auf Office 365-Gruppen und bietet neue Möglichkeiten, auf freigegebene Ressourcen für eine Office 365-Gruppe zuzugreifen. Teams ist die beste Lösung für beständigen Chat zwischen Gruppen- bzw. Teammitgliedern. Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann. 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a>Inwiefern unterscheidet sich der Gastzugriff von externem Zugriff (Verbund)?

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Weitere Informationen
    
[Kontaktieren des Office 365 Business-Supports - Administratorhilfe](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  

  [Gastzugriff in Office 365-Gruppen](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|Einführung in Gastzugriff   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|Umfassender Einblick in Gastzugriff   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| Hinzufügen von Gästen in Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

