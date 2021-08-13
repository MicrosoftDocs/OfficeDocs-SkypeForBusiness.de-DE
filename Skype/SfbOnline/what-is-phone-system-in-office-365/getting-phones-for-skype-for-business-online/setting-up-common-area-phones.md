---
title: Einrichten von Telefonen für gemeinsame Bereiche
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Informieren Sie sich über die Bereitstellungsschritte, um die richtige Firmware zu erhalten, sie bei Bedarf zu aktualisieren, Lizenzen zuzuordnen und Einstellungen für Telefone im allgemeinen Bereich zu konfigurieren.
ms.openlocfilehash: a73de696e8ac7410e9cccbca99dbabb74df392f58a8bf0ad82e5bdf1ec9ccd75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300401"
---
# <a name="set-up-common-area-phones"></a>Einrichten von Telefonen für gemeinsame Bereiche

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
Ein Telefon für gemeinsame Bereiche (CAP) wird typischerweise in einem Bereich wie in einer Lobby oder in einem anderen Bereich platziert, der vielen Menschen zur Verfügung steht. Zum Beispiel ein Telefon im Empfangsbereich, ein Türtelefon oder ein Konferenzraumtelefon, CAPs werden als Geräte und nicht als Benutzer eingerichtet und melden sich automatisch in einem Netzwerk an. In den folgenden Schritten helfen wir Ihnen, ein Konto für das Telefonsystem mit Anrufplänen einzurichten, damit Sie diese Art von Telefone für Ihr Unternehmen bereitstellen können.

## <a name="prerequisites-for-common-area-phones"></a>Voraussetzungen für Telefone für gemeinsame Bereiche

Zunächst müssen Sie bestätigen, dass Folgendes zutrifft:

- Sie haben eine Lizenz für Telefone für gemeinsame Bereiche und einen Anrufplan gekauft.
- Sie haben nach zugelassenen Telefonen gesucht und sie gekauft (siehe die Liste [hier](deploying-skype-for-business-online-phones.md)).
- Sie haben die Firmware auf Ihren Telefonen aktualisiert (siehe unterstützte Firmware [in diesem Thema](getting-phones-for-skype-for-business-online.md)).  Sie können die Firmware auf Ihrem Telefon wie folgt überprüfen:
  - **Polycom VVX-Telefone:** Wechseln Sie **zu Einstellungen**  >  **Status**  >  **Platform**  >  **Application**  >  **Main**.
  - **Yealink-Telefone:** Wechseln Sie **auf dem Hauptbildschirm** des Telefons zu Status.
  - **AudioCodes-Telefone:** Wechseln Sie vom **Startbildschirm** aus zum  >    >  **Menü** Gerätestatus Firmwareversion.
  - **Telefone Telefon Lync Telefon Edition (LPE):** Wechseln Sie Systeminformationen   >   Startbildschirm zu Menümenü.

    Firmwareupdates werden vom Skype for Business-Dienst verwaltet. Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert.

    Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert. Sie können die Geräteupdateeinstellungen deaktivieren, indem Sie das  [Cmdlet Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) verwenden und den *EnableDeviceUpdate-Parameter* auf `false` festlegen.

## <a name="setting-up-a-common-area-phone"></a>Einrichten eines Telefons für gemeinsame Bereiche
Sie müssen diese Schritte befolgen:

### <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen
1. Wechseln Sie im Admin Center zu  >  **Abrechnungskaufsdienste**, und fügen Sie **Weitere Pläne hinzu.**

    ![Screenshot der Telefon des gemeinsamen Bereichs](../../images/cap-license.png)
2. Klicken Sie auf **Telefon für gemeinsame Bereiche** > **Jetzt kaufen** > auf der Seite **Check-Out** klicken Sie auf **Jetzt kaufen**.
3. Klicken Sie darauf, um **Add-on-Abonnements** zu erweitern, und klicken Sie dann darauf, um einen Anrufplan zu kaufen. Wählen Sie entweder den **Plan für Inlandsrufe** oder **einen Plan für Inlands- und Auslandsrufe aus.**

> [!Note]
> Sie benötigen für das Telefonsystem keine Lizenz. Sie ist in der Lizenz **Telefon für gemeinsame Bereiche** enthalten.

