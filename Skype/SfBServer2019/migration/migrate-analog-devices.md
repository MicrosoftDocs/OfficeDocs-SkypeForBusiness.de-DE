---
title: Migrieren analoger Geräte
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways konfigurieren, um die Verwendung analoger Geräte in Ihrer Skype for Business Server Umgebung zu unterstützen. Nach der Migration zu Skype for Business Server 2019 müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie Skype for Business Server Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die den älteren analogen Geräten zugeordnet sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: d64552a53b5cb37187a25febe5ce6171d1c64ec9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599690"
---
# <a name="migrate-analog-devices"></a>Migrieren analoger Geräte

Skype for Business Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways konfigurieren, um die Verwendung analoger Geräte in Ihrer Skype for Business Server Umgebung zu unterstützen. Nach der Migration zu Skype for Business Server 2019 müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie Skype for Business Server Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die den älteren analogen Geräten zugeordnet sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.

### <a name="to-migrate-analog-devices"></a>So migrieren Sie analoge Geräte

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Microsoft Skype for Business Server 2019"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Geben Sie in die Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Stellen Sie sicher, dass alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden. Geben Sie in die Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Stellen Sie sicher, dass alle Kontaktobjekte nun dem pool Skype for Business Server 2019 zugeordnet sind.


