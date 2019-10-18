---
title: 'Telefon System – virtuelle Benutzerlizenzen '
ms.author: jambirk
author: jambirk
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
description: Informationen zu kostenlosen virtuellen Benutzerlizenzen.
ms.openlocfilehash: ebf98f852610dd5acfea2bcd65daca7b7541b5aa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571169"
---
# <a name="phone-systemvirtual-user-license"></a>Telefon System – virtuelle Benutzerlizenz 

Ab dem 2. Juli 2019 kann eine Organisation mit lizenzierten Benutzern des Telefonsystems nun eine ﻿kostenlose Telefonanlage – eine virtuelle Benutzerlizenz oder eine gebührenpflichtige Telefonsystem-Benutzerlizenz für Ressourcenkonten erwerben und zuweisen. Ein Anrufplan ist nicht mehr erforderlich. Für alle automatischen Telefonzentralen oder Anrufwarteschlangen ist ein zugeordnetes Ressourcenkonto erforderlich. Ressourcenkonten, für die eine Telefonnummer erforderlich ist, benötigen ein kostenloses Telefonsystem – eine virtuelle Benutzerlizenz oder eine kostenpflichtige Telefonsystem-Benutzerlizenz, bevor eine Telefonnummer auf das Ressourcenkonto angewendet werden kann.

> [!TIP]
> Für Ressourcenkonten, die mit geschachtelten automatischen Telefonzentralen oder Anrufwarteschlangen verwendet werden, denen keine Telefonnummer zugewiesen ist, ist keine Lizenz erforderlich. In der folgenden Abbildung finden Sie eine Referenz: 

![Lizenzen für virtuelle Benutzer](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Zuweisung virtueller Benutzerlizenzen

Ihr Unternehmen ist abhängig von der Gesamtgröße Telefon System – virtuelle Benutzerlizenzen zugeteilt. Jede Organisation, die über mindestens eine Lizenz mit Telefonsystem oder über das Telefonsystem verfügt, verfügt über 25 virtuelle Benutzerlizenzen, die kostenlos zur Verfügung stehen. Wenn Sie in Ihrer Organisation 10 Telefonsystem-Benutzerlizenzen hinzufügen, wird eine weitere Telefonsystem – virtuelle Benutzerlizenz verfügbar.

> [!NOTE]
> Telefon System ist eine Add-on-Lizenz, die mit Office 365 E1 und E3 zur Verfügung steht. Das Telefon System ist auch als Teil der Office 365 E5-Lizenzen enthalten.

Wenn Ihre Organisation das verfügbare ﻿kostenlose Telefonsystem – virtuelle Benutzerlizenzen beim Erstellen von automatischen Telefonzentralen oder Anruf Warteschlangen Knoten – verwendet, können Sie weiterhin die gebührenpflichtigen Telefonsystem Lizenzen mit einem Ressourcenkonto verwenden. Die meisten Organisationen verfügen über genügend virtuelle Benutzerlizenzen basierend auf dem Skalierungs Plan. 

### <a name="license-allocation-example"></a>Beispiel für die Lizenzzuteilung

Contoso, Inc. hat 600-Lizenzen erworben, die das Telefon System enthielten (eines für jeden Mitarbeiter). Contoso wird ein anfängliches 25 plus 60-Telefon System zugeteilt – virtuelle Benutzerlizenzen, 85 insgesamt. Ihre Organisation verfügt über 90-Anrufwarteschlangen und automatische Telefonzentralen mit Telefonnummern. Sie müssen alle Telefonsystem-Lizenzen für virtuelle Benutzer zuweisen und fünf reguläre Telefonsystem Lizenzen erwerben. 

Contoso sollte eine Neugestaltung der automatischen Telefonzentrale und des Anruf Warteschlangensystems in Frage stellen. Wenn Sie weniger Telefonnummern und verschachtelte Knoten verwenden, die keine Telefonnummern benötigen, vereinfachen Sie die Implementierung und senken die Kosten. 

## <a name="how-to-acquire-phone-systemvirtual-user-licenses"></a>Telefon System erwerben – Lizenzen für virtuelle Benutzer 

> [!NOTE] 
> Wenn Sie diese Anweisungen befolgen, deaktivieren Sie den Vorschaumodus, um eine Telefon System-Virtual User-Lizenz zu erwerben.

1. Anmelden beim Microsoft 365 Admin Center.
2. Wechseln Sie zu den**Add-on-Abonnements** für **Billing** > **Purchase Services** > .
3. Scrollen Sie bis zum Ende, um die Lizenz **"Telefon System – virtueller Benutzer"** zu finden. Wählen Sie **Jetzt kaufen** aus.

> [!WARNING]
> Beachten Sie, dass Sie die Lizenz weiterhin **kaufen** müssen, auch wenn Sie Kosten von NULL hat. 

## <a name="change-an-existing-resource-account-to-use-a-phone-systemvirtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung eines Telefonsystems – virtuelle Benutzerlizenz

Wenn Sie sich entschließen, die Lizenz für Ihr Ressourcenkonto von einer Telefonsystem Lizenz auf eine Telefonanlage umzustellen – virtuelle Benutzerlizenz: 

1. Holen Sie sich das neue Telefon System – Virtual User License. 
2. Führen Sie die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer in ein anderes Abonnement zu verschieben](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Entfernen Sie immer eine vollständige Telefonsystem Lizenz, und weisen Sie die Lizenz für das Telefonsystem – virtuelle Benutzer in derselben Lizenz Aktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. Wenn dies der Fall ist, empfehlen wir, ein neues Ressourcenkonto für die Telefon System-Virtual User-Lizenz zu erstellen und das fehlerhafte Ressourcenkonto zu entfernen. 

## <a name="related-information"></a>Verwandte Informationen

[Dienst Update für automatische Telefonzentrale und Anrufwarteschlangen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Verwalten von Ressourcenkonten in Microsoft Teams](../manage-resource-accounts.md)
