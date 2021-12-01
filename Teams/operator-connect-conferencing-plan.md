---
title: Planen von Verbinden Konferenzen
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
description: Weitere Informationen zu Operatoren Verbinden Konferenzen, z. B. Anforderungen und Planung der Bereitstellung.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257538"
---
# <a name="plan-for-operator-connect-conferencing"></a>Planen von Verbinden Konferenzen

Microsoft-Audiokonferenzen bieten die Möglichkeit, sich mithilfe von PstN-Telefonnummern (Public Switched Telephone Network) in eine Konferenz ein- und aus einer Konferenz heraus zu wählen.  Teilnehmer nehmen Microsoft Teams über eine Nur-Audio-Konferenzbrücke an Besprechungen teil.

Mit der Verbinden von Konferenzen können Organisationen Telefonnummern von einem Drittanbieter verwenden, um an Besprechungen Microsoft Teams teilzunehmen. Wenn Ihr aktueller Netzbetreiber Teil des Microsoft Operator Verbinden-Programms ist, können Sie Ihrer Audiokonferenzbrücke Telefonnummern von Ihrem Netzbetreiber hinzufügen und diese verwenden, um an Besprechungen teilzunehmen.

Ohne die Verbinden für Audiokonferenzen können Organisationen nur die von Microsoft bereitgestellten Telefonnummern für ihre Audiokonferenzbrücke verwenden.

