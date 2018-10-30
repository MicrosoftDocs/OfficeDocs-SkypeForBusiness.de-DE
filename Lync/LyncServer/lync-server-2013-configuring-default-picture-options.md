---
title: Konfigurieren der Standardoptionen für das Benutzerbild
TOCTitle: Konfigurieren der Standardoptionen für das Benutzerbild
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn205074(v=OCS.15)
ms:contentKeyID: 53901851
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Standardoptionen für das Benutzerbild

 

_**Letztes Änderungsdatum des Themas:** 2013-03-22_

Standardmäßig werden Bilder von Benutzern automatisch angezeigt. Wenn Benutzer ihre Bilder ausblenden möchten, können sie im Lync-Client die Option **Mein Bild ausblenden** aktivieren. Diese Einstellungen wird allerdings von einigen anderen Office-Anwendungen ignoriert.

Wenn die Möglichkeit, dass Bilder auch dann angezeigt werden, wenn dies vom Benutzer deaktiviert wurde, unerwünscht ist, können Sie die Lync-Einstellungen zum Anzeigen von Bildern global für einen Standort oder Dienst ändern, sodass die Bilder von Benutzern standardmäßig nicht angezeigt werden. Verwenden Sie das folgende Lync Server-Verwaltungsshell-Cmdlet, damit die Bilder von Benutzern nicht angezeigt werden, sofern sie die Option **Mein Bild anzeigen** im Client nicht explizit aktivieren:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Weitere Informationen zu diesem Cmdlet finden Sie unter [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration) in der Lync Server-Verwaltungsshell-Dokumentation.

