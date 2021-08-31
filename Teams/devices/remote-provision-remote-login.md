---
title: Remotebereitstellung und -anmeldung für Teams Android-Geräte
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Remotebereitstellung und -anmeldung für Teams Android-Geräte verwenden.
ms.openlocfilehash: 668e50eab20d96f28ff7a6be49a0ddcac872b393
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733314"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Remotebereitstellung und -anmeldung für Teams Android-Geräte

IT-Administratoren können Remotebereitstellung und -anmeldung bei einem Teams Android-Gerät ausführen. Um ein Gerät remote bereitstellen zu können, muss der Administrator die MAC-IDs der bereitgestellten Geräte hochladen und einen Prüfcode erstellen. Der gesamte Vorgang kann remote über das Admin Center Teams werden.

## <a name="review-the-supported-devices"></a>Überprüfen der unterstützten Geräte

In der folgenden Liste sind die Firmwareanforderungen für Android-Geräte aufgeführt.

|Gerätekategorie|Gerätemodell|Firmwareversion|
|-|-|-|
|Teams-Smartphones|Yealink T55/T56/T58|58.15.0.124|
|Teams-Smartphones|Yealink VP59|91.15.0.58|
|Teams-Smartphones|Yealink CP960|73.15.0.117|
|Teams-Smartphones|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams-Smartphones|Crestron UC-2|1.0.3.52|
|Teams-Smartphones|  Poly Trio C60|  7.0.2.1071|
|Teams-Smartphones|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Teams-Smartphones|  Audiocodes C448HD/C450HD/C470HD|   1.10.120|
|Teams-Panels|  Crestron 770/1070|  1.004.0115|
|Teams-Räume unter Android|Logitech Rally Bar Mini|1.2.982|
|Teams-Räume unter Android|Logitech Rally Bar|1.2.982|
|Teams-Räume unter Android|AudioCodes RECEIVERV80|1.13.361|
|Teams-Räume unter Android|EXPAND Vision 3T|1.2.2.21182.10|
|Teams-Räume unter Android|Yealink MeetingBar A30|133.15.0.60|
|Teams-Räume unter Android|Yealink MeetingBar A20|133.15.0.60|
|Teams-Räume unter Android|Yealink CTP18-Touchkonsole|137.15.0.37|
|Teams-Räume unter Android|Poly Studio X30|3.5.0.344025|
|Teams-Räume unter Android|Poly Studio X50|3.5.0.344025|
|Teams-Räume unter Android|Poly TC8-Touchkonsole |3.5.0.210489|
|Teams-Räume unter Android|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>Hinzufügen einer MAC-Adresse für ein Gerät

Führen Sie die folgenden Schritte zum Bereitstellen eines neuen Geräts aus.

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Erweitern **Sie Geräte**.
3. Wählen **Sie auf der Registerkarte Aktionen die** Option Neues Gerät **bereitstellen** aus.

Im Fenster **Neue Geräte bereitstellen** können Sie entweder die MAC-Adresse manuell hinzufügen oder eine Datei hochladen.

### <a name="manually-add-a-device-mac-address"></a>Manuelles Hinzufügen einer MAC-Adresse für das Gerät

1. Wählen Sie **auf der Registerkarte Awaiting Activation** die Option Add MAC ID **aus.**

   ![Fügen Sie manuell eine Mac-Adresse für das Gerät hinzu.](../media/remote-provision-6.png)

1. Geben Sie die MAC-ID ein.
1. Geben Sie einen Standort ein, mit dem Techniker ermitteln können, wo die Geräte installiert werden sollen.
1. Wenn Sie **fertig sind,** wählen Sie Übernehmen aus.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Hochladen einer Datei zum Hinzufügen einer MAC-Adresse für ein Gerät

1. Wählen Sie **auf der Registerkarte Awaiting Activation** die Option Hochladen MAC **IDs aus.**
2. Laden Sie die Dateivorlage herunter.
3. Geben Sie die MAC-ID und den Speicherort ein, und speichern Sie dann die Datei.
4. **Wählen Sie Datei** und dann **Hochladen** aus.

## <a name="generate-a-verification-code"></a>Generieren eines Prüfcodes

Sie benötigen einen Prüfcode für die Geräte. Der Überprüfungscode wird in Massen oder auf Geräteebene generiert und ist 24 Stunden gültig.

1. Wählen Sie **auf der Registerkarte Awaiting Activation** eine vorhandene MAC-ID aus.
   Für die MAC-Adresse wird ein Kennwort erstellt und in der Spalte **Prüfcode** angezeigt.

2. Stellen Sie die Liste der MAC-IDs und Prüfcodes für Die Feldtechniker zur Verfügung. Sie können die Details direkt in eine Datei exportieren und die Datei für den Techniker freigeben, der die eigentlichen Installationsarbeiten überarbeiten soll.

## <a name="provision-the-device"></a>Bereitstellen des Geräts

Wenn das Gerät eingeschaltet und mit dem Netzwerk verbunden ist, wird das Gerät vom Techniker bereitgestellt. Diese Schritte werden auf dem Gerät Teams durchgeführt.

1. Der Techniker wählt geräte **bereitstellen aus** der Liste **Einstellungen.**  

   ![Option "Neues Gerät bereitstellen" auf der Registerkarte "Aktionen".](../media/provision-device1.png)
  
2. Der Techniker gibt den gerätespezifischen Prüfcode in das bereitgestellte Eingabefeld ein.

   ![Neue Geräteüberprüfung bereitstellen.](../media/provision-device-verification1.png)

   Sobald das Gerät erfolgreich bereitgestellt wurde, wird der Mandantname auf der Anmeldeseite angezeigt.

   ![Der Mandantname auf der Anmeldeseite.](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Remote anmelden

Das bereitgestellte Gerät wird auf der Registerkarte **Awaiting sign in** angezeigt. Starten Sie den Remote-Anmeldevorgang, indem Sie das einzelne Gerät auswählen.

1. Wählen Sie auf der Registerkarte **Awaiting sign in ein Gerät** aus.

   ![Das Fenster mit einer Liste der geräte, die für die Anmeldung bereit sind.](../media/remote-device1.png)

2. Folgen Sie den Anweisungen unter Anmelden bei einem **Benutzer,** und wählen Sie dann **Schließen aus.**

   ![das Fenster "Anmelden bei einem Benutzer" für ein einzelnes Gerät.](../media/sign-in-user.png)

## <a name="related-article"></a>Verwandter Artikel

- [Verwalten Ihrer Geräte in Teams](device-management.md).
- [Remoteupdate Teams Geräte](remote-update.md)
