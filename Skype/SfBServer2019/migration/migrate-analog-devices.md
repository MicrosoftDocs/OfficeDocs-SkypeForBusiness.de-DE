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
localization_priority: Normal
description: Skype for Business Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie Skype for Business Server Verwaltungsshell, um zuerst alle Contact-Objekte abzurufen, die den älteren analogen Geräten zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752827"
---
# <a name="migrate-analog-devices"></a>Migrieren analoger Geräte

Skype for Business Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie Skype for Business Server Verwaltungsshell, um zuerst alle Contact-Objekte abzurufen, die den älteren analogen Geräten zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.

### <a name="to-migrate-analog-devices"></a>So migrieren Sie analoge Geräte

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie in die Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Stellen Sie sicher, dass alle Kontaktobjekte in den Pool Skype for Business Server 2019 verschoben wurden. Geben Sie in die Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Stellen Sie sicher, dass alle Contact-Objekte nun dem Pool Skype for Business Server 2019 zugeordnet sind.


