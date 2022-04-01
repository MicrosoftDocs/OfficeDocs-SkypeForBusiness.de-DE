---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593662"
---
Stellen Sie vor Beginn sicher, dass Sie über die folgenden Voraussetzungen verfügen:

- Blue Yonder WFM Version 2020.3, 2021.1 oder 2021.2.

    > [!NOTE]
    > Wenn Sie über Blue Yonder WFM 2020.3 oder 2021.1 verfügen, wenden Sie das Patch 2020.3.0.4 oder 2021.1.0.3 an. Dieser Patch behebt ein Problem, bei dem Benutzer in Schichten eine dauerhafte Fehlermeldung erhalten. Außerdem wird ein Problem behoben, das verhindert, dass Benutzer ihre Verfügbarkeit in Schichten aktualisieren.

- Name des Blue Yonder WFM-Dienstkontos sowie Kennwort- und Dienst-URLs:

    - Verbundauthentifizierungs-URL
    - COOKIE-Authentifizierungs-URL
    - Mitarbeiter-Self-Service-URL
    - URL der Einzelhandels-Web-API
    - URL der Website-Manager-API
    - VERWALTUNGS-API-URL

    Wenn Ihnen diese Informationen nicht zur Verfügung sind, wenden Sie sich an den Blue Yonder-Support. Das Konto wird auf Unternehmensstammebene von einem Unternehmensadministrator von Blue Yonder erstellt. Sie muss über API-Zugriff, Clientadministrator und Store-Manager-Zugriff verfügen. Das Konto und das Kennwort sind erforderlich, um eine Verbindung herzustellen.
- Die Verbund-SSO-Authentifizierung ist in Ihrer Blue Yonder WFM-Umgebung aktiviert. Wenden Sie sich an den Blue Yonder-Support, um sicherzustellen, dass Verbund-SSO aktiviert ist. Sie benötigen die folgenden Informationen:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` dabei ist {TenantId} Ihre Mandanten-ID.
     - proxyHeader: X-MS-AuthToken

- Mindestens ein Team ist in der Teams.
- Sie haben Ihr Microsoft 365-Systemkonto als Teambesitzer zu allen Teams hinzugefügt, die Sie karten möchten.</br> [Erstellen Sie dieses Konto in Microsoft 365](/microsoft-365/admin/add-users/add-users), und weisen Sie ihm eine Microsoft 365 zu. Fügen Sie dann das Konto als Teambesitzer zu allen Teams hinzu, die Sie zuordnungen möchten. Der Schichten-Connector verwendet dieses Konto beim Synchronisieren von Schichtenänderungen von Blue Yonder WFM.

    Wir empfehlen, dass Sie zu diesem Zweck ein bestimmtes Konto erstellen und nicht Ihr Benutzerkonto verwenden.