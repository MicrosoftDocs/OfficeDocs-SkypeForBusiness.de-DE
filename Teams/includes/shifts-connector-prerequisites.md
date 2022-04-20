---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593662"
---
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Voraussetzungen verfügen:

- Blue Yonder WFM Version 2020.3, 2021.1 oder 2021.2.

    > [!NOTE]
    > Wenn Sie über Blue Yonder WFM 2020.3 oder 2021.1 verfügen, wenden Sie den Patch 2020.3.0.4 oder 2021.1.0.3 an. Dieser Patch behebt ein Problem, bei dem Benutzer eine dauerhafte Fehlermeldung in Schichten erhalten. Außerdem wird ein Problem behoben, das verhindert, dass Benutzer ihre Verfügbarkeit in Schichten aktualisieren.

- Name des Blue Yonder WFM-Dienstkontos sowie Kennwort- und Dienst-URLs:

    - Verbundauthentifizierungs-URL
    - COOKIE-Authentifizierungs-URL
    - Self-Service-URL für Mitarbeiter
    - URL der Einzelhandelsweb-API
    - WEBSITE-Manager-API-URL
    - URL der Verwaltungs-API

    Wenn Sie diese Informationen nicht haben, wenden Sie sich an den Blue Yonder-Support. Das Konto wird auf Unternehmensstammebene von einem Blue Yonder-Unternehmensadministrator erstellt. Es muss ÜBER API-Zugriff, Clientadministrator und Store-Manager-Zugriff verfügen. Das Konto und das Kennwort sind erforderlich, um eine Verbindung zu erstellen.
- Die Verbund-SSO-Authentifizierung ist in Ihrer Blue Yonder WFM-Umgebung aktiviert. Wenden Sie sich an den Blue Yonder-Support, um sicherzustellen, dass verbundverbundenes SSO aktiviert ist. Sie benötigen die folgenden Informationen:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` wobei {tenantId} Ihre TenantId ist
     - proxyHeader: X-MS-AuthToken

- In Teams ist mindestens ein Team eingerichtet.
- Sie haben Ihr Microsoft 365-Systemkonto als Teambesitzer zu allen Teams hinzugefügt, die Sie zuordnen möchten.</br> [Erstellen Sie dieses Konto in Microsoft 365](/microsoft-365/admin/add-users/add-users), und weisen Sie ihm eine Microsoft 365 Lizenz zu. Fügen Sie dann das Konto als Teambesitzer allen Teams hinzu, die Sie zuordnen möchten. Der Shifts-Connector verwendet dieses Konto beim Synchronisieren von Schichtenänderungen aus Blue Yonder WFM.

    Es wird empfohlen, dass Sie ein Konto speziell für diesen Zweck erstellen und nicht Ihr Benutzerkonto verwenden.