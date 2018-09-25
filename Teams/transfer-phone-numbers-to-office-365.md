---
title: Übertragen von Telefonnummern zu Office 365
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PortingNumbersOverview
ms.custom:
- Calling Plans
- LIL_Placement
description: Learn what you need to know and do before porting phone numbers to Skype for Business, and how to create a port order to transfer them.
ms.openlocfilehash: 69ed5566d516f89b5b3f2c96ab37e43690693708
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017897"
---
# <a name="transfer-phone-numbers-to-office-365"></a>Übertragen von Telefonnummern zu Office 365

Ihre Telefonnummern lassen sich ganz leicht von Ihrem derzeitigen Dienstanbieter an Skype for Business übertragen. Nachdem Sie Ihre Telefonnummern an Skype for Business portiert haben, wird Microsoft zu Ihrem Dienstanbieter und stellt Ihnen diese Telefonnummern in Rechnung.
  
Bevor Sie mit dem Übertragen von Telefonnummern beginnen, sollten Sie die Informationen unter [Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md) lesen.Wenn Sie über Servicenummern für Einwahlkonferenzbrücken oder automatische Telefonzentralen bzw. Wenn Sie Service Nummern für einwahlkonferenzen Brücken, automatischen Telefonzentralen oder andere Zahlen Service verfügen, gebührenfreie Telefonnummer Zahlen oder mehr als 999 Benutzer (Abonnent) Telefonnummern, die Sie benötigen zum Weiterleiten an Skype für Unternehmen finden Sie unter [Verwalten von Rufnummern für haben Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) die richtige Formulare herunterladen und diese für uns senden.

  > [!NOTE]
  > Wir bearbeiten Portierungsaufträge für Telefonnummern nur an Werktagen (USA), nicht an gesetzlichen Feiertagen oder an Wochenenden. 
  
## <a name="how-to-create-a-port-order-and-transfer-your-phone-numbers-to-skype-for-business"></a>So erstellen Sie einen Portierungsauftrag und übertragen Ihre Telefonnummern an Skype for Business
<a name="bk_LNPcountries_1"> </a>

  > [!NOTE]
  > Wenn Sie Service Nummern für einwahlkonferenzen Brücken, automatischen Telefonzentralen oder andere Zahlen Service verfügen, gebührenfreie Telefonnummer Zahlen oder mehr als 999 Benutzer (Abonnent) Telefonnummern, die Sie benötigen zum Weiterleiten an Skype für Unternehmen finden Sie unter [Verwalten von Rufnummern für haben Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) auswählen das richtige Land/Region und Laden Sie die richtige Formulare aus, und senden sie uns.
 
