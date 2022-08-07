---
title: Maskieren von Telefonnummern in Microsoft Teams-Besprechungen
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informationen zum Maskieren von Telefonnummern in Microsoft Teams-Besprechungen
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270820"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Maskieren von Telefonnummern in Microsoft Teams-Besprechungen

Für zusätzlichen Datenschutz werden die Telefonnummern der Teilnehmer, die sich mit Audiokonferenzen in eine Teams-Besprechung einwählen, den internen Teilnehmern vollständig angezeigt. Die Nummern werden von den Teilnehmern außerhalb Ihrer Organisation maskiert. Diese Einstellung ist die Standardeinstellung für alle Organisationen. Die maskierte Zahl wird wie in der folgenden Abbildung dargestellt angezeigt:

![Ein Beispiel für eine maskierte Telefonnummer.](media/hiddenPhoneNum.png)

Für bestimmte Branchen-Anwendungsfälle können Administratoren auswählen, wie die Telefonnummern der Audiokonferenzteilnehmer in Besprechungen angezeigt werden, die in ihrem Mandanten organisiert sind. Die Administratoren können aus drei Optionen wählen:

- Telefonnummern werden nur von externen Teilnehmern maskiert. Die Teilnehmer, die zum Mandanten des Besprechungsorganisators gehören, sehen weiterhin die vollständige Telefonnummer.
- Telefonnummern werden von allen Teilnehmern der Besprechung mit Ausnahme des Organisators maskiert.
- Telefonnummern werden entlarvt, wodurch sie für alle Teilnehmer der Besprechung sichtbar sind.

Diese Einstellung wird auf alle Oberflächen in der Besprechung angewendet, auf denen Telefonnummern verfügbar gemacht werden.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Verwenden von Microsoft PowerShell zum Festlegen der Telefonnummernmaskierung

Um die Einstellung für die PSTN-Maskierung (Public Switched Telephone Network) zu ändern, legen Sie den **`MaskPstnNumbersType`** Parameter des Cmdlets [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) auf eine der verfügbaren Optionen fest.

Führen Sie den folgenden Befehl aus, um Telefonnummern nur von externen Teilnehmern zu maskieren:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Führen Sie den folgenden Befehl aus, um Telefonnummern aller Teilnehmer der Besprechung (mit Ausnahme des Organisators) zu maskieren:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Um die Maskierung von Telefonnummern zu deaktivieren, führen Sie den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
