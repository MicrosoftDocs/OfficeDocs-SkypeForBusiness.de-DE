---
title: Remotebereitstellung und Anmeldung für Teams Android-Geräte
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
description: Erfahren Sie, wie Sie remote bereitstellen und sich für Teams Android-Geräte anmelden.
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410355"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Remotebereitstellung und Anmeldung für Teams Android-Geräte

IT-Administratoren können Remotebereitstellung und -anmeldung bei einem Teams Android-Gerät ausführen. Um ein Gerät remote bereitstellen zu können, muss der Administrator die MAC-IDs der bereitgestellten Geräte hochladen und einen Überprüfungscode erstellen. Der gesamte Prozess kann remote vom Teams Admin Center aus abgeschlossen werden.

## <a name="review-the-supported-devices"></a>Überprüfen der unterstützten Geräte

Die folgende Liste enthält die Firmwareanforderungen für Android-Geräte.

|Gerätekategorie|Gerätemodell|Firmwareversion|
|-|-|-|
|Teams-Telefone|Yealink T55/T56/T58|58.15.0.124|
|Teams-Telefone|Yealink VP59|91.15.0.58|
|Teams-Telefone|Yealink CP960|73.15.0.117|
|Teams-Telefone|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams-Telefone|Crestron UC-2|1.0.3.52|

## <a name="add-a-device-mac-address"></a>Hinzufügen einer GERÄTE-MAC-Adresse

Führen Sie die folgenden Schritte zum Bereitstellen eines neuen Geräts aus.

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Erweitern Sie **Geräte**.
3. Wählen **Sie auf der Registerkarte** Aktionen die Option Neues Gerät bereitstellen aus. 

Im Fenster **Neue Geräte bereitstellen** können Sie entweder die MAC-Adresse manuell hinzufügen oder eine Datei hochladen.

### <a name="manually-add-a-device-mac-address"></a>Manuelles Hinzufügen einer GERÄTE-MAC-Adresse

1. Wählen Sie **auf der Registerkarte Auf Aktivierung warten** die Option **Mac-ID hinzufügen aus.**

   ![Manuelles Hinzufügen einer Geräte-Mac-Adresse](../media/remote-provision-6.png)

1. Geben Sie die MAC-ID ein.
1. Geben Sie einen Ort ein, der Technikern hilft, zu ermitteln, wo die Geräte installiert werden sollen.
1. Wählen **Sie Übernehmen** aus, wenn Sie fertig sind.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Hochladen einer Datei zum Hinzufügen einer Geräte-MAC-Adresse

1. Wählen Sie **auf der Registerkarte Auf Aktivierung warten** die Option **MAC-IDs hochladen aus.**
2. Laden Sie die Dateivorlage herunter.
3. Geben Sie die MAC-ID und den Speicherort ein, und speichern Sie die Datei.
4. **Wählen Sie Datei** und dann **Hochladen aus.**

## <a name="generate-a-verification-code"></a>Generieren eines Überprüfungscodes

Sie benötigen einen Überprüfungscode für die Geräte. Der Überprüfungscode wird in Massen oder auf Geräteebene generiert und ist 24 Stunden lang gültig.

1. Wählen Sie **auf der Registerkarte Wartende Aktivierung** eine vorhandene MAC-ID aus.
   Für die MAC-Adresse wird ein Kennwort erstellt und in der Spalte **Überprüfungscode** angezeigt.

2. Stellen Sie den Feldtechnikern die Liste der MAC-IDs und Überprüfungscodes zur Verfügung. Sie können die Details direkt in eine Datei exportieren und die Datei für den Techniker freigeben, der die eigentlichen Installationsarbeiten vor sich hat.

## <a name="provision-the-device"></a>Bereitstellen des Geräts

Wenn das Gerät eingeschaltet und mit dem Netzwerk verbunden ist, wird das Gerät vom Techniker bereitgestellt. Diese Schritte werden auf dem Gerät von Teams abgeschlossen.

1. Der Techniker wählt in **den** Einstellungen die Option Gerät **bereitstellen aus.**  

   ![Option "Neues Gerät bereitstellen" auf der Registerkarte "Aktionen"](../media/provision-device1.png)
  
2. Der Techniker gibt den gerätespezifischen Überprüfungscode in das bereitgestellte Eingabefeld ein.

   ![Bereitstellen der Überprüfung neuer Geräte](../media/provision-device-verification1.png)

   Nachdem das Gerät erfolgreich bereitgestellt wurde, wird der Name des Mandanten auf der Anmeldeseite angezeigt.

   ![Name des Mandanten auf der Anmeldeseite](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Remote anmelden

Das bereitgestellte Gerät wird auf der Registerkarte **Wartezeichen** angezeigt. Starten Sie den Remote-Anmeldevorgang, indem Sie das einzelne Gerät auswählen.

1. Wählen Sie ein Gerät auf der Registerkarte **Wartezeichen** aus.

   ![Das Fenster mit einer Liste der Geräte, die zur Anmeldung bereit sind.](../media/remote-device1.png)

2. Folgen Sie den Anweisungen unter **Anmelden bei einem Benutzer,** und wählen Sie dann **Schließen aus.**

   ![Anmelden in einem Benutzerfenster für einzelne Geräte](../media/sign-in-user.png)

## <a name="related-article"></a>Verwandter Artikel

- [Verwalten Ihrer Geräte in Teams](device-management.md).
- [Remoteupdate für Teams-Geräte](remote-update.md)