Weitere Informationen zu Lizenzen finden Sie [unter Skype for Business und Microsoft Teams-Add-On-Lizenzierung.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen
1. Wechseln Sie im Admin Center **zu** Aktive  >  **Benutzer Hinzufügen**  >  **eines Benutzers**.
2. Geben Sie einen **Benutzernamen** wie "Haupt" für den Vornamen und "Empfang" für den Nachnamen ein.
3. Geben Sie einen **Anzeigename** ein, falls nicht automatisch einer wie "Hauptempfang" generiert wurde.
4. Geben Sie einen **Benutzernamen** wie "Hauptempfang" oder "Hauptlobby" ein.
5. Für Telefone für gemeinsame Bereiche können Sie ein Kennwort manuell festlegen oder das gleiche Kennwort für alle Telefone für gemeinsame Bereiche verwenden. Sie können auch darüber nachdenken, die Wahl von **Benutzer veranlassen, sein Passwort bei der Erstanmeldung zu ändern** aufzuheben.
6. Wenn Sie sich noch dort befinden, weisen Sie die Lizenzen diesem Benutzer zu. Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern. Aktivieren Sie Folgendes:
   - Telefon für gemeinsame Bereiche
   - Danach müssen Sie entweder einen **Anrufplan für Inland** oder einen Anrufplan für Inland und **Ausland** auswählen.

     Die Zuweisung der Lizenzen sieht dann so aus:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Nur zu Ihrer Information Skype for Business Plan 2 ist in der Lizenz **Telefon für gemeinsame Bereiche** enthalten.

Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen

![Symbol mit dem Skype for Business Zuweisen einer Telefonnummer zum Benutzer über das ](../../images/sfb-logo-30x30.png) **Skype for Business Admin Center**

1. Im Admin Center > **Admin Center Skype for Business.**  >  
2. In dem **Skype for Business Admin Center** >  **Sprache** > **Telefonnummern**.
3. Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.
4. Geben Sie auf der Seite **Zuweisen** im Feld **Sprachbenutzer** den Namen des Benutzers ein, der für das Telefon verwendet wird, und wählen Sie den Benutzer im Feld **Sprachbenutzer auswählen** aus.
5. Hier müssen Sie eine Notfalladresse angeben. Nach der Suche schauen Sie unter **Notfalladresse auswählen**, um die richtige für Sie auszuwählen.
6. Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:

    ![Screenshot der Telefonnummer eines Benutzers](../../images/cap-user-number.png)

   > [!Note]
   > Benutzer werden nur angezeigt, wenn sie eine **Telefonsystem**-Lizenz beantragt haben. Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.

Weitere Informationen finden Sie unter [Erhalten von Telefonnummern für Ihre Benutzer](/microsoftteams/getting-phone-numbers-for-your-users).

Wenn Sie sich fragen, können Sie auch Ihre Telefonnummer, die Sie bei einem anderen Netzbetreiber haben, und *"Portieren"* verwenden oder diese zu Microsoft 365 oder Office 365. Weitere Informationen [finden Sie unter Übertragen von Telefonnummern Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

### <a name="step-4---setting-up-your-phone"></a>Schritt 4 - Einrichten des Telefons

**Einstellen des Telefonmodus**

Das oder die Telefone, die Sie besitzen, müssen den Modus **Telefone für gemeinsame Bereiche** aktiviert haben. Vielleicht sollten Sie das überprüfen, um sicherzugehen.

**Hier ein Beispiel für die Einrichtung eines Polycom VVX-Telefons**

- Aktivieren Sie mit den folgenden Schritten den Modus "Telefon für gemeinsame Bereiche" für Polycom VVX:
    1. Stellen Sie in Ihrem Browser eine Verbindung zur Webschnittstelle her, damit Sie den CAP-Modus aktivieren können.
    2. Danach gehen Sie zu **Einstellung** und wählen in der Option **Skype for Business-Einstellungen** **Telefone für gemeinsame Bereiche**.
    3. Klicken Sie auf **Ja**, um Ihre Einstellungen zu speichern.

- Nachdem der CAP-Modus aktiviert wurde, richten Sie das Telefon über die Anzeige des Telefons ein. Die Anzeige sollte **CaAP ist aktiviert** anzeigen. Gehen Sie wie folgt vor:

    1. Klicken Sie auf **Einstellungen speichern.**
    2. Wählen Sie **Erweitert aus.**
    3. Geben Sie das Kennwort ein.
    4. Wählen Sie unter **Verwaltungseinstellungen** **Einstellungen für Telefone für gemeinsame Bereiche**.
    5. Aktivieren Sie **CAP** und **CAP Admin-Modus**.
    6. Klicken Sie auf **Konfiguration speichern**.

- Ok, jetzt ist Ihr Telefon bereit, damit Sie sich auf dem Startbildschirm anmelden können.

    1. Melden Sie sich an, indem Sie **Einstellungen** > **Funktionen** > **Skype for Business** auswählen.
    2. Wählen Sie **Benutzeranmeldeinformationen**, und wählen Sie **Webanmeldung (CAP)**, um einen Code zu generieren.
    3. Gehen Sie zum [Provisioning-Portal](https://aka.ms/skypecap), und melden Sie sich als **Administrator** an.
    4. Geben Sie den Anzeigenamen ein (z. B. Hauptempfang).

       > [!Note]
       > Wenn **Nur nach Telefonen für gemeinsame Bereiche suchen** markiert ist, deaktivieren Sie das Kontrollkästchen und suchen Sie erneut.

    5. Geben Sie im Fenster Kopplungscode den auf dem Telefon angezeigten Code ein und klicken Sie auf **Bereitstellen**.

        Nach diesem letzten Schritt sollte sich das Telefon automatisch anmelden.


> [!NOTE]
> Die CAP-Bereitstellungsseite gibt an, dass sie das Passwort des CAP-Kontos auf ein zufälliges Passwort zurücksetzt. Beachten Sie, dass das Konto, auf das sich die CAP bezieht, das Azure Active Directory (AAD)-Konto ist. Wenn Sie das Konto nur in AAD angelegt haben, ist der Prozess einfach. Wenn Sie ein lokales Active Directory mit AAD synchronisiert haben und einen Drittanbieter-IDP oder ADFS verwenden, kann die CAP-Bereitstellung nicht bereitgestellt werden. In diesem Fall müssen Sie nur ein Microsoft 365- oder Office 365/Azure Active Directory-Konto (z. B.  ein Konto mit onmicrosoft.com-Domäne) verwenden, damit die CAP-Bereitstellung funktioniert.


### <a name="related-topics"></a>Verwandte Themen

- Weitere Informationen über verfügbare Telefone finden Sie unter [Einsatz von Skype for Business Online-Telefonen](deploying-skype-for-business-online-phones.md).
- [Erwerben von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md)
