---
title: Microsoft-Teams, Verwendung bezogenen Verzeichnissuche
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
ms.openlocfilehash: 65952539ceb52ec62f0c6cd2520f8b898a6a89b5
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839262"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft-Teams, Verwendung bezogenen Verzeichnissuche

Microsoft-Teams, bereichsbasierte Verzeichnissuche finden kann Organisationen virtuelle Grenzen erstellen, die steuern, wie Benutzer suchen und mit anderen Benutzern in ihrer Organisation kommunizieren können. 

Microsoft-Teams können Organisationen benutzerdefinierte Ansichten des Verzeichnisses für ihre Benutzer bereitstellen. Microsoft-Teams, verwendet [Exchange adressbuchrichtlinien](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) , um diese benutzerdefinierten Ansichten unterstützen. Nachdem die Richtlinien aktiviert sind, werden von der Suche für andere Benutzer (beispielsweise um einen Chat zu initiieren oder ein Team Mitglieder hinzu) zurückgegebenen Ergebnisse gemäß den konfigurierten Richtlinien zugewiesen. Benutzer werden nicht suchen oder erkennen und neue Teams außerhalb diese Richtlinien beitreten können. 

## <a name="when-should-you-use-scoped-directory-searches"></a>Wann sollten Sie bereichsbezogenen Verzeichnissuchen werden verwendet?

Szenarien, die von bereichsbezogenen Verzeichnissuchen profitieren ähneln Address Book Policy Szenarien. Sie möchten beispielsweise bereichsbezogenen Verzeichnissuche in den folgenden Situationen verwenden:

- Ihre Organisation verfügt über mehrere Mandanten innerhalb dessen Mandanten, die Sie trennen möchten. 
- Ihre Schule möchte Chats zwischen Fakultät und Schüler zu beschränken. 
 
Weitere Informationen finden Sie Informationen zu wie adressbuchrichtlinien verwendet werden können [hier](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).

> [!IMPORTANT]
> Adressbuchrichtlinien enthalten nur eine virtuelle Trennung von Benutzern aus der Perspektive Directory. Benutzer können weiterhin initiieren Kommunikation mit anderen Personen vollständige e-Mail-Adressen bereitstellt. 

## <a name="enable-scoped-directory-search"></a>Aktivieren Sie bereichsbezogenen Verzeichnissuche

1.  Verwenden Sie adressbuchrichtlinien, um Ihre Organisation in virtuellen Untergruppen konfigurieren. Weitere Informationen finden Sie unter [Prozeduren für adressbuchrichtlinien](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).

2.  Melden Sie sich bei Microsoft 365 Administrationscenter, wählen Sie **Admin centers**und wählen Sie dann **Teams & Skype**.
 
3.  Wählen Sie in der Microsoft-Teams & Skype für Business Administrationscenter **Org geltende Einstellungen** > **Teams Einstellungen**.

4.  Aktivieren Sie unter **Search**neben- **Bereich der Verzeichnissuche in eine adressbuchrichtlinie (APB) für das Exchange-Teams**die Umschaltfläche **auf**. 

    ![Bereich der Verzeichnissuche in Teams & Skype für Business-Verwaltungskonsole](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Hybridkonfigurationen (mit lokale Exchange-Teams) unterstützt bereichsbezogenen Search-Modus nicht. 

