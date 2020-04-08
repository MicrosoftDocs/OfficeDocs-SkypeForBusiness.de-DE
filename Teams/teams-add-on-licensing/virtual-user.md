---
title: Microsoft 365 Phone System – Lizenzen für virtuelle Benutzer
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
description: Informationen zu kostenlosen virtuellen Benutzerlizenzen.
ms.openlocfilehash: f2ecaddc6fd1dcc4bbb179fde3f495a0eea29353
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190817"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System – virtuelle Benutzerlizenz 

Organisationen mit lizenzierten Telefonsystem Benutzern können einem kostenlosen Microsoft 365-Telefonsystem – einer virtuellen Benutzerlizenz oder einer gebührenpflichtigen Telefonsystem-Benutzerlizenz für Ressourcenkonten zuweisen. Ein Anrufplan ist nicht erforderlich. Für alle automatischen Telefonzentralen oder Anrufwarteschlangen ist ein zugeordnetes Ressourcenkonto erforderlich. Ressourcenkonten, für die eine Telefonnummer erforderlich ist, benötigen ein kostenloses Microsoft 365-Telefonsystem – eine virtuelle Benutzerlizenz oder eine gebührenpflichtige Telefonsystem-Benutzerlizenz, bevor eine Telefonnummer auf das Ressourcenkonto angewendet werden kann.

> [!TIP]
> Für Ressourcenkonten, die mit geschachtelten automatischen Telefonzentralen oder Anrufwarteschlangen verwendet werden, denen keine Telefonnummer zugewiesen ist, ist keine Lizenz erforderlich. In der folgenden Abbildung finden Sie eine Referenz: 

![Lizenzen für virtuelle Benutzer](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Zuweisung virtueller Benutzerlizenzen

In Ihrer Organisation wird Microsoft 365 Phone System – virtuelle Benutzerlizenzen abhängig von der Gesamtgröße zugeteilt. Jede Organisation, die über mindestens eine Lizenz mit Telefonsystem oder über das Telefonsystem verfügt, verfügt über 25 virtuelle Benutzerlizenzen, die kostenlos zur Verfügung stehen. Wenn Sie in Ihrer Organisation 10 Telefonsystem-Benutzerlizenzen hinzufügen, wird eine weitere Microsoft 365-Telefonsystem – virtuelle Benutzerlizenz verfügbar.

> [!NOTE]
> Telefon System ist eine Add-on-Lizenz, die mit Office 365 E1 und E3 zur Verfügung steht. Das Telefon System ist auch Teil der Office 365 E5-und Microsoft 365 Business Voice-Lizenzen.

Wenn Ihre Organisation das verfügbare ﻿kostenlose Microsoft 365-Telefonsystem – virtuelle Benutzerlizenzen beim Erstellen von automatischen Telefonzentralen oder Anruf Warteschlangen Knoten – verwendet, können Sie weiterhin die gebührenpflichtigen Telefonsystem Lizenzen mit einem Ressourcenkonto verwenden. Die meisten Organisationen verfügen über genügend virtuelle Benutzerlizenzen basierend auf dem Skalierungs Plan. 

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuteilung

Contoso, Inc. hat 600-Lizenzen erworben, die das Telefon System enthielten (eines für jeden Mitarbeiter). Contoso wird ein anfängliches 25 plus 60 Microsoft 365-Telefon System zugeteilt – virtuelle Benutzerlizenzen, insgesamt 85. Ihre Organisation verfügt über 90-Anrufwarteschlangen und automatische Telefonzentralen mit Telefonnummern. Sie müssen alle Microsoft 365-Telefonsystem-Lizenzen für virtuelle Benutzer zuweisen und fünf reguläre Telefonsystem Lizenzen erwerben. 

Contoso sollte eine Neugestaltung der automatischen Telefonzentrale und des Anruf Warteschlangensystems in Frage stellen. Wenn Sie weniger Telefonnummern und verschachtelte Knoten verwenden, die keine Telefonnummern benötigen, vereinfachen Sie die Implementierung und senken die Kosten. 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>So kaufen Sie das Telefon System von Microsoft 365 – virtuelle Benutzerlizenzen 

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Wechseln Sie zu " **Billing** > **Purchase Services** > "**-Add-ons** .
3. Scrollen Sie bis zum Ende, um die Lizenz für **Virtual User für Microsoft 365 Phone System** zu finden. Wählen Sie **Jetzt kaufen** aus.

> [!NOTE]
> Beachten Sie, dass Sie die Lizenz weiterhin **kaufen** müssen, auch wenn Sie Kosten von NULL hat. 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung eines Microsoft 365-Telefonsystems – Virtual User License

Wenn Sie sich entschließen, die Lizenz für Ihr Ressourcenkonto von einer Telefonsystem Lizenz auf ein Microsoft 365-Telefonsystem umzustellen – virtuelle Benutzerlizenz: 

1. Besorgen Sie sich das neue Microsoft 365 Phone System – Virtual User License. 
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer in ein anderes Abonnement zu verschieben](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Entfernen Sie immer eine vollständige Telefonsystem Lizenz, und weisen Sie die Lizenz für den Microsoft 365 Phone System – Virtual User in derselben Lizenz Aktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfehlen wir, ein neues Ressourcenkonto für die Microsoft 365 Phone System – Virtual User License zu erstellen und das fehlerhafte Ressourcenkonto zu entfernen. 

## <a name="related-information"></a>Verwandte Informationen

[Dienst Update für automatische Telefonzentrale und Anrufwarteschlangen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)
