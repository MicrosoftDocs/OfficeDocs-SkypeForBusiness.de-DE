---
title: 'Lync Server 2013: Konfigurieren der Medienverschlüsselung für öffentliche Anbieter'
TOCTitle: Konfigurieren der Medienverschlüsselung für öffentliche Anbieter
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205149(v=OCS.15)
ms:contentKeyID: 49295034
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-12-12_

Ausführliche Informationen zu den Lizenzierungsanforderungen und zum Abschließen des Bereitstellungsprozesses finden Sie in der "Anleitung zur Bereitstellung von Verbindungen mit öffentlichen Instant Messaging-Diensten für Microsoft Lync Server, Office Communications Server und Live Communications Server" unter [http://go.microsoft.com/fwlink/p/?linkId=155970](http://go.microsoft.com/fwlink/p/?linkid=155970)

Wenn Sie einen A/V-Verbund (Audio/Video) mit Windows Live Messenger implementieren, müssen Sie zwei Parameter ändern: die Lync Server-Verschlüsselungsstufe und die Richtlinie "EnablePublicCloudAccess". Standardmäßig ist die Verschlüsselungsstufe auf "Erforderlich" festgelegt. Sie müssen diese Einstellung in "Unterstützt" ändern. Die Richtlinie "EnablePublicCloudAccess" ist auf "False" festgelegt, sie muss jedoch auf **True** festgelegt werden. Sie können diese Änderung in der Lync Server-Verwaltungsshell durchführen.


> [!IMPORTANT]
> Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard-Clientzugriffslizenz (CAL). Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht es Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.



## Konfigurieren des Verbunds für Windows Live

1.  Starten Sie die Lync Server-Verwaltungsshell auf dem Front-End-Server: Klicken Sie auf **Start** , klicken Sie auf **Alle Programme** , klicken Sie auf **Microsoft Lync Server 2013**, und klicken Sie dann auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie an der Eingabeaufforderung die folgenden Befehle ein:
    
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption

       &nbsp;
    
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    

    > [!NOTE]
    > Dieser Schritt ist erforderlich, weil Windows Live Messenger die Audio-/Videoverschlüsselung nicht unterstützt. Mithilfe des Befehls wrid die globale Richtlinie auf eine Einstellung zur Unterstützung der Verschlüsselung festgelegt, anstatt die Verschlüsselung der Audio-/Videodaten zu fordern. Auf Clients, die die Verschlüsselung unterstützen, wird die Verschlüsselung weiterhin verwendet, dies ist beispielsweise bei Lync 2013 der Fall.


