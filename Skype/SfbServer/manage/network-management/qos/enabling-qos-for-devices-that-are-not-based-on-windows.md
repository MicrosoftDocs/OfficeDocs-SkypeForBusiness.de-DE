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
ms.localizationpriority: medium
description: Erfahren Sie, wie Sie QoS für Geräte in Ihrer Organisation aktivieren, die ein anderes Betriebssystem als Windows verwenden.
ms.openlocfilehash: eda6f1c825d00c7e8b1804ad866603b3429273d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634259"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows


Wenn Sie Skype for Business Server installieren, wird QoS (Quality of Service) nicht für geräte in Ihrer Organisation aktiviert, die ein anderes Betriebssystem als Windows verwenden. Sie können dies überprüfen, indem Sie den folgenden Befehl in der Skype for Business ServerManagement Shell ausführen:

**Get-CsMediaConfiguration**

Wenn Sie keine Änderungen an den Medienkonfigurationseinstellungen vorgenommen haben, sollten Sie Informationen wie die folgende abrufen:

Identität : Global<br/>
EnableQoS: False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

Wenn die EnableQoS-Eigenschaft auf False festgelegt ist (wie in der vorherigen Ausgabe), bedeutet dies, dass Quality of Service für Computer und Geräte, die ein anderes Betriebssystem als Windows verwenden, nicht aktiviert ist.

Führen Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell aus, um Quality of Service auf globaler Ebene zu aktivieren:

**Set-CsMediaConfiguration -EnableQoS $True**

Der vorstehende Befehl aktiviert QoS auf globaler Ebene. Es ist jedoch wichtig zu beachten, dass Medienkonfigurationseinstellungen auch auf den Standortbereich angewendet werden können. Wenn Sie Quality of Service für einen Standort aktivieren müssen, müssen Sie beim Aufrufen von "Set-CsMediaConfiguration" die Identität der Konfigurationseinstellungen angeben. Mit diesem Befehl wird beispielsweise QoS für den Standort Redmond aktiviert:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> Müssen Sie QoS auf Standortebene aktivieren? Das kommt darauf an. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Angenommen, Sie haben QoS auf globaler Ebene aktiviert, aber auf Standortebene deaktiviert (für den Standort Redmond). In diesem Fall wäre Quality of Service für den Standort Redmond deaktiviert. Dies liegt daran, dass die Websiteeinstellungen Vorrang haben. Um QoS für den Standort Redmond zu aktivieren, müssen Sie dies mithilfe der Medienkonfigurationseinstellungen tun, die auf diesen Standort angewendet werden.


Wenn Sie QoS für alle Medienkonfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der LSkype for Business Server-Verwaltungsshell aus:

**Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True**

Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf "False" festlegen. Zum Beispiel:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

Auf diese Weise können Sie QoS in einigen Bereichen des Netzwerks implementieren (z. B. für den Standort Redmond), während QoS für andere Bereiche des Netzwerks deaktiviert bleibt.

QoS kann nur mit Windows PowerShell aktiviert und deaktiviert werden. Diese Optionen sind in der Skype for Business Server Systemsteuerung nicht verfügbar.

> [!NOTE]
> Skype for Business Clients für iOS Version 6.17 und höher unterstützen jetzt QoS.  Diese QoS-Funktion gilt nur für Skype for Business Clients und IP-Telefongeräte, die direkt bei einem internen Skype for Business oder Lync-Poolserver in verwalteten Netzwerken registriert sind. QoS gilt nicht für Datenverkehr, der über das Internet weitergeleitet wird.
