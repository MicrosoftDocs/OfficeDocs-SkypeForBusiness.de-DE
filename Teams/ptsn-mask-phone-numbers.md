---
title: Maskieren von Telefonnummern in Microsoft Teams-Besprechungen
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen zum Maskieren von Telefonnummern in Microsoft Teams-Besprechungen
ms.openlocfilehash: 5a59ef07873660e79d6c8bc69b7e92095a2fac1a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726781"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Maskieren von Telefonnummern in Microsoft Teams-Besprechungen

Für zusätzlichen Datenschutz werden die Telefonnummern der Teilnehmer, die sich über Audiokonferenzen in eine Teams-Besprechung einwählen, vollständig für die internen Teilnehmer angezeigt. Die Zahlen werden von den Teilnehmern außerhalb Ihrer Organisation maskiert. Diese Einstellung ist die Standardeinstellung für alle Organisationen. Die maskierte Zahl wird wie in der folgenden Abbildung dargestellt angezeigt:

![Beispiel für eine maskierte Telefonnummer](media/hiddenPhoneNum.png)

Bei bestimmten Branchennutzungsfällen können Administratoren auswählen, wie die Telefonnummern der Audiokonferenzteilnehmer in Besprechungen angezeigt werden, die in ihrem Mandanten organisiert sind. Die Administratoren können aus drei Optionen auswählen:

- Telefonnummern werden nur von externen Teilnehmern maskiert. Die Teilnehmer, die zum Mandanten des Besprechungsorganisators gehören, sehen weiterhin die vollständige Telefonnummer.
- Telefonnummern werden von allen Besprechungsorganisatoren maskiert.
- Telefonnummern werden entlarvt, wodurch sie für jeden in der Besprechung sichtbar sind.

Diese Einstellung wird auf alle Oberflächen in der Besprechung angewendet, auf denen Telefonnummern verfügbar gemacht werden.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Verwenden von Microsoft PowerShell zum Festlegen der Telefonnummernformatierung

Wenn Sie die Maskierungseinstellung für das öffentliche Telefonnetz (PstN) ändern möchten, legen Sie den Parameter des **`MaskPstnNumbersType`** [Cmdlets Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) auf eine der verfügbaren Optionen fest.

Führen Sie den folgenden Befehl aus, um Telefonnummern nur von externen Teilnehmern zu maskieren:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Führen Sie zum Maskieren von Telefonnummern aller Teilnehmer an der Besprechung (mit Ausnahme des Organisators) den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Führen Sie zum Deaktivieren der Telefonnummernformatierung den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
