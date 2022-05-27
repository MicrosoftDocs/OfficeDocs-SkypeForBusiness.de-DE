---
title: Planen von Konferenzen per Telefonieanbieter
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über Konferenzen per Telefonieanbieter, z. B. Anforderungen und planung für die Bereitstellung.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881df7d9bd2d2d2bcbf6775654a97066a2927250
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676017"
---
# <a name="plan-for-operator-connect-conferencing"></a>Planen von Konferenzen per Telefonieanbieter

Microsoft Audiokonferenz bietet die Möglichkeit, sich mit PSTN-Telefonnummern (Public Switched Telephone Network) in eine Konferenz ein- und aus einer Konferenz herauszuwählen.  Teilnehmer nehmen mithilfe einer Audiokonferenzbrücke an Microsoft Teams Besprechungen teil.

Mit Konferenzen per Telefonieanbieter Funktionen können Organisationen Telefonnummern eines Drittanbieters verwenden, um an Microsoft Teams Besprechungen teilzunehmen. Wenn Ihr aktueller Operator Teil des Microsoft Telefonieanbieter-Programms ist, können Sie Telefonnummern von Ihrem Betreiber zu Ihrer Audiokonferenz Brücke hinzufügen und diese für die Teilnahme an Besprechungen verwenden.

Ohne Konferenzen per Telefonieanbieter Funktionen können Organisationen nur die von Microsoft bereitgestellten Telefonnummern für ihre Audiokonferenzbrücke verwenden.

