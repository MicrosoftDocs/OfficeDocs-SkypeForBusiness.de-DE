---
title: Gastzugriff in Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c2e13a97c367a61559a33ea0229d7ef682744c7
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706267"
---
<a name="guest-access-in-microsoft-teams"></a>Gastzugriff in Microsoft Teams
======================================

## <a name="guest-access-overview"></a>Übersicht über den Datenzugriff Gast

Gastzugriff ist eines der Features, die für die meisten Kunden hatten. Hier wird, wie Sie mit den Fortschritt auf Gast Access halten und teilen Sie uns Ihre Meinung:

- Wenn Sie Probleme mit dem Gastzugriff haben, lesen Sie [Bekannte Probleme für Microsoft Teams](Known-issues.md).
- Informationen zu geplanten neuen oder aktualisierten Funktionen finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).
- Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.
- Berichten Sie unten im Abschnitt „Kommentare“ über Ihre Erfahrungen.

Gast Access ermöglicht Teams in Ihrer Organisation für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation durch gewähren sie Zugriff auf vorhandenen Teams und Kanäle in einem oder mehreren Mandanten. Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams.

Gastzugriff ist in allen Office 365 Business Premium, Office 365 Enterprise und Office 365 Education Abonnements mit keine zusätzliche Lizenzierung Anforderung enthalten. Sie können bis zu 5 Gäste pro lizenzierten Benutzer bei Ihrem Mandanten haben. Weitere Informationen zur Lizenzierung finden Sie unter [Azure Active Directory B2B Zusammenarbeit Lizenzierung Anweisungen](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance). 

Der Gastzugriff ist eine Einstellung auf Mandantenebene in Microsoft Teams, die standardmäßig deaktiviert ist. Gast Access unterliegt Azure AD und Einschränkungen für Office 365-Dienst.

> [!NOTE]
> Benutzer in Ihrer Organisation mit Office 365-Abonnement-Plänen nur, wie Exchange Online – Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams betrachtet diese Benutzer in derselben Organisation angehören. Für diese Benutzer zu Teams verwenden müssen sie ein Office 365 Business Premium, Office 365 Enterprise oder Office 365 Education-Abonnement zugewiesen werden. 

## <a name="who-is-a-guest"></a>Wer ist Gastsystem?

Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation. Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein. Jeder Benutzer, der nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden. Dies bedeutet, dass jeder Benutzer mit einer Business-Konto (d. h., ein Azure Active Directory-Konto) oder die Consumer e-Mail-Konto (mit Outlook.com, Gmail.com oder andere) als Gast in Teams, mit Vollzugriff auf den Teams teilnehmen kann und Channel guter. (Sie können über Gast Einschränkungen in [Access Gast autorisieren Microsoft-Teams](teams-dependencies.md)lesen.) Alle Gäste in Teams unterliegen den gleichen Einhaltung von Vorschriften und Überwachung Schutz als den Rest von Office 365 und in Azure AD sicher verwaltet werden können.

## <a name="why-use-guest-access"></a>Gründe für die Verwendung von Access Gast
      
Mit Gast Access können Organisationen, mit denen Teams externen Zugriff auf Teams, Dokumente in Kanäle, Ressourcen, Chats und an ihre Partner Applications Beibehaltung vollständige Kontrolle über ihre eigenen Unternehmensdaten bereitstellen. Alle Gäste in Teams unterliegen den gleichen Einhaltung von Vorschriften und Überwachung Schutz als den Rest von Office 365 und Gäste in Azure AD sicher verwaltet werden können.  

Teams basiert auf Office 365-Gruppen und bietet eine neue Möglichkeit zum Zugriff auf gemeinsame Elemente für ein Office 365-Gruppe. Teams ist die beste Lösung für beständigen Chat zwischen Gruppen- bzw. Teammitgliedern. Office 365-Gruppen ist ein Dienst, der anwendungsübergreifende Mitgliedschaft für bestimmte freigegebene Teamressourcen (beispielsweise eine SharePoint-Website oder ein Power BI-Dashboard) bietet, damit das Team effektiv und sicher zusammenarbeiten kann. 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a>Wie Vergleich Access Gast im zu den externen Zugriff (Verbund)?

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Weitere Informationen
    
[Supportressourcen für Microsoft Teams](support-resources.md)  
[Gast Access in Office 365-Gruppen](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|Einführung in Access Gast   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|Ausführliche Behandlung von Gastzugriff   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| Hinzufügen von Gäste in Microsoft-Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

