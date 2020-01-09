---
title: Migrieren analoger Geräte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server bietet Unterstützung für analoge Geräte. Die unterstützten analogen Geräte sind analoge Audio-Telefone und analoge Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server-Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie die Skype for Business Server-Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die mit den Legacy-Analoggeräten verknüpft sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: 7ca36c92270685709c479a1d164f60d0960c526c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990090"
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


