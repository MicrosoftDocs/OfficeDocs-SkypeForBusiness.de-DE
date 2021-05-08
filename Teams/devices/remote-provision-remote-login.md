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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Remotebereitstellung und -anmeldung für Teams Android-Geräte verwenden.
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059189"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Remotebereitstellung und -anmeldung für Teams Android-Geräte

IT-Administratoren können Remotebereitstellung und -anmeldung auf einem Teams Android-Gerät ausführen. Um ein Gerät remote bereitstellen zu können, muss der Administrator die MAC-IDs der bereitgestellten Geräte hochladen und einen Prüfcode erstellen. Der gesamte Vorgang kann remote über das Admin Center Teams werden.

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

## <a name="add-a-device-mac-address"></a>Hinzufügen einer MAC-Adresse für ein Gerät

Führen Sie die folgenden Schritte zum Bereitstellen eines neuen Geräts aus.

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Erweitern **Sie Geräte**.
3. Wählen **Sie auf der Registerkarte Aktionen die** Option Neues Gerät **bereitstellen** aus.

Im Fenster **Neue Geräte bereitstellen** können Sie entweder die MAC-Adresse manuell hinzufügen oder eine Datei hochladen.

### <a name="manually-add-a-device-mac-address"></a>Manuelles Hinzufügen einer MAC-Adresse für das Gerät

1. Wählen Sie **auf der Registerkarte Awaiting Activation** die Option Add MAC ID **aus.**

   ![Manuelles Hinzufügen einer Mac-Adresse für ein Gerät](../media/remote-provision-6.png)

1. Geben Sie die MAC-ID ein.
1. Geben Sie einen Standort ein, mit dem Techniker ermitteln können, wo die Geräte installiert werden sollen.
1. Wenn Sie **fertig sind,** wählen Sie Übernehmen aus.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Hochladen einer Datei, um eine MAC-Adresse des Geräts hinzuzufügen

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

1. Der Techniker wählt in **der Liste Gerät** bereitstellen **Einstellungen** aus.  

   ![Option "Neues Gerät bereitstellen" auf der Registerkarte "Aktionen"](../media/provision-device1.png)
  
2. Der Techniker gibt den gerätespezifischen Prüfcode in das bereitgestellte Eingabefeld ein.

   ![Bereitstellung der Überprüfung neuer Geräte](../media/provision-device-verification1.png)

   Sobald das Gerät erfolgreich bereitgestellt wurde, wird der Mandantname auf der Anmeldeseite angezeigt.

   ![Tenant name on sign-in page](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Remote anmelden

Das bereitgestellte Gerät wird auf der Registerkarte **Awaiting sign in** angezeigt. Starten Sie den Remote-Anmeldevorgang, indem Sie das einzelne Gerät auswählen.

1. Wählen Sie auf der Registerkarte **Awaiting sign in ein Gerät** aus.

   ![Das Fenster mit einer Liste der geräte, die für die Anmeldung bereit sind.](../media/remote-device1.png)

2. Folgen Sie den Anweisungen unter Anmelden bei einem **Benutzer,** und wählen Sie dann **Schließen aus.**

   ![das Fenster "Anmelden bei einem Benutzer" für ein einzelnes Gerät](../media/sign-in-user.png)

## <a name="related-article"></a>Verwandter Artikel

- [Verwalten Ihrer Geräte in Teams](device-management.md).
- [Remoteupdate für Teams Geräte](remote-update.md)
