---
title: Migrieren analoger Geräte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server bietet Unterstützung für analoge Geräte. Die unterstützten analogen Geräte sind analoge Audio-Telefone und analoge Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server-Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie die Skype for Business Server-Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die mit den Legacy-Analoggeräten verknüpft sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813593"
---
# <a name="migrate-analog-devices"></a>Migrieren analoger Geräte

Skype for Business Server bietet Unterstützung für analoge Geräte. Die unterstützten analogen Geräte sind analoge Audio-Telefone und analoge Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server-Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie die Skype for Business Server-Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die mit den Legacy-Analoggeräten verknüpft sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.

### <a name="to-migrate-analog-devices"></a>So migrieren Sie analoge Geräte

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

2. Geben Sie in der Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Überprüfen Sie, ob alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden. Geben Sie in der Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Überprüfen Sie, ob alle Kontaktobjekte jetzt dem Skype for Business Server 2019-Pool zugeordnet sind.


