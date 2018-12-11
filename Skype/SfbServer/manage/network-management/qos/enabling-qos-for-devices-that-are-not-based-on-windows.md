---
title: Aktivieren von QoS für Geräte, die nicht auf Windows basieren
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Hier erfahren Sie, wie Sie QoS für Geräte in Ihrer Organisation verwendeten aktivieren, die ein Betriebssystem als Windows verwenden.
ms.openlocfilehash: 0dc870080b3cfcd5f73eaf6e45aee841b9c8b488
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222772"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Aktivieren von QoS in Skype für Business Server für Geräte, die nicht auf Windows basieren


Bei der Installation von Skype für Business Server wird Quality of Service (QoS) nicht für alle Geräte in Ihrer Organisation verwendeten aktiviert sein, die ein Betriebssystem als Windows verwenden. Sie können dies überprüfen, durch den folgenden Befehl aus, in der Skype für Business ServerManagement Shell ausführen:

    Get-CsMediaConfiguration

Vorausgesetzt, dass Sie keine Änderungen an den medienkonfigurationseinstellungen vorgenommen haben, sollten Sie ähnliche Informationen wie die folgende erhalten:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Wenn die EnableQoS-Eigenschaft auf False (wie in der vorherigen Ausgabe), das heißt festgelegt ist, Quality of Service nicht aktiviert ist für Computer und Geräte, die ein Betriebssystem als Windows verwenden.

Um Quality of Service auf globaler Ebene zu aktivieren, führen Sie den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell aus:

    Set-CsMediaConfiguration -EnableQoS $True

Mit dem vorstehende Befehl können QoS auf globaler Ebene. jedoch ist es wichtig zu beachten, dass medienkonfigurationseinstellungen auch, die auf Standortebene angewendet werden können. Wenn Sie Quality of Service für eine Website aktivieren möchten, müssen Sie die Identität der Konfigurationseinstellungen für die einbeziehen, beim Aufruf von Set-CsMediaConfiguration. Beispielsweise kann mit diesem Befehl QoS für den Standort Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> So aktivieren Sie QoS auf Standortebene muss? Das ist unterschiedlich. Einstellungen, die auf Standortebene zugewiesen haben Vorrang vor Einstellungen auf globaler Ebene zugewiesen. Angenommen Sie, Sie QoS auf globaler Ebene aktiviert, aber die auf Standortebene (für den Standort Redmond) deaktiviert haben. In diesem Fall würde Quality of Service für den Standort Redmond deaktiviert werden. Dies liegt daran die Einstellungen Vorrang haben. Zum Aktivieren von QoS für den Standort Redmond müssten Sie dazu mit der medienkonfigurationseinstellungen auf dieser Website angewendet.


Wenn Sie gleichzeitig QoS für alle medienkonfigurationseinstellungen (unabhängig vom Gültigkeitsbereich) aktivieren möchten, führen Sie folgenden Befehl in der LSkype für Business Server-Verwaltungsshell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Sie können QoS für Geräte deaktivieren, die ein Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festgelegt. Beispiel:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Dadurch werden die Möglichkeit zum Implementieren von QoS auf einige Teile des Netzwerks (beispielsweise auf den Standort Redmond) und dabei Quality of Service auf andere Teile des Netzwerks deaktiviert zu lassen.

QoS kann nur aktiviert, und mithilfe von Windows PowerShell deaktiviert. Diese Optionen sind nicht verfügbar in den Skype Business Server-Systemsteuerung.


