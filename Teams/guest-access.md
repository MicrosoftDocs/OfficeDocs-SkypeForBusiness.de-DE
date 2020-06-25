---
title: Gastzugriff in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c025e408842c3d883112b7c99d930fc77db47435
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44867972"
---
<a name="guest-access-in-microsoft-teams"></a>Gastzugriff in Microsoft Teams
======================================

Mit Gastzugriff können Sie einzelne Benutzer von außerhalb Ihrer Organisation zu Ihren Teams und Kanälen in Microsoft Teams hinzufügen. 

Wenn Sie den externen Zugriff (Partnerverbund) mit Gastzugriff vergleichen möchten (und entscheiden, welchen Sie verwenden sollten), lesen Sie [Kommunizieren mit Benutzern aus anderen Organisationen in Teams](communicate-with-users-from-other-organizations.md).

Wenn Sie bereit sind, den Gastzugriff in Ihrer Organisation zu aktivieren, starten Sie mit der [Checkliste für den Gastzugriff](guest-access-checklist.md).

## <a name="guest-access-overview"></a>Übersicht über Gastzugriff

Gastzugriff ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf vorhandene Teams und Kanäle in Teams gewährt wird. Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams. Als Teams-Administrator können Sie steuern, welche Funktionen Gäste in Teams verwenden (und welche nicht). Informieren Sie sich unter [ Verwalten des Gastzugriffs](manage-guests.md).

Der Gastzugriff ist eine organisationsweite Einstellung in Teams, die standardmäßig deaktiviert ist. Gastzugriff unterliegt Azure AD- und Microsoft 365- oder Office 365-Dienstbegrenzungen.


> [!IMPORTANT]
> Gastbenutzer folgen den organisationsweiten Einstellungen in Teams für den Upgrade-Modus. Dies kann nicht geändert werden.

## <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff

Der Gastzugang ist in allen Abonnements von Microsoft 365 Business Standard, Office 365 Enterprise und Office 365 Education enthalten. Eine zusätzliche Microsoft 365- oder Office 365-Lizenz ist nicht erforderlich. Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Allerdings basiert die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, darauf, was gemäß Ihrer Azure AD-Lizenzierung zulässig ist – in der Regel 5 Gäste pro lizenziertem Benutzer. Weitere Informationen finden Sie unter [Lizenzierung für die Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Microsoft 365- oder Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="who-is-a-guest"></a>Wer ist ein Gast?

Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation. Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein. Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden. Dies bedeutet, dass jeder Benutzer mit einem Business-Konto (d. h. ein Azure Active Directory-Konto) oder E-Mail-Consumer-Konto (mit Outlook.com, Gmail.com oder einer sonstigen Adresse) als Gast in Teams teilnehmen kann – mit vollständigem Zugriff auf Team- und Kanalfunktionen.

Um zu erfahren, welche Berechtigungen Gäste haben, lesen Sie [Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md). Oder sehen Sie sich die Tabelle [Vergleich von Funktionen für Teammitglieder und Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities) an. 

Für alle Gäste in Teams gelten letztlich dieselben Compliance- und Überwachungsmaßnahmen wie überall in Microsoft 365 und Office 365. Sie können in Azure AD sicher verwaltet werden.

## <a name="why-use-guest-access"></a>Warum Gastzugriff verwenden?

Mit Gastzugriff können Organisationen, die Teams verwenden, ihren Partnern Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über ihre eigenen Unternehmensdaten behalten. Für alle Gäste in Teams gelten dieselben Compliance- und Überwachungsmaßnahmen wie überall in Microsoft 365 und Office 365 und die Gäste können in Azure AD sicher verwaltet werden.  

## <a name="understand-the-limitations-for-guests"></a>Grundlegendes zu den Einschränkungen für Gäste

Die Gastumgebung hat Beschränkungen, die beabsichtigt sind. Stellen Sie sicher, dass Sie die Gastumgebung verstehen, damit Sie nicht versuchen, ein Problem zu beheben, das keines ist. Hier finden Sie beispielsweise eine Liste der Funktionen, die für einen Gast in Microsoft Teams nicht verfügbar sind:

- OneDrive for Business
- Personensuche außerhalb von Teams
- Kalender, geplante Besprechungen oder Besprechungsdetails
- Telefonfestnetz (PSTN)
- Organigramm
- Erstellen oder Überarbeiten eines Teams
- Suche nach Teams
- Hochladen von Dateien in einen persönlichen Chat
- Derzeit unterstützt Teams nur die Gastbenutzer vom Typ "Zustand 1" und "Zustand 2" [gemäß der Definition durch Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

Eine vollständige Liste dessen, was ein Gast in Teams tun kann und was nicht, finden Sie in der Tabelle [Vergleich der Funktionen von Teammitgliedern und Gästen](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Wenn Sie mehr über den Gastzugriff auf der Microsoft 365- und Office 365-Ebene wissen möchten, lesen Sie [Hinzufügen von Gästen zu Microsoft 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).


## <a name="more-information"></a>Weitere Informationen

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[Gastzugriff in Microsoft 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
