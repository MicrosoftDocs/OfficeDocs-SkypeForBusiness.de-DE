---
title: Bereitstellen von Telefonen für Skype for Business Online
description: Hier erfahren Sie die Schritte zur Bereitstellung, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Telefone in öffentlichen Bereichen.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a>Telefone in öffentlichen Bereichen
Ein Telefon im öffentlichen Bereich oder Cap hat, wird in der Regel in einem freigegebenen Bereich platziert und nicht mit einem einzelnen Benutzer verknüpft. Beispielsweise ein Empfang für Telefone, Tür Telefon- oder Meeting Room Telefon, CAPs Geräte, sondern als Benutzer eingerichtet sind, und automatisch mit dem Netzwerk anmelden. In den folgenden Schritten helfen wir Ihnen richten Sie ein Konto für Microsoft Telefonsystem mit Aufrufen plant und anschließendem Bereitstellen einer Cap hat.

## <a name="prerequisites-for-common-area-phones"></a>Erforderliche Komponenten für Telefone in öffentlichen Bereichen

Vergewissern Sie sich, dass Sie über Folgendes verfügen:

    - Telefone in öffentlichen Bereichen SKU erworben 
    - Aktualisierte Firmware (finden Sie unter Unterstützte Firmware im Themahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
    - Genehmigte (anzeigen die Liste am Telefonehttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones) 


## <a name="check-the-firmware-for-your-phone"></a>Überprüfen Sie die Firmware für Ihr Telefon
- **Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.
- **Yealink-Telefone**: Navigieren Sie auf dem Hauptbildschirm des Telefons zu **Status** (Status).
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen. 
- **Telefone mit Lync Phone Edition (LPE)**: Navigieren Sie vom Startbildschirm aus zu **Menü** > **Systeminformationen**.

Firmwareupdates werden vom Skype for Business-Dienst verwaltet. Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert. 

Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert. Sie können die Einstellungen für Geräteupdates mit dem [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)-Cmdlet deaktivieren und den  _EnableDeviceUpdate_-Parameter auf  `false` festlegen.

## <a name="create-cap"></a>CAP erstellen
Erstellen Sie die CAP durch Konfigurieren der Einstellungen, bevor Sie die Telefonapparat einrichten.

#### <a name="purchase-the-common-area-phone-sku"></a>Kaufen Sie das Telefon im öffentlichen Bereich SKU. 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>Richten Sie das Telefon im öffentlichen Bereich<!-- this section could use a screen shot-->

**Benutzer erstellen** 
1. Zuweisen von Kontaktobjekten für Telefone SKU
2. Zuweisen von Aufrufen planen (bei Verwendung von Microsoft Telefonsystem mit Aufrufen plant). 
3. Zuweisen einer verfügbaren Telefonnummer in die Skype für Business Admin Center, oder fordern Sie eine neue Telefonnummer.

**Erstellen Sie neuen Benutzer**

1. Klicken Sie im Bereich Bereitstellung müssen Sie eine Option, um einen ersten und letzten Namen (beispielsweise Empfang Main) eingeben.
2. Geben Sie einen Anzeigenamen (erforderlich), z. B. "Main Empfang."
3. Geben Sie einen Benutzernamen (erforderlich), zum Beispiel "MainReception" @"Domäne" (Name des Unternehmens oder Enterprise)
4. Geben Sie Speicherort (Land).

**Zuweisen von Kontaktobjekten für Telefone SKU** Wechseln Sie in das Office 365 Administrationscenter zu **Abrechnung > Dienste erwerben** und Hinzufügen von **Kontaktobjekten für Telefone**

**Aufrufen von Plan CAP SKU zuweisen**

1. Wählen Sie eine Aufrufen des Telefons aktivieren möchten. 
2. Fügen Sie der Caps um Telefonsystem und Skype für Business Online – Plan 2 in der CAP SKU zu aktivieren. <!-- odd order for step -->

**Weisen Sie eine Telefonnummer**
1. Überprüfen Sie unter Verfügbare Telefonnummern **VoIP > Telefonnummern**.
2. Wählen Sie eine Rufnummer aus der Liste der verfügbaren Nummern Telefonnummer.
3. Bestätigen Sie Ihre Auswahl durch Auswählen von **Sprach-** und **Rufnummern**.

    >[Hinweis] VoIP-Benutzer werden nur anzeigen, wenn sie Telefonsystem Lizenz angewendet, obwohl auch nach dem anwenden, es aktualisieren dauern kann verfügen. Können erneut öffnen irgendwann Skype für Business Admin Center.
    
## <a name="configure-phone"></a>Konfigurieren des Telefons

**Vorbereiten der physischen Telefone** 

Das ausgewählte Telefon muss den Modus für Telefone in öffentlichen Bereichen haben. 

***Beispiel Polycom VVX Telefon***

Aktivieren Sie Common Area Phone Mode auf Polycom VVX folgende Schritte aus:
1. Verwenden Sie in Ihrem Browser die Weboberfläche, um auf die VVX CAP-Modus aktivieren
2. Wechseln Sie zur **Einstellung** und in der Skype für Business Festlegen der Option, und wählen Sie **Telefone in öffentlichen Bereichen**.
3. Klicken Sie auf **Speichern** , um die Konfigurationseinstellungen speichern.

Nun, dass der CAP Telefon-Modus aktiviert ist, richten Sie das Telefon mit Display des Telefons.

1. Wählen Sie in den Einstellungen für **Erweitert**.
2. Geben Sie das Kennwort ein.
3. Wählen Sie im administrationseinstellungen **Common Area Phone Settings**.
4. Aktivieren von Common Area Phone and CAP Admin
5. Wählen Sie **Config speichern**.

Ihr Telefon kann jetzt bereitgestellt werden, was werden Sie bei der Anmeldung auf dem Startbildschirm.

1. Melden Sie sich durch Auswählen von **Einstellungen > Funktionen > Skype für Business.**
2. Wählen Sie Benutzeranmeldeinformationen und wählen Sie **Web - Anmeldung (CAP)** um einen Code zu generieren.
3. Wechseln Sie zu der Bereitstellung Portal http://aka.ms/skypecap, und melden Sie sich als **Administrator**.
4. Geben Sie Anzeigenamen ein (beispielsweise Main Empfang), um Ihre CAP anzuzeigen.

>[Hinweis] Wenn "-Suche für Telefone in öffentlichen Bereichen nur" ist ausgecheckt, deaktivieren Sie das Kontrollkästchen, und wiederholen Sie die Suche.

5. Klicken Sie im Codefenster paarungs Geben Sie den Code auf dem Telefon angezeigt, und klicken Sie auf **Bereitstellung**.

In diesem letzten Schritt Wht, sollte das Telefon automatisch anmelden.

Weitere Informationen zu verfügbaren Telefonen [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).


