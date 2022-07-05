---
title: Microsoft Teams Telefon Ressourcenkontolizenzen
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie ressourcenkonten in Ihrer Organisation kostenlose Microsoft Teams Phone-Ressourcenkontolizenzen oder eine kostenpflichtige Teams Telefon Standard-Benutzerlizenzen zuweisen.
ms.openlocfilehash: 07b47b2ec5b24b1edbfb599dc5a61e96169a02a2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615401"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams Telefon Ressourcenkontolizenzen

Organisationen mit Teams Telefon Standard- oder Teams-Telefon mit Anrufplan-lizenzierten Benutzern können Ressourcenkonten entweder eine kostenlose *Microsoft Teams Telefon-Ressourcenkontolizenz* oder eine kostenpflichtige *Teams Telefon Standard-Benutzerlizenz* zuweisen. Ein Microsoft-Anrufplan ist nicht immer erforderlich (unter ["Plan for Teams Auto attendant and call queues](../plan-auto-attendant-call-queue.md#prerequisites) for prerequisites when transferring calls to an external phone number").

Alle automatischen Telefonzentralen und Anrufwarteschleifen erfordern ein zugeordnetes Ressourcenkonto. Ressourcenkonten, für die eine Telefonnummer erforderlich ist, benötigen entweder eine kostenlose *Microsoft Teams Telefon Ressourcenkontolizenz* oder eine kostenpflichtige *Teams Telefon Standard* Benutzerlizenz, bevor eine Telefonnummer auf das Ressourcenkonto angewendet werden kann.

> [!TIP]
> Für Ressourcenkonten, die mit geschachtelten automatischen Telefonzentralen oder Anrufwarteschleifen verwendet werden, denen keine Telefonnummer zugewiesen ist, ist keine Lizenz erforderlich. Weitere Informationen finden Sie im folgenden Diagramm.

## <a name="resource-account-license-allocation"></a>Ressourcenkonto-Lizenzzuweisung

Ihrer Organisation werden je nach Gesamtgröße *Microsoft Teams Telefon Ressourcenkontolizenzen* zugewiesen. Jede Organisation, die über mindestens eine Lizenz mit Microsoft Teams-Telefonsystemfeatures verfügt, einschließlich Teams Telefon Standard- und Teams-Telefon mit Anrufplanlizenzen, verfügt über 25 Ressourcenkontolizenzen ohne Kosten. Wenn Sie 10 Teams Telefon Standard- oder Teams-Telefon mit Anrufplan-Benutzerlizenzen in Ihrer Organisation hinzufügen, wird eine weitere *Microsoft Teams Telefon Ressourcenkontolizenz* verfügbar.

> [!NOTE]
> Teams Telefon Standard und Teams Phone with Calling Plan sind Add-On-Lizenzen, die für alle Microsoft 365-Abonnenten verfügbar sind. Teams Telefon Standard Lizenzen sind ebenfalls Bestandteil Microsoft 365 E5 Plänen.

Wenn Ihre Organisation die kostenlosen *Microsoft Teams Telefon Ressourcenkontolizenzen* zum Erstellen automatischer Telefonzentralen- oder Anrufwarteschleifenknoten verwendet, können Sie die kostenpflichtigen *Teams Telefon Standard-Lizenzen* weiterhin mit einem Ressourcenkonto verwenden. Die meisten Organisationen verfügen über genügend Ressourcenkontolizenzen basierend auf dem Skalierungsplan.

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuweisung

Contoso, Inc. hat 600 Lizenzen erworben, die das Telefonsystem enthalten (eine für jeden Mitarbeiter). Contoso werden zunächst 25 plus 60 *Microsoft Teams Telefon Ressourcenkontolizenzen* zugewiesen, insgesamt 85. Ihre Organisation verfügt über 90 Anrufwarteschleifen und automatische Telefonzentralen mit Telefonnummern. Sie müssen alle *Microsoft Teams Telefon Ressourcenkontolizenzen* zuweisen und fünf reguläre *Teams Telefon Standard-Lizenzen* erhalten.

Contoso sollte eine Neugestaltung der automatischen Telefonzentrale und des Anrufwarteschleifensystems in Betracht ziehen. Wenn sie weniger Telefonnummern und mehr geschachtelte Knoten verwenden, die keine Telefonnummer benötigen, vereinfachen sie die Implementierung und senken die Kosten.

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>So kaufen Sie Microsoft Teams Telefon Resource Account-Lizenzen

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Wechseln **Sie zu** > **Add-Ons für Abrechnungskaufdienste** > .
3. Scrollen Sie, um die **Lizenz für das Microsoft Teams Telefon Ressourcenkonto** zu finden. Wählen Sie **Jetzt kaufen** aus.

   > [!NOTE]
   > Denken Sie daran, dass Sie die Lizenz weiterhin **kaufen** müssen, obwohl sie kosten null.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung einer Microsoft Teams Telefon Resource Account-Lizenz

Wenn Sie sich entscheiden, die Lizenz für Ihr Ressourcenkonto von einer *Teams Telefon Standard-Lizenz* auf eine *Microsoft Teams Telefon Resource Account-Lizenz* umzustellen:

1. Rufen Sie die neue *Microsoft Teams Telefon Resource Account-Lizenz ab*.
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer in ein anderes Abonnement zu verschieben](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Entfernen Sie immer eine vollständige *Teams Telefon Standard* Lizenz, und weisen Sie die *Microsoft Teams Telefon Ressourcenkontolizenz* in derselben Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall wird empfohlen, ein neues Ressourcenkonto für die *Lizenz Microsoft Teams Telefon Ressourcenkonto* zu erstellen und das fehlerhafte Ressourcenkonto zu entfernen.

## <a name="related-information"></a>Verwandte Informationen

[Dienstaktualisierung für automatische Telefonzentrale und Anrufwarteschleifen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)
