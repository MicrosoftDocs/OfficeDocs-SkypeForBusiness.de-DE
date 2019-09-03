---
title: Einrichten des Telefonsystems in Ihrer Organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Erfahren Sie, wie Sie das Telefonsystem (Cloud PBX) für Ihre Organisation einrichten können. '
ms.openlocfilehash: e7d833e6170a442f9e97ff867e979bfd52700969
ms.sourcegitcommit: 26b3d786da07fde20878b0f4a1656070fe01d918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "36645300"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Einrichten des Telefonsystems in Ihrer Organisation

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Schritt 1: Stellen Sie sicher, dass Telefonsystem in Ihrem Land oder Ihrer Region verfügbar ist

1.  Gehen Sie zunächst auf [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus der Liste oben auf der Seite. 
2.  Überprüfen Sie die Liste der Features und Details unter **Telefonsystem**. 
3.  Wenn Telefonsystem verfügbar ist, fahren Sie fort mit Schritt 2. 

**Weitere Informationen zur regionalen Verfügbarkeit von Telefonsystem und Audiokonferenzen finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Schritt 2: Kaufen und Zuweisen von Lizenzen für Telefonsystem und Anrufplan

Um eine Lizenz für das Telefonsystem und den Anrufplan für einen einzelnen Benutzer zuzuweisen, folgen Sie den gleichen Schritten wie bei der Zuweisung einer Office 365-Lizenz. Mehr dazu finden Sie unter [Microsoft Teams Lizenzen zuweisen](assign-teams-licenses.md). Wenn Sie mehrere Benutzer gleichzeitig zuweisen möchten, lesen Sie hierzu den Abschnitt [Microsoft Teams-Lizenzen zuweisen](assign-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Schritt 3: Abrufen von Telefonnummern für Ihre Benutzer

Bevor Sie in Ihrer Organisation Benutzer für das Tätigen und Empfangen von Anrufen einrichten können, müssen Sie Telefonnummern für diese anfordern.

Ihnen stehen drei Methoden zum Abrufen von Telefonnummern für Ihre Benutzer zur Verfügung:
- Neue Telefonnummern mittels Skype for Business Admin Centers anfordern.
- Beziehen Sie neue Nummern, die im Skype for Business Admin Center nicht verfügbar sind.
- Portieren oder übertragen Sie Ihre vorhandenen Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Office 365.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>Neue Telefonnummern für Benutzer anfordern 
 
![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.

2. Navigieren Sie zum **Microsoft 365 Admin Center** > **Skype for Business**.
    
3. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**, klicken Sie auf **Neue Nummer hinzufügen**![Die Schaltfläche „Hinzufügen“, die als Pluszeichen angezeigt wird](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png) und dann auf **Neue Nutzernummern**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Beziehen von neuen Nummern, die im Skype for Business Admin Center nicht verfügbar sind
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem Dienstanbieter oder Netzbetreiber
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- Wenn Sie mehr als 999 Telefonnummern portieren müssen, finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) weitere Informationen zum Übermitteln einer Serviceanfrage für einen Portierungsauftrag oder einen Auftrag für die Portierung dieser Telefonnummern zu Office 365. 

**Ausführliche Informationen zum Abrufen neuer Telefonnummern oder zum Übertragen bestehender Nummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Schritt 4: Service-Telefonnummern beziehen (Audiokonferenzen, Anruf-Warteschlangen, automatische Vermittlung)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Neue Leistungsnummern beziehen

![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**


1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Navigieren Sie zum **Microsoft 365 Admin Center** > **Skype for Business**.

3. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern** > **Neue Nummer hinzufügen**, und klicken Sie auf **Neue Leistungsnummern**.

    > [!IMPORTANT]
    > Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Beziehen von neuen Nummern, die im Skype for Business Admin Center nicht verfügbar sind
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Portieren oder übertragen von bestehenden Servicenummern

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Schritt 5: Wenn Sie Anrufpläne einrichten möchten

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Fügen Sie Notfalladressen und -standorte für Ihre Organisation hinzu

1. Wählen Sie auf der Seite **VoIP** die Optionen **Notfallstandorte** > **Neue Adresse hinzufügen** aus.

2. Geben Sie im Bereich **Neue Adresse** einen Namen für Ihre Adresse ein, und füllen Sie dann die verbleibenden Felder aus.
    
     ![Screenshot des Bereichs „Neue Adresse“](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Wenn der Straßenname für englische Kunden eine Zahl ist, stellen Sie sicher, dass Sie „st" oder „th" am Ende anfügen (siehe Abbildung oben).

3. Wählen Sie **Überprüfen** aus.

    Bei Bedarf werden Sie aufgefordert, Korrekturen an der Adresse vorzunehmen.

    > [!CAUTION]
    > Durch die Validierung einer Postanschrift oder Adresse wird sichergestellt, dass die Adresse legitim und richtig formatiert ist. Es ist möglich, dass eine teilweise korrekte Notfalladresse, wie z. B. ein falsch geschriebener Name einer Stadt, bei der Validierung anerkannt wird. Trotz des Schreibfehlers besteht die Adresse die Validierung, da die Kombination aus falsch geschriebenem Ortsnamen und anderen richtigen Adressangaben ausreicht, um den Anruf an die zuständige Rettungsleitstelle weiterzuleiten.

    > [!TIP]
    > Wenn die Adresse für Rettungsaktionen korrigiert werden muss, werden Sie über ein grünes Banner informiert, dass die Adresse aktualisiert wurde.

4. Klicken Sie nach der Überprüfung der Adresse auf **Speichern**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Zuweisen von Telefonnummern und Notfalladressen zu Benutzern

> [!TIP]
> Wenn Sie vor diesem Schritt weitere Personen zu Ihrem Unternehmen hinzufügen, kann es **mehrere Stunden** dauern, bis diese auf der Seite **VoIP-Benutzer** angezeigt werden. Es ist eine Latenz vorhanden.

1. Wählen Sie auf der Seite **VoIP-Benutzer** die Benutzer aus, denen Sie eine Telefonnummer und eine Notfalladresse zuweisen möchten.

2. Klicken Sie im Aktionsbereich auf **Nummer zuweisen**.

3. Wählen Sie auf der Seite **Nummer zuweisen** in der Liste **Zuzuweisende Nummer auswählen** die Telefonnummer für den Benutzer aus.

4. Um eine Notfalladresse auszuwählen, geben Sie den Namen der Stadt in das Feld ein, und wählen Sie **Suchen** aus.

    > [!IMPORTANT]
    > Wenn Sie sich außerhalb der Vereinigten Staaten befinden, verfügen Ihre Nummern bereits über eine Notfalladresse. Sie können diese jedoch ändern. Weitere Informationen finden Sie unter [Zuweisen oder Ändern einer Notfalladresse für einen Benutzer](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Nachdem Sie die Telefonnummer und die Notfalladresse zugewiesen haben, wählen Sie **Speichern**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informieren Sie Ihre Benutzer über die neuen Telefonnummern


Wir empfehlen das Senden von E-Mail-Nachrichten oder die in Ihrem Unternehmen bevorzugte Kommunikationsmethode, um die Benutzer über ihre neuen Telefonnummern in Kenntnis zu setzen.

Im Folgenden erfahren Sie, wie die eigene Telefonnummer in der **Skype for Business**-App angezeigt werden kann:

1. Melden Sie sich bei Skype for Business auf Ihrem Desktop an.
    
2. Wählen Sie **Einstellungen** > **Tools** > **Optionen** aus. 
    
     ![Screenshot der Optionen im Menü "Tools"](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Wählen Sie dann **Telefone**. 
    
    ![Screenshot der Skype for Business-Telefonoptionen](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![Screenshot der verfügbaren Optionen nach dem Klicken auf „Anrufe“](media/teams-phone-number.png)

**Ausführlichere Informationen zu allen über die Schritte zum Einrichten eines Anfrufplans finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Schritt 6: Wenn Sie Audiokonferenzen einrichten möchten

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).
    
1. Wenn Sie Add-On-Lizenzen für **Audiokonferenzen** und Lizenzen für Guthaben für Kommunikationen erworben haben, weisen Sie diese ebenfalls zu. Anweisungen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Microsoft Teams-Benutzer können keinen Drittanbieter für Audiokonferenzen verwenden.

    - **Microsoft als Anbieter von Audiokonferenzen**: Wenn Sie die einfachste Lösung für Audiokonferenzen verwenden möchten, wählen Sie Microsoft als Anbieter von Audiokonferenzen.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [Einladungen zu Besprechungen in Skype for Business anpassen](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). Die Einwahlnummern, die für den Benutzer festgelegt sind, werden automatisch zu den Einladungen hinzugefügt, die an die Teilnehmer gesendet werden. Sie können jedoch Ihre eigene Hilfe und rechtliche Links, eine Textnachricht und eine kleine Firmengrafik hinzufügen.
    
   2. Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) oder in [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md). Diese Telefonnummer wird in der Besprechung angezeigt, die der Nutzer plant.
    
   3. Festlegen der Sprachen für Audiokonferenzen in [Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing)oder in[Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md), die die automatische Telefonzentrale zur Begrüßung eines Anrufers verwendet, wenn er sich in eine Audiokonferenz-Rufnummer einwählt. Dieser Schritt gilt nur, wenn Sie Microsoft als Ihren Audioanbieter verwenden.
    
   4. Festlegen der Länge der PIN für Audiokonferenzbesprechungen in [Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Weitere Informationen zu Audiokonferenzen finden Sie unter [Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md).**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Schritt 7: Wenn Sie eine Cloudanrufwarteschleifen einrichten möchten

Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

Um eine neue Warteschleife zu erstellen, klicken Sie unter **Skype for Business Admin Center** auf **Anrufrouting** > **Warteschleifen**, klicken Sie auf **Neu hinzufügen**, und folgen Sie dann den Anweisungen in **Schritt 3** von [Eine Cloudanrufwarteschleife erstellen](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Weitere Informationen zu Anrufwarteschleifen finden Sie unter [Eine Cloudanrufwarteschleife erstellen](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Schritt 8: Wenn Sie eine automatische Cloudtelefonzentrale einrichten möchten

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Um eine neue Telefonzentrale zu erstellen, klicken Sie im Admin Center von Skype for Business auf **Rufweiterleitung** > **Auto-Telefonzentrale**. Dort klicken Sie auf **Neu hinzufügen**. Anschließend folgen Sie den Anweisungen für jede Seite in **Schritt 2** von [Einrichten einer Cloudtelefonzentrale](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).


**Weitere Informationen zu Cloudtelefonzentralen finden Sie unter [Einrichten einer Cloudtelefonzentrale](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Schritt 9: Servicenummern zuweisen (Audiokonferenzen, Anruf-Warteschleifen, automatische Vermittlung)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- Für Audiokonferenzen: Sie können einer Konferenzbrücke eine dedizierte Nummer zuweisen, indem Sie zu**Microsoft 365 Admin Center** > **Admin Center** > **Skype for Business** > **Audiokonferenzen**gehen. Dort klicken Sie auf die Konferenzbrücke oder sehen Sie[Ändern der gebührenpflichtigen oder gebührenfreien Nummern auf Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Für Audiokonferenzen: Sie können eine Telefonzentrale eine dedizierte Nummer zuweisen, indem Sie zu**Microsoft 365 Admin Center** > **Admin Center** > **Skype for Business** > **Anrufrouting** > **Telefonzentralen**gehen. Dort klicken Sie auf die Telefonzentrale. Auf der Seite **Allgemein**wird Ihre bereits vorhandene Servicenummer in der Dropdown-Liste **Telefonnummer**aufgeführt. Weitere Informationen finden Sie unter[Einrichten einer Cloudtelefonzentrale](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).
- Für Warteschleifen: Sie können eine Telefonzentrale eine dedizierte Nummer zuweisen, indem Sie zu**Microsoft 365 Admin Center** > **Admin Center** > **Skype for Business** > **Anrufrouting**  > **Warteschleifen** gehen. Dort klicken Sie auf die Warteschleife. Auf der Seite **Allgemein**wird Ihre bereits vorhandene Servicenummer in der Dropdown-Liste **Telefonnummer** aufgeführt. Weitere Informationen finden Sie unter[Einrichten einer Cloudwarteschleife](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue).

**Ausführliche Informationen zum Bezug neuer Servicerufnummern und zur Portierung bestehender Servicerufnummern finden Sie unter [Servicerufnummern beziehen](/microsoftteams/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Schritt 10: Einrichten von Guthaben für Kommunikationen für Ihre Organisation

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Weitere Informationen zu den Kosten finden Sie [unter den Tarifen hier](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Guthaben für Kommunikationen einrichten

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.

2. Navigieren Sie in der linken Navigationsleiste des Admin Center zu **Abrechnung** > **Abonnements** > **Add-Ons** > **Add-Ons kaufen**. Wählen Sie dann **Guthaben für Kommunikationen** > **Jetzt kaufen** aus.

3. Geben Sie auf der Seite **Guthaben für Kommunikationen**-Abonnement Ihre Informationen ein, und klicken Sie dann auf **Weiter**.

4. Geben Sie jetzt Ihre Zahlungsinformationen ein, und wählen Sie **Bestellung aufgeben**aus.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**Ausführlichere Informationen zum Einrichten von Kommunikations-Guthaben finden Sie unter [Einrichten von Kommunikations-Guthaben für Ihre Organisation](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Zuweisen einer Lizenz für Guthaben für Kommunikationen für Benutzer

1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Navigieren Sie in der linken Navigationsleiste des Microsoft 365 Admin Center zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste aus.

3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.

4. Aktivieren Sie auf der Seite **Produktlizenzen** das Kontrollkästchen **Guthaben für Kommunikationen** auf **Ein**, um diese Lizenz zuzuweisen, und klicken Sie dann auf **Speichern**.

    > [!NOTE]
    > Auch wenn Sie Benutzer haben, denen eine **Enterprise E5**-Lizenz zugewiesen ist, wird dies weiterhin empfohlen.

**Weitere Informationen zum Zuweisen von Kommunikations-Guthaben-Lizenzen finden Sie unter [Kommunikations-Guthaben für Ihre Organisation einrichten](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Verwandte Themen
[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
