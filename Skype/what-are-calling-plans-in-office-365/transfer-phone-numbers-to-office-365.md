---
title: "Übertragen von Telefonnummern zu Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PortingNumbersOverview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e

description: "Learn what you need to know and do before porting phone numbers to Skype for Business, and how to create a port order to transfer them."
---

# Übertragen von Telefonnummern zu Office 365

Ihre Telefonnummern lassen sich ganz leicht von Ihrem derzeitigen Dienstanbieter an Skype for Business übertragen. Nachdem Sie Ihre Telefonnummern an Skype for Business portiert haben, wird Microsoft zu Ihrem Dienstanbieter und stellt Ihnen diese Telefonnummern in Rechnung. 
  
Bevor Sie mit dem Übertragen von Telefonnummern beginnen, sollten Sie die Informationen unter [Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md) lesen.Wenn Sie über Servicenummern für Einwahlkonferenzbrücken oder automatische Telefonzentralen bzw. über andere Servicenummern, gebührenfreie Telefonnummern oder mehr als 999 Telefonnummern von Benutzern (Teilnehmern) verfügen, die Sie an Skype for Business übertragen müssen, laden Sie unter [Manuelles Übermitteln einer benutzerdefinierten Serviceanfrage](manually-submit-a-custom-service-request.md) die entsprechenden Formulare herunter, und senden Sie sie an uns.
> [!NOTE]
> Wir bearbeiten Portierungsaufträge für Telefonnummern nur an Werktagen (USA), nicht an gesetzlichen Feiertagen oder an Wochenenden. 
  
## So erstellen Sie einen Portierungsauftrag und übertragen Ihre Telefonnummern an Skype for Business
<a name="bk_LNPcountries_1"> </a>

> [!NOTE]
> Wenn Sie über Servicenummern für Einwahlkonferenzbrücken oder automatische Telefonzentralen bzw. über andere Servicenummern, gebührenfreie Telefonnummern oder mehr als 999 Telefonnummern von Benutzern (Teilnehmern) verfügen, die Sie an Skype for Business übertragen müssen, laden Sie unter [Manuelles Übermitteln einer benutzerdefinierten Serviceanfrage](manually-submit-a-custom-service-request.md) die entsprechenden Formulare herunter, und senden Sie sie an uns.
  
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
    
## Wie geht es weiter?
<a name="bk_LNPcountries_1"> </a>

Nachdem der Portierungsauftrag übermittelt und erhalten wurde, wird eine E-Mail zur Verifizierung Ihres Portierungsauftrags an Sie gesendet.
  
Ihr Portierungsauftrag wird täglich überprüft und aktualisiert, und Sie werden per E-Mail über den Fortschritt und Status benachrichtigt. Falls Ihre Anforderung abgelehnt wird, werden Sie aufgefordert, ein Supportticket zu öffnen, in dem Sie die **Portierungsauftrags-ID** angeben müssen. Die Portierungsauftrags-ID finden Sie im Skype for Business Admin Center unter **VoIP** > **Portierungsaufträge** > Spalte **Auftrags-ID**.
  
## Was ist, wenn Probleme auftreten?
<a name="bk_LNPcountries_1"> </a>

 **Die Dienstadresse entspricht nicht der Rechnungsadresse. Warum wird der Auftrag abgelehnt, obwohl die von mir im Auftrag übermittelten Adressinformationen mit meiner Rechnungskopie übereinstimmen?** Die meisten Netzbetreiber identifizieren die Portierungsinformationen anhand der Dienstadresse, nicht anhand der Rechnungsadresse. Da eine Rechnungskopie ein Abrechnungsdokument ist, enthält sie möglicherweise nicht dieselben Informationen wie die Dienstadresse für die zu portierenden Telefonnummern.
  
 **Was soll ich tun, wenn die Bearbeitung meines Auftrags zu lange dauert?** Wir möchten, dass die Nummernportierung sehr einfach und schnell abläuft. Wenn der Auftrag Ihrer Ansicht nach zu viel Zeit in Anspruch nimmt und der Status im Skype for Business Admin Center immer noch nicht als abgeschlossen angezeigt wird, öffnen Sie ein Supportticket, und geben Sie dabei die Portierungsauftrags-ID an.
  
## 
<a name="bk_LNPcountries_1"> </a>

||
|:-----|
|![Symbol für LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Neu bei Office 365?**         Entdecken Sie kostenlose Videokurse für **Office 365-Administratoren und IT-Experten**, bereitgestellt von LinkedIn Learning. |
   
## Verwandte Themen
<a name="bk_LNPcountries_1"> </a>

[Einrichten von Anrufplänen](set-up-calling-plans.md)
  
[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)
  

