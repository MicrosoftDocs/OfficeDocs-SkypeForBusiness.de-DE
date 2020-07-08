---
title: Kommunikations Kompatibilität für Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Sie erfahren mehr über die Compliance der Kommunikation, die Teil der Insider Risiko-Lösung sind, und zwar aus der Perspektive von Microsoft Teams (Dies ist Teil der M365 Communication Compliance-Funktion).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077693"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Kommunikations Kompatibilität für Microsoft Teams

Die Compliance für die Kommunikation ist Teil der neuen Insider Risiko Lösung von Microsoft 365, die Ihnen hilft, Kommunikationsrisiken zu minimieren, indem Sie Ihnen dabei hilft, in Ihrer Organisation unangemessene Nachrichten zu erkennen, zu erfassen und zu Behebungen. Es hilft bei der Ermittlung anstößiger Sprache und Anti-Mobbing in Team Kanälen oder 1:1 und Gruppen-Chats. Sie können auch Richtlinien einrichten, um festzustellen, ob vertrauliche Informationen als Teil von Team Kanälen oder 1:1-und Gruppen-Chats freigegeben werden. Weitere Informationen zu verschiedenen Richtlinientypen und zur Einrichtung finden Sie im [Artikel M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-teams"></a>Verwenden der Kommunikations Konformität in Teams

### <a name="identify-inappropriate-messages"></a>Identifizieren unangemessener Nachrichten

Wenn Sie alle Nachrichten identifizieren möchten, die in Microsoft Teams (1:1, Gruppen-Chats oder Kanal Unterhaltungen) gesendet werden, anstößige Sprache oder Schikanen enthalten, können Sie Richtlinien aktivieren, um dies zu erkennen, und der Bearbeiter kann die Nachrichten prüfen und die erforderlichen Schritte wie das Senden von Schulungsmaterial oder die Eskalation an die richtigen Behörden durchführen.

### <a name="identify-sensitive-or-regulatory-information"></a>Identifizieren vertraulicher oder behördlicher Informationen

Wenn Sie Nachrichten überprüfen möchten, die in Microsoft Teams (1:1, Gruppen-Chats oder Kanal Unterhaltungen) für vertrauliche Informationen oder behördliche Typen gesendet wurden, können Sie Richtlinien auswählen, die vordefinierte sensible oder regulatorische Typen unterstützen.

> [!NOTE]
> Private Kanäle werden von der Kommunikations Konformität nicht unterstützt.

### <a name="custom-policy"></a>Benutzerdefinierte Richtlinie

Verwenden Sie diese Vorlage, um bestimmte Kommunikationskanäle, individuelle Erkennungs Bedingungen und die Anzahl der zu überwachenden und zu überprüfenden Inhalte in Ihrer Organisation zu konfigurieren.

### <a name="custom-trainable-classifier"></a>Benutzerdefinierte Klassifizierung

Verwenden Sie Lernbare Klassifizierungen, wenn eine der Out-of-the-Box-Klassifizierungen Ihre Anforderungen nicht erfüllt. Eine Microsoft 365-Klassifizierung ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie Ihnen Beispiele für deren Betrachtung geben. Schulung die Klassifizierung beinhaltet zunächst, dass Sie Beispiele für Personen enthält, die von Menschen ausgewählt werden und der Kategorie positiv entsprechen. Nachdem Sie diese Beispiele verarbeitet haben, testen Sie die Vorhersagen, indem Sie Ihr eine Mischung aus positiven und negativen Samples geben. Weitere Informationen zu diesem Thema finden Sie im [Artikel M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) .

> [!NOTE]
> Die Kommunikations Kompatibilität unterstützt jetzt Exchange-hybridbereitstellungen.

Communication Compliance unterstützt den Konversations Verlauf für alle Nachrichten, die den Richtlinien entsprechen. Dies bietet Kontext für den untersuchenden Administrator.

:::image type="content" source="media/communication-compliance-1.png" alt-text="Ein Bildschirm für die Kommunikations Kompatibilität in Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>Wo Kommunikationsrichtlinien in Teams angewendet werden können

Kommunikations Konformitätsrichtlinien können für Nachrichten eingerichtet werden, die in Teams auf den folgenden Ebenen gesendet werden:

- Benutzerebene: ein Administrator kann Richtlinien auf einer einzelnen Benutzerebene einrichten oder auf alle Benutzer im Mandanten anwenden. Dies gilt nur für Nachrichten, die ein Benutzer in 1:1 oder Gruppen-Chats gesendet hat.
- Team Ebene: ein Administrator kann auch Richtlinien für ein Team einrichten. Dies umfasst alle Nachrichten, die in dem Kanal in diesem Team gesendet werden (private Kanal Nachrichten werden nicht unterstützt).