![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

 
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Portierungsanträge** und klicken Sie auf **Hinzufügen**.
    
4. Lesen Sie die Informationen auf der Seite **Antrag zur Portierung der neuen lokalen Rufnummern** und klicken Sie anschließend auf **Erste Schritte**.
    
5. Geben Sie auf der Seite **Kontoinformationen** die folgenden Informationen ein und klicken Sie anschließend auf **Weiter**:
    
  - **Kontonummer** Kontonummer für den Dienstanbieter oder Netzbetreiber.
    
  - Die **Abrechnungstelefonnummer** muss im E.164-Format vorliegen (mit +-Zeichen vor der Nummer). Verwenden Sie beispielsweise für eine Telefonnummer aus Nordamerika das Format +1XXXYYYZZZZ.
    
  - **PIN zum Zulassen blockierter Nummern** PIN - falls vom aktuellen Dienstanbieter oder Netzbetreiber gefordert.
    
  - **Firmenname** Dies ist der Name Ihres Unternehmens oder Ihrer Organisation.
    
    > [!NOTE]
    > Im Feld **Firmenname** sind höchstens 25 Zeichen inklusive Leerzeichen zugelassen. Wenn der Firmenname länger als 25 Zeichen ist, werden die ersten 25 Zeichen des Namens eingereicht und der Portierungsantrag wird ausgeführt.
  
  - **Berechtigte Person** Name der berechtigten Person.
    
    > [!NOTE]
    > Im Feld **Berechtigte Person** sind höchstens 15 Zeichen inklusive Leerzeichen zugelassen. Wenn der Name der berechtigten Person länger als 15 Zeichen ist, werden die ersten 15 Zeichen des Namens eingereicht und der Portierungsantrag wird ausgeführt.
  
  - **Serviceadresse** Serviceadresse für das Konto. Diese Adresse wird auf der Rechnung Ihres Dienstanbieters oder Netzbetreibers aufgeführt.
    
  - **Ort**, **Bundesland**, **PLZ** der Serviceadresse.
    
6. Geben Sie auf der Seite **Telefonnummern** die Telefonnummern, die Sie übertragen möchten, im E.164-Format ein. Verwenden Sie beispielsweise für eine Telefonnummer aus Nordamerika das Format +1XXXYYYZZZZ. Trennen Sie mehrere Telefonnummern mit Kommas.
    
    > [!NOTE]
    > Wenn Sie eine vollständige Portierung durchführen, müssen Sie die Abrechnungstelefonnummer (Billing Telephone Number, BTN) in die Liste eintragen. Wenn Sie eine teilweise Portierung durchführen, tragen Sie die Abrechnungstelefonnummer (Billing Telephone Number, BTN) nicht in die Liste ein. 
  
    Bei einer vollständigen Portierung wählen Sie **Ich übertrage alle Telefonnummern meines aktuellen Netzbetreibers** aus. Bei einer teilweisen Portierung wählen Sie **Ich übertrage nur einige meiner Telefonnummern** aus. Nach Auswahl der richtigen Option klicken Sie auf **Portierbarkeit der Telefonnummern überprüfen.**
    
7. Klicken Sie auf **Fortfahren**.
    
8. Wählen Sie auf der Seite **Übertragungsdatum** in der Dropdownliste **Tag** das Datum und in der Dropdownliste **Startzeit** die Uhrzeit (EST) aus. Klicken Sie anschließend auf **Weiter**.
    
9. Überprüfen Sie auf der Seite **Genehmigungsschreiben** die folgenden Felder. Geben Sie dann unter dem Feld **Unterschrift** den Namen der Person ein, die berechtigt ist, Änderungen am Konto vorzunehmen. Dabei handelt es sich um den gleichen Namen, der auf der Seite **Kontoinformationen** unter **Genehmigende Person** verwendet wird. Klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Übermitteln** unter **Andere Personen benachrichtigen** die E-Mail-Adressen der gewünschten Personen ein, und klicken Sie auf **Portierungsauftrag übermitteln**. Der Portierungsauftrag wird jetzt auf der Seite **Portierungsaufträge** aufgeführt. Den Status des Auftrags können Sie der Spalte **Status** entnehmen. Sie können Details des Portierungsauftrags wie zum Beispiel **Auftrags-ID**, **Übermittelt**, **Übertragungsdatum** und **Status** anzeigen. Im Aktionsbereich werden weitere Details des Portierungsauftrags angezeigt, darunter auch der Name des Netzbetreibers.
    
## <a name="what-happens-next"></a>Wie geht es weiter?
<a name="bk_LNPcountries_1"> </a>

Nachdem der Portierungsauftrag übermittelt und erhalten wurde, wird eine E-Mail zur Verifizierung Ihres Portierungsauftrags an Sie gesendet. 
  
Your port order request will be checked and updated daily and you will be notified of its progress and status in email. If your request is rejected, you will be asked to open a support ticket and in that support ticket we ask that you provide **Port Order ID**. The port order ID can be found in the Skype for Business admin center under **Voice** > **Port orders** > **Order ID** column.
  
## <a name="what-if-i-have-problems"></a>Was ist, wenn Probleme auftreten?
<a name="bk_LNPcountries_1"> </a>

 **Die Dienstadresse entspricht nicht der Rechnungsadresse. Warum wird der Auftrag abgelehnt, obwohl die von mir im Auftrag übermittelten Adressinformationen mit meiner Rechnungskopie übereinstimmen?** Die meisten Netzbetreiber identifizieren die Portierungsinformationen anhand der Dienstadresse, nicht anhand der Rechnungsadresse. Da eine Rechnungskopie ein Abrechnungsdokument ist, enthält sie möglicherweise nicht dieselben Informationen wie die Dienstadresse für die zu portierenden Telefonnummern.
  
 **Was soll ich tun, wenn die Bearbeitung meines Auftrags zu lange dauert?** Wir möchten, dass die Nummernportierung sehr einfach und schnell abläuft. Wenn der Auftrag Ihrer Ansicht nach zu viel Zeit in Anspruch nimmt und der Status im Skype for Business Admin Center immer noch nicht als abgeschlossen angezeigt wird, öffnen Sie ein Supportticket, und geben Sie dabei die Portierungsauftrags-ID an.

   
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 