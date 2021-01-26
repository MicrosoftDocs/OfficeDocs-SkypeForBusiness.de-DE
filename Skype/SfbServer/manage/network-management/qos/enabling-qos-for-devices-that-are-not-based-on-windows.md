---
title: Aktivieren von QoS für Windows-fremde Geräte
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Erfahren Sie, wie Sie QoS für Geräte aktivieren, die in Ihrer Organisation verwendet werden und ein anderes Betriebssystem als Windows verwenden.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814175"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren


Bei der Installation von Skype for Business Server wird QoS (Quality of Service) nicht für Geräte in Ihrer Organisation aktiviert, die ein anderes Betriebssystem als Windows verwenden. Sie können dies überprüfen, indem Sie den folgenden Befehl in der Skype for Business ServerManagement Shell ausführen:

    Get-CsMediaConfiguration

Unter der Voraussetzung, dass Sie keine Änderungen an den Medienkonfigurationseinstellungen vorgenommen haben, sollten Sie Informationen wie dies erhalten:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Wenn die Eigenschaft "EnableQoS" auf "False" (wie in der vorherigen Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte, die ein anderes Betriebssystem als Windows verwenden, nicht aktiviert ist.

Führen Sie zum Aktivieren der Dienstqualität auf globaler Ebene den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus:

    Set-CsMediaConfiguration -EnableQoS $True

Mit dem vorstehenden Befehl wird QoS auf globaler Ebene aktiviert. Es ist jedoch wichtig zu beachten, dass Medienkonfigurationseinstellungen auch auf Standortbereich angewendet werden können. Wenn Sie Quality of Service für einen Standort aktivieren müssen, müssen Sie beim Aufrufen von "Set-CsMediaConfiguration" den Identitätsdatensatz der Konfigurationseinstellungen verwenden. Mit diesem Befehl wird beispielsweise QoS für den Standort "Redmond" aktiviert:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Müssen Sie QoS auf Standortebene aktivieren? Das kommt darauf an. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Angenommen, QoS ist auf globaler Ebene aktiviert, aber auf Standortbereich (für den Standort Redmond) deaktiviert. In diesem Fall würde Quality of Service für den Standort "Redmond" deaktiviert. Dies liegt daran, dass die Websiteeinstellungen Vorrang haben. Um QoS für den Standort "Redmond" zu aktivieren, müssen Sie dazu die auf diesen Standort angewendeten Medienkonfigurationseinstellungen verwenden.


Wenn Sie QoS für alle Medienkonfigurationseinstellungen (unabhängig vom Gültigkeitsbereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der LSkype for Business Server-Verwaltungsshell aus:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der Eigenschaft "EnableQoS" auf "False" festlegen. Beispiel:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Auf diese Weise können Sie QoS in einigen Bereichen des Netzwerks implementieren (z. B. für den Standort Redmond), während QoS für andere Bereiche des Netzwerks deaktiviert bleibt.

QoS kann nur mithilfe von Windows PowerShell. Diese Optionen sind in der Skype for Business Server-Systemsteuerung nicht verfügbar.

> [!NOTE]
> Skype for Business-Clients für iOS, Version 6.17 und höher, unterstützen jetzt QoS.  Diese QoS-Funktion gilt nur für Skype for Business-Clients und IP-Telefongeräte, die direkt für einen internen Skype for Business- oder Lync-Poolserver in verwalteten Netzwerken registriert sind. QoS gilt nicht für Datenverkehr, der über das Internet geroutet wird.



