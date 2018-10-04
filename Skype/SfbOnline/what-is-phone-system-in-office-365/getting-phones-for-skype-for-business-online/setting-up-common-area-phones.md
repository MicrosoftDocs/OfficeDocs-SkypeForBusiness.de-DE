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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Hier erfahren Sie die Schritte zur Bereitstellung, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Telefone in öffentlichen Bereichen.
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370675"
---
# <a name="set-up-common-area-phones"></a>Einrichten von Telefonen für gemeinsame Bereiche
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Voraussetzungen für Telefone für gemeinsame Bereiche

Zunächst müssen Sie bestätigen, dass Folgendes zutrifft:

- Sie haben eine Lizenz für Telefone für gemeinsame Bereiche und einen Anrufplan gekauft.
- Sie haben nach zugelassenen Telefonen gesucht und sie gekauft (siehe die Liste [hier](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Telefone Polycom VVX**: Rufen Sie die **Einstellungsseite** > **Status** > **Plattform** > **Anwendung** > **Main**.
  - **Yealink Telefone**: Wechseln Sie auf **Status** auf dem Bildschirm Telefon.
  - **AudioCodes Telefone**: Gehen Sie zum **Menü** > **Gerätestatus** > **Firmwareversion** auf der Startseite.
  - **Lync Phone Edition (LPE) Telefone**: Gehen Sie zum **Menü** > **Systeminformationen** aus dem Startbildschirm.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Einrichten eines Telefons für gemeinsame Bereiche
Sie müssen diese Schritte befolgen:

### <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen
1. Gehen Sie im Office 365 Admin Center zu **Rechnung** > **Kaufdienste** und fügen Sie **Weitere Pläne** hinzu.

    ![CAP-license.png](../../images/cap-license.png)
2. Klicken Sie auf **Telefon für gemeinsame Bereiche** > **Jetzt kaufen** > auf der Seite **Check-Out** klicken Sie auf **Jetzt kaufen**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Weitere Informationen zu Lizenzen finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen
1. Gehen Sie im Office 365 Admin Center zu **Benutzer** > **Aktive Benutzer** > **Benutzer hinzufügen**.
2. Geben Sie einen **Benutzernamen** wie "Haupt" für den Vornamen und "Empfang" für den Nachnamen ein.
3. Geben Sie einen **Anzeigename** ein, falls nicht automatisch einer wie "Hauptempfang" generiert wurde.
4. Geben Sie einen **Benutzernamen** wie "Hauptempfang" oder "Hauptlobby" ein.
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.

    > [!Tip]
    > WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.

6. If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:
   - Telefon für gemeinsame Bereiche
   - Danach müssen Sie entweder einen **Anrufplan für Inland** oder einen Anrufplan für Inland und **Ausland**auswählen.

     Die Zuweisung der Lizenzen sieht dann so aus:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Nur zu Ihrer Information Skype for Business Plan 2 ist in der Lizenz **Telefon für gemeinsame Bereiche** enthalten.

Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Dem Benutzer mit dem **Skype for Business Admin Center** eine Telefonnummer zuweisen

1. Im Office 365 Administrationscenter > **Admin zentriert** > **Skype für Unternehmen**.
2. In dem **Skype for Business Admin Center** >  **Sprache** > **Telefonnummern**.
3. Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.
4. Geben Sie auf der Seite **Zuweisen** im Feld **Sprachbenutzer** den Namen des Benutzers ein, der für das Telefon verwendet wird, und wählen Sie den Benutzer im Feld **Sprachbenutzer auswählen** aus.
5. While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.
6. Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:

    ![cap-user-nummer.png](../../images/cap-user-number.png)

   > [!Note]
   > Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.

Weitere Informationen finden Sie unter [Erhalten von Telefonnummern für Ihre Benutzer](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Schritt 4 - Einrichten des Telefons

**Einstellen des Telefonmodus**

The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.

**Hier ein Beispiel für die Einrichtung eines Polycom VVX-Telefons**

- Aktivieren Sie mit den folgenden Schritten den Modus "Telefon für gemeinsame Bereiche" für Polycom VVX:
    1. Stellen Sie in Ihrem Browser eine Verbindung zur Webschnittstelle her, damit Sie den CAP-Modus aktivieren können.
    2. Danach gehen Sie zu **Einstellung** und wählen in der Option **Skype for Business-Einstellungen** **Telefone für gemeinsame Bereiche**.
    3. Klicken Sie auf **Ja**, um Ihre Einstellungen zu speichern.

- Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:

    1. Klicken Sie auf **Einstellungen speichern.**
    2. Klicken Sie auf **Erweitert**.
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
> The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.


### <a name="related-topics"></a>Verwandte Themen

- Weitere Informationen über verfügbare Telefone finden Sie unter [Einsatz von Skype for Business Online-Telefonen](deploying-skype-for-business-online-phones.md).
- [Erwerben von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md)


