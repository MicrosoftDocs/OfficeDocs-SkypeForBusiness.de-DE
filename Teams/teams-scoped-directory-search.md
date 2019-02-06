---
title: Verwenden der Verzeichnissuche in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Microsoft-Teams, bereichsbasierte Verzeichnissuche verwenden, um benutzerdefinierte Ansichten des Verzeichnisses bereitzustellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a4a36de9b535d7c95f93175a97ce5266fdc37ec
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754307"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Verwenden der Verzeichnissuche in Microsoft Teams

Microsoft-Teams, bereichsbasierte Verzeichnissuche finden kann Organisationen virtuelle Grenzen erstellen, die steuern, wie Benutzer suchen und mit anderen Benutzern in ihrer Organisation kommunizieren können. 

Microsoft-Teams können Organisationen benutzerdefinierte Ansichten des Verzeichnisses für ihre Benutzer bereitstellen. Microsoft-Teams, verwendet [Exchange adressbuchrichtlinien](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) , um diese benutzerdefinierten Ansichten unterstützen. Nachdem die Richtlinien aktiviert sind, werden von der Suche für andere Benutzer (beispielsweise um einen Chat zu initiieren oder ein Team Mitglieder hinzu) zurückgegebenen Ergebnisse gemäß den konfigurierten Richtlinien zugewiesen. Benutzer werden nicht zu suchen oder Teams bei der bereichsbezogenen Suche wirksam ist ermitteln können. 

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie bereichsbezogenen Verzeichnissuchen werden verwendet?

Szenarien, die von bereichsbezogenen Verzeichnissuchen profitieren ähneln Address Book Policy Szenarien. Sie möchten beispielsweise bereichsbezogenen Verzeichnissuche in den folgenden Situationen verwenden:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 
 
Weitere Informationen finden Sie Informationen zu wie adressbuchrichtlinien verwendet werden können [hier](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).

> [!IMPORTANT]
> Adressbuchrichtlinien enthalten nur eine virtuelle Trennung von Benutzern aus der Perspektive Directory. Benutzer können weiterhin initiieren Kommunikation mit anderen Personen vollständige e-Mail-Adressen bereitstellt. Es ist außerdem zu beachten, dass alle Benutzerdaten, die bereits, bevor Sie die Erzwingung von neuen oder aktualisierten adressbuchrichtlinien zwischengespeicherten hatte bis zu 30 Tage für Benutzer verfügbar bleiben.

## <a name="enable-scoped-directory-search"></a>Aktivieren Sie bereichsbezogenen Verzeichnissuche

1.  Verwenden Sie adressbuchrichtlinien, um Ihre Organisation in virtuellen Untergruppen konfigurieren. Weitere Informationen finden Sie unter [Prozeduren für adressbuchrichtlinien](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).

2.  Melden Sie sich bei Microsoft 365 Administrationscenter, wählen Sie **Admin zentriert**, und wählen Sie dann **Teams & Skype**.
 
3.  Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Org geltende Einstellungen** > **Teams Einstellungen**.

4.  Aktivieren Sie unter **Search**neben- **Bereich der Verzeichnissuche in eine adressbuchrichtlinie (APB) für das Exchange-Teams**die Umschaltfläche **auf**. 

    ![Bereich der Verzeichnissuche im Microsoft-Teams, Administrationscenter](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Hybridkonfigurationen (mit lokale Exchange-Teams) unterstützt bereichsbezogenen Search-Modus nicht. 

