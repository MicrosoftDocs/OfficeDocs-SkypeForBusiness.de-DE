---
title: Gastzugriff in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761241"
---
# <a name="guest-access-in-microsoft-teams"></a>Gastzugriff in Microsoft Teams

Gastzugriff ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf vorhandene Teams und Kanäle in Teams gewährt wird. Jeder Benutzer mit einem e-Mail-Konto für Unternehmen oder Verbraucher wie Microsoft 365, Outlook, Gmail oder andere Personen kann als Gast in Teams mit Vollzugriff auf Team-Chats, Besprechungen und Dateien teilnehmen. Als Teams-Administrator können Sie steuern, welche Funktionen Gäste in Teams verwenden (und welche nicht). Informieren Sie sich unter [ Verwalten des Gastzugriffs](manage-guests.md).

Wenn Sie den externen Zugriff (Partnerverbund) mit Gastzugriff vergleichen möchten (und entscheiden, welchen Sie verwenden sollten), lesen Sie [Kommunizieren mit Benutzern aus anderen Organisationen in Teams](communicate-with-users-from-other-organizations.md).

Der Gastzugriff ist eine organisationsweite Einstellung in Teams, die standardmäßig deaktiviert ist. (Sie können den Gastzugriff auf einzelne Teams mithilfe von [Vertraulichkeits Beschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)steuern.)

Wenn Sie mit der Einladung von Gästen zu Teams beginnen möchten, lesen Sie eine der folgenden Themen:

- Informationen zum Konfigurieren des Gastzugriffs für Teams zur allgemeinen Verwendung finden Sie unter [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Informationen zur Zusammenarbeit mit einer Partnerorganisation, die Azure Active Directory verwendet und es Gästen ermöglicht, sich selbst für Team Zugriff zu registrieren, finden Sie unter [Erstellen eines B2B-Extranets mit verwalteten Gästen](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

Gastzugriff unterliegt Azure AD- und Microsoft 365- oder Office 365-Dienstbegrenzungen.

> [!IMPORTANT]
> Gastbenutzer folgen den organisationsweiten Einstellungen in Teams für den Upgrade-Modus. Dies kann nicht geändert werden.

## <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff

Der Gastzugang ist in allen Abonnements von Microsoft 365 Business Standard, Office 365 Enterprise und Office 365 Education enthalten. Eine zusätzliche Microsoft 365- oder Office 365-Lizenz ist nicht erforderlich. Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, kann jedoch durch die kostenpflichtigen Funktionen von Azure AD eingeschränkt sein. Weitere Informationen finden Sie unter [Lizenzierung für die Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Microsoft 365- oder Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="who-is-a-guest"></a>Wer ist ein Gast?

Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation. Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein. Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden. Dies bedeutet, dass jeder Benutzer mit einem Business-Konto (d. h. ein Azure Active Directory-Konto) oder E-Mail-Consumer-Konto (mit Outlook.com, Gmail.com oder einer sonstigen Adresse) als Gast in Teams teilnehmen kann – mit vollständigem Zugriff auf Team- und Kanalfunktionen.

Um zu erfahren, welche Berechtigungen Gäste haben, lesen Sie [Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md). Oder sehen Sie sich die Tabelle [Vergleich von Funktionen für Teammitglieder und Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities) an. 

Schließlich fallen alle Gäste in Teams unter den gleichen Compliance-und Überwachungs Schutz wie die restlichen Microsoft 365 und können in Azure AD verwaltet werden.

## <a name="why-use-guest-access"></a>Warum Gastzugriff verwenden?

Mit Gastzugriff können Organisationen, die Teams verwenden, ihren Partnern Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über ihre eigenen Unternehmensdaten behalten. 

## <a name="understand-the-limitations-for-guests"></a>Grundlegendes zu den Einschränkungen für Gäste

Die Gastumgebung hat Beschränkungen, die beabsichtigt sind. Stellen Sie sicher, dass Sie die Gastumgebung verstehen, damit Sie nicht versuchen, ein Problem zu beheben, das keines ist. Nachfolgend finden Sie eine Liste mit einigen Funktionen, die für einen Gast in Microsoft Teams nicht zur Verfügung stehen:

- OneDrive
- Personensuche außerhalb von Teams
- Kalender, geplante Besprechungen oder Besprechungsdetails
- Telefonfestnetz (PSTN)
- Organigramm
- Erstellen oder Überarbeiten eines Teams
- Suche nach Teams
- Hochladen von Dateien in einen persönlichen Chat
- Derzeit unterstützt Teams nur [Status 1-und State 2-Typen von Gastbenutzern](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) .

Eine vollständige Liste dessen, was ein Gast in Teams tun kann und was nicht, finden Sie in der Tabelle [Vergleich der Funktionen von Teammitgliedern und Gästen](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Weitere Informationen zum Gastzugriff auf der Microsoft 365-Ebene finden Sie unter [Zusammenarbeit mit Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).


## <a name="related-topics"></a>Verwandte Themen

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Konfigurieren von Teams mit drei Schutzebenen](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
