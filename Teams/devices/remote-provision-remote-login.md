---
title: Remotebereitstellung und Anmeldung für Teams Android-Geräte
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Für Teams Android-Geräte remote bereitstellen und sich anmelden
ms.openlocfilehash: 566f7428d03a16082a37ff7a8896cffbb27b85ec
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267790"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Remotebereitstellung und Anmeldung für Teams Android-Geräte

IT-Administratoren können remote ein Android-Gerät von Teams bereitstellen und sich anmelden. Um ein Gerät remote bereitzustellen, muss der Administrator die MAC-IDs der bereitgestellten Geräte hochladen und einen Überprüfungscode erstellen. Der gesamte Prozess kann remote aus dem Teams Admin Center abgeschlossen werden.

## <a name="review-the-supported-devices"></a>Überprüfen der unterstützten Geräte

In der folgenden Liste sind die Firmwareanforderungen für Android-Geräte aufgeführt.

|Gerätekategorie|Gerätemodell|Firmwareversion|
|---|---|---|
|Teams-Telefone|Yealink T55/T56/T58|58.15.0.124|
|Teams-Telefone|Yealink VP59|91.15.0.58|
|Teams-Telefone|Yealink CP960|73.15.0.117|
|Teams-Telefone|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams-Telefone|Crestron UC-2|1.0.3.52|
|Teams-Telefone|Poly Trio C60|7.0.2.1071|
|Teams-Telefone|CCX400/CCX500/CCX600 |7.0.2.1072|
|Teams-Telefone|Audiocodes C448HD/C450HD/C470HD|1.10.120|
|Teams-Bereiche|Crestron 770/1070|1.004.0115|
|Teams-Räume unter Android|Logitech Rally Bar Mini|1.2.982|
|Teams-Räume unter Android|Logitech Rally Bar|1.2.982|
|Teams-Räume unter Android|AudioCodes RXV80|1.13.361|
|Teams-Räume unter Android|EPOS EXPAND Vision 3T|1.2.2.21182.10|
|Teams-Räume unter Android|Yealink MeetingBar A30|133.15.0.60|
|Teams-Räume unter Android|Yealink MeetingBar A20|133.15.0.60|
|Teams-Räume unter Android|Yealink-CTP18-Touchkonsole|137.15.0.37|
|Teams-Räume unter Android|Poly Studio X30|3.5.0.344025|
|Teams-Räume unter Android|Poly Studio X50|3.5.0.344025|
|Teams-Räume unter Android|Poly TC8 Touch-Konsole |3.5.0.210489|
|Teams-Räume unter Android|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>Hinzufügen einer MAC-Adresse eines Geräts

Führen Sie die folgenden Schritte aus, um ein neues Gerät bereitzustellen.

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Erweitern Sie **Teams-Geräte**.
3. Wählen Sie auf der Registerkarte **"Aktionen"** die Option **"Neues Gerät bereitstellen**" aus.

Im Fenster " **Neue Geräte bereitstellen** " können Sie entweder die MAC-Adresse manuell hinzufügen oder eine Datei hochladen.

### <a name="manually-add-a-device-mac-address"></a>Manuelles Hinzufügen einer MAC-Adresse eines Geräts

1. Wählen Sie auf der Registerkarte **"Warten auf Aktivierung** " die Option **"MAC-ID hinzufügen"** aus.

   ![fügen Sie manuell eine Mac-Adresse des Geräts hinzu.](../media/remote-provision-6-new.png)

1. Geben Sie die MAC-ID ein.
1. Geben Sie einen Speicherort ein, der Technikern hilft, zu ermitteln, wo die Geräte installiert werden sollen.
1. Wählen Sie **"Übernehmen** " aus, wenn Sie fertig sind.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Hochladen einer Datei zum Hinzufügen einer MAC-Geräteadresse

1. Wählen Sie auf der Registerkarte **"Warten auf Aktivierung** " **die Option "MAC-IDs hochladen" aus**.
2. Laden Sie die Dateivorlage herunter.
3. Geben Sie die MAC-ID und den Speicherort ein, und speichern Sie die Datei.
4. **Wählen Sie "Datei"** und dann " **Hochladen"** aus.

## <a name="generate-a-verification-code"></a>Generieren eines Überprüfungscodes

Sie benötigen einen Überprüfungscode für die Geräte. Der Überprüfungscode wird in Massen oder auf Geräteebene generiert und ist 24 Stunden lang gültig.

1. Wählen Sie auf der Registerkarte **"Warten auf Aktivierung** " eine vorhandene MAC-ID aus.
   Ein Kennwort wird für die MAC-Adresse erstellt und in der Spalte **"Überprüfungscode"** angezeigt.

2. Stellen Sie den Außendiensttechnikern die Liste der MAC-IDs und Überprüfungscodes bereit. Sie können die Details direkt in eine Datei exportieren und die Datei für den Techniker freigeben, der die eigentliche Installationsarbeit ausführt.

## <a name="provision-the-device"></a>Bereitstellen des Geräts

Wenn das Gerät eingeschaltet und mit dem Netzwerk verbunden ist, stellt der Techniker das Gerät bereit. Diese Schritte werden auf dem Microsoft Teams-Gerät ausgeführt.

1. Der Techniker wählt **"Bereitstellungsgerät** " in den **Einstellungen** aus.  

   ![Stellen Sie die neue Geräteoption auf der Registerkarte "Aktionen" bereit.](../media/provision-device1.png)
  
2. Der Techniker gibt den gerätespezifischen Überprüfungscode in das bereitgestellte Eingabefeld ein.

   ![Stellen Sie die Überprüfung neuer Geräte bereit.](../media/provision-device-verification1.png)

   Nachdem das Gerät erfolgreich bereitgestellt wurde, wird der Name des Mandanten auf der Anmeldeseite angezeigt.

   ![Mandantenname auf der Anmeldeseite.](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>Erstmalige Remoteanmeldung

Das bereitgestellte Gerät wird auf der Registerkarte **"Warten auf Anmeldung** " angezeigt. Starten Sie den Remoteanmeldungsprozess, indem Sie das einzelne Gerät auswählen.

1. Wählen Sie auf der Registerkarte **"Auf Anmeldung warten"** ein Gerät aus.

   ![Das Fenster mit einer Liste der Geräte, die für die Anmeldung bereit sind.](../media/remote-device1.png)

2. Folgen Sie den Anweisungen **unter "Anmelden bei einem Benutzer**", und wählen Sie dann " **Schließen"** aus.

   ![das Fenster "Anmelden bei einem Benutzer" für ein einzelnes Gerät.](../media/sign-in-user.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten Ihrer Geräte in Teams](device-management.md).
- [Remoteanmeldung und -abmeldung](remote-sign-in-and-sign-out.md)
- [Remoteaktualisierung von Teams-Geräten](remote-update.md)
