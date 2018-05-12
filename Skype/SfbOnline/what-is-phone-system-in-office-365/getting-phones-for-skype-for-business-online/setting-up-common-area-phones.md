---
title: Einrichten von Telefonen in öffentlichen Bereichen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
description: Hier erfahren Sie die Schritte zur Bereitstellung, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Telefone in öffentlichen Bereichen.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a>Einrichten von Telefonen in öffentlichen Bereichen
Ein Telefon im öffentlichen Bereich (CAP) platziert wird in der Regel im Bereich der ein Wartebereich oder einem anderen Bereich, der viele Personen zur Verfügung steht. Angenommen, ein Empfang für Telefone, Tür Telefon- oder Meeting Room Telefon, CAPs Geräte, sondern als Benutzer eingerichtet sind, und melden Sie sich automatisch in einem Netzwerk. In den folgenden Schritten helfen wir Ihnen richten Sie ein Konto für Telefonsystem mit plant aufrufen, damit Sie diese Typen von Telefonen für Ihre Organisation bereitstellen können.

## <a name="prerequisites-for-common-area-phones"></a>Erforderliche Komponenten für Telefone in öffentlichen Bereichen

Erstes müssen Sie besteht darin, sicherzustellen, dass Sie über Folgendes verfügen:

 - Kaufen Sie Telefone in öffentlichen Bereichen Lizenz und Aufrufen von planen.
 - Suchen nach und genehmigte Telefone kaufen (Anzeigen der Liste [hier](deploying-skype-for-business-online-phones.md)).         
 - Aktualisieren Sie die Firmware auf Ihrer Telefone (Siehe unterstützt Firmware [in diesem Thema](getting-phones-for-skype-for-business-online.md).  Sie können die Firmware auf Sie Telefon auf diese Weise überprüfen:       
    - **Telefone Polycom VVX**: Rufen Sie die **Einstellungsseite** > **Status** > **Plattform** > **Anwendung** > **Main**.
    - **Yealink Telefone**: Wechseln Sie auf **Status** auf dem Bildschirm Telefon.
    - **AudioCodes Telefone**: Gehen Sie zum **Menü** > **Gerätestatus** > **Firmwareversion** auf der Startseite. 
    - **Lync Phone Edition (LPE) Telefone**: Gehen Sie zum **Menü** > **Systeminformationen** aus dem Startbildschirm.

    Firmwareupdates werden vom Skype for Business-Dienst verwaltet. Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert. 

    Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert. Sie können die Device Update Einstellungen deaktivieren, indem Sie mithilfe des Cmdlets [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) und Festlegen des Parameters *EnableDeviceUpdate* auf `false`.

## <a name="setting-up-a-common-area-phone"></a>Einrichten einer Telefone in öffentlichen Bereichen
Sie müssen die folgenden Schritte ausführen:

### <a name="set-up-your-user-account-for-the-phone"></a>Richten Sie Ihr Benutzerkonto für das Telefon

#### <a name="step-1---buy-the-licenses"></a>Schritt 1: Erwerben von Lizenzen
1. Wechseln Sie in das Office 365 Administrationscenter zu **Abrechnung** > **Dienste erwerben**, und fügen Sie **andere Pläne**.

    ![CAP license.png](../../images/cap-license.png)
2. Klicken Sie auf **Telefon im öffentlichen Bereich** > **Jetzt kaufen** > auf der Seite auf **Auschecken** , klicken Sie auf **Jetzt kaufen**.
3. Klicken Sie auf erweitern **Add-on-Abonnements** , und klicken Sie dann auf Kaufen aufrufen planen. Wählen Sie die **nationalen Plan aufrufen** oder **nationalen und internationalen aufrufen planen**.

> [!Note]
> Eine Lizenz Telefonsystem ist nicht erforderlich. Es wurde mit der Lizenz für **Telefone in öffentlichen Bereichen** enthalten.

Weitere Informationen zu Lizenzen finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 – Erstellen eines neuen Benutzerkontos für das Telefon und die Lizenzen zuweisen
1. Wechseln Sie in das Office 365 Administrationscenter zu **Benutzern** > **Aktive Benutzer** > **Benutzer hinzufügen**.
2. Tragen Sie einen **Benutzernamen ein** , wie "Main" für den ersten Namen und "Empfang" für den zweiten Namen.
3. Wenn dies nicht der Fall einer standardbrowserformulare wie "Main Empfang" einen **Anzeigenamen** zu platzieren.
4. Tragen Sie einen **Benutzernamen ein** , wie "MainReception" oder "Mainlobby".
5. Für Telefone in öffentlichen Bereichen möchten Sie möglicherweise ein Kennwort manuell festlegen oder das gleiche Kennwort für alle von Ihnen Telefone in öffentlichen Bereichen haben. Darüber hinaus glauben Sie zum Aufheben der Auswahl **stellen diesen Benutzer ändern ihres Kennworts beim erstmaligen Anmelden**.

    > [!Tip]
    > Warte!! Klicken Sie nicht auf **Hinzufügen**. Ugh, wenn Sie **Hinzufügen** die klicken, dies: Office 365 Administrationscenter > **Benutzer** > **aktive Benutzer** und suchen Sie anschließend den Benutzer. Klicken Sie dann auf der Eigenschaftenseite des Benutzers auf **Lizenzen** , und klicken Sie dann auf **Bearbeiten**. Klicken Sie auf der Seite **Lizenzen** aktivieren Sie **Telefone in öffentlichen Bereichen** , und wählen Sie entweder einen **Nationalen aufrufen planen** oder eine National und **International aufrufen**.

6. Wenn Sie noch vorhanden sind, weisen Sie die Lizenzen an diesen Benutzer. Klicken Sie auf der gleichen Seite **um Lizenzen**zu erweitern. Aktivieren Sie die folgenden:
    - Telefone in öffentlichen Bereichen
    - Klicken Sie dann müssen Sie entweder einen **Nationalen aufrufen planen** oder eine National und **International aufrufen**auswählen.
     
    Zuweisen von Lizenzen wird wie folgt aus:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Nur, damit Sie wissen, ist Skype für Business Plan 2 enthalten, mit der Lizenz für **Telefone in öffentlichen Bereichen** .

Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>Schritt 3: dem Benutzer eine Telefonnummer zuweisen
![SFB-Logo-30x30.png](../../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**
1. Im Office 365 Administrationscenter > **Admin zentriert** > **Skype für Unternehmen**.
2. In der **Skype für Business Administrationscenter** >  **VoIP** > **Rufnummern**.
3. Wählen Sie eine Rufnummer aus der Liste der Rufnummern, und klicken Sie auf **zuweisen**.
4. Geben Sie auf der Seite **zuweisen** im Feld **Voice-Benutzer** den Namen des Benutzers, der für das Telefon und wählen Sie dann der Benutzer in der **ein VoIP-Benutzer auswählen** Dropdown-Liste verwendet wird. 
5. Nutzen Sie dort auch müssen Sie zum Hinzufügen einer Notfall Adresse. Nachdem Sie durchsuchen, suchen Sie unter **Wählen Sie Notfall Adresse** auf die richtige für Sie auswählen.
6. Klicken Sie auf **Speichern** , und die Benutzer sollte wie folgt aussehen:

    ![Cap-Benutzer-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Benutzer werden nur angezeigt, wenn sie eine **Telefonsystem** Lizenz angewendet haben. Wenn Sie nur dies, erst dann manchmal etwas für den Benutzer in der Liste angezeigt wird.

Mehr Inhalte finden Sie unter [Getting Rufnummern für Ihre Benutzer](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Wenn Sie wissen möchten, können Sie auch Ihre Telefonnummer nutzen, indem Sie mit einem anderen Netzbetreiber und "*Port*" oder zu Office 365 übertragen. Angezeigt wird, [Übertragen von Telefonnummern zu Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

## <a name="step-4---setting-up-your-phone"></a>Schritt 4: Einrichten des Telefons

**Festlegen des Modus auf einem Telefon**

Das Telefon oder Telefone, die Sie benötigen den Telefone in öffentlichen Bereichen-Modus aktiviert. Möglicherweise möchten Sie überprüfen, um sicherzustellen, dass dies der Fall ist. 

**Es folgt ein Beispiel dafür, wie Sie ein Telefon Polycom VVX einrichten**

- Aktivieren Sie Telefone in öffentlichen Bereichen Modus für das Polycom VVX, durch die folgenden Schritte ausführen:
    1. In Ihrem Browser eine Verbindung mit der Webschnittstelle, damit Sie CAP-Modus aktivieren können.
    2. Wechseln Sie zur **Einstellung** und die Option **Skype für Business-Einstellung** , und wählen Sie **Telefone in öffentlichen Bereichen**.
    3. Klicken Sie auf **Ja,** um die Einstellungen zu speichern.

- Nun, dass der CAP-Modus aktiviert ist, richten Sie das Telefon mit Display des Telefons. Die Anzeige sollte anzeigen **CaAP ist aktiviert**. Klicken Sie dann folgendermaßen Sie vor:

    1. Klicken Sie auf **Einstellungen**.
    2. Klicken Sie auf **Erweitert**.
    3. Geben Sie das Kennwort ein.
    4. Wählen Sie unter **Einstellungen für die** **Common Area Phone Settings**.
    5. Aktivieren Sie **CAP** und **CAP-Admin-Modus**.
    6. Klicken Sie auf **Konfiguration speichern**.

- OK, kann nun Ihr Telefon, damit Sie auf der Startseite anmelden können.

    1. Melden Sie sich, indem Sie **Einstellungen**auswählen > **Features** > **Skype für Business.**
    2. Wählen Sie **Anmeldeinformationen des Benutzers**aus, und wählen Sie **Web - Anmeldung (CAP)** um einen Code zu generieren.
    3. Besuchen Sie die [Bereitstellung Portal](http://aka.ms/skypecap), und melden Sie sich als **Administrator**.
    4. Geben Sie den Anzeigenamen (beispielsweise Main Empfang).

       > [!Note]
       > Wenn **Suchen für Telefone in öffentlichen Bereichen nur** aktiviert ist, deaktivieren Sie das Kontrollkästchen, und suchen Sie erneut. "

    5. Klicken Sie im Codefenster paarungs Geben Sie den Code auf dem Telefon angezeigt, und klicken Sie auf **Bereitstellung**.

        Nach diesem letzten Schritt sollte das Telefon automatisch anmelden.

### <a name="related-topics"></a>See Also

- Weitere Informationen zu verfügbaren Telefonen unter [Bereitstellen von Skype für Business Online-Telefone](deploying-skype-for-business-online-phones.md).
- [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online.md)