>[!NOTE]
>Auf einen Telefonnummernanbieter, der Teil des Microsoft Telefonieanbieter-Programms ist, wird in diesem Artikel als "Operator" verwiesen.
>
>Informationen dazu, ob Ihr Betreiber am Microsoft Telefonieanbieter-Programm teilnimmt, finden Sie im [Microsoft 365 Telefonieanbieter Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

In diesem Artikel werden Konferenzen per Telefonieanbieter beschrieben:

- [Vorteile](#benefits)
- [Lizenzierungsanforderungen und Abrechnung](#licensing-requirements-and-billing)
- [Weitere Informationen zu Microsoft Audiokonferenz](#additional-information-on-microsoft-audio-conferencing)

Informationen zum Konfigurieren von Konferenzen per Telefonieanbieter finden [Sie unter Konfigurieren Konferenzen per Telefonieanbieter](operator-connect-conferencing-configure.md).

Wenn einige Benutzer Ihrer Organisation externe Anrufe an PSTN-Telefonnummern tätigen müssen, benötigen Sie dennoch einen Anrufplan. Informationen zur Verwendung eines Drittanbieter-Operators für externe PSTN-Verbindungen finden Sie unter [Plan for Telefonieanbieter](operator-connect-plan.md).

## <a name="benefits"></a>Vorteile

Konferenzen per Telefonieanbieter bietet die folgenden Vorteile:

- **Flexible Zuweisung von Telefonnummern zwischen Ihrem Betreiber und Microsoft.** Verwenden Sie Telefonnummern von Microsoft und Ihrem Anbieter (nur mit einem Microsoft Audiokonferenz Standard-Abonnement), oder verwenden Sie nur Telefonnummern von Ihrem Anbieter (nur mit einer Konferenzen per Telefonieanbieter Lizenz).

- **Vom Betreiber verwaltete Infrastruktur.** Ihr Operator verwaltet die Session Border Controller (SBCs) und die Interkonnektivität mit Microsoft, wodurch Sie von zusätzlichen Hardwarekäufen und -verwaltungen profitieren.

- **Schnellere, einfachere Bereitstellung.** Stellen Sie schnell eine Verbindung mit Ihrem Betreiber her, und weisen Sie Ihrer Audiokonferenz Brücke aus dem Teams Admin Center Telefonnummern zu.

- **Verbesserte Unterstützung und Zuverlässigkeit.** Betreiber bieten technischen Support und gemeinsame Vereinbarungen zum Servicelevel, um den Servicesupport zu verbessern, und direktes Peering, das von Azure unterstützt wird, erstellt eine 1:1-Netzwerkverbindung für erhöhte Zuverlässigkeit.

Konferenzen per Telefonieanbieter ist möglicherweise die richtige Lösung für Ihre Organisation, wenn:

- Sie möchten **Ihre Verträge** mit Ihrem bestehenden Telefonnummernanbieter beibehalten.

- Sie möchten **die globale Abdeckung** Ihrer vorhandenen Microsoft Audiokonferenz-Brücke erweitern.

- Sie möchten **Telefonnummern für Audiokonferenz** von einem neuen Telefonnummernanbieter beziehen.

- **Microsoft Audiokonferenz ist an Ihrem geografischen Standort nicht verfügbar**

- Sie möchten **einen Anbieter für Audiokonferenz-Dienste mit einem Minuten-Pay-per-Minute-Modell nutzen**, z. B. gebührenfreie Telefonnummern verwenden und ausgehende Anrufe von Teams Besprechungen an Telefonnummern in Ländern tätigen, die nicht in Ihrem Abonnement enthalten sind.

## <a name="licensing-requirements-and-billing"></a>Lizenzierungsanforderungen und Abrechnung

Benutzern, die Konferenzen per Telefonieanbieter Nummern benötigen, um an den von ihnen organisierten Besprechungen teilzunehmen, muss ihnen entweder ein Microsoft Audiokonferenz Standard-Abonnement oder eine Microsoft Konferenzen per Telefonieanbieter-Lizenz zugewiesen sein.

### <a name="audio-conferencing-standard-subscription"></a>Audiokonferenz Standardabonnement

Ein Microsoft Audiokonferenz Standard-Abonnement kann als Add-On für eine Microsoft Teams-Lizenz erworben werden und ist auch in Microsoft 365 E5- und Office 365 E5-Abonnements enthalten.

Mit dem Audiokonferenz Standard-Abonnement können Abonnenten Telefonnummern von Microsoft verwenden und ihre Audiokonferenzbrücken mit Nummern eines Anbieters erweitern. Abonnenten können auch entscheiden, welche ausgehenden Anrufe von Teams Besprechungen über Microsoft weitergeleitet werden sollen und welche Anrufe über einen Anbieter weitergeleitet werden sollen.

Weitere Informationen finden [**Sie unter Konfigurieren Konferenzen per Telefonieanbieter**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>Konferenzen per Telefonieanbieter-Lizenz

Eine Microsoft Konferenzen per Telefonieanbieter-Lizenz kann als Add-On zu einer Microsoft Teams-Lizenz erworben werden.

Die Konferenzen per Telefonieanbieter-Lizenz ermöglicht Es Abonnenten, Telefonnummern von einem Anbieter zu verwenden, enthält jedoch keine Telefonnummern von Microsoft. Alle ausgehenden Anrufe aus Teams Besprechungen müssen über einen Operator weitergeleitet werden.

Weitere Informationen finden [**Sie unter Konfigurieren Konferenzen per Telefonieanbieter**](operator-connect-conferencing-configure.md).

>[!Note]
>Besprechungsteilnehmer benötigen keine Audiokonferenz Standardabonnementlizenz oder eine Konferenzen per Telefonieanbieter Lizenz, um an einer Besprechung teilzunehmen, die von einem Benutzer mit Konferenzen per Telefonieanbieter Funktionen organisiert wurde.

Bei Konferenzen per Telefonieanbieter berechnet Microsoft Ihre Organisation gemäß dem Typ der Audiokonferenz Lizenz, die von Ihrer Organisation, Microsoft Audiokonferenz oder Konferenzen per Telefonieanbieter und die Verwendung aller von Microsoft bereitgestellten Telefonnummern.

Ihr Betreiber berechnet Ihrer Organisation die Verwendung von Konferenzen per Telefonieanbieter von ihnen bereitgestellten Nummern.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Weitere Informationen zu Microsoft Audiokonferenz

Mit Microsoft Audiokonferenz können Teilnehmer an Microsoft Teams Besprechungen teilnehmen, indem sie sich mit einer PSTN-Telefonnummer einwählen oder eine PSTN-Telefonnummer anrufen. Weitere Informationen zu Microsoft Audiokonferenz Für Ihre Organisation verfügbaren Funktionen finden Sie [unter Audiokonferenz in Microsoft 365](audio-conferencing-in-office-365.md).
