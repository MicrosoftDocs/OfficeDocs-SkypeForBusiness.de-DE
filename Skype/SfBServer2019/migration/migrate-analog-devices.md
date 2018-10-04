---
title: Migrieren von analogen Geräten
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server bietet Unterstützung für analoge Geräte. Sind vor allem die unterstützten analoge Geräte analoge audio Telefone und analoge Fax-. Sie können den qualifizierten Gateways zur Unterstützung der Verwendung von analogen Geräten in Ihrer Skype für Business Server-Umgebung konfigurieren. Nach der Migration zu Skype für Business Server 2019 müssen Sie auch die Kontaktobjekte analogen Geräten zugeordnet migrieren. Verwenden Sie Skype für Business Server-Verwaltungsshell, um alle mit der Vorversionen analogen Geräten verknüpften Objekte Kontakte abrufen, und anschließend verschieben Sie diese Objekte in der Skype für Business Server 2019 Pool.
ms.openlocfilehash: ea100f4e26cc38d5eb30f881de61bf415110ca36
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374850"
---
# <a name="migrate-analog-devices"></a>Migrieren von analogen Geräten

Skype für Business Server bietet Unterstützung für analoge Geräte. Sind vor allem die unterstützten analoge Geräte analoge audio Telefone und analoge Fax-. Sie können den qualifizierten Gateways zur Unterstützung der Verwendung von analogen Geräten in Ihrer Skype für Business Server-Umgebung konfigurieren. Nach der Migration zu Skype für Business Server 2019 müssen Sie auch die Kontaktobjekte analogen Geräten zugeordnet migrieren. Verwenden Sie Skype für Business Server-Verwaltungsshell, um alle mit der Vorversionen analogen Geräten verknüpften Objekte Kontakte abrufen, und anschließend verschieben Sie diese Objekte in der Skype für Business Server 2019 Pool.

### <a name="to-migrate-analog-devices"></a>Migrieren von analogen Geräten

1. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

2. Geben Sie in der Befehlszeile Folgendes ein:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Stellen Sie sicher, dass alle Kontaktobjekte in der Skype für Business Server 2019 Pool verschoben wurden. Geben Sie in der Befehlszeile Folgendes ein:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Stellen Sie sicher, dass die Kontaktobjekte jetzt sind die Skype für Business Server 2019 Pool zugeordnet.