>[!NOTE]
>Ein Telefonnummernanbieter, der Teil des Microsoft Operator Verbinden Programm ist, wird in diesem Artikel als "Operator" bezeichnet.
>
>Wenn Sie sehen möchten, ob Ihr Operator am Microsoft Operator Verbinden-Programm teil nimmt, lesen Sie Microsoft 365 [Operator Verbinden Verzeichnis](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

In diesem Artikel werden Verbinden Konferenzanbieter beschrieben:

- [Vorteile](#benefits)
- [Lizenzierungsanforderungen und Abrechnung](#licensing-requirements-and-billing)
- [Weitere Informationen zu Microsoft-Audiokonferenzen](#additional-information-on-microsoft-audio-conferencing)

Informationen zum Konfigurieren von Operatoren Verbinden Konferenzen finden Sie unter Konfigurieren der [Verbinden von Konferenzen.](operator-connect-conferencing-configure.md)

Wenn einige Benutzer Ihrer Organisation externe Anrufe an PSTN-Telefonnummern rufnummernieren müssen, benötigen Sie dennoch einen Anrufplan. Informationen zur Verwendung eines Externen Netzbetreibers für die externe PSTN-Anbindung finden Sie unter [Planen der Verbinden.](operator-connect-plan.md)

## <a name="benefits"></a>Vorteile

Die Verbinden Konferenzanbieter bieten die folgenden Vorteile:

- **Flexible Zuweisung von Telefonnummern zwischen Ihrem Netzbetreiber und Microsoft.** Verwenden Sie Telefonnummern von Microsoft und Ihrem Netzbetreiber (nur mit einem Microsoft Audio Conferencing Standard-Abonnement), oder verwenden Sie nur Telefonnummern von Ihrem Anbieter (nur mit einer Lizenz für die Verbinden konferenz).

- **Von Operatoren verwaltete Infrastruktur.**   Ihr Operator verwaltet die Session Border Controller (SBCs) und die Verbindung mit Microsoft, was Sie durch zusätzliche Hardwarekäufe und Verwaltung erspart.

- **Schnellere und einfachere Bereitstellung.**   Stellen Sie schnell eine Verbindung mit Ihrem Netzbetreiber herzustellen, und weisen Sie Ihrer Audiokonferenzbrücke vom Teams Admin Center aus Telefonnummern zu.

- **Verbesserte Unterstützung und Zuverlässigkeit.**   Operatoren bieten Vereinbarungen zum technischen Support und Vereinbarungen zum Servicelevel zur Verbesserung der Serviceunterstützung, und direktes Peering mit Unterstützung von Azure erstellt eine 1:1-Netzwerkverbindung zur Verbesserung der Zuverlässigkeit.

Die Verbinden- und Konferenzkonferenzen sind möglicherweise die richtige Lösung für Ihre Organisation, wenn:

- Sie möchten Ihre **Verträge mit Ihrem** derzeitigen Telefonnummernanbieter behalten.

- Sie möchten die **globale Abdeckung Ihrer** vorhandenen Microsoft Audio Conferencing Bridge erweitern.

- Sie möchten **Telefonnummern für Audiokonferenzen** von einem neuen Telefonnummernanbieter erhalten

- **Microsoft-Audiokonferenzen sind in Ihrem geografischen Standort nicht verfügbar**

- Sie möchten einen Netzbetreiber für Audiokonferenzdienste mit einem **Kosten-pro-Minuten-Modell** nutzen, z. B. gebührenfreie Nummern verwenden und ausgehende Anrufe von Teams-Besprechungen an Telefonnummern in Ländern/Ländern ab telefonieren, die nicht in Ihrem Abonnement enthalten sind.

## <a name="licensing-requirements-and-billing"></a>Lizenzierungsanforderungen und Abrechnung

Benutzern, die an den von ihnen organisierten Besprechungen Verbinden-Konferenznummern teilnehmen müssen, muss entweder ein Microsoft Audio Conferencing Standard-Abonnement oder eine Microsoft Operator Verbinden Conferencing-Lizenz zugewiesen sein.

### <a name="audio-conferencing-standard-subscription"></a>Standardabonnement für Audiokonferenzen

Ein Microsoft Audio Conferencing Standard-Abonnement kann als Add-On für eine Microsoft Teams-Lizenz erworben werden und ist auch in den Abonnements Microsoft 365 E5 und Office 365 E5 enthalten.

Das Abonnement Audio Conferencing Standard ermöglicht es Abonnenten, Telefonnummern von Microsoft zu verwenden und ihre Audiokonferenzbrücken mit Nummern von einem Anbieter zu erweitern. Abonnenten können auch entscheiden, welche ausgehenden Anrufe von Teams-Besprechungen über Microsoft und welche Anrufe über eine Netzbetreiber routen.

Weitere Informationen finden Sie unter [**Konfigurieren von Verbinden Konferenzen.**](operator-connect-conferencing-configure.md)

### <a name="operator-connect-conferencing-license"></a>Lizenz Verbinden Operator für Konferenzen

Eine Microsoft Operator Verbinden Conferencing-Lizenz kann als Add-On für eine Lizenz Microsoft Teams erworben werden.

Die Lizenz Verbinden Operator für Konferenzen ermöglicht Abonnenten die Verwendung von Telefonnummern von einem Anbieter, enthält jedoch keine Telefonnummern von Microsoft. Alle ausgehenden Anrufe Teams Besprechungen müssen über einen Netzbetreiber geroutet werden.

Weitere Informationen finden Sie unter [**Konfigurieren von Verbinden Konferenzen.**](operator-connect-conferencing-configure.md)

>[!Note]
>Für Besprechungsteilnehmer ist keine Standardabonnement-Lizenz für Audiokonferenzen oder eine Lizenz des Operators Verbinden Conferencing erforderlich, um an einer von einem Benutzer mit der Funktion "Operator Verbinden Conferencing" organisierten Besprechung teilnehmen zu können.

Mit der Verbinden-Konferenzen stellt Microsoft für Ihre Organisation die Abrechnung gemäß dem von Ihrer Organisation verwendeten Lizenztyp Audiokonferenz, Microsoft Audio Conferencing oder Operator Verbinden Conferencing (Microsoft Audiokonferenz) und der Verwendung aller von Microsoft bereitgestellten Telefonnummern in Rechnung.

Ihr Netzbetreiber stellt Ihrer Organisation die Verwendung von Verbinden Konferenznummern in Rechnung.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Weitere Informationen zu Microsoft-Audiokonferenzen

Microsoft Audio Conferencing ermöglicht Teilnehmern die Teilnahme an Microsoft Teams-Besprechungen, indem sie sich mit einer PSTN-Telefonnummer einwählen oder eine PSTN-Telefonnummer anrufen. Weitere Informationen zu den in Ihrer Organisation verfügbaren Microsoft-Audiokonferenzfunktionen finden Sie unter [Audiokonferenzen in Microsoft 365.](audio-conferencing-in-office-365.md)
