---
title: Einrichten von Guthaben für Kommunikationen für Ihre Organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: ce0503eea868e7fd4c2cef3afeb5394ad034b1c2
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-communications-credits-for-your-organization"></a>Einrichten von Guthaben für Kommunikationen für Ihre Organisation

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Wenn Sie wissen möchten, welche Kosten anfallen, [finden Sie hier die Tarife](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>Schritt 1: Zuweisen einer Audiokonferenz- und Anrufplanlizenz für Ihre Benutzer

Bei der Registrierung erhalten Sie je nach Land/Region eine bestimmte Anzahl Minuten. You can see the number of minutes you will get search for the country or region [here].(../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)). Anrufe werden getrennt, sobald Sie diese Minuten aufgebraucht haben. Um dies zu verhindern, müssen Sie Guthaben für Kommunikationen einrichten.
  
Dazu **müssen Sie Ihren Benutzern eine Lizenz für Audiokonferenzen oder für Telefonsysteme zuweisen**.
  
- Weisen Sie Ihren Benutzern eine Lizenz für **Audiokonferenzen** zu. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    Nachdem Sie diese Lizenz zugewiesen haben, müssen Sie Audiokonferenzen einrichten. For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md).
    
- Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.
  
    Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
Weitere Informationen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Schritt 2: Einrichten von Guthaben für Kommunikationen für Ihre Organisation

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie in der linken Navigationsleiste des Office 365 Admin Center zu **Abrechnung** > **Abonnements** > **Add-Ons** > **Add-Ons kaufen**. Wählen Sie dann **Guthaben für Kommunikationen** > **Jetzt kaufen** aus.
    
3. On the **Communications Credits** subscription page, fill in your information, and then click **Next**:
    
  - **Guthaben hinzufügen**: Geben Sie den Betrag ein, den Sie Ihrem Konto hinzufügen möchten. Wenn Sie das automatische Aufladen nicht aktivieren, werden nach dem Aufbrauchen des Guthabens die Anruffunktionen, die über das Guthaben für Kommunikationen aktiviert werden, unterbrochen (z. B. eingehende gebührenfreie Dienste). Um zu vermeiden, dass Sie den Guthabensaldo für Kommunikationen jedes Mal auffüllen müssen, wenn er 0 (null) erreicht, empfehlen wir, die automatische Aufladefunktion zu aktivieren.
    
  - **Automatisch aufladen**: Wenn Sie das automatische Aufladen aktivieren, erhält Ihr Konto automatisch neues Guthaben, wenn der Saldo unter das von Ihnen festgesetzte Limit sinkt.
    
    Sie sollten die Option **Automatisches Aufladen** nutzen, um Dienstunterbrechungen zu vermeiden, falls der Guthabensaldo für Kommunikationen 0 (null) erreicht. Sie erhalten eine E-Mail, wenn Transaktionen für eine Aufladung erfolgreich waren oder fehlgeschlagen sind (z. B. im Fall einer abgelaufenen Kreditkarte) und wenn der Guthabensaldo für Kommunikationen 0 (null) erreicht.
    
  - **Aufladebetrag**: Geben Sie in das Feld **Aufladen mit** den Betrag ein, der Ihrem Konto hinzugefügt werden soll, nachdem es den Kontostand, der das automatische Auffüllen auslöst, erreicht hat.
    
  - **Kontostand, der das automatische Auffüllen auslöst**: Geben Sie in das Feld **bei Guthaben unter** den Betrag ein, bei dem das automatische Aufladen „ *ausgelöst*  " wird. Nachdem Ihr Saldo diesen Betrag unterschritten hat, wird der Aufladebetrag dem Konto automatisch hinzugefügt.

      > [!NOTE]
    > Das Guthaben wird nur zu den von Microsoft veröffentlichten Tarifen auf Guthaben für Kommunikationen angewendet, wenn die Dienste genutzt werden. Wenn ein Guthaben nicht innerhalb von 12 Monaten ab dem Kaufdatum aufgebraucht wird, verfällt es. 
    
4. Geben Sie Ihre Zahlungsinformationen ein, und klicken Sie auf **Bestellung aufgeben**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.
  
Wenn Sie Guthaben für Kommunikationen einrichten, müssen Sie die Anrufnutzung für Ihre Organisation prüfen, um die Beträge zu bestimmen, die Sie aufladen müssen. Informationen zur Anrufnutzung finden Sie im Bericht **PSTN-Nutzungsdetails**. Die Anrufdatensätze aus diesem Bericht können Sie nach Excel exportieren, wenn Sie die Daten speichern oder benutzerdefinierte Berichte erstellen möchten. To see usage, see [Skype for Business PSTN usage report](../skype-for-business-online-reporting/pstn-usage-report.md)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Schritt 3: Zuweisen einer Lizenz für Guthaben für Kommunikationen für Benutzer

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie in der linken Navigationsleiste des Office 365 Admin Center zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste aus.
    
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.
    
4. On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.
    
    > [!NOTE]
    > Selbst wenn Sie über Benutzer verfügen, denen eine **Enterprise E5** -Lizenz zugewiesen ist, wird diese Vorgehensweise dennoch empfohlen.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Sie suchen Informationen zu Plänen und Preisen?

Die Pläne und Preise finden Sie unter den folgenden Links:
  
- [Anrufpläne](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Audio Conferencing Plans](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Telefonsystempläne](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Sie können sich die Informationen auch ansehen, indem Sie sich [beim Office 365 Admin Center anmelden](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) und zu **Abrechnung** > **Abonnements** > **Abonnements hinzufügen** navigieren.
  
Eine Tabelle mit den Lizenzen für die jeweilige Funktion finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>See Also

- [Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Einrichten von Voicemail für Telefonsysteme - Administratorhilfe](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)
    
- [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)
    
- [Hinzufügen von Guthaben und Verwalten von Guthaben für Kommunikationen](add-funds-and-manage-communications-credits.md)
    
- [Configure the Cloud Connector](https://technet.microsoft.com/en-us/library/mt605228.aspx) and [Download the Cloud Connector](https://aka.ms/CloudConnectorInstaller)

  
 