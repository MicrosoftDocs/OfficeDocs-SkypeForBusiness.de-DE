---
title: Aktivieren von QoS für Windows-fremde Geräte
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Hier erfahren Sie, wie Sie QoS für in Ihrer Organisation verwendete Geräte aktivieren, die ein anderes Betriebssystem als Windows verwenden.
ms.openlocfilehash: 74f964f6156c8b2f2d7a7359193b5dbffe95a011
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817414"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren


Wenn Sie Skype for Business Server installieren, wird Quality of Service (QoS) nicht für alle in Ihrer Organisation verwendeten Geräte aktiviert, die ein anderes Betriebssystem als Windows verwenden. Sie können dies überprüfen, indem Sie in der Skype for Business-Servermanagement-Shell den folgenden Befehl ausführen:

    Get-CsMediaConfiguration

Angenommen, Sie haben keine Änderungen an den Medien Konfigurationseinstellungen vorgenommen, sollten Sie Informationen ähnlich wie in diesem Fall zurück erhalten:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Wenn die EnableQoS-Eigenschaft auf "false" (wie in der vorhergehenden Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte, die ein anderes Betriebssystem als Windows verwenden, nicht aktiviert ist.

Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell aus, um Quality of Service auf globaler Ebene zu aktivieren:

    Set-CsMediaConfiguration -EnableQoS $True

Der obige Befehl aktiviert QoS im globalen Bereich; Beachten Sie jedoch, dass die Einstellungen für die Medienkonfiguration auch auf den Website Bereich angewendet werden können. Wenn Sie die Dienstqualität für eine Website aktivieren müssen, müssen Sie beim Aufrufen von "CsMediaConfiguration" die Identität der Konfigurationseinstellungen angeben. Mit diesem Befehl wird beispielsweise QoS für die Website "Redmond" aktiviert:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Müssen Sie QoS im Website Bereich aktivieren? Das hängt davon ab. Dem Website Bereich zugewiesene Einstellungen haben Vorrang vor den dem globalen Bereich zugewiesenen Einstellungen. Angenommen, Sie haben QoS im globalen Bereich aktiviert, aber für den Website Bereich deaktiviert (für die Website "Redmond"). In diesem Fall ist die Dienstqualität für die Website "Redmond" deaktiviert; Das liegt daran, dass die Websiteeinstellungen Vorrang haben. Um QoS für die Website "Redmond" zu aktivieren, müssen Sie die Medien Konfigurationseinstellungen verwenden, die auf diese Website angewendet wurden.


Wenn Sie QoS für alle Medien Konfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der LSkype for Business Server-Verwaltungsshell aus:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festlegen. Beispiel:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Dadurch haben Sie die Möglichkeit, QoS in einigen Teilen Ihres Netzwerks (beispielsweise auf der Website "Redmond") zu implementieren, während Sie die Dienstqualität für andere Teile Ihres Netzwerks deaktiviert lassen.

QoS kann nur mithilfe von Windows PowerShell aktiviert und deaktiviert werden. Diese Optionen stehen im Skype Control Panel für Unternehmen-Server nicht zur Verfügung.

> [!NOTE]
> Skype for Business-Clients für IOS, Version 6,17 und höher, unterstützen jetzt QoS.  Diese QoS-Funktion gilt nur für Skype for Business-Clients und IP-Telefongeräte, die direkt bei einem internen Skype for Business-oder lync-Pool-Server in verwalteten Netzwerken registriert sind. QoS gilt nicht für Datenverkehr, der über das Internet weitergeleitet wird.



