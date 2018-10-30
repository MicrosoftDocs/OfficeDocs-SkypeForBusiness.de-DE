---
title: Aktivieren von QoS für Windows-fremde Geräte
TOCTitle: Aktivieren von QoS für Windows-fremde Geräte
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204750(v=OCS.15)
ms:contentKeyID: 49293478
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von QoS für Windows-fremde Geräte

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Bei der Installation von Microsoft Lync Server 2013 wird die Dienstqualität (Quality of Service, QoS) nur für Geräte in der Organisation installiert, auf denen das Betriebssystem Windows ausgeführt wird wird. Sie können dies überprüfen, indem Sie in der Verwaltungsshell für Lync Server 2013 den folgenden Befehl ausführen:

    Get-CsMediaConfiguration

Sofern Sie noch keine Änderungen an den Medienkonfigurationseinstellungen vorgenommen haben, sollten ähnliche Informationen wie die folgenden zurückgegeben werden:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Wenn die Eigenschaft **EnableQoS** auf **False** gesetzt ist (siehe oben), bedeutet dies, dass QoS nicht für Computer und Geräte aktiviert wird, für die ein anderes Betriebssystem als Windows verwendet wird. QoS wird für Lync Phone Edition-Geräte standardmäßig aktiviert. Sie können QoS jedoch für Lync Phone Edition deaktivieren.

Führen Sie in der Lync Server-Verwaltungsshell den folgenden Befehl aus, um QoS auf globaler Ebene zu aktivieren:

    Set-CsMediaConfiguration -EnableQoS $True

Mit dem obigen Befehl wird QoS auf globaler Ebene aktiviert. Es ist jedoch wichtig, dass die Medienkonfigurationseinstellungen auch auf Standortebene angewendet werden können. Wenn Sie QoS für einen Standort aktivieren möchten, müssen Sie beim Aufruf von **Set-CsMediaConfiguration** die Identität der Konfigurationseinstellungen angeben. Mit dem folgenden Befehl wird QoS beispielsweise für den Standort Redmond aktiviert:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True


> [!NOTE]
> Müssen Sie QoS auf Standortebene aktivieren? Das kommt darauf an. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Angenommen, Sie haben QoS auf globaler Ebene aktiviert, aber auf Standortebene (für den Standort Redmond) deaktiviert. In diesem Fall wird QoS für den Standort Redmond deaktiviert, da die Standorteinstellungen Vorrang haben. Um QoS für den Standort Redmond zu aktivieren, müssen Sie entsprechende Medienkonfigurationseinstellungen auf den Standort anwenden.



Wenn Sie QoS für alle Medienkonfigurationseinstellungen (unabhängig vom Gültigkeitsbereich) aktivieren möchten, führen Sie den folgenden Befehl in der Lync Server-Verwaltungsshell aus:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Sie können QoS für Geräte deaktivieren, auf denen ein anderes Betriebssystem als Windows ausgeführt wird, indem Sie die Eigenschaft **EnableQoS** auf **False** setzen. Beispiel:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Auf diese Weise können Sie QoS in einigen Bereichen des Netzwerks implementieren (z. B. für den Standort Redmond), während QoS für andere Bereiche des Netzwerks deaktiviert bleibt.

QoS kann nur über die Lync Server-Verwaltungsshell aktiviert und deaktiviert werden. Diese Optionen sind nicht in der Lync Server-Systemsteuerung verfügbar.

